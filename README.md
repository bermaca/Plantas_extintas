Trabajo plantas extintas
================

# Introduccion

Este trabajo corresponde a una practica para aprender a utilizar
Rmarkdown, del curso de Derek Corcoran. Se utilizaran datos de plantas
extintas en silvestria segun la \[*IUCN*\]
<https://www.iucnredlist.org/>.

Cargamos las librerias

``` r
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ ggplot2 3.3.2     ✓ purrr   0.3.4
    ## ✓ tibble  3.0.3     ✓ dplyr   1.0.2
    ## ✓ tidyr   1.1.2     ✓ stringr 1.4.0
    ## ✓ readr   1.3.1     ✓ forcats 0.5.0

    ## ── Conflicts ──────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

ahora el archivo

``` r
plants <- readr::read_csv("https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-08-18/plants.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   binomial_name = col_character(),
    ##   country = col_character(),
    ##   continent = col_character(),
    ##   group = col_character(),
    ##   year_last_seen = col_character(),
    ##   red_list_category = col_character()
    ## )

    ## See spec(...) for full column specifications.

# Filtro datos

Filtrano datos para hacer ejercicio. El codigo siguiente es para
resolver le problema del siguiente \[slide\]
(<https://derek-corcoran-barrios.github.io/Clase2/Clase2InvestigacionReproducible#29>).

``` r
Chile_plants <- plants %>%  filter(plants$country == "Chile") %>% 
  select(binomial_name, country, red_list_category)

Chile_plants
```

    ## # A tibble: 2 x 3
    ##   binomial_name           country red_list_category  
    ##   <chr>                   <chr>   <chr>              
    ## 1 Santalum fernandezianum Chile   Extinct            
    ## 2 Sophora toromiro        Chile   Extinct in the Wild

## Subtitulo
