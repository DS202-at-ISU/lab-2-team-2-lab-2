
<!-- README.md is generated from README.Rmd. Please edit the README.Rmd file -->

# Lab report \#1

Follow the instructions posted at
<https://ds202-at-isu.github.io/labs.html> for the lab assignment. The
work is meant to be finished during the lab time, but you have time
until Monday evening to polish things.

Include your answers in this document (Rmd file). Make sure that it
knits properly (into the md file). Upload both the Rmd and the md file
to your repository.

All submissions to the github repo will be automatically uploaded for
grading once the due date is passed. Submit a link to your repository on
Canvas (only one submission per team) to signal to the instructors that
you are done with your submission.

#### import data

``` r
library(classdata)
library(ggplot2)
```

    ## Warning: package 'ggplot2' was built under R version 4.4.2

``` r
library(dplyr)
```

    ## Warning: package 'dplyr' was built under R version 4.4.2

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

## 1. inspect the first few lines of the data set:

``` r
?ames
```

    ## starting httpd help server ... done

``` r
names(ames)
```

    ##  [1] "Parcel ID"             "Address"               "Style"                
    ##  [4] "Occupancy"             "Sale Date"             "Sale Price"           
    ##  [7] "Multi Sale"            "YearBuilt"             "Acres"                
    ## [10] "TotalLivingArea (sf)"  "Bedrooms"              "FinishedBsmtArea (sf)"
    ## [13] "LotArea(sf)"           "AC"                    "FirePlace"            
    ## [16] "Neighborhood"

- There are 16 variables. These include Parcel ID, Address, Style,
  Occupancy, Sale Date, Sale Price, Multi Sale, YearBuilt, Acres,
  TotalLivingArea(sf), Bedrooms, FinishedBsmtArea(sf), LotArea(sf), AC,
  FirePlace, and Neighborhood. You can find data on the meaning and
  range of the variables by running the code.

## 2. is there a variable of special interest or focus?

Since the main varible for exploration is Sales Price, we want to look
at variables that would likely influence the price. Of the 16, we think
Acres, YearBuilt, TotalLivingArea, and Bedrooms would be variables worth
looking at that would likely effect the Sales Price.

## 3. start the exploration with the main variable:

## 4. pick a variable that might be related to the main variable.
