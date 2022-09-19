# Aspen_XPolarisSoilData
Importing coordinates of SRM to define area in the XPolaris Map
library(curl)
library(sp)
library(sf)
library(tidyverse)
library(terra)
library(spDataLarge)
library(spData)
library(httr)

setwd("~/0_XPolarisdata")
srm_csv<-read.csv(file.choose())
View(srm_csv)
library(XPolaris)
df.loc<-srm_csv
df.loc
xplot(locations = df.loc,
localPath = getwd())
