
# TidyTuesday

-----

### Week 21 - California Fires

| Data                                                                                       | Source                                                                  | Article                                                                                                                                                                                         |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [California Fires](https://github.com/rfordatascience/tidytuesday/tree/master/data/week21) | [BuzzFeed.com](https://github.com/BuzzFeedNews/2018-07-wildfire-trends) | [BuzzFeed News - California Fires](https://www.buzzfeednews.com/article/peteraldhous/california-wildfires-people-climate), [RMarkdown](https://buzzfeednews.github.io/2018-07-wildfire-trends/) |

  - `data.table` read large csv files

<!-- end list -->

``` r
library(data.table)
files <- list.files(path = "../data/week20/", pattern = "*.csv", full.names = T)
DT <- do.call(rbind, lapply(files[-5], fread))
```

  - `gghightlight`  
    ![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week20/total.png)

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week20/cat4.png)
