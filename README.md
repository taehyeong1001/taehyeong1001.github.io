# taehyeong1001.github.io

Personal research website of Taehyeong Kim (UNIST), built with [Jekyll](https://jekyllrb.com/) and the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme.

- Content: `_pages/` (about, research, cv), `_projects/` (research pages), `_data/navigation.yml` (menu), `_config.yml` (sidebar profile)
- Colors: `assets/css/main.scss`; math (MathJax) and favicon: `_includes/head/custom.html`
- Local preview: `bin/serve-local` → http://localhost:4000
- Deploy: pushing to `main` runs `.github/workflows/deploy.yml`, which builds the site to the `gh-pages` branch.
