### Linkovi - Web Tutorijali za Markdown syntax

[Basic Syntax](https://www.markdownguide.org/basic-syntax/)

[Extended Syntax](https://www.markdownguide.org/extended-syntax/)

---

## Naslovi


```
# Naslov1
```
```
## Naslov2
```
```
### Naslov3
```
```
#### Naslov4
```
```
##### Naslov5
```

---
## Paragraf
Za novi paragraf koristiti prazan red.
Ako nema praznog reda tekst se nastavlja u istom paragrafu.

Ovaj tekst je u novom paragrafu

<p style="color:red">Kolor za paragraf je moguć u nekim editorima (kao što je VS Code), dok je u GitHub-u onemogućen CSS kod zbog sigurnosti, pa tako promena boje teksta nije moguća.</p>

Primer za ***promenu boje teksta za VS Code***
```
<p style="color:red">Text</p>
```
GitHub nedozvoljava upotrebu CSS tagova, ali možemo koristiti HTML tagove u md fajlovima, za prikaz *bold/italic* teksta, za prelazak u sledeći red `<br>`, za prikaz linije u dokumentu `<hr>` 
Primer...
`<b><i>Text bold/italic - HTML tag</b></i>`

`<b>Proba za BOLD teksta</b><br>`

Osim HTML tagova za bold ili italic prikaz teksta možemo koristiti i md syntax...

BOLD - `**Primer teksta**` **Primer teksta**

ITALIC - `*Primer teksta*` *Primer teksta*

BOLD/ITALIC - `***Primer teksta***` ***Primer teksta***

Za *underline* sintaksa je...
`Some of these words <ins>will be underlined</ins>.`
Some of these words <ins>will be underlined</ins>.

---

## Blokovi teksta
Da bi se kreirali vidljivi blokovi teksta postavlja se znak `>` ispred paragrafa.
Blokovi mogu biti višelinijski ili mogu imati više paragrafa. Primeri...

**Sintaksa za jednoredni blok**
```
>Ovde_ide_sadržaj_jednorednog_bloka
```
>Ovde_ide_sadržaj_jednorednog_bloka

**Sintaksa za višerednog bloka - jedan paragraf**
```
>Ovde_ide_sadržaj_prvog_reda
>Ovde_ide_sadržaj_drugog_reda
```
>Ovde_ide_sadržaj_prvog_reda
>Ovde_ide_sadržaj_drugog_reda

**Sintaksa za blok sa više paragrafa**
```
>Ovde_ide_sadržaj_prvog_reda
>
>Ovde_ide_sadržaj_drugog_reda
```
>Ovde_ide_sadržaj_prvog_paragrafa
>
>Ovde_ide_sadržaj_drugog_paragrafa

Blokovi mogu sadržati i druge elemente (naslove, liste, tabele, druge ugnežđene blokove,...)

---

## Liste

Liste u md fajlovima mogu biti sredjene (redni brojevi) ili nesredjene 

**Sintaksa za sredjene liste**
```
1. Item 1
2. Item 2
3. Item 3
4. Item 4
```
1. Item 1
2. Item 2
3. Item 3
4. Item 4

>Za sredjene liste koristimo brojeve `1, 2, 3, 4, ...`

**Sintaksa za nesredjene liste** 

Za nesredjene liste koristimo znakove `-, +, *`

```
* Item 1
* Item 2
* Item 3
* Item 4
```
* Item 1
* Item 2
* Item 3
* Item 4

Nesredjene liste mogu biti ugneždjene kada ih uvlačimo sa `tab`

```
* Item 1
* Item 2
    * Item 3
    * Item 3
* Item 3
* Item 4
```
* Item 1
* Item 2
    * Item 3
    * Item 3
* Item 3
* Item 4

---

## Slike

Sintaksa za prikaz slika u md fajlovima...
```
![nazivFajla](images/file.png "Tekst koji se pojavljuje prelaskom kursora miša")
```
![nazivFajla](images/github.png "Tekst koji se pojavljuje prelaskom kursora miša")

Slike se mogu setovati i HTML kodom kada možemo setovati i veličinu slike...
>`<img src="image.png" width="200" height="100">`

<img src="images/github.png" width="200" height="100"><br>

<img src="images/github.png" width="100">
<img src="images/github.png" width="150">
<img src="images/github.png" width="200">
 
---
## Linkovi
Sintaksa za linkove u md fajlovima...
*[Tekst linka](URL Adresa)*
```
[clickMe](https://lazicsasa.com)
```
[clickMe](https://lazicsasa.com "Tekst koji se pojavljuje kada se postavi kursor miša")

U VS Code i drugim editorima koji mogu prikazati md fajlove dozvoljeno je koristiti html tagove za linkove. GitHub sanetizuje iz sigurnosnih razloga neke HTML tagove (target, onclick, style, etc.) tako da ih ignoriše i ne možemo ih koristiti za md fajlove u GitHub-u. Bilo je već reči za text color.

#### Anchor Linkovi - Linkovi ka naslovu

Osim spoljnih adresa (van md fajla) možemo praviti linkove ka pointu (anchor) u okviru istog fajla ili nekog drugog fajla, ali i ovde GitHub pravi ograničenja, što ćemo kasnije objasniti. 
Sintaksa za *Anchor Link* md fajlova je...
```
[clickMe for link on Anchor](#anchorID)
``` 
[clickMe for link on Anchor](#anchorID) ... gde se *anchorID* obeležava u md fajlu sintaksom...
```
## Neki naslov {#anchorID}
```
Anchor Linkovi u okviru istog fajla ili drugog se mogu praviti samo na naslove. Za VS Code (provereno) se koristi *Anchor*, dok u GitHub-u nije potrebno pored naslova kreirati *Anchor* već je dovoljno samo navesti naslov. Prazna mesta se popunjavaju sa ` - `, kao u sledećem primeru...
```
[clickMe](#Naslov-sa-vise-reci)
```
Za AnchorLink ka naslovu drugog fajla potrebno je (za GitHub) navesti punu URL adresu sa nazivom fajla i dodati bez razmaka `#Naslov-za-link`
```
[clickMe](https://github.com/lazicsasa/mdTutorial/blob/main/README.md#mdTutorijal)
```
[clickMe](https://github.com/lazicsasa/mdTutorial/blob/main/README.md#mdTutorijal)

Ipak, osim ka naslovima možemo HTML tagom **`<a id="custom-anchor"></a>`** napraviti *Anchor* i usmeriti Link na njega, bilo gde u fajlu ili u nekom drugom fajlu... 
**`[Go here](#custom-anchor)`**

Isto tako možemo kreirati link ka Anchor-u u drugom fajlu ... primer...
`[Go here](https://github.com/lazicsasa/mdTutorial/blob/main/README.md#custom-anchor)`
[Go here](https://github.com/lazicsasa/mdTutorial/blob/main/README.md#custom-anchor)

> *Dobra praksa za GitHub je da se piše cela URL adresa.*

#### Slika kao pointer za Link
U md fajlu možemo koristiti sliku kao pointer za Link. Sintaksa je...
```
[![GitHub Logo](images/github.jpg)](https://lazicsasa.com)
```
[![GitHub Logo](images/github.png)](https://lazicsasa.com)

---

## Blokovi koda
Razlikuje se sintaksa md fajlova za VS Code i GitHub za pisanje blokova koda
Za VS Code dovoljno je kod uvući za 4 mesta (ili 1 tab).

Najbolja praksa za sve je korišćenje znaka `` ` `` za *inline* ispis koda, a za blok koda koriste se 3 znaka `` ``` `` ...

![blok koda](images/blok_koda_primer.png)

```php
$x = 32;
echo $x;
```
Poželjno je navesti programski jezik za koji se kod odnosi zbog boljeg izgleda bloka koda, ali nije obavezno. Dobra je stvar što GitHub na bloku koda automatski generiše *Copy* ikonicu što olakšava kopiranje bloka koda. 

---

## Subscript and Superscript

GitHub ne prihvata klasičan md skript za subscript i superscript, kao što je primer za VS Code ...

X^m2^

... za GitHub mora HTML kod... 

E = mc<sup>2</sup> ...ili...

H<sub>2</sub>O

moraju se koristiti `<sub> ... </sub>` ili `<sup> ... </sup>` HTML tagovi

---

## Tabele
Da bi se formirala tabela u md fajlovima (važi i za GitHub) potrebno je odvojiti kolone sa uspravnim znakom ` | ` i koristiti 3 ili više crtica ` ----- ` u drugom redu tabela. Primer...
| Naslov1     | Naslov2     |
| ----------- | ----------- |
| Text        | Text        |
| Text        | Text        |
| Text        | Text        |

Za pozicioniranje sadržaja u polju kolone koristimo znak ` : ` levo-desno-obe strane, po potrebi...
```
| Naslov1     | Naslov2     | Naslov 3    |
| :---------- | :---------: | ----------: |
| Text        | Text        | Text        |
| Text        | Text        | Text        |
| Text        | Text        | Text        |
| Text        | Text        | Text        |
```

| Naslov1     | Naslov2     | Naslov 3    |
| :---------- | :---------: | ----------: |
| Text        | Text        | Text        |
| Text        | Text        | Text        |
| Text        | Text        | Text        |
| Text        | Text        | Text        |



---

## Specijalni karakteri

Korišćenje HTML specijalnih karaktera u md fajlovima...
Primer `&copy; 2004 Foo Corporation` - &copy; 2004 Foo Corporation

Ostali specijalni karakteri...

| Sintaksa   | Znak     | Opis         |
| :---:      |  :----:  | :---         |
| `&copy;`   | &copy;   | Copyright    |
| `&reg;`    | &reg;    | Registered   |
| `&trade;`  | &trade;  | Trademark    |
| `&sect;`   | &sect;   | Section      |
| `&para;`   | &para;   | Paragraph    |
| `&euro;`   | &euro;   | Euro         |
| `&dollar;` | &dollar; | Dollar       |
| `&pound;`  | &pound;  | Pound        |
| `&yen;`    | &yen;    | Yen          |
| `&cent;`   | &cent;   | Cent         |
| `&frac14;` | &frac14; | Math         |
| `&frac12;` | &frac12; | Math         |
| `&frac34;` | &frac34; | Math         |
| `&le;`     | &le;     | Math         |
| `&ge;`     | &ge;     | Math         |
| `&ne;`     | &ne;     | Math         |
| `&asymp;`  | &asymp;  | Math         |
| `&infin;`  | &infin;  | Math         |
| `&plusmn;` | &plusmn; | Math         |
| `&radic;`  | &radic;  | Math         |
| `&sum;`    | &sum;    | Math         |
| `&check;`  | &check;  | Checkmark    |
| `&cross;`  | &cross;  | Checkmark    |
| `&bull;`   | &bull;   | Checkmark    |
| `&starf;`  | &starf;  | Checkmark    |
| `&star;`   | &star;   | Checkmark    |
| `&alpha;`  | &alpha;  | Greek letter |
| `&beta;`   | &beta;   | Greek letter |
| `&gamma;`  | &gamma;  | Greek letter |
| `&delta;`  | &delta;  | Greek letter |
| `&theta;`  | &theta;  | Greek letter |
| `&lambda;` | &lambda; | Greek letter |
| `&pi;`     | &pi;     | Greek letter |
| `&sigma;`  | &sigma;  | Greek letter |
| `&omega;`  | &omega;  | Greek letter |
| `&larr;`   | &larr;   | Arrow        |
| `&rarr;`   | &rarr;   | Arrow        |
| `&uarr;`   | &uarr;   | Arrow        |
| `&darr;`   | &darr;   | Arrow        |
| `&harr;`   | &harr;   | Arrow        |
| `&rArr;`   | &rArr;   | Arrow        |
| `&lArr;`   | &lArr;   | Arrow        |
| `x<sup>2</sup>`   | x<sup>2</sup>    | Superscript  |
| `H<sub>2</sub>O`  | H<sub>2</sub>O   | Subscript    |

---

## Fusnote





Here's a simple footnote,[^1].

Here's a simple footnote,[^2].

Here's a simple footnote,[^3].


---

## Task liste
<!-- NOTE Objašnjenje za pravljenje task liste i komentar da se ne koriste često -->

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

## Komentari
<!--NOTE Objasniti da se mogu pisati komentari kao u HTML tekstu ili u primeru ispod (md sintaksa) -->

Here's a paragraph that will be visible.

[This is a comment that will be hidden.]: #

And here's another paragraph that's visible.

---
### Ikonice u Markdown textu
<!-- NOTE Ikonice prebaciti u tabelu zbog sintakse i izgleda ikonice -->

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





## Writing mathematical expressions
<!-- NOTE Videti za matematičke formule koliko da se opiše i postavi u tutorijalu. Ovo ostaviti za kraj, nije relevantno toliko -->


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






[^1]: This is the first footnote.

[^2]: This is the second footnote.
Ova fusnota može biti u više redova
Ne može sadržati neki kod, nego samo tekst ***jebi ga***

[^3]: This is the five footnote.



