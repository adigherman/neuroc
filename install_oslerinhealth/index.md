---
output: 
  html_document:
    keep_md: true
    theme: cosmo
    toc: true
    toc_depth: 3
    toc_float:
      collapsed: false
    number_sections: true
---





All code for this document is located at [here](https://raw.githubusercontent.com/muschellij2/neuroc/master/install_oslerinhealth/index.R).

# Installing OSLERinHealth Packages 

[Install and start the latest release version of R](#installing-and-starting-r).  Although the installer will try to download and install `devtools`, there may be some system requirements for `devtools` that you may need before going forward.  Please visit [installing devtools](../installing_devtools/index.html) before going forward if you do not have `devtools` currently installed. 

Then, you can install a package using the following command:

```r
## try http:// if https:// URLs are supported
source("http://oslerinhealth.org/oslerLite.R")
osler_install("PACKAGE")
```
where `PACKAGE` is the name of the package you'd like to install, such as `baker`.  For example, if we want to install `spotgear` and `baker` we can run:
```r
source("http://oslerinhealth.org/oslerLite.R")
osler_install(c("baker", "spotgear"))
```

### Installing the `oslerInstall` package

The `oslerInstall` package contains the `oslerLite`/`osler_install` functions, as well as others relevant for OSLERinHealth.  You can install the package as follows:

```r
source("http://oslerinhealth.org/oslerLite.R")
osler_install("oslerInstall")
```

After installation, you can use `` oslerInstall::oslerLite() `` to install packages without source-ing the URL above.


## Installing Stable/Current/Release Versions

### Stable Versions
In OSLERinHealth, there are stable versions, which correspond to a submitted package.  This stable version has passed the OSLERinHealth checks on Travis for Linux using the other packages in OSLERinHealth that are in OSLERinHealth at the time of submission.  Thus, if you install this package with all the dependencies listed for this package (using specific OSLERinHealth versions), it should work.

To install a stable version (which should be the default), you can run:

```r
source("http://oslerinhealth.org/oslerLite.R")
osler_install(c("baker", "spotgear"), release = "stable")
```

### Current Versions

In OSLERinHealth, a "current" version mirrors the repository of the developer of the package.  This does not ensure that the package is passing OSLERinHealth checks, but will give you the development version from that developer.  This, at least, standardizes the username for all the repositories in OSLERinHealth.  You can install a current version using:

```r
source("http://oslerinhealth.org/oslerLite.R")
osler_install(c("baker", "spotgear"), release = "current")
```

### Release Versions

Every few months, we snapshot all of OSLERinHealth in their current forms.  We save the source tarballs as well as the binary releases from Travis and Appveyor.  We then host these releases on the OSLERinHealth website.  These downloads are stable in time and will not be changed until the next release.  These downloads are also logged to show the activity/amount of use for each package of this release.  To install the release, you would use:

```r
source("http://oslerinhealth.org/oslerLite.R")
osler_install(c("baker", "spotgear"), release = "release")
```

See the `release_repo` argument for how to specify which release to use.

### `oslerLite`: an alias for `osler_install`

As Bioconductor uses the `biocLite` function to install packages, we have created a duplicate of `osler_install`, called `oslerLite`, for ease of use for those users accustomed to Bioconductor.  The same command could have been executed as follows:
```r
source("http://oslerinhealth.org/oslerLite.R")
oslerLite(c("baker", "spotgear"))
```


## Installing OSLERinHealth Packages without upgrading dependencies

The `oslerLite`/`osler_install` functions depend on `devtools::install_github`, which will upgrade dependencies by default, which is recommended.  If you would like to install a package, but not upgrade the dependencies (missing dependencies will still be installed), you can set the `upgrade_dependencies` argument to `FALSE`:

```r
oslerLite(c("baker", "spotgear"), upgrade_dependencies = FALSE)
```

# Installing and starting R 

1.  Download the most recent version of R from [https://cran.r-project.org/](https://cran.r-project.org/). There are detailed instructions on the R website as well as the specific R installation for the platform you are using, typically Linux, OSX, and Windows.

2.  Start R; we recommend using R through [RStudio](https://www.rstudio.com/).  You can start R using RStudio (Windows, OSX, Linux), typing "R" at in a terminal (Linux or OSX), or using the R application either by double-clicking on the R application (Windows and OSX).

3.  For learning R, there are many resources such as [Try-R at codeschool](http://tryr.codeschool.com/) and [DataCamp](https://www.datacamp.com/getting-started?step=2&track=r).


# Packages not available on OSLERinHealth

If a package is not in the OSLERinHealth [list of packages ](http://oslerinhealth.org/list-packages/all), then it is not located on the [OSLERinHealth Github](https://github.com/oslerinhealth?tab=repositories).  Therefore, when installing, you'll get the following error:

```r
Error in osler_install(...) : 
  Package(s) PACKAGE_TRIED_TO_INSTALL are not in oslerinhealth
```

Once a package is located on the list of packages, then it will be available to install. 


# Session Info


```r
devtools::session_info()
```

```
## ─ Session info ───────────────────────────────────────────────────────────────
##  setting  value                       
##  version  R version 4.0.2 (2020-06-22)
##  os       macOS Catalina 10.15.6      
##  system   x86_64, darwin17.0          
##  ui       X11                         
##  language (EN)                        
##  collate  en_US.UTF-8                 
##  ctype    en_US.UTF-8                 
##  tz       America/New_York            
##  date     2020-09-22                  
## 
## ─ Packages ───────────────────────────────────────────────────────────────────
##  package     * version     date       lib source                            
##  assertthat    0.2.1       2019-03-21 [2] CRAN (R 4.0.0)                    
##  backports     1.1.10      2020-09-15 [1] CRAN (R 4.0.2)                    
##  callr         3.4.4       2020-09-07 [1] CRAN (R 4.0.2)                    
##  cli           2.0.2       2020-02-28 [2] CRAN (R 4.0.0)                    
##  colorout    * 1.2-2       2020-06-01 [2] Github (jalvesaq/colorout@726d681)
##  crayon        1.3.4       2017-09-16 [2] CRAN (R 4.0.0)                    
##  desc          1.2.0       2020-06-01 [2] Github (muschellij2/desc@b0c374f) 
##  devtools      2.3.1.9000  2020-08-25 [2] Github (r-lib/devtools@df619ce)   
##  digest        0.6.25      2020-02-23 [2] CRAN (R 4.0.0)                    
##  ellipsis      0.3.1       2020-05-15 [2] CRAN (R 4.0.0)                    
##  evaluate      0.14        2019-05-28 [2] CRAN (R 4.0.0)                    
##  fansi         0.4.1       2020-01-08 [2] CRAN (R 4.0.0)                    
##  fs            1.5.0       2020-07-31 [2] CRAN (R 4.0.2)                    
##  glue          1.4.2       2020-08-27 [1] CRAN (R 4.0.2)                    
##  htmltools     0.5.0       2020-06-16 [2] CRAN (R 4.0.0)                    
##  knitr         1.29        2020-06-23 [2] CRAN (R 4.0.2)                    
##  lifecycle     0.2.0       2020-03-06 [2] CRAN (R 4.0.0)                    
##  magrittr      1.5         2014-11-22 [2] CRAN (R 4.0.0)                    
##  memoise       1.1.0       2017-04-21 [2] CRAN (R 4.0.0)                    
##  pkgbuild      1.1.0       2020-07-13 [2] CRAN (R 4.0.2)                    
##  pkgload       1.1.0       2020-05-29 [2] CRAN (R 4.0.0)                    
##  prettyunits   1.1.1       2020-01-24 [2] CRAN (R 4.0.0)                    
##  processx      3.4.4       2020-09-03 [1] CRAN (R 4.0.2)                    
##  ps            1.3.4       2020-08-11 [2] CRAN (R 4.0.2)                    
##  purrr         0.3.4       2020-04-17 [2] CRAN (R 4.0.0)                    
##  R6            2.4.1       2019-11-12 [2] CRAN (R 4.0.0)                    
##  remotes       2.2.0       2020-07-21 [2] CRAN (R 4.0.2)                    
##  rlang         0.4.7.9000  2020-09-09 [1] Github (r-lib/rlang@60c0151)      
##  rmarkdown     2.3         2020-06-18 [2] CRAN (R 4.0.0)                    
##  rprojroot     1.3-2       2018-01-03 [2] CRAN (R 4.0.0)                    
##  rstudioapi    0.11        2020-02-07 [2] CRAN (R 4.0.0)                    
##  sessioninfo   1.1.1       2018-11-05 [2] CRAN (R 4.0.0)                    
##  stringi       1.5.3       2020-09-09 [1] CRAN (R 4.0.2)                    
##  stringr       1.4.0       2019-02-10 [2] CRAN (R 4.0.0)                    
##  testthat      2.99.0.9000 2020-09-17 [1] Github (r-lib/testthat@fbbd667)   
##  usethis       1.6.1.9001  2020-08-25 [2] Github (r-lib/usethis@860c1ea)    
##  withr         2.2.0       2020-04-20 [2] CRAN (R 4.0.0)                    
##  xfun          0.17        2020-09-09 [1] CRAN (R 4.0.2)                    
##  yaml          2.2.1       2020-02-01 [2] CRAN (R 4.0.0)                    
## 
## [1] /Users/johnmuschelli/Library/R/4.0/library
## [2] /Library/Frameworks/R.framework/Versions/4.0/Resources/library
```

# References
