Lab 6 - La Quinta is Spanish for next to Denny’s, Pt. 1
================
Musab Isah

Student ID:

Load the needed packages.

To help with our analysis we will also use a dataset on US states, which
is located in your repository’s `data` folder.

# Exercises

1.  What are the dimensions of the Denny’s dataset? (Hint: Use inline R
    code and functions like `nrow` and `ncol` to compose your answer.)
    What does each row in the dataset represent? What are the variables?

2.  What are the dimensions of the La Quinta’s dataset? What does each
    row in the dataset represent? What are the variables?

Knit, *commit, and push your changes to GitHub with an appropriate
commit message. Make sure to commit and push all changed files so that
your Git pane is cleared up afterwards.*

We would like to limit our analysis to Denny’s and La Quinta locations
in the United States.

1.  Filter for `state`s that are not in \`states$abbreviation

2.  Add a country variable to the Denny’s dataset and set all
    observations equal to `"United States"`. Remember, you can use the
    `mutate` function for adding a variable. Make sure to save the
    result of this as `dn` again so that the stored data frame contains
    the new variable going forward.

🧶 ✅ ⬆️ Knit, *commit, and push your changes to GitHub with an
appropriate commit message. Make sure to commit and push all changed
files so that your Git pane is cleared up afterwards.*

1.  Filter the La Quinta dataset for locations in United States.

2.  Which states have the most and fewest Denny’s locations? What about
    La Quinta? Is this surprising? Why or why not?

3.  Which states have the most Denny’s locations per thousand square
    miles? What about La Quinta?

Since the two data frames have the same columns, we can easily bind them
with the `bind_rows` function:

We can plot the locations of the two establishments using a scatter
plot, and color the points by the establishment type. Note that the
latitude is plotted on the x-axis and the longitude on the y-axis.

🧶 ✅ ⬆️ Knit, *commit, and push your changes to GitHub with an
appropriate commit message. Make sure to commit and push all changed
files so that your Git pane is cleared up afterwards and review the md
document on GitHub to make sure you’re happy with the final state of
your work.*
