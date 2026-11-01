# haazen-blog

Source for **https://blog.haazen.xyz**: a Jekyll site built and hosted by GitHub Pages.
(The 2017 PHP version lives on at [Neko_Blog_Sytem](https://github.com/nekocentral/Neko_Blog_Sytem).)

## Write a post

1. Create `_posts/YYYY-MM-DD-my-title.md`
2. Start it with front matter:
   ```yaml
   ---
   title: My title
   tags: [homelab]
   ---
   ```
3. Write Markdown, commit, push. GitHub Pages rebuilds in about a minute.

Post URLs look like `/2026/11/my-title/`. Drafts go in `_drafts/` (not published).

## Preview locally

```bash
bundle install
bundle exec jekyll serve --drafts
```

Then open http://localhost:4000.

## Where things are

| Path | What |
|---|---|
| `_config.yml` | Site title, header nav links, footer social links, posts per page |
| `_layouts/` | Page templates (`default`, `post`) |
| `_includes/` | Header and footer |
| `assets/css/main.css` | All styling (light + dark mode) |
| `CNAME` | Custom domain `blog.haazen.xyz` |
