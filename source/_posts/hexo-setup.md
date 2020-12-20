---
title: Setup a free personal blog using Hexo
date: 2020-07-06 15:26:17
tags: ["hexo", "github", "gitlab", "nodejs"]
categories: ["Hexo"]
---

Short notes to set up a [Hexo](https://hexo.io/) blog site, as a reminder for the future me.

<!-- more -->

## Setup Node package manager (npm)

- Windows: Download and install from the [official website](https://nodejs.org/en/download/).
- MacOS / Linux: [nvm](https://github.com/nvm-sh/nvm) is recommended to install your local version of npm.

## Copy over my template site

It's the fastest way to get started. If starting from zero is preferred, checkout [getting started for Hexo Next](https://theme-next.js.org/docs/getting-started/).

My template includes these features:

- [Hexo](https://hexo.io/zh-tw/) static site generator.
- Fast and elegant [Next theme](https://theme-next.js.org/).
- [pandoc as renderer](https://github.com/wzpan/hexo-renderer-pandoc).
- GitHub actions and GitLab CI enabled.


- Hosting on GitHub: click `use as template` and optionally you can clone (now yours) the repo back for further editing.
- Hosting on others e.g. GitLab: clone / import this repo.

In `_config.yml`, Change `baseurl` and your personal settings. Also see [Hexo configuration](https://hexo.io/docs/configuration.html) for more details.
```yml _config.yml
url: https://username.github.io
root: /repo-name/  # root:/ for personal website (username.github.io)
```

In `_config.next.yml`, change the settings of the Next theme. Also see [Next theme settings](https://theme-next.js.org/docs/theme-settings/) for further customizations.
