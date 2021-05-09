---
title: Setup a free personal blog using Hexo
date: 2020-07-06 15:26:17
tags: ["hexo", "github", "gitlab", "nodejs"]
categories: ["Hexo"]
---

Notes to set up a [Hexo](https://hexo.io/) blog site, as a reminder for the future me. 😁

<!-- more -->

## Setup Node JS

Install the node package manager (npm) if you want to preview/build the website on the local machine.

- Windows: Download and install from the [official website](https://nodejs.org/en/download/).
- MacOS / Linux: [nvm](https://github.com/nvm-sh/nvm) is recommended to install and manage your local version(s) of npm.

## The easy way: copy my template site

This template includes these features:

- [Hexo](https://hexo.io/) static site generator.
- Fast and elegant [Next theme](https://theme-next.js.org/).
- [markdown-it renderer](https://github.com/wzpan/hexo-renderer-markdown-it) and KaTeX math.
- GitHub actions and GitLab CI included.


- Hosting on GitHub: click `use as template` to copy this template under your GitHub account.
- Hosting on GitLab: import this repo.

In `_config.yml`, change `baseurl` and your personal settings.
```yml _config.yml
url: https://username.github.io
root: /repo-name/  # or "/" for personal/group website (username.github.io)
```

Also see [Hexo configuration](https://hexo.io/docs/configuration.html) for more details.

In `_config.next.yml`, change the settings of the Next theme. Also see [Next theme settings](https://theme-next.js.org/docs/theme-settings/) for further customizations.

## The self-serving way

Also checkout [getting started in Hexo Next](https://theme-next.js.org/docs/getting-started/).

### Hexo website and and Next theme

1. install the `hexo` command:
```bash
npm install hexo-cli -g
```

2. setup `Next` theme:
```bash
# Created the website in `blog` folder.
hexo init blog
cd blog

# Install Hexo npm dependencies
npm install

# Install Next theme
npm install hexo-theme-next

# Copy the theme config file for future customizations
cp ./node_modules/hexo-theme-next/_config.yml _config.next.yml

# Remove the original landscape theme
rm -rf ./themes/landscape
```

3. use `Next` theme in the config
```yml _config.yml
theme: next
```

1. preview your setup.
```bash
# Test your setup.
# This command will open a browser and visit http://localhost:4000.
# Ctrl+C to exit
hexo clean && hexo server -o --debug
```

You can start blogging using the `hexo new `command e.g. `hexo new post hello` or start to customize your settings. Press [[Ctrl]] + [[C]] to exit preview.

### Browser sync

By default, you need to press the refresh button when you make a change to the markdown file, which is tedious.

The `hexo-browsersync` package comes to the rescue. It issues browser refresh automatically upon filesystem changes in your website in `server` mode.

```bash
npm i hexo-browsersync -D
```

### Useful hexo plugins

```bash
# Word and read time counter
npm i hexo-word-counter

# Local search
npm i hexo-generator-searchdb

# Emoji tag plugin
npm i hexo-filter-emoji
```

### Switch to a better renderer

The default renderer `hexo-renderer-marked` does not fully support LaTeX math syntax. Thus, we could switch to a better one.

See the {% post_link math "math rendering" %} post to switch the renderer and setup the math typesetting libraries.

#### Additional markdown-it settings

Install some other useful plugins:

```bash
npm i markdown-it-imsize markdown-it-named-headings markdown-it-task-checkbox markdown-it-kbd
```

Add the [settings](https://github.com/hexojs/hexo-renderer-markdown-it/wiki/Advanced-Configuration) of `hexo-renderer-markdown-it` in `_config.yml` like this:

```yml _config.yml
markdown:
  render:
    html: true
    xhtmlOut: false
    breaks: true
    linkify: true
    typographer: false
    quotes: ''
  plugins:
    - markdown-it-abbr
    - markdown-it-deflist
    - markdown-it-footnote
    - markdown-it-latex2img
    - markdown-it-mark
    - markdown-it-task-checkbox
    - markdown-it-kbd
    - name: markdown-it-emoji
      options:
        shortcuts: {}
  anchors:
    # Minimum level for ID creation. (Ex. h2 to h6)
    level: 2
    # A suffix that is prepended to the number given if the ID is repeated.
    collisionSuffix: 'v'
    # If `true`, creates an anchor tag with a permalink besides the heading.
    permalink: true
    # Class used for the permalink anchor tag.
    permalinkClass: header-anchor
    # Set to 'right' to add permalink after heading
    permalinkSide: 'left'
    # The symbol used to make the permalink
    permalinkSymbol: ""
    # Transform anchor to (1) lower case; (2) upper case
    case: 1
    # Replace space with a character
    separator: '-'
```

### Deployment

{% tabs deploy %}
<!-- tab GitHub pages -->

Create a file `.github/workflows/gh-pages.yml` for GitHub actions.

Also see [GitHub action for GitHub pages](https://github.com/peaceiris/actions-gh-pages)

#### With pandoc

```yml
name: github pages
env:
  NODE_ENV: production
  PDC_VER: "2.11.3.1"

on:
  push:
    branches:
      - main

jobs:
  build:
    name: Build website
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Restore last modified time
      run: "git ls-files -z | while read -d '' path; do touch -d \"$(git log -1 --format=\"@%ct\" \"$path\")\" \"$path\"; done"
    - uses: actions/setup-node@v2.1.4
      with:
        node-version: '14'
    - name: Cache Dependencies
      uses: actions/cache@v2
      with:
        path: ~/.npm
        key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
        restore-keys: |
          ${{ runner.os }}-node-
    - name: Setup Pandoc
      run: wget -qO- https://github.com/jgm/pandoc/releases/download/${PDC_VER}/pandoc-${PDC_VER}-linux-amd64.tar.gz | sudo tar xvz --strip-components 1 -C /usr/local
    - name: Build website
      run: npm ci && npm run build
    - name: Deploy
      uses: peaceiris/actions-gh-pages@v3
      with:
        personal_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./public
        full_commit_message: ${{ github.event.head_commit.message }}
```

#### With markdown-it

```yml
name: github pages
env:
  NODE_ENV: production

on:
  push:
    branches:
      - main

jobs:
  build:
    name: Build website
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Restore last modified time
      run: "git ls-files -z | while read -d '' path; do touch -d \"$(git log -1 --format=\"@%ct\" \"$path\")\" \"$path\"; done"
    - uses: actions/setup-node@v2.1.4
      with:
        node-version: '14'
    - name: Cache Dependencies
      uses: actions/cache@v2
      with:
        path: ~/.npm
        key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
        restore-keys: |
          ${{ runner.os }}-node-
    - name: Build website
      run: npm ci && npm run build
    - name: Deploy
      uses: peaceiris/actions-gh-pages@v3
      with:
        personal_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./public
        full_commit_message: ${{ github.event.head_commit.message }}
```

<!-- endtab -->
<!-- tab GitLab pages -->

Create a file `.gitlab-ci.yml` for GitLab CI/CD. Also see the [documentation](https://docs.gitlab.com/ee/user/project/pages/) of GitLab pages.

#### With pandoc

```yml
# https://hub.docker.com/r/tarampampam/node/
image: tarampampam/node:lts-alpine

# Cache modules in between jobs: https://docs.gitlab.com/ee/ci/caching/#caching-nodejs-dependencies
cache:
    key: ${CI_COMMIT_REF_SLUG}
    paths:
    - .npm/

variables:
  NODE_ENV: "production"
  PDC_VER: "2.11.3.1"

before_script:
- "git ls-files -z | while read -d '' path; do touch -d \"$(git log -1 --format=\"@%ct\" \"$path\")\" \"$path\"; done"
- "wget -qO- https://github.com/jgm/pandoc/releases/download/${PDC_VER}/pandoc-${PDC_VER}-linux-amd64.tar.gz | tar xvz --strip-components 1 -C /usr/local"
- npm ci --cache .npm --prefer-offline
- npm run build

test:
  stage: test
  script:
  - echo "Done"
  except:
  - main

pages:
  stage: build
  script:
  - apk add --update brotli
  - find public -type f -regex '.*\.\(htm\|html\|txt\|text\|js\|css\|svg\|xml\)$' -exec gzip   -f -k {} \; || echo 'Gzip failed. Skipping...'
  - find public -type f -regex '.*\.\(htm\|html\|txt\|text\|js\|css\|svg\|xml\)$' -exec brotli -f -k {} \; || echo 'Brotli failed. Skipping...'
  artifacts:
    paths:
    - public
  only:
  - main
```

#### With markdown-it

```yml
# https://hub.docker.com/r/tarampampam/node/
image: tarampampam/node:lts-alpine

# Cache modules in between jobs: https://docs.gitlab.com/ee/ci/caching/#caching-nodejs-dependencies
cache:
    key: ${CI_COMMIT_REF_SLUG}
    paths:
    - .npm/

variables:
  NODE_ENV: "production"

before_script:
- "git ls-files -z | while read -d '' path; do touch -d \"$(git log -1 --format=\"@%ct\" \"$path\")\" \"$path\"; done"
- npm ci --cache .npm --prefer-offline
- npm run build

test:
  stage: test
  script:
  - echo "Done"
  except:
  - main

pages:
  stage: build
  script:
  - apk add --update brotli
  - find public -type f -regex '.*\.\(htm\|html\|txt\|text\|js\|css\|svg\|xml\)$' -exec gzip   -f -k {} \; || echo 'Gzip failed. Skipping...'
  - find public -type f -regex '.*\.\(htm\|html\|txt\|text\|js\|css\|svg\|xml\)$' -exec brotli -f -k {} \; || echo 'Brotli failed. Skipping...'
  artifacts:
    paths:
    - public
  only:
  - main
```

<!-- endtab -->
{% endtabs %}
