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

Add `image: /images/whatever.jpg` (or a full https:// URL) to a post's front matter. It shows on the blog list and at the top of the post. Posts without one use `default_image` from `_config.yml`. Use `image_position: center 70%` to choose which part of a tall photo shows on the list. Add `header_image: false` to use the image on the list only, without repeating it at the top of the post.

## Credits

Design: [Forty](https://html5up.net/forty) by HTML5 UP, CC BY 3.0 (see `LICENSE.txt`).

## Where things are

| Path | What |
|---|---|
| `_config.yml` | Site title, header nav links, footer social links, posts per page |
| `_layouts/` | Page templates (`default` = Forty header/menu/footer, `post`) |
| `assets/css/main.css`, `assets/js/` | Forty by HTML5 UP, copied unchanged from Haazen_website |
| `assets/css/blog.css` | Blog-only style additions |
| `CNAME` | Custom domain `blog.haazen.xyz` |
