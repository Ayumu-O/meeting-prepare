# Repository Guidelines

## Project Structure & Module Organization

This repository is a static GitHub Pages site for meeting and work preparation boards.

- `index.html`: main meeting design board.
- `design-board.html`: work design board variant.
- `.github/workflows/pages.yml`: deploys the repository root to GitHub Pages on pushes to `main`.
- `.gitignore`: excludes local `.extra` files.

There is no package manifest, build system, or separate asset directory. CSS and JavaScript are embedded in each HTML file, so keep related markup, styles, and behavior together unless a future change introduces shared assets.

## Build, Test, and Development Commands

- `python3 -m http.server 8000`: serve the site locally from the repository root.
- `open http://localhost:8000/` or visit it in a browser: preview `index.html`.
- `open http://localhost:8000/design-board.html`: preview the work design board.

No build step is required. GitHub Pages uploads the repository contents directly.

## Coding Style & Naming Conventions

Use the existing single-file HTML style: semantic HTML, embedded `<style>` and `<script>` sections, two-space CSS indentation, and kebab-case class names such as `.header-title` and `.column-body`. Prefer CSS custom properties in `:root` for shared colors, fonts, spacing, and radii. Keep UI text in Japanese to match the current product surface, and preserve the existing dark board aesthetic unless the change explicitly redesigns it.

When adding files, use lowercase descriptive names with hyphens, for example `meeting-template.html`.

## Testing Guidelines

There is no automated test suite. Before committing, manually verify changed pages in a browser at desktop and narrow mobile widths. Check that textareas, buttons, save/load behavior, column scrolling, and exported or copied content still work. For layout changes, inspect both `index.html` and `design-board.html` because they share visual patterns but not code.

## Commit & Pull Request Guidelines

Recent commits use concise Japanese messages that describe the visible change, for example `論点テキストエリアの高さ0問題を修正` or `GitHub Pages デプロイ設定追加`. Follow that style: one focused change per commit, imperative or descriptive wording, and no vague messages such as `update`.

Pull requests should include a short summary, the pages affected, manual browser checks performed, and screenshots or screen recordings for visual changes. Link related issues when available.

## Deployment Notes

Pushes to `main` trigger GitHub Pages deployment through `.github/workflows/pages.yml`. Avoid committing generated local files or scratch notes; keep local-only material under `.extra`.
