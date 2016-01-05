<!-- README.md is generated from README.Rmd. Please edit that file -->
Friendly Time Formats
=====================

Have you ever had to build a way too complicated sprintf format?

``` r
my_string_format = "%1$+03.0f and 1%% and %1$-+3.0f"
```

No human could read this. sprintfr allows you to build understandable time formats.

``` r
library(sprintfr)
library(magrittr)

string_format(list(double %>% 
                     zero_pad,
                   "1%",
                   double %>% 
                     left_justify) %>%
                use_input(1) %>%
                always_sign %>%
                before_decimal(3) %>%
                after_decimal(0),
              sep = " and ")
#> [1] "%1$+03.0f and 1%% and %1$-+3.0f"
```

Inspired by kevinushey/rex

Installation
============

``` r
library(devtools)
install_github("bramtayl/sprintfr")
```
