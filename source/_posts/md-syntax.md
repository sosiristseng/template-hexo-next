---
title: Markdown syntax 
date: 2020-06-29 16:47:33
tags: ["markdown"]
categories: ["Hexo"]
---

This page showcases the Markdown syntax and extensions by tag plugins available to Hexo Next theme. 

Some are taken from [Grav](http://learn.getgrav.org/content/markdown), [Hugo LoveIt theme](https://hugoloveit.com/basic-markdown-syntax/), Hexo, and the Next theme [documentation](https://theme-next.js.org)

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

## Inline HTML

If you need a certain HTML tag or comments you can simply use HTML:

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

## Quotes

### Blockquotes

{% note default %}
```markdown
> **Fusion Drive** combines a hard drive with a flash storage (solid-state drive) and presents it as a single logical volume with the space of both drives combined.

> One
> Two
```
{% endnote %}


> **Fusion Drive** combines a hard drive with a flash storage (solid-state drive) and presents it as a single logical volume with the space of both drives combined.

> One
> Two

### Centered Quote

{% note default %}
```markdown
{% centerquote %}Something{% endcenterquote %}
<!-- Or in short -->
{% cq %}Something{% endcq %}
```
{% endnote %}

{% cq %}Elegant in code, simple in core{% endcq %}

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


## Code blocks

### Regular markdown

* Inline code: `` `code here` ``.
* Block fenced code start with `` ```type `` and end with `` ``` ``. Syntax highlighting is enabled.

### Hexo tag plugin

{% note default %}
```markdown
{% codeblock [title] [lang:language] [url] [link text] [additional options] %}
code snippet
{% endcodeblock %}
```

```markdown
{% codeblock _.compact lang:javascript http://underscorejs.org/#compact Underscore.js %}
_.compact([0, 1, false, 2, '', 3]);
=> [1, 2, 3]
{% endcodeblock %}
```
{% endnote %}

{% codeblock _.compact lang:javascript http://underscorejs.org/#compact Underscore.js %}
_.compact([0, 1, false, 2, '', 3]);
=> [1, 2, 3]
{% endcodeblock %}

### Github gist

{% note default %}
```markdown
{% gist sosiristseng/5406c151b54ed182bf8e57e1a2a4c57e %}
```
{% endnote %}

{% gist sosiristseng/5406c151b54ed182bf8e57e1a2a4c57e %}

### Include code

The directory containing code is defined at `code_dir` option in `_config.yml`, default to `downloads/code`, corresponding to `source/downloads/code`

{% note default %}
```markdown
{% include_code [title] [lang:language] [from:line] [to:line] path/to/file %}
```

```markdown
{% include_code lang:bash bootstrap-conda.sh %}
```
{% endnote %}

{% include_code lang:bash bootstrap-conda.sh %}

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

### Link to other post

Insert reference link to other posts regardless the permalink. Not working in local server.

[See Include-Posts Tag plugin](https://hexo.io/docs/tag-plugins#Include-Posts).

{% note default %}
```markdown
{% post_link filename [title] [escape]  %}
```

```markdown
{% post_link emoji "Emoji support" %}
```
{% endnote %}

{% post_link emoji %}

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

## Emojis

See {% post_link emoji "this post" %} 

## Images

### Basic Markdown syntax

{% note default %}
```markdown
![Minion](https://octodex.github.com/images/minion.png)
![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")
```
{% endnote %}

![Minion](https://octodex.github.com/images/minion.png)
![Alt text](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

It's simplier to use absolute paths than relative ones in Hexo. 

You could [attach](https://docs.github.com/en/github/managing-your-work-on-github/file-attachments-on-issues-and-pull-requests) images or documents to GitHub issues for free hosting.

## Videos

### URL

{% note default %}
```markdown
{% video url %}

{% video https://upload.wikimedia.org/wikipedia/commons/transcoded/c/c4/Physicsworks.ogv/Physicsworks.ogv.240p.vp9.webm %}
```
{% endnote %}

{% video https://upload.wikimedia.org/wikipedia/commons/transcoded/c/c4/Physicsworks.ogv/Physicsworks.ogv.240p.vp9.webm %}

### YouTube videos

{% note default %}
```markdown
{% youtube JtUAAXe_0VI %}
```
{% endnote %}

{% youtube JtUAAXe_0VI %}

### Vimeo

{% note default %}
```markdown
{% vimeo 63830488 %}
```
{% endnote %}

{% vimeo 63830488 %}

## PDF files

[Next theme docs: PDF](https://theme-next.js.org/docs/tag-plugins/pdf.html). 

{% note default %}
In `next.yml`
```yaml
pdf:
  enable: true
  height: 500px  # Default height
```
{% endnote %}

{% note default %}
```markdown
{% pdf http://www.africau.edu/images/default/sample.pdf 700px %}
```
{% endnote %}

{% pdf http://www.africau.edu/images/default/sample.pdf 700px %}

{% note warning %}
1. Only browsers supporting PDF embedding are supported.
2. PDF file loading may be block by [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) policy.
{% endnote %}

## Documents iframe

View your documents inline by [embedding](https://gist.github.com/tzmartin/1cf85dc3d975f94cfddc04bc0dd399be) the Google Docs Viewer into `iframe`.

{% note default %}
```markdown
{% iframe https://docs.google.com/viewer?url=FILEPATH&embedded=true [width] [height] %}
```
{% endnote %}


For example, 
```markdown
{% iframe "https://docs.google.com/viewer?url=https://gitlab.com/sosiristseng/sosiristseng.gitlab.io/uploads/55f69d2020662c7900269c2c9c4f6a40/file_example_PPT_250kB.ppt&embedded=true" %}
```

{% iframe "https://docs.google.com/viewer?url=https://gitlab.com/sosiristseng/sosiristseng.gitlab.io/uploads/55f69d2020662c7900269c2c9c4f6a40/file_example_PPT_250kB.ppt&embedded=true" %}


## Note

[Next theme: Notes](https://theme-next.js.org/docs/tag-plugins/note.html). 

Similar to [admonition](https://hugoloveit.com/theme-documentation-extended-shortcodes/#4-admonition) in Hugo LoveIt.

Related settings in `next.yml`.

```yml
# Note tag (bs-callout)
note:
  # Note tag style values:
  #  - simple    bs-callout old alert style. Default.
  #  - modern    bs-callout new (v2-v3) alert style.
  #  - flat      flat callout style with background, like on Mozilla or StackOverflow.
  #  - disabled  disable all CSS styles import of note tag.
  style: simple
  icons: true
  # Offset lighter of background in % for modern and flat styles (modern: -12 | 12; flat: -18 | 6).
  # Offset also applied to label tag variables. This option can work with disabled note tag.
  light_bg_offset: 0
```

{% note default %}

```markdown
{% note %}
### Header
(without define class style)
{% endnote %}

{% note default %}
### Default Header
Welcome to [Hexo!](https://hexo.io)
{% endnote %}

{% note primary %}
### Primary Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note info %}
### Info Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note success %}
### Success Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note warning %}
### Warning Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note danger %}
### Danger Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note info no-icon %}
### No icon note
Note **without** icon: `note info no-icon`

note info, note info, note info
note info, note info, note info
note info, note info, note info
{% endnote %}

{% note success %}
### Codeblock in note
{% code %}
code block in note tag
code block in note tag
code block in note tag
{% endcode %}
{% endnote %}

{% note default %}
### Table in Note
| 1 | 2 |
| - | - |
| 3 | 4 |
| 5 | 6 |
| 7 | 8 |
{% endnote %}

```
{% endnote %}

{% note %}
### Header
(without define class style)
{% endnote %}

{% note default %}
### Default Header
Welcome to [Hexo!](https://hexo.io)
{% endnote %}

{% note primary %}
### Primary Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note info %}
### Info Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note success %}
### Success Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note warning %}
### Warning Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note danger %}
### Danger Header
**Welcome** to [Hexo!](https://hexo.io)
{% endnote %}

{% note info no-icon %}
### No icon note
Note **without** icon: `note info no-icon`

note info, note info, note info
note info, note info, note info
note info, note info, note info
{% endnote %}

{% note success %}
### Codeblock in note
{% code %}
code block in note tag
code block in note tag
code block in note tag
{% endcode %}
{% endnote %}

{% note default %}
### Table in Note
| 1 | 2 |
| - | - |
| 3 | 4 |
| 5 | 6 |
| 7 | 8 |
{% endnote %}

## Tabs

[Hexo Next: Tags](https://theme-next.js.org/docs/tag-plugins/tabs.html)

{% note default %}
```markdown
{% tabs Sixth Unique name %}
<!-- tab Solution 1@text-width -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab Solution 2 @font -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab Solution 3@bold -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```
{% endnote %}

{% tabs Sixth Unique name %}
<!-- tab Solution 1@text-width -->
**This is Tab 1.**
<!-- endtab -->

<!-- tab Solution 2 @font -->
**This is Tab 2.**
<!-- endtab -->

<!-- tab Solution 3@bold -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}

Define a tab via `<!-- tab title @icon --> ... <!-- endtab -->`. Both `title` and `font` are optional.

## Label

[Hexo Next: Labels](https://theme-next.js.org/docs/tag-plugins/label.html)

{% note default %}

```markdown
Lorem {% label @ipsum %} {% label primary@dolor sit %} amet, consectetur {% label success@adipiscing elit, %} sed {% label info@do eiusmod %} tempor incididunt ut labore et dolore magna aliqua.

Ut enim *{% label warning @ad %}* minim veniam, quis **{% label danger@nostrud %}** exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate ~~{% label default @velit %}~~ <mark>esse</mark> cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```
{% endnote %}

Lorem {% label @ipsum %} {% label primary@dolor sit %} amet, consectetur {% label success@adipiscing elit, %} sed {% label info@do eiusmod %} tempor incididunt ut labore et dolore magna aliqua.

Ut enim *{% label warning @ad %}* minim veniam, quis **{% label danger@nostrud %}** exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate ~~{% label default @velit %}~~ <mark>esse</mark> cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Button

[Hexo Next: Buttons](https://theme-next.js.org/docs/tag-plugins/button.html)

{% note default %}
```markdown
{% btn #, Text %}{% btn #, Text & Title,, Title %}

<!-- with icon -->

<div>{% btn #,, home %}{% btn #,, home %}{% btn #,, home %}</div>

<p>{% btn #, Text & Icon (buggy), home %}
{% btn #, Text & Icon (fixed width), home fa-fw %}</p>

```
{% endnote %}


{% btn #, Text %}{% btn #, Text & Title,, Title %}


<div>{% btn #,, home %}{% btn #,, home %}{% btn #,, home %}</div>

<p>{% btn #, Text & Icon (buggy), home %}
{% btn #, Text & Icon (fixed width), home fa-fw %}</p>


## Link Grid

[Hexo Next: Link grid](https://theme-next.js.org/docs/tag-plugins/link-grid.html)

{% note default %}
```markdown
{% linkgrid %}
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
% Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
{% endlinkgrid %}
```
{% endnote %}

{% linkgrid %}
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
% Theme NexT | https://theme-next.js.org/ | Stay Simple. Stay NexT. | /images/apple-touch-icon-next.png
{% endlinkgrid %}

## MathJax rendering

See {% post_link md-math "math rendering" %} 

## Others

* [Group Pictures](https://theme-next.js.org/docs/tag-plugins/group-pictures.html)
