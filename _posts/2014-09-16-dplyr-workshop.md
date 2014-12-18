---
layout: post
title:  dplyr workshop
author: Sean Anderson
---

I just added the slides to the Dropbox folder:
<https://www.dropbox.com/sh/kn6fwmef5e9np8l/AAAv2KMlapwAs6Yd30UbYV9ea?dl=0>

    stats %>%
    beers(as = "homebrew", ignore.low.stock = TRUE) %>%
    frustration %>%
    learning %>%
    filter(success == TRUE)

If you want to go further, see these links:

dplyr:

<http://cran.r-project.org/web/packages/dplyr/vignettes/introduction.html>
<https://github.com/hadley/dplyr>

pipes from the magrittr package:

<http://cran.r-project.org/web/packages/magrittr/vignettes/magrittr.html>
<https://github.com/smbache/magrittr>

Also, if you've ever wanted to get really deep into R programming,
there's no better source than Hadley's new book. The digital version
will always be available at: <http://adv-r.had.co.nz/>

And the physical version of "Advanced R" is available for pre-order
now:
<http://www.amazon.ca/dp/1466586966/ref=cm_sw_su_dp?tag=devtools-20>
