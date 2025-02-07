## Install package
Install the package using the following commands  <img align="right" src="ReadMEFigures/logo.png" width=300>

```r
# for now you can install the developemental version
# first you need to install the devtools package if you do not have it
install.packages("devtools") 
# and load it
library(devtools)

# then you can install the dev version of the ltc
install_github("loukesio/ltc_palettes")
# and load it
library(ltc)
```

## All palettes

```r
# see the available palettes
names(palettes)
 [1] "paloma"     "maya"       "dora"       "ploen"      "olga"       "mterese"    "gaby"      
 [8] "franscoise" "fernande"   "sylvie"     "crbhits"    "expevo"        

# see the hex code from each palette 
palettes$paloma
[1] "#83AF9B" "#C8C8A9" "#f8da8a" "#f7bf95" "#fe8ca1"
 ```

## Palettes
### paloma
```r
# select the palette
paloma <- ltc("paloma")

#and print it with 
pltc(paloma)
```
<img src="ReadMEFigures/paloma.png">

```r
# hex plot
pal=ltc("paloma",100,"continuous")
ggplot2::ggplot(data.frame(x = rnorm(1e4), y = rnorm(1e4)), aes(x = x, y = y)) +
  ggplot2::geom_hex() +
  ggplot2::coord_fixed() +
  ggplot2::scale_fill_gradientn(colours = pal) +
  ggplot2::theme_minimal()
```
<img src="ReadMEFigures/paloma_hex.png">

```r
# stakc plot
ggplot2::ggplot(diamonds, aes(price, fill = cut)) +
  ggplot2::geom_histogram(binwidth = 500, position = "fill") +
  ggplot2::scale_fill_manual(values = pal) +
  ggplot2::theme_bw() +
  ggplot2::theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank())
```
<img src="ReadMEFigures/paloma_stack.png">

###
### maya

```
# select the palette
maya <- ltc("maya")

#and print it with 
pltc(maya)
```
<img src="ReadMEFigures/maya.png">

```r
pal=ltc("maya",100,"continuous")
ggplot2::ggplot(data.frame(x = rnorm(1e4), y = rnorm(1e4)), aes(x = x, y = y)) +
  ggplot2::geom_hex() +
  ggplot2::coord_fixed() +
  ggplot2::scale_fill_gradientn(colours = pal) +
  ggplot2::theme_minimal()
```
<img src="ReadMEFigures/maya_hex.png">

```r
pal=ltc("maya",7,"continuous")
ggplot2::gplot(diamonds, aes(price, fill = color)) +
  ggplot2::geom_histogram(binwidth = 500, position = "fill") +
  ggplot2::scale_fill_manual(values = pal) +
  ggplot2::theme_bw() +
  ggplot2::theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank())
```
  
<img src="ReadMEFigures/maya_stack.png">

```r
pal=ltc("maya",7,"continuous")
plts(pal, main = "maya")
```
  
<img src="ReadMEFigures/maya_sinus.png">

```r
pal=ltc("mterese",500,"continuous")
plts(col2transparent(pal, 75))
```

<img src="ReadMEFigures/mterese_sinus_transparent.png">

## R/theodosiou

### License

This package is free software; you can redistribute it and/or modify it
under the terms of the GNU General Public License, version 3, as
published by the Free Software Foundation.

This program is distributed in the hope that it will be useful, but
without any warranty; without even the implied warranty of
merchantability or fitness for a particular purpose.  See the GNU
General Public License for more details.

A copy of the GNU General Public License, version 3, is available at
<https://www.r-project.org/Licenses/GPL-3>
