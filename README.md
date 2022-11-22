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

3. Install `browse-sync` for livereload in the browser.

```bash
npm install -g browser-sync
```

4. Run Hexo server

```bash
npm run server
```

5. Open another terminal window and run `browse-sync`

```bash
browser-sync start --proxy localhost:4000 --files *
```

6. Checkout the `browse-sync` port `localhost:3000` (not hexo server port `localhost:4000`) in the browser and the contents should reload with filesystem changes.

