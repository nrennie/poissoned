
<!-- README.md is generated from README.Rmd. Please edit that file -->

# poissoned

<!-- badges: start -->

![](https://img.shields.io/badge/cool-useless-green.svg)
[![CRAN](https://www.r-pkg.org/badges/version/poissoned)](https://CRAN.R-project.org/package=poissoned)
[![R-CMD-check](https://github.com/coolbutuseless/poissoned/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/coolbutuseless/poissoned/actions/workflows/R-CMD-check.yaml)
<!-- badges: end -->

## Multi-dimensional poisson disc sampling

`poissoned` is an R implementation of the poisson disk sampling
algorithm from [Bridson’s paper - Fast Poisson Disk Sampling in
Arbitrary
Dimensions](https://www.cs.ubc.ca/~rbridson/docs/bridson-siggraph07-poissondisk.pdf)

### What’s in the box

- `poisson2d()` for the 2D case
- `poisson3d()` for the 3D case

## Installation

You can install from
[GitHub](https://github.com/coolbutuseless/poissoned) with:

``` r
# install.packages("devtools")
devtools::install_github("coolbutuseless/poissoned")
```

## Basic Usage

``` r
library(poissoned)

set.seed(1)
points <- poissoned::poisson2d(w = 500, h = 300, r = 10, verbosity = 1)
#> poisson2d(): 500x300, minimum distance = 10

ggplot(points) +
  geom_point(aes(x, y)) +
  theme_bw() +
  coord_fixed() +
  theme(
    panel.grid = element_blank(),
    axis.title = element_blank()
  ) 
```

<img src="man/figures/README-example-1.png" width="100%" />
