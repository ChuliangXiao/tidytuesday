
#### Load library

``` r
library(tidyverse)
library(readxl)
library(ggthemes)
```

#### Read in Data

``` r
file15    <- "../data/week15_beers.xlsx"
excel_sheets(file15)
```

    ## [1] "beers"     "breweries"

``` r
beer_df   <- read_xlsx(file15, 1)
brewer_df <- read_xlsx(file15, 2)

raw_df    <- left_join(beer_df, brewer_df, by = c("brewery_id" = "id")) %>% 
  mutate(abv = abv * 100)

beer5 <- raw_df %>% count(style) %>% arrange(desc(n)) %>% top_n(5) 
st_beer5 <- crossing(distinct(raw_df, state), beer5)

st_df <- raw_df %>% 
#  right_join(beer5) %>% 
  group_by(state, style) %>% 
  summarize(count = n()) %>% 
  right_join(st_beer5) %>% 
  arrange(state, desc(count)) %>% 
  slice(1:5) %>% 
  mutate(style = case_when(style == "American Double / Imperial IPA" ~ "A D/I IPA",
                           style == "American Blonde Ale" ~ "ABA",
                           style == "American Amber / Red Ale" ~ "A A/R A",
                           style == "American Pale Ale (APA)" ~ "APA",
                           style == "American IPA" ~ "A IPA")) %>% 
  {.}
```

### `geofacet` map

``` r
library(geofacet)
p1 <- st_df %>% 
  ggplot(aes(style, count)) + 
  geom_col() +
  coord_flip() +
  facet_geo(~ state) +
  theme_bw() +
  labs(title = "Numbers of Top 5 nationally most popular beer styles in each state",
       caption = "Source: Craft Beer USA"  ) +
  NULL
p1
```

![](Week15_files/figure-gfm/geofacet-1.png)<!-- -->

``` r
ggsave("top5_state.png", p1, dpi = 300)
```

### *ABV* Density ridge

``` r
library(ggridges)
library(viridis)
library(forcats)
beer10 <- raw_df %>% count(style) %>% arrange(desc(n)) %>% top_n(5) 
p2 <- raw_df %>% 
  filter(style %in% beer5$style) %>% 
  ggplot(aes(x =  abv, y = fct_rev(style), fill = ..x..)) +
  geom_density_ridges_gradient(scale = 2, rel_min_height = 0.01) +
  scale_fill_viridis(name = "ABV", option = "%") + 
  theme_minimal() +
  labs(title = "Alcohol by Volume (ABV) of Top 5 most popular beer styles",
       x = "Alcohol by volume (%)",
       y = "Craft Beer Style",
       caption = "Source: Craft Beer USA"  ) +
  NULL
p2  
```

![](Week15_files/figure-gfm/ridge-1.png)<!-- -->

``` r
ggsave("top5_ridge.png", p2, dpi = 300)
```

### Scatter *ABV* vs *IBU*

``` r
library(ggridges)
library(viridis)
library(forcats)
p3 <- raw_df %>% 
  filter(style %in% beer5$style) %>% 
  select(abv, ibu, style) %>% 
  drop_na() %>% 
  ggplot() + 
  geom_jitter(aes(x = abv, y = ibu, color = style), 
              size = 3, alpha = 0.8, width = 0.1, height = 1) +
  scale_color_brewer(palette = "Dark2")  + 
  theme_minimal() +
  theme(legend.position="right") +
  labs(title = "Bitterness (IBU) and Alcohol Content (ABV)",
       x = "Alcohol by volume (%)", 
       y = "Bitterness (International Bitterness Units)", 
       color="Craft beer styles",
       caption = "Source: Craft Beer USA"  ) +
  NULL
p3  
```

![](Week15_files/figure-gfm/Scatter-1.png)<!-- -->

``` r
ggsave("top5_scatter.png", p3, dpi = 300)
```

### Panel grid

``` r
library(patchwork)
#p1 + {p2 + p3 + plot_layout(ncol = 2)} + plot_layout(ncol = 1)
```
