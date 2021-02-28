---
layout: page
title: Services
---

Notice: the following are not generic public services; they are just my [projects][proj] that can be (to some extent) accessed on the Internet. As parts of my personal experiments, they are subject to change, and have no [SLA][sla] guarantees. No abuse.

[proj]: projects.html
[sla]: https://en.wikipedia.org/wiki/Service-level_agreement

## PURL

PURL stands for [Persistent Uniform Resource Locator][purl-wp].

- Visiting the PURL returns a `HTTP 307 Temporary Redirect` to the registered URL; i.e. a simple redirection.
- Visiting a non-existent resource returns `HTTP 404 Not Found`.

Usage:

- `GET http://purl.yhi.moe/<name>`
- `GET http://yhi.moe/<name>`

... where:

- `<name>` is a path or a resource name allocated.

[URL shortening][surl-wp] service is provided using the same infrastructure, so `yhi.moe` is just a shortcut to `purl.yhi.moe`. `/` is used to jump to `www.yhi.moe`.

You may register one by contacting me, but why?

[purl-wp]: https://en.wikipedia.org/wiki/PURL
[surl-wp]: https://en.wikipedia.org/wiki/URL_shortening
