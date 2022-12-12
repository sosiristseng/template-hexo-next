# Site template for Hexo Next

- [Hexo](https://hexo.io/zh-tw/) static site generator.
- Fast and elegant [Next theme](https://theme-next.js.org/).
- GitHub actions building the website to [GitHub pages](https://pages.github.com/)

## Copy over my template site

- Hosting GitHub: click `use as template`
- Hosting on others e.g. GitLab: clone / import this repo

In `_config.yml`, Change `baseurl` and your personal settings. See also [Hexo configuration](https://hexo.io/docs/configuration.html).
```yml _config.yml
url: https://username.github.io
root: /repo-name/  # root:/ for personal website (username.github.io)
```

### Notes On GitHub

Open your repository settings => Pages => GitHub Pages
=> Build and deployment => Source, Select `GitHub actions`


In `_config.next.yml`, change the settings of the Next theme. See also [Next theme settings](https://theme-next.js.org/docs/theme-settings/).

## How to develop

1. Clone the repo (using SSH in this case)

```bash
git clone git@github.com:sosiristseng/template-hexo-next.git
cd template-hexo-next
```

1. Install npm dpendencies. Node package manager (npm) is needed.

```bash
npm install
```

3. Install `live-server` and `hexo-cli` for live reload in the browser. From [this SO thread](https://stackoverflow.com/questions/36898508/how-to-use-hexo-server-draft-and-livereload/54872963#54872963).

```bash
npm install -g live-server hexo-cli
```

4. Run

```bash
hexo generate --draft --watch & live-server --port=4000 public
```


