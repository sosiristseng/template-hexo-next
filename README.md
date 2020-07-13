# Site template for Hexo Next

![Page Deploy](https://github.com/sosiristseng/site-hexo-next/workflows/Page%20Deploy/badge.svg)

Site template powered by [Hexo Next](https://theme-next.js.org/) and [GitHub pages](https://pages.github.com/).

## TL;DR
1. Use this site as a template
2. Change `baseurl` and personal settings, etc in `_config.yml`
   ```yml
   url: https://username.github.io
   root: /repo-name/  # root:/ for personal website (username.github.io)
   ```

## Features
- [Hexo](https://hexo.io/zh-tw/) static site generator
- Fast and elegant [Next theme](https://theme-next.js.org/)
- Fast [`markdown-it`](https://github.com/hexojs/hexo-renderer-markdown-it) renderer with a bunch of plugins
- Serve-side MathJax math rendering powered by [markdown-it-latex2img](https://github.com/MakerGYT/markdown-it-latex2img)
- Listed JS package dependencies in `package.json`
- GitHub actions for deploy the HTML pages to `master` branch from `source` (default) branch

## Tips
### How to Download the Latest Release Version of Next theme

In your blog site folder:

```bash
rm -rf themes/next
mkdir themes/next
curl -s https://api.github.com/repos/next-theme/hexo-theme-next/releases/latest | grep tarball_url | cut -d '"' -f 4 | wget -i - -O- | tar -zx -C themes/next --strip-components=1
```

## See also
* Create a Acedemic site powerered by Hugo static site generator, the academic theme, and Netlify: https://sourcethemes.com/academic/docs/install/
