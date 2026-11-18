
<!-- README.md is generated from README.Rmd. Please edit that file -->

# assignmentB2SadilaJayasinghe

`assignmentB2SadilaJayasinghe` contains one function,
`count_all_missing_by_group()`, which counts the number of missing
values in every column of a data frame, separately for each level of a
grouping column. It is a quick way to see where data is missing before
starting an analysis.

## Installation

You can install the package from GitHub with:

``` r
devtools::install_github("UBC-STAT545-F2026/assignmentB2SadilaJayasinghe", ref = "0.1.0")
```

## Example

Count the missing values in each column of the `airquality` data set,
for each month:

``` r
library(assignmentB2SadilaJayasinghe)
count_all_missing_by_group(airquality, Month)
#> # A tibble: 5 × 6
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
```

By default the output is ungrouped. Use `.groups = "keep"` to keep it
grouped by month:

``` r
count_all_missing_by_group(airquality, Month, .groups = "keep")
#> # A tibble: 5 × 6
#> # Groups:   Month [5]
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
```
