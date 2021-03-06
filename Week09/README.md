TidyTuesday
===========

------------------------------------------------------------------------

### Week 9 - Comic Book Characters

[Comic book characters](https://github.com/rfordatascience/tidytuesday/blob/master/data/week9_comic_characters.csv)
[FiveThirtyEight package](https://github.com/rudeboybert/fivethirtyeight)
[FiveThirtyEight.com](https://fivethirtyeight.com/features/women-in-comic-books/)

------------------------------------------------------------------------

#### `theme_fivethirtyeight()` from the `ggthemes` package

##### New Characters Introduced per Year

Bar chart with `facet_wrap`

-   `scale_fill_manual` customizing the fill color
-   `scale_y_continuous` and `scale_x_continuous` customizing the coordinates
-   `strip.text.x` in `theme` adjusting the size of `face_wrap` titles

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week09/New_Characters.png)

##### Ration of New Female Characters Introduced per Year

Line plot

-   [`count()`](https://dplyr.tidyverse.org/reference/tally.html) to simplify the code
-   `geom_text`

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week09/Female_Characters.png)

##### Ration of Female Charaters Evolving with Year

-   `cumsum()` by year in `mutate`

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week09/Female_Characters_Cumulated.png)

##### Character Alignment by Gender

-   `replace_na()` to replace `NA`
-   `fct_relevel()` to relevel
-   `geom_text` customization
-   `annotate()` to add text

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week09/Alignment.png)
