---
layout: post
title: Plain Text Oriented Markdown
category:
  - blog
  - en
---

Markdown is designed to be readable even without rendering, but most people
today use it only as a medium to the rendered converted work. What if the
"source text" *is* the final work? A text file filled with Markdown markups can
still be difficult to read. To keep Markdown documents "plain" enough, I have a
set of rules for writing plain text documents with a Markdown syntax, and I'm
noting them down here.

-------------------------------------------------------------------------------

If a plain text document is written to be published as-is, then any typesetting
effect (font size, font weight, ...) need to be directly applied to the plain
text. There's however no magic automatic styling in a plain text document, so
it all comes to the art of ASCII drawing[^1]. Some documents have this style of
first-level headings, for example:

    ########################################################################
    ##                I M P O R T A N T    D O C U M E N T                ##
    ########################################################################

Whilst outstanding in plain text, it's impossible to convert such markup to
other formats. If these structural markups follow an existing standard, then
the document *can* be converted to those formats, if needed. However, there are
situations where we don't want to sacrifice too much about the readability of
text file. There can be a balance between readable plain text and convertible
source text.

Why plain text in the first place? Because it's the most universal file format.
No special software is required to display and edit text files. However, plain
text has no styling options. There's no graphics support. Extra semantics is
added with markup conventions. Meanwhile, documents in HTML and PDF are
graphical and can present the document in a far better and intuitive way,
albeit special software is required. As a result, some markup conventions are
designed to be machine convertible. Markdown is one of them.

It doesn't have to be Markdown though. Some other lightweight markup
languages[^2] look nicer indeed, but surely Markdown has higher popularity.
People who already know about Markdown will find the markups familiar. People
who don't know about Markdown can also understand them well. People who
completely cannot comprehend can convert it to a webpage or a printed document.
It's an added benefit to a plain text document.

Over the past decades, Markdown has been extended by lots of people to support
all kinds of elements. However, not all Markdown markups look nice in the
source text. Markdown also allows raw HTML input, which is solely for web-based
tools to interpret and only clutters the source text. As a result, a lot of
Markdown markups are avoided to keep the source text in a better structure.

Therefore, when I write plain text documents, I focus on the readability of
text, but also try to make the document Markdown-compatible. It comes with
sacrifices: it doesn't offer splendid ASCII effects in the text file nor offers
enough styling options in the converted document. Whether this is worthy or
not, I don't know.

In this article, I'm only noting down caveats and differences to common
Markdown writing practices (that I can think of). Not all Markdown features are
well-supported by all tools, but I don't feel the need of limiting the choice
of syntaxes; there's never a "standard" Markdown after all.

This article is written with these rules in mind -- you can read the source
text file of this article for a taste of it:
<https://raw.githubusercontent.com/jyhi/www/refs/heads/main/_posts/2025-01-19-plain-text-oriented-markdown.md>.


Headings
--------

The Setext[^3] style is preferred because of its higher visibility:

    Heading 1
    =========

    Heading 2
    ---------

There's however no more deeper heading levels in this style. Generally I'd try
avoiding deeper levels of heading first, but this is not always possible. To be
frank, I don't have a strong opinion about this. The ATX[^4] style is
acceptable to me (only at heading 3/4):

    ### Heading 3

    #### Heading 4

Instead, I often use a title-cased sentence followed by a colon (":") to create
a sense of heading. It can have its own block:

    New Heading:

    A new paragraph starts.

It can also lead a paragraph or a list item:

    Heading: a paragraph -- normally just one -- follows.

    * Heading: a list item follows, but it can have multiple paragraphs.

If a heading occupies its own paragraph, then it should be two blank lines
apart from the preceding paragraph. However, if two such headings are next to
each other, then they only need to have one blank line of gap between them.
This is to make the section separation clearer while avoiding excessive blank
lines.

If a heading doesn't have its own paragraph, then it's treated like the
paragraph text: it loses its styling and only retains its semantics (if
applicable).

If heading 1 is right at the start of document and can be seen as the title of
the whole document, then it doesn't have to have any blank line before it,
although including one seems to look better.

    Example Document
    ================

    Preface
    -------

    This document is an example.


    Background
    ----------

    It all started a while ago.

    Last Month: ...

    Last Weekend: ...


Emphasis
--------

Use asterisks ("*") to denote emphasized texts. For most of the time, one pair
of asterisks (rendered as italics in Markdown) is sufficient. Two pairs of
asterisks (rendered as bold in Markdown) is a really strong emphasis.
Underscores ("_") are avoided, as I think they're likely to be understood as
underlines.

    *general emphasis*
    **heavy emphasis**

Strikethroughs ("~") are acceptable, but people who don't know about Markdown
might not get the idea, so they're better avoided as well. That said, I've seen
geeks trying to express this idea in a plain text email with a key stroke
notation ("^W" / "Ctrl+W" is delete last word on Bash):

    The quick brown fox jumps over the lazy you^Wdog.


Lists
-----

An asterisk ("*") is preferred for denoting a bullet point in an unordered
list. Hyphen ("-") and plus sign ("+") are okay, and can sometimes be used to
convey extra semantics. For example, I like to put up a change list with plus
signs meaning additions, asterisks meaning changes, and hyphen meaning
removals. However, note that Markdown implementations may have different
thoughts about a list with mixed items.

    * List item.
    * List item.
    * List item.

For ordered lists, continue to use numbers followed by periods (".").

    1. List item one.
    2. List item two.
    3. List item three.

If a list contains several long items, then when wrapped (either automatically
or manually) they don't look separate enough. A gap of one blank line should
be added between long list items. Each of them can start with a sub-heading to create a feeling of separate sections.

That said, long list items should be avoided in the first place. It can be
rewritten as a list containing short abstracts followed by paragraphs
explaining each point in the list.


Codes
-----

Plain code blocks are preferred to fenced code blocks. This loses syntax
highlight, but looks more natural in a plain text document.

    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua.

        :(){:|:&};:

    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
    aliquip ex ea commodo consequat.

For code spans (inline code), backticks ("`") are okay, but it's more a
Markdown convention than a natural way to quote codes. If it's not important to
have the code span rendered differently in a converted format, then quotation
marks (" / ') look plainer and should be preferred.

    The quick "brownFox" "jumps()" over the "lazyDog".


Links
-----

Because *hypertext* is by itself *beyond* plain text, it's normally not used in
a plain text document. To include a link at a specific position, mark a
footnote ("[^#]") to a website, just like journal articles. However, note that
footnotes may not be widely supported, and for formats without a "foot" they'll
become endnote. A shortcut reference link[^5] ("[Text]" with "[Text]: link") is
also acceptable, and can achieve a better result in the converted document.
Other link syntaxes are not recommended, as they clutter the plain text too
much.

    Here[^1] and [here] are two examples of website hosted on the Internet.

    [here]: https://www.example.com/

    [^1]: <http://www.example.com/>


Reference
---------

[^1]: ASCII art - Wikipedia. <https://en.wikipedia.org/wiki/ASCII_art>
[^2]: Lightweight markup language - Wikipedia. <https://en.wikipedia.org/wiki/Lightweight_markup_language>
[^3]: Setext headings, CommonMark Spec. <https://spec.commonmark.org/0.31.2/#setext-headings>
[^4]: ATX headings, CommonMark Spec. <https://spec.commonmark.org/0.31.2/#atx-headings>
[^5]: CommonMark Spec. <https://spec.commonmark.org/0.31.2/#shortcut-reference-link>
