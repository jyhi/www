---
layout: page
title: Projects
---

This is a page showcasing projects I have worked on, is working on, or plan to work on. I give brief introductions to, technologies I use in, concepts involved in, and personal thoughts on the projects. I usually think too much when creating projects, and most of the time people just don't understand what I think. This time, I try to write them down.

**Note:** I'm still working on this page, so information is not complete yet.

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

### PeaZip Simplified Chinese Localization

## Under Maintenance

These are projects that have "finished" and have entered a "stable" state. The progress of these projects may look inactive, but I'm still accepting new issues (bug reports) and pull requests.

### LibYAML Vala Binding

- URL: <https://github.com/lmy441900/yaml-vala/>
  - also in: <https://gitlab.gnome.org/GNOME/vala-extra-vapis>

This is the [Vala][vala] API (`.vapi`) definition for the use of [LibYAML][libyaml] in Vala. It's basically a transcription from the LibYAML C APIs to Vala style APIs.

[vala]: https://wiki.gnome.org/Projects/Vala
[libyaml]: https://pyyaml.org/wiki/LibYAML

### ForEveryone.net Simplified Chinese Subtitles {#foreveryone-net}

## Planned (Stalled) {#planned}

These are projects that have never been started, or have been paused due to insufficient spare time. At this moment, I don't have an idea when can I start these projects, but I'd like to first note them down.

### Coreboot Distribution for ThinkPad X200

### TinyWoT

### Itinerary

## Discontinued

These are projects that are abandoned. I'm not planning to improve them, but if someone is still interested in the ideas of them, I'll be very happy.

### MDBFS

### URM

## Coursework

Projects fulfilling requirements of coursework assignments are never meant to be functionally complete, but they did cost me a great amount of time. When I do coursework projects, I usually try practicing my novel ideas, and some of them might be worth talking.

### AAA

### Teapot

### Phone Book
