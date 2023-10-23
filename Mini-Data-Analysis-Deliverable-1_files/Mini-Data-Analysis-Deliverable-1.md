Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

3.  Make a repository in the <https://github.com/stat545ubc-2023>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

The 4 datasets that appeal to me include:

1: cancer_sample 2: flow_sample 3: steam_games 4: vancouver_tree

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

**Cancer Sample Dataset Investigation**

``` r
#Determining Total Number of Columns in Dataset
head(cancer_sample)
```

    ## # A tibble: 6 × 32
    ##         ID diagnosis radius_mean texture_mean perimeter_mean area_mean
    ##      <dbl> <chr>           <dbl>        <dbl>          <dbl>     <dbl>
    ## 1   842302 M                18.0         10.4          123.      1001 
    ## 2   842517 M                20.6         17.8          133.      1326 
    ## 3 84300903 M                19.7         21.2          130       1203 
    ## 4 84348301 M                11.4         20.4           77.6      386.
    ## 5 84358402 M                20.3         14.3          135.      1297 
    ## 6   843786 M                12.4         15.7           82.6      477.
    ## # ℹ 26 more variables: smoothness_mean <dbl>, compactness_mean <dbl>,
    ## #   concavity_mean <dbl>, concave_points_mean <dbl>, symmetry_mean <dbl>,
    ## #   fractal_dimension_mean <dbl>, radius_se <dbl>, texture_se <dbl>,
    ## #   perimeter_se <dbl>, area_se <dbl>, smoothness_se <dbl>,
    ## #   compactness_se <dbl>, concavity_se <dbl>, concave_points_se <dbl>,
    ## #   symmetry_se <dbl>, fractal_dimension_se <dbl>, radius_worst <dbl>,
    ## #   texture_worst <dbl>, perimeter_worst <dbl>, area_worst <dbl>, …

``` r
#Determining Total Number of Rows in Dataset
nrow(cancer_sample)
```

    ## [1] 569

``` r
#Determining Class of Dataset
class(cancer_sample)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

The cancer_sample dataset has a total of 569 rows, with 32 columns and
classes of spec_tbl_df, tbl_df, tbl and data.frame.

**Flow Sample Dataset Investigation**

``` r
#Determining Total Number of Columns in Dataset
head(flow_sample)
```

    ## # A tibble: 6 × 7
    ##   station_id  year extreme_type month   day  flow sym  
    ##   <chr>      <dbl> <chr>        <dbl> <dbl> <dbl> <chr>
    ## 1 05BB001     1909 maximum          7     7   314 <NA> 
    ## 2 05BB001     1910 maximum          6    12   230 <NA> 
    ## 3 05BB001     1911 maximum          6    14   264 <NA> 
    ## 4 05BB001     1912 maximum          8    25   174 <NA> 
    ## 5 05BB001     1913 maximum          6    11   232 <NA> 
    ## 6 05BB001     1914 maximum          6    18   214 <NA>

``` r
#Determining Total Number of Rows in Dataset
nrow(flow_sample)
```

    ## [1] 218

``` r
#Determining Class of Dataset
class(flow_sample)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

The flow_sample dataset has a total of 218 rows, with 7 columns and
classes of tbl_df, tbl, and data.frame.

**Steam Games Dataset Investigation**

``` r
#Determining Total Number of Columns in Dataset
head(steam_games)
```

    ## # A tibble: 6 × 21
    ##      id url     types name  desc_snippet recent_reviews all_reviews release_date
    ##   <dbl> <chr>   <chr> <chr> <chr>        <chr>          <chr>       <chr>       
    ## 1     1 https:… app   DOOM  Now include… Very Positive… Very Posit… May 12, 2016
    ## 2     2 https:… app   PLAY… PLAYERUNKNO… Mixed,(6,214)… Mixed,(836… Dec 21, 2017
    ## 3     3 https:… app   BATT… Take comman… Mixed,(166),-… Mostly Pos… Apr 24, 2018
    ## 4     4 https:… app   DayZ  The post-so… Mixed,(932),-… Mixed,(167… Dec 13, 2018
    ## 5     5 https:… app   EVE … EVE Online … Mixed,(287),-… Mostly Pos… May 6, 2003 
    ## 6     6 https:… bund… Gran… Grand Theft… NaN            NaN         NaN         
    ## # ℹ 13 more variables: developer <chr>, publisher <chr>, popular_tags <chr>,
    ## #   game_details <chr>, languages <chr>, achievements <dbl>, genre <chr>,
    ## #   game_description <chr>, mature_content <chr>, minimum_requirements <chr>,
    ## #   recommended_requirements <chr>, original_price <dbl>, discount_price <dbl>

