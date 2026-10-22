# AGENTS.md

## Overview

Static HTML/CSS/JS portfolio — a collection of standalone web design exercises. No build system, no package manager, no tests, no CI.

## Structure

- `index.html` — portfolio hub / entry page linking to all exercises
- Numbered HTML files (`2-1.html` through `10-4.html`) — individual exercise pages
- `tencent_music.html` — standalone app UI clone
- `css.css` — minimal shared styles (most pages use inline `<style>`)
- `images/`, `img/` — image assets referenced by the HTML files

## Conventions

- Implement pages with native HTML, CSS, and JavaScript
- Do not use third-party libraries or CDNs
- Use iconfont icons from the `font/` directory
- Use `fetch` to retrieve server-side data
- Language: `zh-CN` (Chinese content)
- File names use Chinese characters — be careful with encoding on Windows
- No linter, formatter, or type checker configured
- All variable names, CSS class names, and id names must start with `pzy_`
- Every HTML page must include the comment `<!-- 姓名：庞智元，日期：功能名称。 -->`
- Before executing any task, append the prompt to `pang_prompt.md` (never overwrite). Include: timestamp (`yyyy-mm-dd-hh-mm`), model used, and the full prompt content
- After creating a new HTML file, add a hyperlink to it in `index.html` (follow the existing card format in the `work-grid` section)

## Running

Open any `.html` file directly in a browser, or serve the directory:

```powershell
python -m http.server 8000
```
