---
title: Extended Markdown syntax 
date: 2020-06-29 17:47:33
tags: ["markdown"]
categories: ["Hexo"]
---

This post shows tag plugins available to Hexo Next theme. Take from the Next theme [documentation](https://theme-next.js.org)

<!-- more -->

## Quotes

### Centered Quote

From [Hexo Next](https://theme-next.js.org/docs/tag-plugins/#Centered-Quote)

{% note default %}
```markdown
{% centerquote %}Something{% endcenterquote %}
<!-- Or in short -->
{% cq %}Something{% endcq %}
```
{% endnote %}

{% cq %}Elegant in code, simple in core{% endcq %}

### Pull Quote

From [Hexo](https://hexo.io/docs/tag-plugins.html#Pull-Quote)

Rendered the as the regular markdown quote.

{% note default %}
```markdown
{% pullquote %}
content
{% endpullquote %}
```
{% endnote %}

{% pullquote %}
content
{% endpullquote %}

### Block Quote

From [Hexo](https://hexo.io/docs/tag-plugins.html#Block-Quote)

{% note default %}
```markdown
{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}
```
{% endnote %}

{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}

## Code blocks

### Hexo tag plugin

From [Hexo](https://hexo.io/docs/tag-plugins.html#Code-Block)

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

From [Hexo](https://hexo.io/docs/tag-plugins.html#Gist)

{% note default %}
```markdown
{% gist sosiristseng/5406c151b54ed182bf8e57e1a2a4c57e %}
```
{% endnote %}

{% gist sosiristseng/5406c151b54ed182bf8e57e1a2a4c57e %}

### Include code

From [Hexo](https://hexo.io/docs/tag-plugins.html#Include-Code)

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

## Link to other post

From [Hexo](https://hexo.io/docs/tag-plugins#Include-Posts).

{% note default %}
```markdown
{% post_link filename [title] [escape]  %}
```

```markdown
{% post_link emoji "Emoji support" %}
```
{% endnote %}

{% post_link emoji %}

## Image

From [Hexo](https://hexo.io/docs/tag-plugins.html#Image)

{% note default %}

```markdown
{% img [class names] /path/to/image [width] [height] '"title text" "alt text"' %}
```

```markdown
{% img https://octodex.github.com/images/stormtroopocat.jpg 200 200 '"The Stormtroopocat" "Alt text"' %}
```

{% endnote %}

{% img https://octodex.github.com/images/stormtroopocat.jpg 200 200 '"The Stormtroopocat" "Alt text"' %}

## Videos

### URL

From [Hexo Next](https://theme-next.js.org/docs/tag-plugins/video.html)

{% note default %}
```markdown
{% video url %}

{% video https://upload.wikimedia.org/wikipedia/commons/transcoded/c/c4/Physicsworks.ogv/Physicsworks.ogv.240p.vp9.webm %}
```
{% endnote %}

{% video https://upload.wikimedia.org/wikipedia/commons/transcoded/c/c4/Physicsworks.ogv/Physicsworks.ogv.240p.vp9.webm %}

### YouTube videos

From [Hexo](https://hexo.io/docs/tag-plugins.html#YouTube)

{% note default %}
```markdown
{% youtube JtUAAXe_0VI %}
```
{% endnote %}

{% youtube JtUAAXe_0VI %}

### Vimeo

From [Hexo](https://hexo.io/docs/tag-plugins.html#Vimeo)

{% note default %}
```markdown
{% vimeo 63830488 %}
```
{% endnote %}

{% vimeo 63830488 %}

## PDF files

From [Hexo Next](https://theme-next.js.org/docs/tag-plugins/pdf.html). 

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

From [Hexo:iframe](https://hexo.io/zh-tw/docs/tag-plugins.html#iframe)

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

From [Hexo Next](https://theme-next.js.org/docs/tag-plugins/note.html). 

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

[Hexo Next: Tabs](https://theme-next.js.org/docs/tag-plugins/tabs.html)

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


## Others

* [Group Pictures](https://theme-next.js.org/docs/tag-plugins/group-pictures.html)
* [Caniuse](https://theme-next.js.org/docs/tag-plugins/caniuse.html)