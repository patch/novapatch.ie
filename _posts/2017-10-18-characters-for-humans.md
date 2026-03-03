---
title: 'Characters for Humans'
language: en
layout: post
permalink: /en/characters-for-humans
category: coding
tags:
  - unicode
  - i18n
  - emoji
---

The <code>\X</code> Files: programming with extended grapheme clusters and emoji
sequences.

<script async class="speakerdeck-embed" data-id="92864267464d4a088a1095e6992983af"
data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

A “character” can mean different things to different people, but the largest
disparity is between applications and the humans who use them. Programmers
aren’t to blame, as our programming languages, libraries, and databases provide
little or no support for understanding user-perceived characters. Many systems
disagree on the basic units of characters, some use code points, others use code
units, and others still operate on individual bytes by default. This frequently
leads to products with a poor experience in some users’ languages, especially
written languages that use grapheme clusters, sequences of code points that
compose a single user-perceived character. With the rise in global emoji usage
and the rapid evolution of standard emoji sequences, this problem is
increasingly experienced by users worldwide, regardless of their language.

This presentation covers:
 * Extended grapheme clusters and emoji sequences 
 * Programming with these user-perceived characters 
 * Data input, parsing, analysis, formatting, and output 
 * Setting product requirements for character support 
 * Examples from Shutterstock’s platforms for content editing and collaboration

### Resources
 * **[Fabric.js](http://fabricjs.com/)**: Open source HTML5 Canvas library
 * **[Shutterstock Editor](https://www.shutterstock.com/editor)**: Browser-based
   editing of images and text, including emoji
 * Editor emoji examples:
   [new emoji](https://www.shutterstock.com/editor/design/388751?share_code=46290a14e125fc3abe96cc02f29a6019)
   ([json](https://www.shutterstock.com/editor/image/api/v1/design/388751?share_code=46290a14e125fc3abe96cc02f29a6019)),
   [dolphin bicycle](https://www.shutterstock.com/editor/design/391449?share_code=7186a895d4799476b957a76c1e85c016),
   [cinco de mayo](https://www.shutterstock.com/editor/design/393687?share_code=6911bc271253f0a5c58be37f972c410f),
   [cinco de mayo?](https://www.shutterstock.com/editor/design/395297?share_code=3d6d9ffe8cd50e5da5fae5a87de4746d), and
   [halloween](https://www.shutterstock.com/editor/design/391447?share_code=aec9a98c23a2713cdf6d9aa844da6b83)
 * **Perl 6**: [strings](https://docs.perl6.org/type/Str),
   [regular expressions](https://docs.perl6.org/language/regexes), and
   [Unicode](https://docs.perl6.org/language/unicode)
 * **Swift**: [strings](https://developer.apple.com/documentation/swift/string),
   [characters](https://developer.apple.com/documentation/swift/character), and
   [strings and characters](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/StringsAndCharacters.html)
 * **[Unicode Line Breaking Algorithm](https://unicode.org/reports/tr14/)** (UAX #14)
 * **[Unicode Regular Expressions](https://unicode.org/reports/tr18/)** (UTS #18)
 * **[Unicode Text Segmentation](https://unicode.org/reports/tr29/)** (UAX #29)
 * **[Unicode Character Database](https://unicode.org/reports/tr44/)** (UAX #44)
 * **[Unicode Emoji](https://unicode.org/reports/tr51/)** (UTS #51)

### Presented at
 * 2017-10-18: Internationalization & Unicode Conference 41 (IUC41), Santa Clara, CA
 * 2017-06-21: The Perl Conference (YAPC::NA), Washington, DC
