---
title: When a Space Is Not Just a Space
language: en
permalink: /en/when-a-space-is-not-just-a-space
layout: page
category: coding
tags:
  - unicode
  - regex
  - java
  - perl
  - japanese
  - cjk
---

*Interview by <a href="https://www.linkedin.com/in/mccormickdaniel/" rel="author">Dan McCormick</a>, originally published on 30 April 2014 in the [Shutterstock Tech Blog](https://tech.shutterstock.com/).*

During a recent email exchange with our search team, Nova Patch, our resident Unicode expert, offered the following advice for a chunk of Java code used to detect Japanese characters:

> > ```java
> > Pattern.compile("^[\p{IsHiragana}\p{IsKatakana}\p{IsHan}\{IsCommon}\s]+$");
> > ```
> 
> We should use one of the following options instead:
> 
> ```java
> Pattern.compile("^[\p{IsHiragana}\p{IsKatakana}\p{IsHan}\{IsCommon}\p{IsWhite_Space}]+$");
> 
> Pattern.compile("(?U)^[\p{IsHiragana}\p{IsKatakana}\p{IsHan}\{IsCommon}\s}]+$");
> 
> Pattern.compile("^[\p{IsHiragana}\p{IsKatakana}\p{IsHan}\{IsCommon}\s]+$", Pattern.UNICODE_CHARACTER_CLASS);
> ```
> 
> They all do the exact same thing, which is matching on any Unicode whitespace instead of just ASCII whitespace. This is important so that it will also match U+3000 `IDEOGRAPHIC SPACE`, which is commonly found in CJK text.
> 
> By default the predefined character class `\s` just matches ASCII whitespace while `\p{IsWhite_Space}` matches Unicode whitespace. When Unicode character class mode is enabled, it makes `\s` work just like `\p{IsWhite_Space}` as well as the corresponding ASCII to Unicode mappings for `\d`, `\w`, `\b`, and their negated versions. Unicode character class mode can be enabled with `Pattern.UNICODE_CHARACTER_CLASS` or by starting the regex with `(?U)`. All predefined character classes that were defined only with Unicode semantics are the same in either mode, like Unicode property matching using `\p{…}`.

Nova’s insightful reply left me full of questions, so I sat down with him to get some more details.

## So there are different kinds of spaces in Unicode? What’s up with that?

There are lots of different character encodings out there, and different ones have encoded characters for different types of spaces. Some of these have been for traditional typographical use such as an “em space,” which is the width of an uppercase M in the font that you’re using. Another one is the hairline space, which is extremely thin. And then in CJK (Chinese, Japanese, and Korean) languages, there’s an ideographic space, which is a square space that is the same size as the CJK characters, whether it’s hanzi in Chinese, kanji in Japanese, etc.

If you were to create a character encoding from scratch—say you were going to invent Unicode—and not care about backward compatibility with any existing encoding, you would probably just have one space that’s the whitespace character. But we do have to have compatibility with lots of historical encodings so that we can both take that encoding and transform it into Unicode and then back, or so we can represent the same characters that we formerly represented in our old encoding.

## How many different kinds of spaces are there in Unicode?

Twenty-five different characters have the `White_Space` property in Unicode 6.3. Any regular expression engine with proper [Unicode support](http://www.unicode.org/reports/tr18/) will match these and only these characters with `\s`. It can also be more explicitly matched with `\p{White_Space}` or `\p{IsWhite_Space}`, depending on the regex engine ([Perl](http://perldoc.perl.org/perluniprops.html) and [ICU4C](https://unicode-org.github.io/icu/userguide/strings/properties.html) use the former while [Java](http://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html) uses the latter).

## Do different spaces have different meanings?

Most of the spaces you’ll find are just for width or formatting. Ideally, you don’t want to perform document layout on the character level. Instead, it’s better to do that with your markup language or word processor—say, CSS if you’re using HTML—and you’d just stick with the standard space character within your text.

But there are a few space characters that have interesting rules to them, like the “non-breaking space,” which forces line breaking algorithms to not provide a break opportunity for line wrapping.

Alternately, newline characters are a form of whitespace that designate a mandatory line break.

## How do CJK languages use spaces?

In most cases, CJK languages don’t use spaces between ideographs. You’ll often see a long series of characters without any spaces. If you’re able to read the language, you’re able to determine the word boundaries. But there is no computer algorithm that can precisely detect CJK word boundaries. We have to use a hybrid approach that’s based more on a dictionary than an algorithm, and it’s never going to be perfect. The only perfect way is to sit a human down and have them read the text, which makes it difficult for us to figure out what the words are within a search query. In CJK characters, one ideograph can be a word, but also a series of multiple ideographs can be a single word. It’s a tricky problem to determine the boundaries.

## How does Unicode define a space?

In Unicode, every character has a [set of properties](http://www.unicode.org/reports/tr44/). So it’s more than just an encoding scheme for characters, it has defined metadata for every character. For example, “Is this character a symbol? A number? A separator? Is it punctuation? Or alphabetic? Or numeric?” It also has rules around the type of character—so if it’s a letter, what’s the uppercase version? What’s the lowercase version? What’s the title case version?”

With whitespace, there’s a boolean property called `White_Space`. Additionally, there’s a property called `General_Category`, and every character has a value for this property. Examples of the values are `Letter`, `Number`, `Punctuation`, `Symbol`, `Separator`, `Mark`, and `Other`. But there are also subcategories, and one of the subcategories of `Separator` is `Space_Separator`, which is given to any character which is specifically used as a space between words, as opposed to lines or paragraphs. So there are programmatic ways to determine not just, “What is whitespace?” but “How is it used?”

## How do different regular expression engines handle different kinds of spaces?

Traditionally, regex engines only understood ASCII characters, where the whitespace characters include just one space character plus the tab and newline characters. Then, regular expressions started to support Unicode. Some of them started treating all matches with Unicode semantics, so that if you’re matching on whitespace, now you would match on any Unicode whitespace (which includes ASCII whitespace).

Other ones, for backward compatibility, continue to match only on ASCII whitespace and provide a “Unicode mode” that will allow you to match on any Unicode whitespace. That’s what Java and many languages do, whereas some of the dynamic languages like [Perl](http://perldoc.perl.org/perlre.html) and [Python 3](https://docs.python.org/3/library/re.html) have upgraded to Unicode semantics by default and provide an optional “ASCII mode.”

Unfortunately, regex engines that default to ASCII semantics make it increasingly difficult to work with Unicode, because every time you want to execute a regular expression against a Unicode string, you have to put each regex in Unicode mode. In ten years, this will seem very antiquated.

## Fascinating! Thanks, Nova!
