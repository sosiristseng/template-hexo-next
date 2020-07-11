---
title: Emoji support
date: 2020-07-01 00:00:33
tags: ["emoji", "markdown", "hexo-filter-emoji", "markdown-it-emoji"]
categories: ["Hexo"]
---

This post showed how to render [emoji](https://github.com/ikatyang/emoji-cheat-sheet) in Hexo sites.

<!-- more -->

## Go with the default Markdown renderer in Hexo

You'll need `hexo-filter-emoji` as the default Hexo Markdown renderer (`hexo-renderer-marked`) does not natively support emojis.

```bash
npm i hexo-filter-emoji
```

**Usage**

```markdown
:sparkles:

{% emoji sparkles %}
```

## Go with an alternative renderer `hexo-renderer-markdown-it`

Install both `hexo-renderer-markdown-it` and `markdown-it-emoji`

```bash
npm un hexo-renderer-marked
npm i markdown-it-emoji hexo-renderer-markdown-it
```

## Table of emoji

{% gist rxaviers/7360908 %}