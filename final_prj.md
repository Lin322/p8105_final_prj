Consumer product-related injuries in the United States
================

Group Member:
-------------

-   Lin Feng (LF2649)

``` r
library(neiss)
```

We plan to use data from [National Electronic Injury Surveillance System (NEISSS)](https://www.cpsc.gov/Research--Statistics/NEISS-Injury-Data/) to invistigate the risk of consumer product-related injuries occurring in the United States. NEISS is operated by United States Consumer Product Safety Commission (CPSC) who conducted the statistically valid injury surveillance for more than 45 years.

``` r
data("injuries")
data("population")
data("products")

head(population)
```

    ## # A tibble: 6 x 4
    ##    year   age sex          n
    ##   <int> <int> <chr>    <int>
    ## 1  2013     0 female 1921491
    ## 2  2013     0 male   2009717
    ## 3  2013     1 female 1926877
    ## 4  2013     1 male   2015564
    ## 5  2013     2 female 1949297
    ## 6  2013     2 male   2041998

``` r
head(injuries)
```

    ## # A tibble: 6 x 18
    ##   case_num trmt_date     age sex   race  race_other body_part diag  diag_other
    ##   <chr>    <date>      <dbl> <chr> <chr> <chr>      <chr>     <chr> <chr>     
    ## 1 1301049~ 2013-01-01 57     Male  White <NA>       Face      Cont~ <NA>      
    ## 2 1301049~ 2013-01-01  0.583 Fema~ Asian <NA>       Head      Inte~ <NA>      
    ## 3 1301049~ 2013-01-01 59     Fema~ White <NA>       Lower Tr~ Cont~ <NA>      
    ## 4 1301049~ 2013-01-01 17     Fema~ White <NA>       Ankle     Stra~ <NA>      
    ## 5 1301049~ 2013-01-01 38     Male  White <NA>       Finger    Lace~ <NA>      
    ## 6 1301049~ 2013-01-01 39     Fema~ White <NA>       Wrist     Frac~ <NA>      
    ## # ... with 9 more variables: disposition <chr>, location <chr>, fmv <chr>,
    ## #   prod1 <dbl>, prod2 <dbl>, stratum <chr>, psu <dbl>, weight <dbl>,
    ## #   narrative <chr>

``` r
head(products)
```

    ## # A tibble: 6 x 2
    ##    code title                                   
    ##   <int> <chr>                                   
    ## 1   101 washing machines without wringers or oth
    ## 2   102 wringer washing machines                
    ## 3   103 washing machines with unheated spin drye
    ## 4   106 electric clothes dryers without washers 
    ## 5   107 gas clothes dryers without washers      
    ## 6   108 mangle irons
