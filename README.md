# Site template for Hexo Next

- [Hexo](https://hexo.io/zh-tw/) static site generator.
- Fast and elegant [Next theme](https://theme-next.js.org/).
- GitHub actions building the website to [GitHub pages](https://pages.github.com/)

## Copy over my template site

Hosting GitHub: click `use as template`

In `_config.yml`, Change `baseurl` and your personal settings. See also [Hexo configuration](https://hexo.io/docs/configuration.html).
```yml _config.yml
url: https://username.github.io
root: /repo-name/  # root:/ for personal website (username.github.io)
```

### To enable GitHub pages

Open your repository settings => Pages => GitHub Pages
=> Build and deployment => Source, Select `GitHub actions`

### Customizations

You can customize the theme settings by editing `_config.next.yml`. See also [Next theme settings](https://theme-next.js.org/docs/theme-settings/).

## How to develop (in VS Code)

Clone this repository

```bash
git clone git@github.com:sosiristseng/sosiristseng.github.io.git
cd sosiristseng.github.io
```

Install npm dpendencies with Node package manager (npm).
```bash
npm install
```

Install [live server VS code extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) and set the root folder to `public` in `.vscode/settings.json`
```json
{
    "liveServer.settings.root": "/public"
}
```

Build the website locally and watch for file changes
```bash
hexo generate --draft --watch
```

Open Live Server with VSCode command palette (Shift + Command + P (Mac) / Ctrl + Shift + P (Windows/Linux)) and enjoy :)

