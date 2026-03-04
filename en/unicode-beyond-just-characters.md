---
title: 'Unicode beyond just characters: Localization with the CLDR'
language: en
layout: post
permalink: /en/unicode-beyond-just-characters
category: coding
tags:
  - unicode
  - i18n
  - L10n
  - cldr
---

Here are notes, slides, video, and additional resources for my talk on software
localization with the Unicode CLDR, presented recently at
[OSCON](http://www.oscon.com/) and the [NY Tech Localization
Meetup](http://www.meetup.com/NY-Tech-Localization-Meetup/). Code examples are
in Python, Ruby, and Perl, plus libraries in other popular languages are
highlighted.

### Abstract

Unicode is much more than just characters. The Unicode Consortium defines open
standards for collating, parsing, and formatting data in much of the world’s
languages. The Common Locale Data Repository (CLDR) is the largest standard
repository of locale data along with specifications for its use, and is a
powerful resource for software localization.

The Unicode CLDR has become the de facto locale standard with widespread use
among companies, including Google, Apple, and Microsoft; projects ranging from
Linux distributions to Wikipedia; and increasing support in many programming
languages. This talk provides an introduction to software localization and
highlights popular CLDR-based open source libraries in a variety of programming
languages.

Topics include localized formatting of:

 * Numbers, percents, and ranges of numbers
 * Prices and currencies
 * Dates and times
 * Localized sorting lists of strings

### Slides

<iframe src="https://speakerdeck.com/player/495471c0e10a0131fe8a36fb43230fd9"
id="talk_frame_302715" width="560" height="378" frameborder="0"
allowfullscreen="true" allowtransparency="true" mozallowfullscreen="true"
webkitallowfullscreen="true"
style="border:0; padding:0; margin:0; background:transparent"></iframe>

<span style="font-size: 80%">
  Direct link:
  [https://speakerdeck.com/patch/localization-with-the-unicode-cldr](https://speakerdeck.com/patch/localization-with-the-unicode-cldr)
</span>

### Video

Here’s the video from the first presentation of this talk at YAPC::NA 2014. Note
though that this version was tailored to the Perl community and there’s been
much development in CLDR-based open source libraries in many programming
languages over the last year.

<iframe src="https://www.youtube.com/embed/DcPpUnlENAs?feature=oembed"
width="560" height="315" frameborder="0" allowfullscreen="true"></iframe>

<span style="font-size: 80%">
  Direct link:
  [https://youtu.be/DcPpUnlENAs](https://youtu.be/DcPpUnlENAs)
</span>

### Resources

 * [Unicode CLDR](http://cldr.unicode.org/) — Common Locale Data Repository
 * [CLDR Survey Tool Accounts](http://cldr.unicode.org/index/survey-tool/accounts) — Contribute CLDR data
 * [CLDR TL;DR](http://perladvent.org/2014/2014-12-23.html) — article I wrote for the Perl Advent Calendar
 * [Unicode Programming Examples](https://github.com/patch/unicode-programming) — open source documentation project

#### Libraries

**ICU**

International Components for Unicode: the premiere library implementing and providing access to the CLDR.

 * [ICU4C and ICU4J](http://site.icu-project.org/) — C/C++ and Java
 * [ICU4C-based Libraries](http://site.icu-project.org/related) — note that not all are maintained!

**ICU4C-based Libraries**

 * [Python: PyICU](https://pypi.python.org/pypi/PyICU/)
 * [PHP: intl](http://php.net/manual/en/book.intl.php)
 * [Erlang: i18n](https://github.com/erlang-unicode/i18n)

**CLDR-based Libraries**

 * [JS: twitter-cldr-js](https://github.com/twitter/twitter-cldr-js)
 * [Node: twitter-cldr-npm](https://github.com/twitter/twitter-cldr-npm)
 * [JS/Node: Globalize](https://github.com/jquery/globalize)
 * [Ruby: twitter-cldr-rb](https://github.com/twitter/twitter-cldr-rb)
 * [Ruby: Misc. RubyGems](https://rubygems.org/search?utf8=%E2%9C%93&query=cldr)
 * [Perl: CLDR::Number](https://metacpan.org/pod/CLDR::Number)
 * [Perl: Misc. CPAN](https://metacpan.org/search?q=cldr)

**CLDR Data**

 * [XML](http://cldr.unicode.org/index/downloads) — official
 * [JSON](https://github.com/unicode-cldr/cldr-json) — official
 * [JavaScript: cldr.js](https://github.com/rxaviers/cldrjs)
 * [Ruby: cldr](https://github.com/svenfuchs/ruby-cldr)
 * [Go: text/cldr](https://godoc.org/golang.org/x/text/cldr)

Thanks to everyone who participated in the session and discussion!
