
# TidyTuesday

-----

### Week 14 - Global Life Expectancy

| Data                                                                                      | Source                                            | Article                                                          |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------- | ---------------------------------------------------------------- |
| [Global Life Expectancy](https://github.com/rfordatascience/tidytuesday/tree/master/data) | [ourworldindata.org](https://ourworldindata.org/) | [ourworldindata.org](https://ourworldindata.org/life-expectancy) |

### Simple Feature `sf`

  - Get world map in sf with `rnaturalearth::ne_download`  

<!-- end list -->

``` r
worldmap <- rnaturalearth::ne_download(scale = 110,
                                       type = "countries",
                                       category = "cultural",
                                       destdir = tempdir(),
                                       load = TRUE,
                                       returnclass = "sf") %>% 
  select(SOVEREIGNT, SOV_A3, ADMIN, ADM0_A3, geometry)
```

  - Convert `map` class to `sf`
      - Lots of mismatches between map and data

<!-- end list -->

``` r
world1 <- sf::st_as_sf(maps::map('world', plot = FALSE, fill = TRUE))

# data countries not in the worldmap
cnty1 <- read_csv("../data/week14_global_life_expectancy.csv") %>% 
  filter(!is.na(code)) %>% 
  anti_join(world1, by = c("country" = "ID")) %>% 
  distinct(country)
cnty1$country
```

    ##  [1] "Antigua and Barbuda"              "Channel Islands"                 
    ##  [3] "Congo"                            "Cote d'Ivoire"                   
    ##  [5] "Democratic Republic of Congo"     "Hong Kong"                       
    ##  [7] "Macao"                            "Melanesia"                       
    ##  [9] "Micronesia (country)"             "Polynesia"                       
    ## [11] "Saint Vincent and the Grenadines" "Timor"                           
    ## [13] "Trinidad and Tobago"              "United Kingdom"                  
    ## [15] "United States"                    "United States Virgin Islands"    
    ## [17] "World"

  - Problem using st\_as\_sf with non-closed polygons [`sf`
    issue](https://github.com/r-spatial/mapedit/issues/48)

<!-- end list -->

``` r
# Error
worldmap <- st_as_sf(rworldmap::getMap())
```

### Some plots

#### Life expectancy, 2015

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week14/life2015.png)

#### Animation from 1950 to 2015

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week14/life_expectancy.gif)
