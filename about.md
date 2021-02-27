---
layout: page
title: About
---

## About Me

I am a...

- (Ongoing) Master of Science in Internet of Things (MSc IoT) at [University of Southampton][uos].
- Bachelor of Science in Computer Science (and Technology) (BSc CS) at [Beijing Normal University - Hong Kong Baptist University United International College (BNU-HKBU UIC)][uic].
- (Not-very-active) Developer at [Anthon Open Source Community (AOSC)][aosc].
- HAM (amateur radio operator), level A (foundation), callsign **BI7PXN**.

See also my:

- CV (coming soon)
- FOAF (coming soon) [(?)][foaf]

[foaf]: https://en.wikipedia.org/wiki/FOAF_(ontology)

### Contact

Refer to the site footer for my existence on other media. Alternatively:

- Email:
  - **junde at yhi punkt moe**: personal
  - **lmy441900 at** ...
    - **live dot com**: personal alternative
    - **aosc dot io**: work, [AOSC][aosc], and development related

[uic]:      https://uic.edu.hk
[uos]:      https://www.southampton.ac.uk/
[aosc]:     https://aosc.io

### PGP / GPG

Fingerprint: **`E6C7 4782 A1FB EE74 1D09  885F D274 286F 672C 800A`**.

Fetch the public key from:

- ca.yhi.moe (not available yet)
- [keys.openpgp.org][koo]
- ~~[SKS keyservers][sks]~~ ([not recommended][sks-death])

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

## About This Site

Blog posts are in English or (Simplified) Chinese. Unless otherwise specified, all contents on the site are licensed under the [CC-BY-SA 4.0][cc-by-sa-4] license.

_This site is proudly built without JavaScript_. As a consequence, no analytical script (e.g. Google Analytics) is used to track users. However, a [Google Search Console][gsc] is set up on the domain name, so Google search results related to this site are indeed analysed. To further enhance personal privacy, using [DuckDuckGo][ddg] is recommended.

This site is [RDFa][rdfa]-enabled. Alternative linked data formats (e.g. RDF/XML, Turtle) are not supported at present.

[cc-by-sa-4]: https://creativecommons.org/licenses/by-sa/4.0/
[gsc]: https://search.google.com/search-console/about
[ddg]: https://duckduckgo.com/
[rdfa]: http://rdfa.info/
