> [!TIP]
> Explore the module on [Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/communicate-using-markdown/).

Context Menu:
- [Introduction](#introduction)
- [Featured Resouces](#featured-resouces)
- [Key Takeways](#key-takeaways)
    - [Headings](#headings)
    - [Text Styles](#text-styles)
        - [Basic Style](#basic-styles-and-patterns)
        - [Text Quoting Block](#text-quotingblock)
        - [Code Quote](#quoting-codes)
    - [Lists](#lists)
        - [Basic Lists](#ordered-and-unordered-list)
        - [Task Boxes](#task-box-gfm-only-effecive-in-github-web)
    - [Links](#links)
        - [Basic Links](#inline-link-and-reference-link)
        - [Footnote](#footnote)


# Introduction
Markdown is a lightweight markup language for creating formatted text using a plain-text editor.

Details can follow https://en.wikipedia.org/wiki/Markdown

# Featured Resouces

Top Recommended:
- [Simple Markdown Cheetsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Ulitmate Markdown Cheetsheet](https://github.com/lifeparticle/Markdown-Cheatsheet)
- [Awesome MarkDown - Full collection details](https://github.com/mundimark/awesome-markdown)

Chinese Resouces:
- [MarkDown CN](https://markdown.com.cn/)
- [USTC MarkDown Guidance Chinese Simplified](https://soc.ustc.edu.cn/CODH/other/markdown/)

Try and Learn:
- [MarkDown Tutorial](https://www.markdowntutorial.com/)

Documents:
- [Original Markdown Documement](https://daringfireball.net/projects/markdown/syntax)
- [GitHub Flavored MarkDown(GFM)](https://github.github.com/gfm/)


# Key Takeaways
## Headings
``` MarkDown 
# heading 1
## heading 2
### heading 3
...
###### heading 6
```

``` MarkDown 
heading 1
=
heading 2
-
```

## Text Styles

### Basic Styles and patterns
``` MarkDown
Normal:
<br>
the normal text example

Bold:
<br>
**the bold text example 1**
__the bold text example 2__

Italic:
<br>
The *Italic* text Example 1
the _Italic_ text example 2

Both Bold and Italic:
<br>
the both ***Bold and Italic*** example 1
the both **_Bold and Italic**_ example 2

Strike Through:
<br>
The ~~Strike Through Text~~
The <strike>Strike Through Text</strike>

Underlined:
<br>
text with <ins>underlied</ins>

```
How above code looks like:

Normal:
<br>
the normal text example

Bold:
<br>
**the bold text example 1**
__the bold text example 2__

Italic:
<br>
The *Italic* text Example 1
the _Italic_ text example 2

Both Bold and Italic:
<br>
the both ***Bold and Italic*** example 1
the both **_Bold and Italic**_ example 2

Strike Through:
<br>
The ~~Strike Through Text~~
The <strike>Strike Through Text</strike>

Underlined:
<br>
text with <ins>underlied</ins>

### Text Quoting(Block)

```MarkDown
> this is a text quoting example

<br>

> this is a text quoting example with multiple lines
>
> line 2
>
> line 3

<br>

> This is a text quoting with different depth
>> depth 2
>>> depth 3

<br>

> This is a text quoting with **Bold Text** and *Italic Text*
```

> this is a text quoting example

<br>

> this is a text quoting example with multiple lines
>
> line 2
>
> line 3

<br>

> This is a text quoting with different depth
>> depth 2
>>> depth 3

<br>

> This is a text quoting with **Bold Text** and *Italic Text*

### Quoting Codes

more GitHub progamming languages Codes please find [here](https://github.com/github-linguist/linguist/tree/main/vendor)
```
`return this.count`


``` Java
public static voild getCount
{
    return this.count;
}
```

`return this.count`


``` Java
public static voild getCount
{
    return this.count;
}
```

## Lists
### Ordered and Unordered List
``` Markdown
1. first
2. second
3. third
```
1. first
2. second
3. third

``` Markdown
* Unordered list item 1
* Unordered list item 2
* Unordered List item 3

- Unordered list item 1
- Unordered list item 2
- Unordered List item 3

+ Unordered list item 1
+ Unordered list item 2
+ Unordered List item 3
```
* Unordered list item 1
* Unordered list item 2
* Unordered List item 3

- Unordered list item 1
- Unordered list item 2
- Unordered List item 3

+ Unordered list item 1
+ Unordered list item 2
+ Unordered List item 3

Multi level 
``` MarkDown
1. First Section 
  1. first item
    * item
    * item
        * sub item
2. Second Section
  1. 2.1
    * 2.1 item

```
1. First Section 
    1. first item
    * item
    * item
        * sub item
2. Second Section
    1. 2.1
        * 2.1 item

## Task Box (GFM only effecive in GitHub web)
``` Markdown
- [x] task 1
- [ ] task 2
- [ ] task 3
```
- [x] task 1
- [ ] task 2
- [ ] task 3

## Links

### Inline Link and Reference Link
``` Markdown
[This is a basic Google Link](www.google.com)

[Use Headings Introduction](#introduction)

[Use Reference Google Link][use reference link]

[use reference link]

[reference link using 1][1]

[I'm a relative reference to a repository file](../../README.md)

[use reference link]: www.google.com
[1]: www.google.com

```
[This is a basic Google Link](www.google.com)

[Use Headings Introduction](#introduction)

[Use Reference Google Link][use reference link]

[use reference link]

[reference link using 1][1]

[I'm a relative reference to a repository file](../../README.md)

[use reference link]: www.google.com
[1]: www.google.com

### Footnote
Only supported in [GRM](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#footnotes)
```
Footnote Example.[^1]

Another Footnote.[^2]

[^1]: this is the first footnote.

[^2]: This is the second footnote.
```

Footnote Example.[^1]

Another Footnote.[^2]

[^1]: this is the first footnote.

[^2]: This is the second footnote.

### Badges
![GitHub forks](https://img.shields.io/github/forks/lifeparticle/Markdown-Cheatsheet?style=for-the-badge)




