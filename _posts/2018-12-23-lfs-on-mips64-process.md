---
layout: post
title: LFS on MIPS64 全过程笔录
lang: cmn-Hans
category:
  - blog
  - cn
---

**Update 20191222:** 咕咕咕！关于 MIPS 我 2019 年什么都没有做，而且短时间内可能也不会做。以下关于发行版配置的内容已经过时，现在我的想法又不同了，所以就当个 LFS 踩坑记录参考吧。先做些备注以免误导大众。

---

> 明年年初，社区合作的 MIPS Port 即将（第二次）正式开机，我将继续扮演架构维护者，我会用维护者技术手段努力创造一个能用的形象，文体两开花，弘扬 MIPS 文化，希望大家多多关注

另可参见我两年前记录的 [LFS on MIPS64 笔记]({% post_url 2016-12-12-lfs-on-mips64-notes %})。

## 编译平台

> Junde Yhi, [22.12.18 22:50]
> [In reply to Neo_Chen (neo_chen@NeoVAX)]
> Host 是由江苏龙芯梦兰公司提供的 Fedora 28 (Loongson ver.) 一套
>
> Junde Yhi, [22.12.18 22:51]
> 在此我们谨对 sunhaiyong 先生表示我们一贯的崇高敬意
>
> Junde Yhi, [22.12.18 22:51]
> 没有 sunhaiyong 就没有 aosc [os mips port]

## 目标平台

**20191222 注：没有 `gnuabin64` 这种写法，完全就是胡搞。N64 就是 `gnuabi64`。**

1. AOSC OS MIPS64EL "Care"[^1] Port
  - `mips64el-aosc-linux-gnuabin64`
  - (Legacy) **MIPS-III** ISA
2. AOSC OS MIPS64EL "Modern" Port
  - `mipsisa64r2el-aosc-linux-gnuabin64`[^2]
  - **MIPS64 revision 2** ISA

LFS 过程基本遵循标准 LFS 教程，因此我只按 LFS 步骤记下要注意或者要添加的事项。

## 4.4. Setting Up the Environment

**20191222 注：`$LFS_BLD` 真的就是为了好看（一些诸如 Bash 之类的软件会记录 Triplet），所以是没有必要的。**

- 注意调整 `$LFS_TGT` 到目标平台 Tuple
- 可以考虑添加一些常用变量：
  - `$LFS_BLD` 当前平台 Tuple，因为 `config.guess` 给的 `*-unknown-*` 还是丑了点
  - `$MAKEFLAGS` 放 `-j$(( $(nproc) + 1 ))`（执行 `nproc` 得到当前 CPU 数，加一）让 `make` 多线程编译，而不需要每次都打 `-jN`

## 5.4. Binutils-2.31.1 - Pass 1

- 注意添加 `--build=$LFS_BLD`（实际上可能没有意义）
- 按照 AOSC OS 文件系统结构定义，LFS 给出的在 x86_64 上的 `lib64 -> lib` 链接也需要做好

## 5.5. GCC-8.2.0 - Pass 1

- 在修改 GCC 默认链接器位置的时候（_The following command will change the location of GCC's default dynamic linker to use the one installed in /tools_），注意切换 `i386` 到 `mips`
  - 并且 `mips` 下没有 `linux64.h`，所以可以免去这一替换
- LFS 对 `x86_64` 修改了默认的 64 位链接库目录到 `lib`（_Finally, on x86\_64 hosts, set the default directory name for 64-bit libraries to "lib"_）；对 MIPS，我尚不清楚位于 `gcc/config/mips/t-linux64` 的类似修改是否有意义，因为这里面的 `lib{,32,64}` 定义是对 Multiarch 的，在没有 Multiarch 的情况下应该不起效，所以我没有修改这一项。
- 在 `configure` 处：
  - 添加 `--build=$LFS_BLD`
  - 对 "Care" Port，添加 `--with-abi=64 --with-arch=mips3 --with-tune=loongson2f`[^3]
  - 对 "Modern" Port，添加 `--with-abi=64 --with-arch=mips64r2 --with-tune=loongson3a`[^4]
    - 另添加 `--without-madd4` 绕过龙芯三号对 MIPS 标准的不兼容实现（unfused -> fused），会有性能损失，但是是兼容性的代价

## 5.7. Glibc-2.28

- 在 `configure` 处：
  - 这里 LFS 指定了 `--build=$(../scripts/config.guess)`，注意我们的 Tuple 和猜的不同，所以需要替换成 `--build=$LFS_BLD`

## 5.8. Libstdc++ from GCC-8.2.0

- 添加 `--build=$LFS_BLD`

## 5.9. Binutils-2.31.1 - Pass 2

- 在 `configure` 后：
  - 添加 `--build=$LFS_TGT`
    - 注意这里要开始使用 Pass 1 GCC 了，是 `TGT`
    - 并且我们的 Tuple 和猜的不同，所以这一项是必要的

## 5.10. GCC-8.2.0 - Pass 2

