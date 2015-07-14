# ViRTUE
R/Shiny application for assessing risks to water supply systems.

#**V**ulnerab**i**lity and **R**isk Assessment **T**ool for Water **U**tiliti**E**s (ViRTUE)

ViRTUE is an R/Shiny web application for assessing risks to small-scale water supply systems in the northeastern United States. The tool provides a mechanism to understand and explore individual water utilities climate risk exposure using a stress test, in which the performance of local reservoir systems is tested over a wide range of potential climate and socioeconomic changes. 

##**Features**
*	Point-and-click map interface for viewing historical climate data for a location
*	Perform a stress test of your water supply system to identify climate risks and hazards 
*	Interactively explore system vulnerabilities to changes in climate, demands, and minimum flow requirements
*	Explore adaptation alternatives (e.g., additional reservoir storage and operational adjustments) and instantaneously observe their impact on system performance
*	Assess the likelihood of vulnerabilities occurring based on the most up-to-date climate science (CMIP5 Global Climate Model projections)
*	Download the results of the tool’s climate risk assessment for use in reports and documents
*	Step-by-step instructions and ‘help’ bubbles in each tab of the tool for ease-of-use and self-guided training

##**Availability**
This repository contains the code and data requirements for the application of ViRTUE. 
The live version of this site is available here: https://virtue.shinyapps.io/myapp

##**Local Installation/ Requirements**
ViRTUE requires R version 2.15 or later. For best results, use the latest version of R. 

To install R and RStudio Desktop go to: https://www.rstudio.com/products/rstudio/download/ 

ViRTUE depends on several R packages. To install them, run the following commands from within R.
install.packages(c(“shiny”, “ncdf”, “mnormt”, “MASS”, “zoo”, “maps”, “mapproj”, “psych”, “fields”, “plotrix”, “chron”))

To start ViRTUE, begin an R session and run the following commands:
library(shiny)
runApp(“/path to ViRTUE folder”)

##**License**

ViRTUE is licensed under…