``` r
#Determining Total Number of Rows in Dataset
nrow(steam_games)
```

    ## [1] 40833

``` r
#Determining Class of Dataset
class(steam_games)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

The steam_games dataset has a total of 40833 rows, with 21 columns and
classes of spec_tbl_df, tbl_df, tbl and data.frame.

**Vancouver Trees Dataset Investigation**

``` r
#Determining Total Number of Columns in Dataset
head(vancouver_trees)
```

    ## # A tibble: 6 × 20
    ##   tree_id civic_number std_street genus_name species_name cultivar_name  
    ##     <dbl>        <dbl> <chr>      <chr>      <chr>        <chr>          
    ## 1  149556          494 W 58TH AV  ULMUS      AMERICANA    BRANDON        
    ## 2  149563          450 W 58TH AV  ZELKOVA    SERRATA      <NA>           
    ## 3  149579         4994 WINDSOR ST STYRAX     JAPONICA     <NA>           
    ## 4  149590          858 E 39TH AV  FRAXINUS   AMERICANA    AUTUMN APPLAUSE
    ## 5  149604         5032 WINDSOR ST ACER       CAMPESTRE    <NA>           
    ## 6  149616          585 W 61ST AV  PYRUS      CALLERYANA   CHANTICLEER    
    ## # ℹ 14 more variables: common_name <chr>, assigned <chr>, root_barrier <chr>,
    ## #   plant_area <chr>, on_street_block <dbl>, on_street <chr>,
    ## #   neighbourhood_name <chr>, street_side_name <chr>, height_range_id <dbl>,
    ## #   diameter <dbl>, curb <chr>, date_planted <date>, longitude <dbl>,
    ## #   latitude <dbl>

``` r
#Determining Total Number of Rows in Dataset
nrow(vancouver_trees)
```

    ## [1] 146611

``` r
#Determining Class of Dataset
class(vancouver_trees)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

The vancouver_trees dataset has a total of 146611 rows, with 20 columns
and classes of tbl_df, tbl and data.frame.

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

The dataset I chose to complete the data analysis milestone on is
vancouver_trees. The reason I chose this dataset specifically is because
there were multiple variables like neighbourhood name, height range,
date planted and other different variables of different types. I wanted
to work with this dataset as I could conduct multiple different analyses
with the different variables of the data.

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

The one research question that I would want to answer with my dataset is
what is the optimal location in the vancouver area to plant a tree and
what are the environment conditions that allow for the trees to grow to
its full potential.

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if
    it makes sense)
3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…
6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

**Plot Distribution of Numeric Variable**

``` r
#Creating freq variable
freq <- ggplot(vancouver_trees, aes(neighbourhood_name)) + geom_bar()

#Swapping axes to make space for neighbourhood names 
freq + coord_flip()
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

I investigated the distribution of the amount of trees observed in each
neighbourhood. From the plot it is evident that renfrew-collingwood has
the highest qunatity of trees. Although this does not particuarly mean
that this neighbourhood has the *largest* diameter and height of trees,
it is still a good indication that tree survival is high in this
neighbourhood.

**Investigation of Missing Variables**

``` r
#Creating missing values variable
missing.values <- vancouver_trees %>%
    gather(key = "key", value = "val") %>%
    mutate(is.missing = is.na(val)) %>%
    group_by(key, is.missing) %>%
    summarise(num.missing = n()) %>%
    filter(is.missing==T) %>%
    select(-is.missing) %>%
    arrange(desc(num.missing)) 
```

    ## Warning: attributes are not identical across measure variables; they will be
    ## dropped

    ## `summarise()` has grouped output by 'key'. You can override using the `.groups`
    ## argument.

``` r
#Visualizing missing values variable in a table
print(missing.values)
```

    ## # A tibble: 5 × 2
    ## # Groups:   key [5]
    ##   key           num.missing
    ##   <chr>               <int>
    ## 1 date_planted        76548
    ## 2 cultivar_name       67559
    ## 3 latitude            22771
    ## 4 longitude           22771
    ## 5 plant_area           1486

``` r
#Creating a missing values variable boxplot
missing.values %>% ggplot() +
    geom_bar(aes(x=key, y=num.missing), stat = 'identity') +
    labs(x='Variable', y="Total Number of Missing values", title='Number of Missing Values in Vancouver Trees Dataset')
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

