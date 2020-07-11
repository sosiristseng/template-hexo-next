---
title: Basic Markdown syntax 
date: 2020-06-29 16:47:33
tags: ["markdown"]
categories: ["Hexo"]
---

This post showcases the basic Markdown syntax you'll see in major Markdown editors.

Some are taken from [Grav](http://learn.getgrav.org/content/markdown), [Hugo LoveIt theme](https://hugoloveit.com/basic-markdown-syntax/) documentation.

<!-- more -->

## Headings

{% note default %}
```markdown
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading
```
{% endnote %}

## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading

## Inline HTML

You can simply use HTML If you need a certain HTML tag or html comments.

{% note default %}
```html
Paragraph in Markdown.

<div class="class">
    This is <b>HTML</b>
</div>

Paragraph in Markdown.

<!--
This is a comment, you should not see me
-->

```
{% endnote %}


Paragraph in Markdown.

<div class="class">
    This is <b>HTML</b>
</div>

Paragraph in Markdown.

<!--
This is a comment, you should not see me
-->

## Horizontal Rules

{% note default %}
```markdown
---
```
{% endnote %}

---

## Emphasis

Bold, italics, and strikethrough can be used either indivisually or in combination.

{% note default %}
```markdown
**rendered as bold text**

__rendered as bold text__

*rendered as italicized text*

_rendered as italicized text_

~~Strike through this text~~
```
{% endnote %}

**rendered as bold text**

__rendered as bold text__

*rendered as italicized text*

_rendered as italicized text_

~~Strike through this text~~

## Blockquotes

{% note default %}
```markdown
> **Fusion Drive** combines a hard drive with a flash storage (solid-state drive) and presents it as a single logical volume with the space of both drives combined.

> One
> Two
```
{% endnote %}


> **Fusion Drive** combines a hard drive with a flash storage (solid-state drive) and presents it as a single logical volume with the space of both drives combined.

Multiline quotes

> One
> Two

## Lists

### Unordered

{% note default %}
```markdown
* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem
```
{% endnote %}

* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem

### Ordered

:bulb: If you just use 1. for each number, Markdown will automatically number each item.

{% note default %}
```markdown
1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem
```
{% endnote %}

1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem

## Markdown Code blocks 

* Inline code: `` `code here` ``.
* Block fenced code start with `` ```type `` and end with `` ``` ``. Syntax highlighting is enabled.

## Tables

:bulb: See [tables generator](https://www.tablesgenerator.com/markdown_tables) for easier inserting tables to your Markdown document.

{% note default %}
```markdown
| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```
{% endnote %}

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |


## Links

{% note default %}
```makrdown
<https://assemble.io>
<contact@revolunet.com>
[Assemble](https://assemble.io)
[Upstage](https://github.com/upstage/ "Visit Upstage!")
```
{% endnote %}

<https://assemble.io>
<contact@revolunet.com>
[Assemble](https://assemble.io)
[Upstage](https://github.com/upstage/ "Visit Upstage!")

## Footnotes

:bulb: Footnotes are automatically numbered.

{% note default %}
```markdown
This is a digital footnote[^1].
This is a footnote with "label"[^label]

[^1]: This is a digital footnote
[^label]: This is a footnote with "label"
```
{% endnote %}

This is a digital footnote[^1]
This is a footnote with "label"[^label]

[^1]: This is a digital footnote
[^label]: This is a footnote with "label"

## Keyboard strokes

[markdown-it-kbd](https://www.npmjs.com/package/markdown-it-kbd) is needed.

{% note default %}
```markdown
[[Ctrl]] + [[Alt]] + [[Delete]]
```
{% endnote %}

[[Ctrl]] + [[Alt]] + [[Delete]]


## Images Markdown syntax

{% note default %}
```markdown
![Minion](https://octodex.github.com/images/minion.png)
![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")
```
{% endnote %}

![Minion](https://octodex.github.com/images/minion.png)
![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

It is actually easier to use absolute paths than relative ones in Hexo. 

You could [attach](https://docs.github.com/en/github/managing-your-work-on-github/file-attachments-on-issues-and-pull-requests) images or documents to GitHub issues for free hosting.

## MathJax rendering

See {% post_link md-math "math rendering" %}.

## Emojis

See {% post_link emoji "emoji" %}.
