This repository holds archived mailing list material from the stats beerz mailing list.

See <https://sfu-stats-beerz.github.io> for the rendered webpage.

To add new material, open the file `index.Rmd` in RStudio. Add a new post at the top matching the style of the other posts:

```
### January 1 2015: Some useful title
*Somone's Name*

Text goes here
```

Then click the `Knit HTML` button in RStudio to create `index.html`. (This runs `rmarkdown::render("index.Rmd")`.) Now push commit and push both files back to GitHub. That's it!
