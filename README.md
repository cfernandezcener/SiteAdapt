# SiteAdapt
Procedure for improving the accuracy of modeled solar irradiance series (GHI, DNI, DHI) through overlapping and quality assured ground-based measurements

Modeled solar irradiance series are useful tools for evaluating the solar resource, as they provide long term series. Unfortunately, they are not usually suitable to meet the strict solar resource assessment requirements imposed by solar energy projects at a specific location. Thus, its site adaptation has become a standard practice of the industry, being typically requested by financial institutions in the detailed solar resource assessments of solar projects. This procedure mitigates the risk of solar projects, enhancing the adequate solar plant design and reducing the uncertainty of its yield estimates.

This R-package allows the adaptation of modeled series with coincident short-term high-quality ground measurements, improving their accuracy. The current version requires: 

   - `Target` Dataframe object including time (with same time zone as calibration_period), the solar irradiance modeled series         to be site adapted, along with their clear sky index and solar elevation. Its columns should be named as follows:               “Year”,“Month”,“Day”,Hour“,”Minute“,”GHI.mod“,”DNI.mod“,”DHI.mod“,”kc“,”Elev"
   - `latitude_target` Site latitude of solar radiation series to be adapted (degrees, +N)
   - `z_target` Site elevation above sea level of solar radiation series to be adapted (m)
   - `Calibration` Dataframe object including time (with same time zone as calibration_period), the solar irradiance modeled          series to be site adapted, along with their clear sky index and solar elevation. Its columns should be named as                 follows: “Year”,“Month”,“Day”, “Hour”,“Minute”,“GHI.obs”,“DNI.obs”,“DHI.obs”,“GHI.mod”,“DNI.mod”,“DHI.mod”,“kc”,“Elev”.
   - `latitude_calibrat` Site latitude of solar radiation series for calibrating (degrees, +N)
   - `z_calibrat` Site elevation above sea level of solar radiation series for calibrating (m)
   - `TimeZone` Time zone specification of the calibration_period and target_period datasets
   - `GHI_threshold` Upper limit of GHI series (same units that Target). For automatic calulation from observed data, set it to -99
   - `DNI_threshold` Upper limit of DNI series (same units that Target). For automatic calulation from observed data, set it to -99


Calibrating and target periods must be at least partially coincident between all of them, but they can be from different locations.

## Further inquiry
The author is happy to answer your questions and is open to future collaborations on this topic. Please contact: cfernandez@cener.com or carlos.peruchena@gmail.com

## Installation

Users can install the development version of `SiteAdapt`:

with either the [remotes](https://install-github.me/r-lib/remotes) package:

```
remotes::install_github("cfernandezcener/SiteAdapt")
```

or with the [devtools](https://cran.r-project.org/web/packages/devtools/index.html) package:

```
devtools::install_github("cfernandezcener/SiteAdapt")
```

## Tutorial

A brief tutorial of `SiteAdapt` can be found at:

https://www.researchgate.net/publication/341793182_SiteAdapt_tutorial

## Citation

The original paper describing the methods implemented in `SiteAdapt` is:
```
Fernández-Peruchena, C.M.; Polo, J.; Martín, L.; Mazorra, L. Site-Adaptation of Modeled Solar Radiation Data: The SiteAdapt Procedure. Remote Sens. 2020, 12, 2127. 
```

The original paper describing the methods implemented can be found at:
https://www.mdpi.com/2072-4292/12/13/2127


## License

This package is free and open source software under GPL-3 license.

