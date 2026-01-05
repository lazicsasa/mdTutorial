# Markdown Syntax Explain

[Basic Syntax](https://www.markdownguide.org/basic-syntax/)

[Extended Syntax](https://www.markdownguide.org/extended-syntax/)

### Proba za naslov 321
---

# Markdown: Syntax

*   [Overview](#overview)
    *   [Philosophy](#philosophy)
    *   [Inline HTML](#html)
    *   [Automatic Escaping for Special Characters](#autoescape)
*   [Block Elements](#block)
    *   [Paragraphs and Line Breaks](#p)
    *   [Headers](#header)
    *   [Blockquotes](#blockquote)
    *   [Lists](#list)
    *   [Code Blocks](#precode)
    *   [Horizontal Rules](#hr)
*   [Span Elements](#span)
    *   [Links](#link)
    *   [Emphasis](#em)
    *   [Code](#code)
    *   [Images](#img)
*   [Miscellaneous](#misc)
    *   [Backslash Escapes](#backslash)
    *   [Automatic Links](#autolink)


**Note:** This document is itself written using Markdown; you
can [see the source for it by adding '.text' to the URL](/projects/markdown/syntax.text).

----

## Overview

### Philosophy

Markdown is intended to be as easy-to-read and easy-to-write as is feasible.

Readability, however, is emphasized above all else. A Markdown-formatted
document should be publishable as-is, as plain text, without looking
like it's been marked up with tags or formatting instructions. While
Markdown's syntax has been influenced by several existing text-to-HTML
filters -- including [Setext](http://docutils.sourceforge.net/mirror/setext.html), [atx](http://www.aaronsw.com/2002/atx/), [Textile](http://textism.com/tools/textile/), [reStructuredText](http://docutils.sourceforge.net/rst.html),
[Grutatext](http://www.triptico.com/software/grutatxt.html), and [EtText](http://ettext.taint.org/doc/) -- the single biggest source of
inspiration for Markdown's syntax is the format of plain text email.

## Block Elements

### Paragraphs and Line Breaks

A paragraph is simply one or more consecutive lines of text, separated
by one or more blank lines. (A blank line is any line that looks like a
blank line -- a line containing nothing but spaces or tabs is considered
blank.) Normal paragraphs should not be indented with spaces or tabs.

The implication of the "one or more consecutive lines of text" rule is
that Markdown supports "hard-wrapped" text paragraphs. This differs
significantly from most other text-to-HTML formatters (including Movable
Type's "Convert Line Breaks" option) which translate every line break
character in a paragraph into a `<br />` tag.

When you *do* want to insert a `<br />` break tag using Markdown, you
end a line with two or more spaces, then type return.

### Headers

Markdown supports two styles of headers, [Setext] [1] and [atx] [2].

Optionally, you may "close" atx-style headers. This is purely
cosmetic -- you can use this if you think it looks better. The
closing hashes don't even need to match the number of hashes
used to open the header. (The number of opening hashes
determines the header level.)

---
### Blockquotes
---
Markdown uses email-style `>` characters for blockquoting. If you're
familiar with quoting passages of text in an email message, then you
know how to create a blockquote in Markdown. It looks best if you hard
wrap the text and put a `>` before every line:

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

Markdown allows you to be lazy and only put the `>` before the first
line of a hard-wrapped paragraph:

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.

Blockquotes can be nested (i.e. a blockquote-in-a-blockquote) by
adding additional levels of `>`:

> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.

Blockquotes can contain other Markdown elements, including headers, lists,
and code blocks:

> ## This is a header.
> 
> 1.   This is the first list item.
> 2.   This is the second list item.
> 
> Here's some example code:
> 
>       return shell_exec("echo $input | $markdown_script");

Any decent text editor should make email-style quoting easy. For
example, with BBEdit, you can make a selection and choose Increase
Quote Level from the Text menu.

---

### Subscript and Superscript in Markdown file for GitHub

GitHub ne prihvata klasičan md skript za subscript i superscript, kao što je primer za VS Code ...

X^m2^

... za GitHub mora HTML kod... 

E = mc<sup>2</sup> ...ili...

H<sub>2</sub>O

moraju se koristiti `<sub> ... </sub>` ili `<sup> ... </sup>` HTML tagovi

---

### Lists

Markdown supports ordered (numbered) and unordered (bulleted) lists.

Unordered lists use asterisks, pluses, and hyphens -- interchangably
-- as list markers:

*   Red
*   Green
*   Blue

is equivalent to:

+   Red
+   Green
+   Blue

and:

-   Red
-   Green
-   Blue

Ordered lists use numbers followed by periods:

1.  Bird
2.  McHale
3.  Parish

It's important to note that the actual numbers you use to mark the
list have no effect on the HTML output Markdown produces. The HTML
Markdown produces from the above list is:

If you instead wrote the list in Markdown like this:

1.  Bird
1.  McHale
1.  Parish

or even:

3. Bird
1. McHale
8. Parish

you'd get the exact same HTML output. The point is, if you want to,
you can use ordinal numbers in your ordered Markdown lists, so that
the numbers in your source match the numbers in your published HTML.
But if you want to be lazy, you don't have to.

To make lists look nice, you can wrap items with hanging indents:

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.

But if you want to be lazy, you don't have to:

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.

List items may consist of multiple paragraphs. Each subsequent
paragraph in a list item must be indented by either 4 spaces
or one tab:

1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.

It looks nice if you indent every line of the subsequent
paragraphs, but here again, Markdown will allow you to be
lazy:

*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.

To put a blockquote within a list item, the blockquote's `>`
delimiters need to be indented:

*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.

To put a code block within a list item, the code block needs
to be indented *twice* -- 8 spaces or two tabs:

*   A list item with a code block:

        <code goes here>

### Code Blocks

Pre-formatted code blocks are used for writing about programming or
markup source code. Rather than forming normal paragraphs, the lines
of a code block are interpreted literally. Markdown wraps a code block
in both `<pre>` and `<code>` tags.

To produce a code block in Markdown, simply indent every line of the
block by at least 4 spaces or 1 tab.

This is a normal paragraph:

    This is a code block.

Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell

A code block continues until it reaches a line that is not indented
(or the end of the article).

Within a code block, ampersands (`&`) and angle brackets (`<` and `>`)
are automatically converted into HTML entities. This makes it very
easy to include example HTML source code using Markdown -- just paste
it and indent it, and Markdown will handle the hassle of encoding the
ampersands and angle brackets. For example, this:

    <div class="footer">
        &copy; 2004 Foo Corporation
    </div>

&copy; 2004 Foo Corporation

Regular Markdown syntax is not processed within code blocks. E.g.,
asterisks are just literal asterisks within a code block. This means
it's also easy to use Markdown to write about Markdown's own syntax.

```
tell application "Foo"
    beep
end tell
```

```python
def hello():
print("Hello, world!")
```
```php
$x = 26;
echo $x;
```

---

### Links

Markdown supports two style of links: *inline* and *reference*.

In both styles, the link text is delimited by [square brackets].

To create an inline link, use a set of regular parentheses immediately
after the link text's closing square bracket. Inside the parentheses,
put the URL where you want the link to point, along with an *optional*
title for the link, surrounded in quotes. For example:

This is [an example](http://example.com/) inline link.

[This link](http://example.net/) has no title attribute.

[Link u okviru fajla](#custom-id) Ovo je primenljivo za VS Code, nije za GitHub

<p style="color: red">Ovo nije primenljivo za GitHub, linkovi se pišu drugačije</p>

Pravilo za Sintaksu *linkova* u GitHub-u je da se u okviru istog fajla mogu praviti linkovi samo ka naslovima (# ## ili ###)

[link](#Manji-naslov)

[link2](#Najmanji-naslov)


Za link ka drugom fajlu i njegovom nekom naslovu moramo koristiti celu putanju do fajla kao što je u sledećem primeru, iako je fajl u istom repositorijumu...

[link3](https://github.com/lazicsasa/mdTutorial/blob/main/TEST.md#Paragraphs-and-Line-Breaks) - Otvara ga u Browser-u

Primer za link u okviru istog fajla...

### My Great Heading {#custom-id} 

<p style="color:red;">Ovakav link ne radi na GitHub-u</p>

Za GitHub je dovoljno da se link veže za neki naslov (# ## ili ###)

<p style="color:green;">Da bi se napravio <i>anchor</i> i link ka njemu </p>
...ovo je primer...

Za anchor sintaksa je kao u HTML-u ... 
`<a id="custom-anchor"></a>`
...a link se pravi...
`[Go here](#custom-anchor)`

Probano na GitHub-u - RADi!!!

---

[Link sasa](#Proba-za-naslov-321)

### Emphasis

Markdown treats asterisks (`*`) and underscores (`_`) as indicators of
emphasis. Text wrapped with one `*` or `_` will be wrapped with an
HTML `<em>` tag; double `*`'s or `_`'s will be wrapped with an HTML
`<strong>` tag. E.g., this input:

*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

### Code

To indicate a span of code, wrap it with backtick quotes (`` ` ``).
Unlike a pre-formatted code block, a code span indicates code within a
normal paragraph. For example:

Use the `printf()` function.

```php
function hdashdh() {
    $a = $b + $c;
}
```

Ovo mora da se prikaže kao kod `$ovo_ovde = 25;`

```php

echo "Tri bitne funkcije PHP-a za manipulaciju datumom su :<br>";
echo  "<li>date()</li>";
echo  "<li>time()</li>";
echo  "<li>strtotime()</li><hr>";
echo "Funkcija <i><b>time()</b></i> ispisuje vreme u sekundama od 01.01.1970. godine - <b>".time()."</b> i vraća ceo broj <br>";
$x=time(); var_dump($x);echo "<br>";
echo "Funkcija <i><b>date()</b></i> ispisuje traženi parametar - <b>".date("d-m-Y")."</b> i ona je string<br>";
$x=date("d-m-Y H:i:s"); var_dump($x);echo "<br>";
echo "Vidimo da funkcijom <i><b>date()</b></i> dobijamo zapis datuma ili vremena u string formatu koji nam je potreban<br>";

```
---


Here's a simple footnote,[^1].

Here's a simple footnote,[^2].

Here's a simple footnote,[^3].


---

| Plugin | README |
| ------ | ------ |
| Dropbox | [This link](https://lazicsasa.com/) has no title attribute. |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

---

## Images

![This is an alt text.](https://markdownlivepreview.com/image/Markdown-mark.svg "This is a sample image.")

---

First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.

~~sadadasdasd~~

---
### Task list

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

I drugi primer za ***Task***

- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item

---

I need to highlight these ==very important words==.

---


| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

---

| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

---


[Heading IDs](readme.md#heading-ids)

---
# Centriranje texta i naslova

<center>This text is centered.</center>

# <center>This naslov veći is centered.</center>

## <center>This naslov manji is centered.</center>

---

Some of these words <ins>will be underlined</ins>.

---

<p style="color: red;">This text is red!</p>

<font color="blue">This text is blue!</font>

---

## Comments

Here's a paragraph that will be visible.

[This is a comment that will be hidden.]: # 

And here's another paragraph that's visible.

---
### Ikonice u Markdown textu

Ovde su navedene neke. Opširnije ima na [linku](https://dev.to/nikolab/complete-list-of-github-markdown-emoji-markup-5aia).

> :warning: **Warning:** Do not push the big red button.

> :memo: **Note:** Sunrises are beautiful.

> :bulb: **Tip:** Remember to appreciate the little things in life.

> :blush: **Smajli:** Remember to appreciate the little things in life.

> :exclamation: **Smajli:** Remember to appreciate the little things in life.

> :question: **Smajli:** Remember to appreciate the little things in life.

> :thumbsup: **Smajli:** Remember to appreciate the little things in life.

> :point_right: **Smajli:** Remember to appreciate the little things in life.

> **Smajli:** Remember to appreciate the little things in life. :point_left:

> :speech_balloon: ***Ovo je primer za naslov*** 
> **Smajli:** Remember to appreciate the little things in life.

> :floppy_disk: **Smajli:** Remember to appreciate the little things in life.

> :computer: **Smajli:** Remember to appreciate the little things in life.

> :house: **Smajli:** Remember to appreciate the little things in life.

> :warning: **Smajli:** Remember to appreciate the little things in life.

> :zero::six::four::eight::one::two::six::five::seven::seven: **Mobilni:** Remember to appreciate the little things in life.

> :nine: **Smajli:** Remember to appreciate the little things in life.

> :mens: **Smajli:** Remember to appreciate the little things in life.

> :no_entry: **Smajli:** Remember to appreciate the little things in life.

> :no_entry_sign: **Smajli:** Remember to appreciate the little things in life.

> :a: **Smajli:** Remember to appreciate the little things in life.

> :ab: **Smajli:** Remember to appreciate the little things in life.

> :abc: **Smajli:** Remember to appreciate the little things in life.

> :clock9: **Smajli:** Remember to appreciate the little things in life.

> :heavy_check_mark: **Smajli:** Remember to appreciate the little things in life.

> :white_check_mark: **Smajli:** Remember to appreciate the little things in life.

> :copyright: **Smajli:** Remember to appreciate the little things in life.

---

### Korišćenje html i CSS tagova u .md fajlu

Dozvoljeno je korišćenje HTML i CSS tagova u Markdown fajlu i oni ih generišu kao u HTML fajlu

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #3c763d; background-color: #dff0d8; border-color: #d6e9c6;">
I am a success message
</div>

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #a94442; background-color: #f2dede; border-color: #ebccd1;">
I am an error message
</div>

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #31708f; background-color: #d9edf7; border-color: #bce8f1;">
I am a info message
</div>

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #8a6d3b;; background-color: #fcf8e3; border-color: #faebcc;">
I am a warning message
</div>

---

[Običan link ka *`lazicsasa.com`*](https://lazicsasa.com/)

---

### Ignoring Markdown formatting

You can tell GitHub to ignore (or escape) Markdown formatting by using \ before the Markdown character.

Let's rename \*our-new-project\* to \*our-old-project\*.

---

## Writing mathematical expressions

Use Markdown to display mathematical expressions on GitHub.
Who can use this feature?

There are two options for delimiting a math expression inline with your text. You can either surround the expression with dollar symbols ($), or start the expression with $` and end it with `$. The latter syntax is useful when the expression you are writing contains characters that overlap with markdown syntax. For more information, see Basic writing and formatting syntax.

$\sqrt{3x-1}+(1+x)^2$

Screenshot of rendered Markdown showing an inline mathematical expression: the square root of 3x minus 1 plus (1 plus x) squared.

$\sqrt{3x-1}+(1+x)^2$

Screenshot of rendered Markdown showing an inline mathematical expression with backtick syntax: the square root of 3x minus 1 plus (1 plus x) squared.
Writing expressions as blocks

To add a math expression as a block, start a new line and delimit the expression with two dollar symbols $$.

Tip

If you're writing in an .md file, you will need to use specific formatting to create a line break, such as ending the line with a backslash as shown in the example below. For more information on line breaks in Markdown, see Basic writing and formatting syntax.

**The Cauchy-Schwarz Inequality**\
$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

Screenshot of rendered Markdown showing a complex equation. Bold text reads "The Cauchy-Schwarz Inequality" above the formula for the inequality.

Alternatively, you can use the ```math code block syntax to display a math expression as a block. With this syntax, you don't need to use $$ delimiters. The following will render the same as above:

**The Cauchy-Schwarz Inequality**

```math
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
```

Writing dollar signs in line with and within mathematical expressions

To display a dollar sign as a character in the same line as a mathematical expression, you need to escape the non-delimiter $ to ensure the line renders correctly.

Within a math expression, add a \ symbol before the explicit $.

This expression uses `\$` to display a dollar sign: $`\sqrt{\$4}`$

Screenshot of rendered Markdown showing how a backslash before a dollar sign displays the sign as part of a mathematical expression.

Outside a math expression, but on the same line, use span tags around the explicit $.

To split \$100 in half, we calculate $100/2$

---




---


[^1]: This is the first footnote.

[^2]: This is the second footnote.
Ova fusnota može biti u više redova
Ne može sadržati neki kod, nego samo tekst ***jebi ga***

[^3]: This is the five footnote.



