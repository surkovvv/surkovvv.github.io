# Technical notes

A Jekyll blog published on GitHub Pages from the root of `main`.

## Preview locally

With Ruby 3.3 and Bundler installed, run these commands from the project directory.

```sh
bundle install
bundle exec jekyll serve --drafts
```

Open `http://127.0.0.1:4000`. Omit `--drafts` to preview the public site.

## Write a note

Use `_drafts/` for unpublished Markdown. Git ignores this directory. When the note is ready, move it to `_posts/` with a name such as `YYYY-MM-DD-flash-attention.md`, then commit and push to `main`. The home page lists published notes by date and pulls each title and description from its front matter.

```yaml
---
title: FlashAttention
description: From GPU memory traffic to a Triton implementation and benchmarks.
math: true
---
```

For a longer note, add this block wherever the contents should appear. Jekyll generates links from the level-two and level-three headings.

```markdown
**Contents**

* Contents
{:toc}
```

Use `$$ ... $$` for equations, with a separate paragraph for display math. Set `math: true` on notes that need MathJax. Specify a language such as `python` on fenced code blocks for syntax highlighting. Store figures under `assets/` and use `relative_url` in their links.
