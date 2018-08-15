
#### Load library

``` r
library(tidyverse)
library(maps)
library(sf)
library(ggthemes)
library(patchwork)
```

#### Read in Data

``` r
raw_df    <- read_csv("../data/week14_global_life_expectancy.csv")
# Get non-country rows
cont_code <- raw_df %>% filter(is.na(code)) %>% distinct(country) 
```

##### get world map data

``` r
world1 <- sf::st_as_sf(map('world', plot = FALSE, fill = TRUE))
# update country names
map_df <- raw_df %>% 
  mutate(country = case_when(
    country == "United States" ~ "USA",
    country == "United Kingdom" ~ "UK",
    country == "Democratic Republic of Congo" ~ "Democratic Republic of the Congo",
    country == "Congo" ~ "Republic of the Congo",
    TRUE ~ country)) %>% 
  filter(!is.na(code)) %>% 
  left_join(world1, by = c("country" = "ID")
```

##### Problem using st\_as\_sf with non-closed polygons

``` r
# https://github.com/r-spatial/sf/issues/430
worldmap <- st_as_sf(rworldmap::getMap())
```

``` r
#ggplot() + geom_sf(data = world1)
worldmap <- rnaturalearth::ne_download(scale = 110,
                                       type = "countries",
                                       category = "cultural",
                                       destdir = tempdir(),
                                       load = TRUE,
                                       returnclass = "sf") %>% 
  select(SOVEREIGNT, SOV_A3, ADMIN, ADM0_A3, geometry)
```

    ## OGR data source with driver: ESRI Shapefile 
    ## Source: "/private/var/folders/5z/0c4j3v1s5tn2wzgy_t7b58lw0000gn/T/RtmpgQ4nYL", layer: "ne_110m_admin_0_countries"
    ## with 177 features
    ## It has 94 fields
    ## Integer64 fields read as strings:  POP_EST NE_ID

##### Join raw\_df and worldmap

``` r
# data countries not in the worldmap
cnty1 <- raw_df %>% 
  filter(!is.na(code)) %>% 
  anti_join(worldmap, by = c("code" = "ADM0_A3")) %>% 
  distinct(country)

# worldmap countries not in the data
cnty2 <- worldmap %>% 
  anti_join(raw_df, by = c("ADM0_A3" = "code")) %>% 
  as_tibble() %>% 
  distinct(ID)
```

    ## Warning: Trying to compute distinct() for variables not found in the data:
    ## - `ID`
    ## This is an error, but only a warning is raised for compatibility reasons.
    ## The operation will return the input unchanged.

``` r
map_df <- raw_df %>% 
  filter(!is.na(code)) %>% 
  left_join(worldmap, by = c("code" = "ADM0_A3"))
```

#### Life expectancy, 2015

``` r
library(scico)
library(hrbrthemes)
library(glue)
year1 <- 2015
p <- map_df %>% 
  filter(year == year1) %>% 
  ggplot() +
  geom_sf(aes(fill = life_expectancy)) + 
  scale_fill_scico(palette = "vik", na.value = "grey50") +
  labs(title = glue("Life expectancy, {year1}"), 
       subtitle = "Shown in the period of life expectancy at birth. This corresponds to the average estimate a newborn\ninfant would live if prevailing patterns of mortality at the time of birth were to stay the same throughout its life.",
       caption = "Source: Clio-Infra estimates until 1949; UN Population Division from 1950 to 2015",
       fill = "Life\nExpectancy") + 
  theme_ipsum() + 
  theme(plot.title = element_text(size = 18),
        plot.subtitle = element_text(size = 12),
        axis.title = element_blank(),
        axis.text = element_blank(), 
        panel.background = element_rect(fill = "grey95", color = NA), 
        plot.background = element_rect(fill = "grey95", color = NA))
p
```

![](Week14_files/figure-gfm/life%202015-1.png)<!-- -->

``` r
ggsave("life2015.png", p, dpi = 300)
```

#### Animation from 1950 to 2015

  - modified from \[dylanjm
    GitHub\](<https://github.com/dylanjm/tidy_tuesday/blob/master/tidy_14/tidy_14.R>}

<!-- end list -->

``` r
library(animation)
library(gganimate)

g <- map_df %>% 
  filter(year %in% seq(1950, 2015, 5)) %>% 
  ggplot(aes(frame = year)) +
  geom_sf(aes(fill = life_expectancy)) + 
  scale_fill_scico(palette = "vik", na.value = "grey50") +
  labs(title = "Life expectancy,", 
       subtitle = "Shown in the period of life expectancy at birth. This corresponds to the average estimate a newborn\ninfant would live if prevailing patterns of mortality at the time of birth were to stay the same throughout its life.",
       caption = "Source: Clio-Infra estimates until 1949; UN Population Division from 1950 to 2015",
       fill = "Life\nExpectancy") + 
  theme_ipsum() + 
  theme(plot.title = element_text(size = 18),
        plot.subtitle = element_text(size = 12),
        axis.title = element_blank(),
        axis.text = element_blank(), 
        panel.background = element_rect(fill = "grey95", color = NA), 
        plot.background = element_rect(fill = "grey95", color = NA))


animation::ani.options(interval = 1/8)
gganimate(g, "life_expectancy.gif", title_frame = T, ani.width = 1200,ani.height = 800)
```
