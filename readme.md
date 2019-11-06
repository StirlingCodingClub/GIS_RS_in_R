An introduction to GIS and Remote Sensing with R
================
Thiago Silva
06/11/2019

There are packages for R that make it surprisingly competent for GIS
(Geographic Information System) and remote sensing (satellite/aerial
image processing). In this session, I will cover the basiscs of reading
spatial data in, performing spatial operations, exporting results and
visualizing data and analyses. It will mostly demoed by live coding.

## Preparation

You should have the following packages installed ahead of time:

``` r
install.packages('rgdal', 'raster', 'sp',
                 'rgeos', 'RStoolbox', 'rasterVis',
                 'sf', 'velox', 'ggplot2', 'ggmap',
                 'mapview', 'tmap')
```

Data: https://drive.google.com/drive/folders/1B4fRJU0XjpoGnvP9UHNqh8PSWEVl5ctD?usp=sharing


## Examples - reading data in

Reading raster data as a `raster` object:

``` r
library(raster)

## Read in a single band raster
ras <- raster(filename)

## Read in a multiband *single file* raster
ras2 <- brick(filename)

## Read in a multiband raster from multiple single-file bands
ras3 <- stack(file1,file2,file3)
```

Reading vector data as `Spatial` objects:

``` r
library(raster)
library(sp)

## Reading vectors using rgdal. Vector type (point, line polygon)
## is determined automagically

shp <- readOGR(dsn = 'file.shp', layer = 'file')
geojs <- 
geopkg <- 
    
## For shapefiles, the raster package has a handy shortcut:
shp <- shapefile('file.shp')
```

Reading vector files as `sf` objects:

``` r
library(sf)

geojs <- 
geopkg <- 
    
## there are quick shortcuts. Deafult for attribute table us a tibble.
shp <- read_sf(file)    
```

## Inspecting objects and simple base ploting