- 在 `configure` 后：
  - 添加 `--build=$LFS_TGT`
    - 同上，这里要开始使用 Pass 1 GCC 了，是 `TGT`
    - 并且我们的 Tuple 和猜的不同，所以这一项是必要的
- 其余步骤参见 Pass 1

## 5.29. Perl-5.28.0

- Perl 的非标准 `Configure` 在这个阶段会两次莫名其妙地进入 Bash 的交互命令行，我不太清楚是怎么回事。

## The Rest

- 为了好看，记得 `--build=$LFS_TGT`（特别是像 Bash 这种记录 Tuple 的）
- 注意 LFS 对很多包做了 FHS 兼容性调整，对 AOSC OS 来说大部分都不必要，因为 AOSC OS 是默认做了 `/usr` merge[^5] 的，所以一些诸如 `/usr/bin/xxx -> /bin` 的移动就没有意义。
  - 这其中还包括在 `configure` 阶段就做出的调整，注意弄清楚各个选项的含义。比如 `systemd` 中的 `--with-xxx-path=yyy` 选项不是要指定安装目录，而是**指定二进制文件所在位置**，`meson` 会将这些信息写入到 Systemd Units 配置中。一开始我就想当然去除了这些选项，启动之后 systemd 就有一堆服务因为找不到二进制文件（找了 `/tools/bin/xxx`，而最终系统中并没有）而发生错误。

## 6.6. Creating Essential Files and Symlinks

- 在 _6.7. Linux-4.18.5 API Headers_ `make mrproper` 的时候还需要 `/bin/awk -> /bin/gawk -> /tools/bin/gawk` 这个链接，加上

## 6.9. Glibc-2.28

- 对 _Determine the GCC include directory_ 一操作，由于 LFS 中指定了是 x86 架构的操作，这里需要手动 `export`
- 我们不 LSB，两个 Symlink 可以不用做
  - 否则还是需要做的，目标库文件名是 `ld.so.1`

## 6.17. GMP-6.1.2

- 由于在 MIPS 上 GMP 支持三种 ABI，在 `configure` 前手动指定 `ABI=64`（或者 `export ABI=64`）
- GMP 带的 `configure` 对 Tuple 的识别不是很标准，把我们 `mipsisa64r2el` 的 CPU 判断成了 32 位的。这里要给 `configure:4664` 做个改动：
  - `mips64*-*-* -> mips*64*-*-*`
  - 如果 Tuple 不是那么奇葩，这里是不需要动的

## 6.21. GCC-8.2.0

- 这里同样要记得参照 "5.5. GCC-8.2.0 - Pass 1" 和 "5.10. GCC-8.2.0 - Pass 2" 在 `configure` 阶段对 GCC 做调校。

## 6.49. Libffi-3.2.1

- 在 _Prepare libffi for compilation_ 处，注意给出的 `configure` 参数中有一个 `--with-gcc-arch=native`，这样会给 GCC 加上 `-march=native`，针对编译机器优化，代码在旧处理器上就跑不起来了。注意更换这一参数到目标平台的 `march`。

## 6.63. GRUB-2.02

- GRUB 的 `configure` 对 `mips{,64}el-*` 都给出龙芯平台（`platform=loongson`）的猜测，抛出了 `configure: error: qemu, coreboot and loongson ports need build-time grub-mkfont (need freetype2 library)` 的错误，但是这个时候因为 LFS 没有给出编译 freetype2 的步骤，加上已经 `chroot` 了，并没有 `grub-mkfont` 可以用。
  - 因此 GRUB 的 `configure` 对 `mipsisa64r2el-*` 直接判定未知处理器类型，不编译平台特定代码
  - 绕过这一问题有两种办法：
    1. 给 `configure` 传 `--with-platform=none`，让 GRUB 不编译平台特定的代码（同上，功能缺失）
    2. 在 Host 上复制一份，我没试过

## Notes

[^1]: [Forwarded from imi415] aosc os，关爱您、您的开发板、您的谜之处理器和您的史前遗产
[^2]: 好吧，我知道这其实是个 [Multiarch](https://wiki.debian.org/Multiarch) Tuple，但是为了明确区分这两个移植，我觉得我可能不得不这么做，毕竟 MIPS-III 是 MIPS64 的子集……
[^3]: 对龙芯二号，有 `-mfix-loongson2f-nop -mfix-loongson2f-jump` 两个 GCC 选项来绕过龙芯 2F 前期批次的 Bug，但是它们没有对应的 `configure` 选项，所以在后期构建系统介入之后注入选项实现修复。
[^4]: 对龙芯三号的 `LL` / `SC` Bug，最好是通过 Binutils 补丁的方式让 `gas` 修复问题，而不是在 GCC 这里 `--without-llsc`，这样性能下降会比较厉害，不推荐。**20191222 注：`gas` 现在已经并入 `--mfix-loongson3-llsc` 选项，可以直接用起。**
[^5]: https://github.com/AOSC-Dev/aosc-os/wiki/FYI_FS_Hierarchy

另，我不知道 `mipsisa64r2el` 这个 Host CPU 有没有给我带来麻烦……**20191222 注：肯定是会有的，黄脑袋应该没错。**
