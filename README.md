# Vulnerability and Risk Assessment Tool for Water UtilitiEs (ViRTUE)

ViRTUE is an R/Shiny web application for assessing risks to small-scale water supply systems in the northeastern United States. The tool provides a mechanism to understand and explore individual water utilities climate risk exposure using a stress test, in which the performance of local reservoir systems is tested over a wide range of potential climate and socioeconomic changes.

ViRTUE was developed by Sarah Whately and the [Hydrosystems Research Group](http://blogs.umass.edu/hydrosystems/) at UMass Amherst.

## Features

*	Point-and-click map interface for viewing historical climate data for a location
*	Perform a stress test of your water supply system to identify climate risks and hazards
*	Interactively explore system vulnerabilities to changes in climate, demands, and minimum flow requirements
*	Explore adaptation alternatives (e.g., additional reservoir storage and operational adjustments) and instantaneously observe their impact on system performance
*	Assess the likelihood of vulnerabilities occurring based on the most up-to-date climate science (CMIP5 Global Climate Model projections)
*	Download the results of the tool’s climate risk assessment for use in reports and documents
*	Step-by-step instructions and ‘help’ bubbles in each tab of the tool for ease-of-use and self-guided training

## Availability

This repository contains the code and data requirements for the application of ViRTUE.

The live version of this site is available here: <https://virtue.shinyapps.io/myapp>

## Local Installation/Requirements

ViRTUE requires R version 2.15 or later. For best results, use the latest version of R.

To install R and RStudio Desktop go to: <https://www.rstudio.com/products/rstudio/download/>

ViRTUE depends on several R packages. To install them, run the following commands from within R.

```r
install.packages(c("shiny", "ncdf", "mnormt", "MASS", "zoo",
  "maps", "mapproj", "psych", "mnormt", "fields", "plotrix",
  "chron", "leaflet", "shinyBS", "devtools"))
devtools::install_github("trestletech/ShinyDash")
devtools::install_github("rstudio/shinyapps")
```

To obtain the ViRTUE source code, clone this repo using git, or [download the zip file](https://github.com/swhatele/ViRTUE/archive/master.zip) from the repo homepage on github and extract the files to some directory.

## External Data

ViRTUE relies on one dataset that must be retrieved externally from the application due to its size. This dataset contains monthly historical climate data for the Northeast US extracted from the [Gridded Meteorological Data: 1949-2010](http://www.engr.scu.edu/~emaurer/gridded_obs/index_gridded_obs.html) dataset by Maurer et al. 2002:

> Maurer, E.P., A.W. Wood, J.C. Adam, D.P. Lettenmaier, and B. Nijssen, 2002, A Long-Term Hydrologically-Based Data Set of Land Surface Fluxes and States for the Conterminous United States, J. Climate 15, 3237-3251.

This dataset can be downloaded as a zip file from the following URL: <https://s3.amazonaws.com/umass-virtue/climate-data.zip>

Simply download this zip file and extract the contents to the `/app` folder. Note that these files must all be located directly within the `app/` folder, and not a subdirectory (e.g. `app/data_39.0625_-74.8125`).

## Running the Application

To start ViRTUE, open a new R session in RStudio and set the working directory to the root folder of this repo (e.g. using `setwd()`).

Then run the following commands:

```r
library(shiny)
runApp("./app")
```

## Package Versions

The latest release of the application was tested using the following R environment:

```r
> sessionInfo()

R version 3.2.1 (2015-06-18)
Platform: x86_64-apple-darwin14.3.0 (64-bit)
Running under: OS X 10.10.4 (Yosemite)

locale:
[1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base

other attached packages:
[1] mnormt_1.5-3      maps_2.3-10       ggplot2_1.0.1     shinyapps_0.4.1.4 shinyBS_0.61      ShinyDash_0.0.1   leaflet_1.0.0
[8] shiny_0.12.1

loaded via a namespace (and not attached):
 [1] Rcpp_0.12.0      rstudioapi_0.3.1 magrittr_1.5     MASS_7.3-43      munsell_0.4.2    colorspace_1.2-6 xtable_1.7-4     R6_2.1.0
 [9] plyr_1.8.3       stringr_1.0.0    httr_1.0.0       tools_3.2.1      grid_3.2.1       gtable_0.1.2     htmltools_0.2.6  digest_0.6.8
[17] RJSONIO_1.3-0    reshape2_1.4.1   htmlwidgets_0.5  mime_0.3         stringi_0.5-5    scales_0.2.5     XML_3.98-1.3     jsonlite_0.9.16
[25] httpuv_1.3.2     proto_0.3-10
```

## License

MIT (see `LICENSE` file)