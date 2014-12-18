This repository holds archived mailing list material from the stats beerz mailing list.

See <https://sfu-stats-beerz.github.io> for the rendered webpage.

To add a new post, 

- Ask to be added to the `sfu-stats-beerz` group on GitHub.

- Go into the `_posts` folder and click the `+` (see the text `sfu-stats-beerz.github.io/_posts/+` at the top).

- Paste an email/post into the document.

- Add a header at the top that follows this format:

```
---
layout: post
title:  A title for the post
author: Author Name
---
```

- Write a commit message at the bottom. E.g. `Add a new post on ...`

- Click the green `Commit new file` button. You're done!

Note that the post should be in Markdown format. This is pretty basic. There are many helpful guides on the internet. E.g. <http://rmarkdown.rstudio.com/authoring_basics.html>.

In particular, note that for URLs to be clickable you need to wrap them in `< >` tags.

To add or edit a new static page (e.g. the About page, or maybe you want a link page), edit a Markdown (`.md`) file in the root folder. E.g. take a look at `about.md`.

To edit an old post, find the post in the `_posts` folder, click on it, and click on the `Edit` button near the top right. Edit away, write a commit message, and commit your change. The site will re-generate on its own.
