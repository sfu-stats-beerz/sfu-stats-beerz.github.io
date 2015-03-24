---
title:  8 ways to selectively alter data in an R data frame 
author: Sean Anderson
---

From Stats Beerz on 2015-03-23. Here's the question: How can you
substitute values in one column based on values in another column? There
are many many ways. Here are a few,

Create some fake data:

{% highlight R %}
d <- data.frame(
  rel = c("yes", "no", "yes"),
  troph = c(1, 2, 3))
d

#>   rel troph
#> 1 yes     1
#> 2  no     2
#> 3 yes     3

d_original <- d # saved to restore `d` later
{% endhighlight %}

Different ways to select only `rel == "no"`:

{% highlight R %}
d[d$rel == "no", ]

#>   rel troph
#> 2  no     2

d[d[,"rel"] == "no", ]

#>   rel troph
#> 2  no     2

subset(d, rel == "no")

#>   rel troph
#> 2  no     2

# note that dplyr::filter() nicely resets the row numbers:
dplyr::filter(d, rel == "no")

#>   rel troph
#> 1  no     2
{% endhighlight %}

Different ways of selecting the `troph` colum with `rel == "no"`:

{% highlight R %}
d[d$rel == "no", ]$troph 

#> [1] 2

d[d$rel == "no", "troph"]

#> [1] 2

d$troph[which(d$rel == "no")]

#> [1] 2
{% endhighlight %}

Use the above to come up with different ways of substituting `NA` for
all values of `troph` where `rel == "no"`:

{% highlight R %}
d[d$rel == "no", "troph"] <- NA
d

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3

d <- d_original # reset the data frame

d[d$rel == "no", ]$troph <- NA
d

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3

d <- d_original # reset the data frame

d$troph <- ifelse(d$rel == "no", NA, d$troph)
d

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3

d <- d_original # reset the data frame

x <- d$rel == "no"
d[x, "troph"] <- NA
d

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3

d <- d_original # reset the data frame

d <- transform(d, troph = ifelse(rel == "no", NA, troph))
d

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3

d <- d_original # reset the data frame

d <- within(d, troph <- ifelse(rel == "no", NA, troph))
d

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3

d <- d_original # reset the data frame
{% endhighlight %}

Pipes, pipes, pipes: (The `%>%` is the pipe symbol from the magrittr
package, which is loaded via the dplyr package, which also loads
`mutate()`. `mutate()` is like `transform()` but allows you to add
columns that build on columns you just built.)

{% highlight R %}
library("dplyr")
d <- d %>% mutate(troph = ifelse(rel == "no", NA, troph))
d

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3

d <- d_original # reset the data frame
{% endhighlight %}

This is just getting silly, but the magrittr package has other kinds of
pipes. One kind is `%<>%` which assigns the value to the object of the
same name to the left of the pipe. E.g.:

{% highlight R %}
library("magrittr")
d %<>% mutate(troph = ifelse(rel == "no", NA, troph))
d # crazy, eh?

#>   rel troph
#> 1 yes     1
#> 2  no    NA
#> 3 yes     3
{% endhighlight %}
