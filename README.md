Hi 👋

# Sagar Chapara — Machine Learning Blog

This repository powers my GitHub Pages site built with [Jekyll](https://jekyllrb.com/) and the popular [Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/). It is configured for long-form machine learning writing with MathJax support for LaTeX, built-in Lunr search, and responsive layouts.

## Getting started locally

```bash
bundle install
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000` in your browser to preview the site.

> **Tip:** If `jekyll serve` complains about a missing `webrick`, run `bundle add webrick` once or keep the dependency pinned in `Gemfile` (already configured here).

If you prefer to keep dependencies isolated, configure Bundler to install gems inside `vendor/bundle`:

```bash
bundle config set --local path 'vendor/bundle'
```

After the initial install you only need to run `bundle exec jekyll serve` to boot the local server.

If you want to generate the static site without starting the server, run:

```bash
bundle exec jekyll build
```

## Features

- MathJax rendering for inline and block equations.
- Full-text search powered by Lunr.js.
- Preconfigured blog, about, projects, and research highlight pages driven by `_pages/`.
- Syntax-highlighted code snippets using Rouge.
- Responsive design with author profile support.

## Resolving merge conflicts

If this branch diverges from `main`, pull the latest changes and resolve conflicts before pushing:

```bash
git checkout work
git fetch origin
git rebase origin/main
# fix any conflicts, then
git add <files>
git rebase --continue
```

Once the rebase succeeds you can force-push the updated branch to refresh the pull request.
