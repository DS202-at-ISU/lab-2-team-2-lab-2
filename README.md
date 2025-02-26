
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
library(dplyr)
```

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

``` r
<<<<<<< HEAD
dfAmes <- classdata::ames
head(dfAmes)
```

    ## # A tibble: 6 × 16
    ##   `Parcel ID` Address      Style Occupancy `Sale Date` `Sale Price` `Multi Sale`
    ##   <chr>       <chr>        <fct> <fct>     <date>             <dbl> <chr>       
    ## 1 0903202160  1024 RIDGEW… 1 1/… Single-F… 2022-08-12        181900 <NA>        
    ## 2 0907428215  4503 TWAIN … 1 St… Condomin… 2022-08-04        127100 <NA>        
    ## 3 0909428070  2030 MCCART… 1 St… Single-F… 2022-08-15             0 <NA>        
    ## 4 0923203160  3404 EMERAL… 1 St… Townhouse 2022-08-09        245000 <NA>        
    ## 5 0520440010  4507 EVERES… <NA>  <NA>      2022-08-03        449664 <NA>        
    ## 6 0907275030  4512 HEMING… 2 St… Single-F… 2022-08-16        368000 <NA>        
    ## # ℹ 9 more variables: YearBuilt <dbl>, Acres <dbl>,
    ## #   `TotalLivingArea (sf)` <dbl>, Bedrooms <dbl>,
    ## #   `FinishedBsmtArea (sf)` <dbl>, `LotArea(sf)` <dbl>, AC <chr>,
    ## #   FirePlace <chr>, Neighborhood <fct>

=======
# summary(ames)
```

>>>>>>> cc0061af82cf3cc3d75984142e3316d443f7ec4a
- There are 16 variables. These include Parcel ID, Address, Style,
  Occupancy, Sale Date, Sale Price, Multi Sale, YearBuilt, Acres,
  TotalLivingArea(sf), Bedrooms, FinishedBsmtArea(sf), LotArea(sf), AC,
  FirePlace, and Neighborhood. You can find data on the meaning and
  range of the variables by running the code.

## 2. is there a variable of special interest or focus?

- Since the main varible for exploration is Sales Price, we want to look
  at variables that would likely influence the price. Of the 16, we
  think Acres, YearBuilt, TotalLivingArea, and Bedrooms would be
  variables worth looking at that would likely effect the Sales Price.

## 3. start the exploration with the main variable:

``` r
ggplot(ames, aes(x = `Sale Price`)) + geom_histogram(binwidth = 100000)
```

![](README_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

- The range of the variable Sale Price is between 0 and 20,500,000. A
  vast majority of the housing price falls between 0 and 200,000.
  There’s a fair amount of outliers roughly in the million to 2 million
  range for housing price.

## 4. pick a variable that might be related to the main variable.