First I created a table containing the number of missing values in the
vancouver trees dataset and thereafter created a bar chart of the
findings. I chose to analyze the number of missing values as this
provides justification of the variables I should generally avoid while
making my analyses. Since cultivar_name, date_planted, latitude,
longitude and plant_area all have missing values, I will make sure not
to incorporate these values into my analyses.

**Creating New Tibble**

``` r
#Creating variable for new tibble
van.trees.new <- select(vancouver_trees, tree_id, species_name, root_barrier,  neighbourhood_name, street_side_name,  height_range_id, diameter)

#Printing new tibble
print(van.trees.new)
```

    ## # A tibble: 146,611 × 7
    ##    tree_id species_name root_barrier neighbourhood_name       street_side_name
    ##      <dbl> <chr>        <chr>        <chr>                    <chr>           
    ##  1  149556 AMERICANA    N            MARPOLE                  EVEN            
    ##  2  149563 SERRATA      N            MARPOLE                  EVEN            
    ##  3  149579 JAPONICA     N            KENSINGTON-CEDAR COTTAGE EVEN            
    ##  4  149590 AMERICANA    N            KENSINGTON-CEDAR COTTAGE EVEN            
    ##  5  149604 CAMPESTRE    N            KENSINGTON-CEDAR COTTAGE EVEN            
    ##  6  149616 CALLERYANA   N            MARPOLE                  ODD             
    ##  7  149617 PLATANOIDES  N            KENSINGTON-CEDAR COTTAGE ODD             
    ##  8  149618 PLATANOIDES  N            KENSINGTON-CEDAR COTTAGE ODD             
    ##  9  149619 PLATANOIDES  N            KENSINGTON-CEDAR COTTAGE ODD             
    ## 10  149625 AMERICANA    N            KENSINGTON-CEDAR COTTAGE EVEN            
    ## # ℹ 146,601 more rows
    ## # ℹ 2 more variables: height_range_id <dbl>, diameter <dbl>

I created a new tibble using the select function which includes the
tree_id, species_name, root_barrier, neighbourhood_name,
street_side_name, height_range_id, and diameter. I chose to create this
new tibble because I wanted to analyze the specific height and diameter
values of the trees and which species would have the largest or smallest
trees. I can further analyze the neighborhood these trees are generally
in and further dissect the environmental conditions in that area to
further understand the optimal growing conditions for each species.

**Density Plot for Variables**

``` r
#Creating variable for height_range_id density plot
height.range<-ggplot(vancouver_trees, aes(height_range_id)) +
   geom_density(aes(colour=neighbourhood_name))+ 
  labs(x='Height Range', y="Density", title='Vancouver Tree Height Desnity in Neighbourhoods')

#Creating variable to make legend size smaller
addSmallLegend <- function(myPlot, pointSize = 5, textSize = 4, spaceLegend = 1) {
    myPlot +
        guides(shape = guide_legend(override.aes = list(size = pointSize)),
               color = guide_legend(override.aes = list(size = pointSize))) +
        theme(legend.title = element_text(size = textSize), 
              legend.text  = element_text(size = textSize),
              legend.key.size = unit(spaceLegend, "lines"))
}

#Combined small legend size with height.range
addSmallLegend(height.range)
```

![](Mini-Data-Analysis-Deliverable-1_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

To create the density plot I first used ggplot and geom_density to
create the density of each height_range_id per neighborhood. I then
created a varaible to make the legend smaller in order to better
visualize the graph. The reason I chose to do this excercise is to
determine which neighbourhood has the highest the tree with the largest
height, this will help me better determine which neirhbourhoods have
optimal conditions for tree growth. From the graph above, I can conclude
the south cambie has the highest density of trees with a large height.

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

**Question \#1** What specific street in vancouver contains the largest
density of trees from different species?

**Question \#2** What species has the largest height and diameter
compared to the species with the smallest height and diameter?

**Question \#3** Does the street side name have effect on the growth of
the trees in terms of heigh and species, or is it negligible?

**Question \#4** Are certain species that are generally tall greatly
influenced by the neighbourhood environment they are in or is their
growth constant regardless of the condition?
<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
