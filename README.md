This repository holds archived mailing list material from the stats beerz mailing list.

See <https://sfu-stats-beerz.github.io> for the rendered webpage.

To add a new post, 

1. Ask to be added to the `sfu-stats-beerz` group on GitHub.

2. Go into the `_posts` folder and click the `+` (see the text `sfu-stats-beerz.github.io/_posts/+` at the top).

3. Paste an email/post into the document.

4. Add a header at the top that follows this format:

```
---
layout: post
title:  A title for the post
author: The authors name goes here
---
```

5. Write a commit message the bottom. E.g. `Add new post on ...`

6. Click the `Commit` button. You're done!

Note that the post should be in Markdown format. This is pretty basic. There are many helpful guides on the internet. E.g. <http://rmarkdown.rstudio.com/authoring_basics.html>.

In particular, note that for URLs to be clickable you need to wrap them in `< >` tags.

To add or edit a new static page (e.g. the About page, or maybe you want a link page), edit a Markdown (`.md`) file in the root folder. E.g. take a look at `about.md`.
