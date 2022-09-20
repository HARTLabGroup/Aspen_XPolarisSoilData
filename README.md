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
library(XPolaris)
mydf <- read.csv(file.choose())
head(mydf)
table(mydf$FID)
colnames(mydf) <- c("ID", "lat", "long")
xplot(locations = df.loc, localPath = getwd())
xplot(locations = mydf, localPath = getwd())
df.out <- ximages(locations = mydf,
                  variables = c('ph','om','clay','silt','sand','theta_s'), 
                  statistics = c('mean'), # Only the mean will be downloaded 
                  layersdepths = c('0_5','5_15','15_30'), # Depth layers (cm) 
                  localPath = getwd())
df.out
nrow(df.out)
xsoil(ximages_output = df.out[], localPath = getwd())  
