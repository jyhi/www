---
layout: page
title: About
---

## About Me {#me}

I am a...

- Postgraduate student in Internet of Things at [University of Southampton][uos].
- BSc (Hons) \'20 in Computer Science and Technology at [BNU–HKBU UIC][uic].
- Contributor in [Anthon Open Source Community][aosc].
- Webmaster of [gddg.studio][gddg].
- HAM (amateur radio operator), class A (foundation), callsign BI7PXN.

*[BSc (Hons) '20]: Bachelor of Science (Honours), class 2020
*[BNU–HKBU UIC]: Beijing Normal University–Hong Kong Baptist University United International College
*[BI7PXN]: Bravo India Seven Papa X-ray November
[uos]: https://www.southampton.ac.uk/
[uic]: https://uic.edu.cn/
[gddg]: https://gddg.studio/

### Contact

Refer to the site footer for my existence on other media. Alternatively:

- IRC: yhi@[irc.libera.chat](ircs://irc.libera.chat)
- Email:
  - **junde at yhi Punkt moe**: personal
  - **lmy441900 at** ...
    - **live dot com**: personal alternative
    - **aosc dot io**: work, [AOSC][aosc], and development related

[aosc]: https://aosc.io/

### PGP

Fingerprint: **`E6C7 4782 A1FB EE74 1D09  885F D274 286F 672C 800A`**.

Fetch the public key from [keys.openpgp.org][koo].

Subkey usage explanation:

- `ed25519/ABDA5B82F36D3DB2 2019-10-19 [S]`
  - Main signing key. Located in a smart card (Yubikey 5 NFC).
- `cv25519/1B318A5615C632D0 2019-10-19 [E]`
  - Main encryption key. Located in a smart card (Yubikey 5 NFC).
- `rsa2048/943D73C9AD8AFB50 2019-10-19 [S] [expires: 2021-03-01]`
  - (Deprecated) On-card signing key. Located in a smart card (Yubikey 4, which doesn't support Curve25519). I'm not using it any more.

My old key, ~~`42F6 3E9D 68B9 884B 414D  4185 1029 4E7C 4008 E282`~~, has been revoked. I have switched my PGP key to a newly generated `ed25519 / cv25519` one, and I'm applying some best practices I learned after I've created my last PGP key. If you have signed on my old key, you can trust my new key since I've signed it with my old key in prior to the revocation. (Unfortunately this process is still not a best practice!)

[ca-pgp]: https://ca.yhi.moe/pgp/main.asc
[koo]: https://keys.openpgp.org/vks/v1/by-fingerprint/E6C74782A1FBEE741D09885FD274286F672C800A
[sks]: https://sks-keyservers.net/
[sks-death]: https://code.firstlook.media/the-death-of-sks-pgp-keyservers-and-how-first-look-media-is-handling-it

## About This Site {#this-site}

Blog posts are in English or (Simplified) Chinese. Unless otherwise specified, all contents on the site are licensed under the [CC-BY-SA 4.0][cc-by-sa-4] license.

This site is proudly built:

- _without JavaScript_
- with [Jekyll][jekyll]
  - and theme [Minima][minima-rdfa] v2.99 ([RDFa][rdfa] enabled fork)
- by and hosted on [Cloudflare Pages][cf-pages]

No analytical script (e.g. Google Analytics) is deployed on the site to track users. However, the following service providers **do** analyse visitors:

- **Google**: [Google Search Console][gsc] is set up on the domain name, so Google search results related to this site are analysed; summaries about e.g. keywords used by the user are given.
- **Cloudflare**: DNS and most network traffic on the domain go through Cloudflare, so the network traffic is analysed; summaries about e.g. visitor locations are given.

[cc-by-sa-4]: https://creativecommons.org/licenses/by-sa/4.0/
[jekyll]: https://jekyllrb.com/
[minima-rdfa]: https://github.com/lmy441900/minima/tree/master-rdfa-lite
[rdfa]: http://rdfa.info/
[cf-pages]: https://pages.cloudflare.com/
[gsc]: https://search.google.com/search-console/about

### Technical Information

This site is built against commit [{{ site.git.last_commit.short_sha }}][src] at {{ site.time }}.

[src]: https://github.com/lmy441900/www/commit/{{ site.git.last_commit.long_sha }}
