Lab 6 - La Quinta is Spanish for next to Denny’s, Pt. 1
================
Musab Isah

Student ID: 2200000456

Load the needed packages. Note: dsbox is not yet on CRAN. For now, you
need to install it before you load the library.

``` r
install.packages("devtools")
devtools::install_github("rstudio-education/dsbox")
```

Load the libraries here.

``` r
library(tidyverse)
library(dsbox)
```

To help with our analysis we will also use a dataset on US states, which
is located in your repository’s `data` folder.

``` r
states <- read_csv("data/states.csv")
```

# Exercises

1.  What are the dimensions of the Denny’s dataset? (Hint: Use inline R
    code and functions like `nrow` and `ncol` to compose your answer.)
    What does each row in the dataset represent? What are the variables?

``` r
dim(dennys)
head(dennys)
```

1.  What are the dimensions of the La Quinta’s dataset? What does each
    row in the dataset represent? What are the variables?

``` r
dim(laquinta)
head(laquinta)
```

Knit, *commit, and push your changes to GitHub with an appropriate
commit message. Make sure to commit and push all changed files so that
your Git pane is cleared up afterwards.*

1.  Add a country variable to the Denny’s and Laquinta’s datasets and
    set all observations equal to `"United States"`. Remember, you can
    use the `mutate` function for adding a variable. Make sure to save
    the result of this as `dn` and lq, respectively, so that the stored
    data frame contains the new variable going forward.

``` r
dn <- dennys %>%
    mutate(country = "United States")
```

``` r
lq <- laquinta %>%
    mutate(country = "United States")
```

🧶 ✅ ⬆️ Knit, *commit, and push your changes to GitHub with an
appropriate commit message. Make sure to commit and push all changed
files so that your Git pane is cleared up afterwards.*

1.  Which states have the most and fewest Denny’s locations? What about
    La Quinta? Is this surprising? Why or why not?

For Denny’s - Most

``` r
dn %>%
    count(state) %>%
    arrange(desc(n))
```

For Denny’s - Fewest

``` r
dn %>%
    count(state) %>%
    arrange((n))
```

For La Quinta - Most

``` r
lq %>%
    count(state) %>%
    arrange(desc(n))
```

For La Quinta - Fewest

``` r
lq %>%
    count(state) %>%
    arrange((n))
```

1.  Which states have the most Denny’s locations per thousand square
    miles? What about La Quinta?

Joining Denny’s and states

``` r
dn %>%
  count(state) %>%
  inner_join(states, by = c("state" = "abbreviation"))
```

Joining La Quinta’s and states

``` r
lq %>%
  count(state) %>%
  inner_join(states, by = c("state" = "abbreviation"))
```

Since the two data frames have the same columns, we can easily bind them
with the `bind_rows` function:

``` r
dn <- dn %>%
  mutate(establishment = "Denny's")
lq <- lq %>%
  mutate(establishment = "La Quinta")
```

Since the two data frames have the same columns, we can easily bind them
with the `bind_rows` function:

``` r
dn_lq <- bind_rows(dn, lq)
```

We can plot the locations of the two establishments using a scatter
plot, and color the points by the establishment type. Note that the
latitude is plotted on the x-axis and the longitude on the y-axis.

``` r
ggplot(dn_lq, mapping = aes(x = longitude, y = latitude, color = establishment)) +
  geom_point()
```

Knit, *commit, and push your changes to GitHub with an appropriate
commit message. Make sure to commit and push all changed files so that
your Git pane is cleared up afterwards and review the md document on
GitHub to make sure you’re happy with the final state of your work.*
