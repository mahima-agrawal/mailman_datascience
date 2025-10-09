ma4705_web_scraper
================
2025-10-09

``` r
url = "http://samhda.s3-us-gov-west-1.amazonaws.com/s3fs-public/field-uploads/2k15StateFiles/NSDUHsaeShortTermCHG2015.htm"
nsduh_html = read_html(url) |>
  html_table()
c_use_st_yr_html = nsduh_html |>
  nth(4) |>
  slice(-1:-6)

c_use_st_yr_html
```

    ## # A tibble: 51 × 16
    ##    State     `12+(2013-2014)` `12+(2014-2015)` `12+(P Value)` `12-17(2013-2014)`
    ##    <chr>     <chr>            <chr>            <chr>          <chr>             
    ##  1 Alabama   1.23             1.22             0.995          0.42              
    ##  2 Alaska    1.54a            2.00             0.010          0.51              
    ##  3 Arizona   2.25             2.29             0.861          1.01              
    ##  4 Arkansas  0.93             1.07             0.208          0.41              
    ##  5 Californ… 2.14             2.16             0.883          0.89              
    ##  6 Colorado  2.57             2.75             0.493          0.89              
    ##  7 Connecti… 2.17             2.43             0.278          0.61              
    ##  8 Delaware  1.85b            2.21             0.061          0.49              
    ##  9 District… 3.47             3.19             0.470          0.39              
    ## 10 Florida   1.98             1.90             0.546          0.73              
    ## # ℹ 41 more rows
    ## # ℹ 11 more variables: `12-17(2014-2015)` <chr>, `12-17(P Value)` <chr>,
    ## #   `18-25(2013-2014)` <chr>, `18-25(2014-2015)` <chr>, `18-25(P Value)` <chr>,
    ## #   `26+(2013-2014)` <chr>, `26+(2014-2015)` <chr>, `26+(P Value)` <chr>,
    ## #   `18+(2013-2014)` <chr>, `18+(2014-2015)` <chr>, `18+(P Value)` <chr>
