
# TidyTuesday

-----

### Week 20 - Russian Troll Tweets

| Data                                                                            | Source                                                                         | Article                                                                                                             |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| [Russian Troll Tweets](https://github.com/fivethirtyeight/russian-troll-tweets) | [FiveThirtyEight.com](https://github.com/fivethirtyeight/russian-troll-tweets) | [538 - Russian Troll Tweets](https://fivethirtyeight.com/features/why-were-sharing-3-million-russian-troll-tweets/) |

  - `data.table` read large csv files

<!-- end list -->

``` r
library(data.table)
files <- list.files(path = "../data/week20/", pattern = "*.csv", full.names = T)
DT <- do.call(rbind, lapply(files[-5], fread))
```

  - `gghightlight`  
    ![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week20/cat4.png)
