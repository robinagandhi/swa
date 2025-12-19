<!-- Repository: Software Assurance (swa) -->
# Copilot / AI Agent Instructions for `swa`

This file contains concise, actionable guidance so an AI coding assistant can be productive immediately in this repository.

- **Project type:** Static course site published via GitHub Pages (Jekyll + remark.js).
- **Primary content locations:** [pages](pages), [slides](slides), [assets](assets), [javascripts](javascripts), `_layouts`.

**Big picture**
- The repo hosts lecture content and course pages as a static site. Presentation pages live under `slides/<lecture>/` and include Markdown fragments from `slides/<lecture>/include/`.
- Site templates and global layout live in `_layouts/default.html` and simple CSS/JS lives under `assets/` and `javascripts/` (e.g., `javascripts/remark-latest.min.js` and `javascripts/main.js`).
- Publishing is done via GitHub Pages; there is no CI/build script in the repo.

**Where to edit content** (concrete examples)
- Update lecture notes: edit files under [slides/<lecture>/include](slides) (for example, [slides/lecture-3/include/requirements-for-software-se.md](slides/lecture-3/include/requirements-for-software-se.md)).
- Update page content: edit files under [pages](pages) (for example, [pages/syllabus.md](pages/syllabus.md)).
- Update layout or HTML wrappers: edit [_layouts/default.html](_layouts/default.html).

**Project-specific patterns & conventions**
- Slides are generated as HTML pages that reference markdown include fragments in `slides/*/include/`. Do not replace the HTML shells unless you know how the includes are used.
- Static assets are expected under `assets/` (stylesheets) and `javascripts/` (client-side scripts). Prefer changing `assets/stylesheets/stylesheet.css` for site-wide style tweaks.
- Images for slides are colocated under each lecture's `images/` directory.

**Developer workflows (what works here)**
- Clone and push as usual (see repository README). For contributor workflow follow the fork → branch → PR pattern described in [README.md](README.md).
- Local preview: the repository uses Jekyll/GitHub Pages conventions. To preview locally (if you have Ruby + Bundler + Jekyll installed) run:

```
bundle exec jekyll serve --livereload
```

If you don't have a Jekyll toolchain, you can preview individual `.html` files directly in a browser (they're static shells that reference local JS/CSS).

**Integration points & external dependencies**
- GitHub Pages / Jekyll for publishing.
- remark.js is used for slide-like presentations (`javascripts/remark-latest.min.js`). Editing slide behavior may require familiarity with remark options in the HTML shells.

**What an AI should do first when asked to modify content or add a page**
1. Locate the target area (e.g., `slides/lecture-*/include` or `pages/`).
2. Edit the markdown fragment; commit to a descriptive branch (e.g., `fix/lecture-3-updates`) and open a PR. Keep changes minimal and content-focused.
3. If altering templates (`_layouts/default.html`) or site-wide CSS/JS, include a short smoke-test: open the primary HTML pages in a browser to confirm rendering.

**What not to assume**
- There is no build or test automation in the repo. Do not add automated pipelines without first confirming repository owner intent.
- There are no unit tests or language-specific toolchains to run; most changes are content/HTML/CSS/JS edits.

**Reference files**
- README and contribution guidance: [README.md](README.md)
- Example slide HTML shell: [slides/lecture-0/software-assurance.html](slides/lecture-0/software-assurance.html)
- Example slide include: [slides/lecture-0/include/software-assurance.md](slides/lecture-0/include/software-assurance.md)
- Layout template: [_layouts/default.html](_layouts/default.html)

If anything in this summary is unclear or you want the instructions expanded (examples of PR titles, branch naming, or a sample local preview setup), tell me which area to expand and I'll update this file.
