What is HDL?
------------

High-Definition Likelihood (HDL) is a likelihood-based method for estimating genetic correlation using GWAS summary statistics. 
Compared to [LD Score regression (LDSC)](https://github.com/bulik/ldsc), It reduces the variance of a genetic correlation estimate by about 60%. 
Here, we provide an R-based computational tool `HDL` to implement our method. Although `HDL` is written in R, 
you can use it with the command line. So no worry if you are not an R user.

In [the wiki](https://github.com/zhenin/HDL/wiki), we provide a detailed tutorial for the application of `HDL` together with real examples. 

What data are required?
-----------------------

-   `gwas1.df` and `gwas2.df`, which are two datasets including GWAS summary statistics of genetic variants for two traits. [This page](https://github.com/zhenin/HDL/wiki/Format-of-summary-statistics) describes the format of summary statistics for `HDL`, and how to perform data wrangling.

*   The eigenvalues and eigenvectors of LD matrices. For the European-ancestry population, 
we have computed the LD matrices and their eigen-decomposition from 336,000 Genomic British individuals in UK Biobank. 
You can download these pre-computed reference files following the [instruction](https://github.com/zhenin/HDL/wiki/Reference-panels) 
in the [wiki](https://github.com/zhenin/HDL/wiki).
    
Installation
------------

Firstly you need an R (version &gt;= 3.5.2) in your computer. If you have not installed R, you can easily download and install it from <https://cran.r-project.org/>.

#### Command line user

In order to download the R package `HDL` and related scripts, you can clone `HDL` repository and then install it using `HDL.install.R`:

``` r
git clone https://github.com/zhenin/HDL
cd HDL
Rscript HDL.install.R
```

Once the installation has completed, you can print out the version information by running `HDL.run.R` without any argument:

``` r
Rscript HDL.run.R
```

    ## HDL: High-definition likelihood inference of genetic correlations
    ## (HDL)

    ## Version 1.1 (2020-02-17) installed

    ## Author: Zheng Ning, Xia Shen

    ## Maintainer: Zheng Ning <zheng.ning@ki.se>

    ## Tutorial: https://github.com/zhenin/HDL

    ## Use citation("HDL") to know how to cite this work.

#### R user

You can use the `install_github` function in `devtools` package to install `HDL` from Github:

``` r
library(devtools)
install_github("zhenin/HDL/HDL")
```

and load the package via:

``` r
library(HDL)
```


For Help
--------

For direct R documentation of `HDL.rg` function, you can use a question mark in R:

``` r
?HDL.rg
```

If you have specific questions, you may email the maintainer of `HDL` via <zheng.ning@ki.se>.
