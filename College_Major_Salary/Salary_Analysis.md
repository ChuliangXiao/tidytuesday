
## Reproducing David Robinson’s [Work](https://github.com/dgrtwo/data-screencasts/blob/master/college-majors.Rmd)

#### Load library

``` r
library(tidyverse)
library(ggthemes)
theme_set(theme_light())
```

#### Read in Data

``` r
dataDir <- "https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2018-10-16/recent-grads.csv"
major_df <- read_csv(dataDir) %>% 
  arrange(desc(Median)) %>% 
  mutate(Major = str_to_title(Major),
         Major = fct_reorder(Major, Median))
```
