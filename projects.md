---
layout: page
title: Projects
---

This is a page showcasing projects I have worked on, is working on, or plan to work on. I give brief introductions to, technologies I use in, concepts involved in, and personal thoughts on the projects. I usually think too much when creating projects, and most of the time people just don't understand what I think. This time, I try to write them down.

**Note:** I'm still working on this page, so the information is not complete yet.

- Table of Contents
{:toc}

## Under Development

These are my recently progressing projects; new features are added from time to time.

### World Wide Web Services

All World Wide Web (WWW) services are included in this category, including:

- [This site][this-src]
  - The [RDFa Lite Minima][minima-rdfa]
- [Persistent URL (PURL)]({% link services.md %}#purl)

[Jekyll][jekyll] is used to statically generate this whole website from [Markdown][markdown]. Despite the fact that this site just uses the Jekyll's default [Minima][minima] theme, a few tweaks are made:

- [Kramdown][kramdown] has a few powerful markups allowing more control of HTML from Markdown
- I [changed][minima-rdfa] [Microdata][microdata] in [Minima][minima] to [RDFa][rdfa]

Both [Microdata][microdata] and [RDFa][rdfa] are [Linked Data][ld] markups. The former is defined in the [HTML Living Standard][html-std], while the latter is defined by [W3C][w3c] and is used in all other non-HTML scenarios.

#### Some Thoughts

In my opinion, informational websites (like this site) should be made with plain HTML documents, rather than Web Apps (e.g. [Vue.js][vue], [React.js][react] powered websites). If a Web App is purely informational (i.e. no interactions are required from the user), it's fucked up.

(I'm not saying that using Vue.js or React.js is bad -- they are both excellent frameworks writing Web Apps. In fact, I have a few planned projects that embrace Vue.js. However, when it comes to information, the use of an App just advocates [information silos][info-silo] and sets up fences around.)

While people can read the documents, machines can too. If a website relies on JavaScript to dynamically render information, then only people can view it. Thus, I deliberately avoided the use of JavaScript. In this way, these ones can benefit:

- People using...
  - the [NoScript][noscript] browser plugin;
  - browsers without JavaScript functionality at all (e.g. [w3m][w3m]);
- Crawers and robots (e.g. search engines).

[Sir Tim Berners-Lee][timbl], who's the inventor of WWW, has a biography, [_Weaving the Web_][weaving-the-web], that explains the original design of the Web, which I think we haven't even achieved yet. There's also a documentary, [ForEveryone.net][foreveryone-net], in which Sir Tim, along with people working on and using the WWW, are interviewed. Some dialogues are taken from the biography. I've also [translated](#foreveryone-net) the subtitles into Simplified Chinese.

[this-src]: https://github.com/lmy441900/www
[minima-rdfa]: https://github.com/lmy441900/minima
[jekyll]: https://jekyllrb.com/
[markdown]: https://en.wikipedia.org/wiki/Markdown
[kramdown]: https://kramdown.gettalong.org/index.html
[minima]: https://github.com/jekyll/minima
[kramdown]: https://kramdown.gettalong.org/
[microdata]: https://html.spec.whatwg.org/multipage/microdata.html#microdata
[rdfa]: http://rdfa.info/
[ld]: https://en.wikipedia.org/wiki/Linked_data
[html-std]: https://html.spec.whatwg.org/multipage/
[w3c]: https://www.w3.org/
[vue]: https://v3.vuejs.org/
[react]: https://reactjs.org/
[info-silo]: https://en.wikipedia.org/wiki/Information_silo
[noscript]: https://noscript.net/
[w3m]: http://w3m.sourceforge.net/
[timbl]: https://en.wikipedia.org/wiki/Tim_Berners-Lee
[weaving-the-web]: https://www.w3.org/People/Berners-Lee/Weaving/Overview.html
[foreveryone-net]: https://www.foreveryone.net/

### TinyWoT

- Repository: <https://github.com/lmy441900/tinywot>

After some quick-and-dirty, ad-hoc implementations of [~~Mozilla~~ Web Thing API][webthing] for contests, I had the idea of creating a universal framework (or a library) that fits into both the model of W3C WoT and an extremely resource-constraint device (e.g. ATmega328p).

I know Web stuff are naturally not designed for devices with only 2KiB of RAM, but what if we really have one, which can also run blazingly fast on larger devices. Meaningless, but cool.

[webthing]: https://webthings.io/api/

### Can

- Repository: <https://git.soton.ac.uk/ml10g20/can>

"Can" is a _ChaCha20-Poly1305 Cryptographic Accelerator Based on a [No-Instruction-Set Computer (NISC)][nisc] Architecture_. It's first an implementation of a NISC processor, and then a cryptographic processor -- the cipher is an application running on it. This is my master's project and thesis.

The concept of NISC starts from [this technical report][dgajski2003nisc] in 2003, which is relatively new. Basically, compared to CISC and RISC, NISC achieves the "N" by directly dropping the concept of instructions. Imagine the control signals behind a RISC processor's decoder -- they're stored as it is in the program memory, called _Control Words_. The downside of NISC is obvious: the code size bloats.

I think NISC is most valuable in [High Level Synthesis (HLS)][hls], although this project has nothing to do about HLS. With a NISC methodology, since there is no instruction and the program (CWs) should control every component in the processor, the compiler will have the ability to generate a hardware processor (along with software (CWs)) directly from software codes in e.g. C. There will be no soft IP core then: it's generated each time a software program is compiled into a NISC processor. _(I might be wrong)_

LLVM [MLIR] and [CIRCT] are very likely to be the basis of a NISC compiler.

[nisc]: https://en.wikipedia.org/wiki/No_instruction_set_computing
[dgajski2003nisc]: http://www.cecs.uci.edu/~cad/publications/tech-reports/2003/TR-03-28.NISC.pdf
[hls]: https://en.wikipedia.org/wiki/High-level_synthesis
[MLIR]: https://mlir.llvm.org/
[CIRCT]: https://circt.llvm.org/

### PeaZip Simplified Chinese Localization

- Repository: <https://github.com/lmy441900/PeaZip-l10n-zh-Hans>

This project translates the language files in PeaZip to Simplified Chinese (zh-Hans). A few collaborators have contributed to this project too, so this is not maintained solely by me.

Unfortunately, the author and maintainer of PeaZip, [Giorgio Tani][gtani], doesn't want to host the source code on Github. As a result, collaboration is done by sending an email to them each time the translation is updated. Every tag I add in the repository is the version I've sent to them.

[gtani]: https://github.com/peazip

## Under Maintenance

These are projects that have "finished" and have entered a "stable" state. The progress of these projects may look inactive, but I'm still accepting new issues (bug reports) and pull requests.

### LibYAML Vala Binding

- URL: <https://github.com/lmy441900/yaml-vala/>
  - also in: <https://gitlab.gnome.org/GNOME/vala-extra-vapis>

This is the [Vala][vala] API (`.vapi`) definition for the use of [LibYAML][libyaml] in Vala. It's basically a transcription from the LibYAML C APIs to Vala style APIs.

[vala]: https://wiki.gnome.org/Projects/Vala
[libyaml]: https://pyyaml.org/wiki/LibYAML

### ForEveryone.net Simplified Chinese Subtitles {#foreveryone-net}

- Repository: <https://github.com/lmy441900/ForEveryone.net-sub-zh-Hans>

This project translates the subtitles of the documentary to Simplified Chinese (zh-Hans).

The former half of the subtitle file was translated by me, and the latter half was translated by [gloomy-ghost][]. The finished subtitles are then rendered into the video (hard-coded into the video). The video has been uploaded to [Bilibili][foreveryone-net-bili].

There're possible improvements though. The timeline was taken from another user from Bilibili who constantly uploads documentary films, and although we've got approval on its free use, it's better to use the W3C version used in their [upload on YouTube][foreveryone-net-ytb-sub]. More tweaks on font sizes and effects can be added.

[gloomy-ghost]: https://github.com/gloomy-ghost
[foreveryone-net-bili]: https://www.bilibili.com/video/BV1qx411o7qs
[foreveryone-net-ytb-sub]: https://youtu.be/4pjG1UfgWD8

## Planned (Stalled) {#planned}

These are projects that have never been started, or have been paused due to insufficient spare time. At this moment, I don't have an idea when can I start these projects, but I'd like to first note them down.

### Coreboot Distribution for ThinkPad X200

- Repository: <https://github.com/lmy441900/coreboot-x200>

I own a ThinkPad X200, and I experiment Coreboot on it. To make the firmware as universal as possible, I plan to install as many payloads as possible, thanks to the abundant room emptied by Libreboot's `ich9gen`. This may include a GRUB 2, a SeaBIOS, a TianoCore, a tiny Linux rescue toolbox, and more. A binary distribution of the image can enable many other people to just use my work. Nevertheless, either automation of image building or end-user customisation are not done yet.

### Itinerary

This will be an application helping people to plan their trips _that rely on public transportation_. This will not be a general sight-seeing adviser; instead, it aims at addressing the pain of managing multiple public transportation trips in a journey.

There will be a few niche features: hand-writing (in e.g. TOML) support, open (linked) data and printable format (PDF) output support, etc.

### WoT Remote Control

This will be a mobile application that is capable of accepting / consuming a [Web of Things (WoT) Thing Description (TD)][wot-td]. It should be easy to generate a UI from it -- there have been a few prototypes, but they're crappy and not quite usable. People can use this application to control the Thing described by the TD on their mobile devices. They can also modify some metadata locally.

This should have a straightforward UI and good UX. I may want to use Flutter.

[wot-td]: https://www.w3.org/TR/wot-thing-description11/

## Discontinued

These are projects that are abandoned. I'm not planning to improve them, but if someone is still interested in the ideas of them, I'll be very happy.

### MDBFS

- Repository: <https://github.com/lmy441900/mdbfs>

"MDBFS" stands for "Mapping DataBases into a File System". The project implements a [file system in userspace (FUSE)][fuse] that takes a database container or a database management system connector, and mounts it as a file system.

This is the final year project for my bachelor's degree. It was started with an ambitious goal of making it an actively maintained open source software, but after knowing some alternatives e.g. [Windows Projected File System (ProjFS)][projfs] and feeling uncertain about my future spare time, I decided to stop maintaining it right after my thesis defense. If you're interested in it, you may request the thesis by contacting me.

[fuse]: https://en.wikipedia.org/wiki/Filesystem_in_Userspace
[projfs]: https://docs.microsoft.com/en-us/windows/win32/projfs/projected-file-system

### URM

- Repository: <https://github.com/lmy441900/urm>

"URM" stands for "Unified Repository Manager". "Repository" here means a _real_ repository; it was a reinvented wheel for simple inventory management. Originally designed for asset management in small laboratories, URM provides a light-weight and straightforward way to manage things without the burden put by enterprise-class inventory management systems.

This is a boring ad-hoc project. The only "novel" concept involved is [content negotiation][ct-neg] (it's not novel at all) on a resource.

[Rocket][rocket-rs] is hard to use when it comes to customising the data flow.

[ct-neg]: https://en.wikipedia.org/wiki/Content_negotiation
[rocket-rs]: https://rocket.rs/

## Coursework

Projects fulfilling requirements of coursework assignments are never meant to be functionally complete, but they did cost me a great amount of time. When I do coursework projects, I usually try practicing my novel ideas, and some of them might be worth talking about.

Not all coursework projects are listed here--only the ones that are _worth talking about_. Many of my other coursework projects only fulfill the basic requirements, even they cost me a large amount of time. Nevertheless, being buried may be their fate.

### AAA

- For: COMP4093 Internet and the World Wide Web
- Repository: <https://github.com/lmy441900/aaa>

"Aaa" (pronounced ei-ei-ei) is an end-to-end encrypted peer-to-peer instant messaging software, _proudly powered by Curve25519_. [(?)][25519-note]

The idea of the name comes from my group-mate [Yvonne][yvonne]. It doesn't have any meaning at all. Despite this fun (?) fact, the project is somewhat sad: it did not work.

- The [Vala][vala] programming language is experimented to write GTK-related codes. However, other modules, e.g. the cryptographic functions based on [libsodium][libsodium], are still written in C. To make the APIs written in the two languages callable to each others', Vala API binding is experimented. The insufficient documentation of Vala have caused difficulty to the process.
  - Later, when the program run, because of ~~our~~ my poor management of memory, garbage collection kept destroying things, and ~~we~~ I didn't know why.
- Yvonne couldn't help much. I feel sorry for using too many new technologies that she hasn't even heard about (and I wasn't confident with).

[25519-note]: https://cr.yp.to/ecdh.html
[yvonne]: https://github.com/YvonneTech
[vala]: https://wiki.gnome.org/Projects/Vala
[libsodium]: https://doc.libsodium.org/

### Teapot

- For: COMP4093 Internet and the World Wide Web
- Repository: <https://github.com/lmy441900/teapot>

Teapot is a simple HTTP server implemented in C. The idea of the name comes from `HTTP 418 I'm a Teapot`: we [implemented it][teapot-impl], but in a sad way.

The coursework requires socket programming, so HTTP processing is done manually. This project tries to make full use of [GLib][glib], utilising all kinds of facilities it provides.

I must say that the experience of writing C with GLib is way better than without GLib.

[teapot-impl]: https://github.com/lmy441900/teapot/blob/master/src/http.c#L44
[glib]: https://wiki.gnome.org/Projects/GLib

### Phone Book

- For: COMP3003 Data Communications and Networking
- Repository: <https://github.com/DRJ31/COMP3003-Project>

This is an implementation of both client and server of an online yellow page service, allowing a user to query contact information of someone using a dedicated graphical client written in GTK.

The coursework requires socket programming, so we derived our own protocol based on HTTP and JSON. HTTP parsing is done manually, while JSON parsing is done using the library [parson][parson]. The GUI is constructed with [Glade][glade]. Keeping both the client and the server in a single executable (the server is invoked by appending a `server` argument) is experimented.

[parson]: https://github.com/kgabis/parson
[glade]: https://glade.gnome.org/
