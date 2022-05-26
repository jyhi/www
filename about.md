---
layout: page
title: About
---

## About Me {#me}

I am a...

- Software Engineer at [IOTA Foundation][if]
- Community member of [Anthon Open Source Community][aosc].
- HAM (amateur radio operator), class A (foundation), callsign BI7PXN.

I was a...

- Postgraduate student in Internet of Things at [University of Southampton][uos].
  - now MSc \'21
- Undergraduate student in Computer Science and Technology at [BNU–HKBU UIC][uic].
  - now BSc (Hons) \'20

I am also at...

- IRC: yhi@irc.libera.chat
- Email: junde \[at\] yhi \[dot\] moe
- Telegram: [@lmy441900](https://t.me/lmy441900)
- Discord: Junde Yhi\#7860
- GitHub: [@lmy441900](https://github.com/lmy441900)
- Twitter: [@lmy441900](https://twitter.com/lmy441900)
- Mastodon: [@lmy441900@sn.angry.im](https://sn.angry.im/@lmy441900)
- YouTube: [Junde Yhi](https://www.youtube.com/channel/UCLfPUs9whRpb70I6Z1swXag)
- Twitch: [JundeYhi](https://www.twitch.tv/jundeyhi)
- Bilibili: <span lang="cmn-Hans">[以俊德](https://space.bilibili.com/50639488)</span>
- osu!: [yhi](https://osu.ppy.sh/users/16462774)
- Arcaea: 873 012 337
- Genshin Impact: 116046150
- ~~QSO: 147.950 MHz, 430.050 MHz, FM Voice~~
- ...

*[MSc '21]: Master of Science, class 2021
*[BSc (Hons) '20]: Bachelor of Science (Honours), class 2020
*[BNU–HKBU UIC]: Beijing Normal University–Hong Kong Baptist University United International College
*[BI7PXN]: Bravo India Seven Papa X-ray November

[if]: https://www.iota.org/
[uos]: https://www.southampton.ac.uk/
[uic]: https://uic.edu.cn/
[aosc]: https://aosc.io/

### PGP

- **`D3B1 90D6 6FF1 DD50 9F83  D71A 385F 41A9 1FE0 82D1`** (in use)
  - fetch the public key from...
    - [keys.openpgp.org](https://keys.openpgp.org/vks/v1/by-fingerprint/D3B190D66FF1DD509F83D71A385F41A91FE082D1)
    - [purl.yhi.moe](https://purl.yhi.moe/pgp/d3b190d66ff1dd509f83d71a385f41a91fe082d1/jyhi.asc) (with key signatures for Web of Trust)
- ~~`E6C7 4782 A1FB EE74 1D09  885F D274 286F 672C 800A`~~ (almost dead)
  - I sadly forget the passphrase to unlock the LUKS partition storing its master key and revocation certificate...
- ~~`42F6 3E9D 68B9 884B 414D  4185 1029 4E7C 4008 E282`~~ (revoked)
  - I sadly forgot the fact that this key was in the PGP Web of Trust Strong Set...

## About This Site {#this-site}

Blog posts are in English or (Simplified) Chinese. Unless otherwise specified, all contents on the site are licensed under the [CC-BY-SA 4.0][cc-by-sa-4] license.

This site is proudly built:

- _without JavaScript_
- with [Jekyll][jekyll]
  - and theme [Minima][minima-self] v2.99 (self-use fork with changes and enhancements)
- by and hosted on [Cloudflare Pages][cf-pages]

No analytical script (e.g. Google Analytics) is deployed on the site, nor there is a cookie set from the site to track users. However, the following service providers **do** analyse visitors:

- **Google**: [Google Search Console][gsc] is set up on the domain name, so Google search results related to this site are analysed; summaries about e.g. keywords used by the user are given.
- **Cloudflare**: DNS and most network traffic on the domain go through Cloudflare, so the network traffic is analysed; summaries about e.g. visitor locations are given.

[cc-by-sa-4]: https://creativecommons.org/licenses/by-sa/4.0/
[jekyll]: https://jekyllrb.com/
[minima-self]: https://github.com/lmy441900/minima/tree/self-use
[cf-pages]: https://pages.cloudflare.com/
[gsc]: https://search.google.com/search-console/about

### Technical Information

{% comment -%}
  The newline_to_br | split trick is because split cannot find a '\n'...
{%- endcomment -%}

This site is built at {{ site.time }} against commit [{{ site.git.last_commit.short_sha }}][src] (_{{ site.git.last_commit.message | newline_to_br | split: '<br />' | first }}_).

[src]: https://github.com/lmy441900/www/commit/{{ site.git.last_commit.long_sha }}
