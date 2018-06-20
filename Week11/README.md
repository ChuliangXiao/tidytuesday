TidyTuesday
===========

------------------------------------------------------------------------

### Week 11 - FIFA Word Cup

[FIFA World Cup Audience](https://github.com/rfordatascience/tidytuesday/blob/master/data/week11_fifa_audience.csv)  
[FiveThirtyEight package](https://github.com/rudeboybert/fivethirtyeight)  
[FiveThirtyEight.com](https://fivethirtyeight.com/features/how-to-break-fifa/)  

------------------------------------------------------------------------

#### `tidyverse` practice in this week

##### Table with `kableExtra`

<table class="table" style="margin-left: auto; margin-right: auto;">
 <thead>
<tr>
<th style="border-bottom:hidden" colspan="3"></th>
<th style="border-bottom:hidden; padding-bottom:0; padding-left:3px;padding-right:3px;text-align: center; " colspan="3"><div style="border-bottom: 1px solid #ddd; padding-bottom: 5px;">IN 2010, SHARE OF ...</div></th>
</tr>
  <tr>
   <th style="text-align:right;">  </th>
   <th style="text-align:left;"> COUNTRY </th>
   <th style="text-align:left;"> BODY </th>
   <th style="text-align:right;"> GLOBAL
POPULATION </th>
   <th style="text-align:right;"> WORLD CUP TV
AUDIENCE </th>
   <th style="text-align:right;"> GDP-WEIGHTED
AUDIENCE </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:left;"> United States </td>
   <td style="text-align:left;"> CONCACAF </td>
   <td style="text-align:right;"> 4.5 </td>
   <td style="text-align:right;"> 4.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 11.3 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:left;"> Japan </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 1.9 </td>
   <td style="text-align:right;"> 4.9 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 9.1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:left;"> China </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 19.5 </td>
   <td style="text-align:right;"> 14.8 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 7.3 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:left;"> Germany </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 1.2 </td>
   <td style="text-align:right;"> 2.9 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 6.3 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 5 </td>
   <td style="text-align:left;"> Brazil </td>
   <td style="text-align:left;"> CONMEBOL </td>
   <td style="text-align:right;"> 2.8 </td>
   <td style="text-align:right;"> 7.1 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 5.4 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:left;"> United Kingdom </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.9 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 4.2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 7 </td>
   <td style="text-align:left;"> Italy </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.9 </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 4.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:left;"> France </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.9 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 4.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 9 </td>
   <td style="text-align:left;"> Russia </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 2.1 </td>
   <td style="text-align:right;"> 3.1 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 3.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 10 </td>
   <td style="text-align:left;"> Spain </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.7 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 3.1 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 11 </td>
   <td style="text-align:left;"> South Korea </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 0.7 </td>
   <td style="text-align:right;"> 1.8 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 3.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 12 </td>
   <td style="text-align:left;"> Indonesia </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 3.5 </td>
   <td style="text-align:right;"> 6.7 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 2.9 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 13 </td>
   <td style="text-align:left;"> Mexico </td>
   <td style="text-align:left;"> CONCACAF </td>
   <td style="text-align:right;"> 1.7 </td>
   <td style="text-align:right;"> 3.2 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 2.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 14 </td>
   <td style="text-align:left;"> Turkey </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 1.1 </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 2.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 15 </td>
   <td style="text-align:left;"> Thailand </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 1.0 </td>
   <td style="text-align:right;"> 2.4 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 1.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 16 </td>
   <td style="text-align:left;"> Argentina </td>
   <td style="text-align:left;"> CONMEBOL </td>
   <td style="text-align:right;"> 0.6 </td>
   <td style="text-align:right;"> 1.5 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 1.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 17 </td>
   <td style="text-align:left;"> Netherlands </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:right;"> 0.6 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 1.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 18 </td>
   <td style="text-align:left;"> Poland </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.6 </td>
   <td style="text-align:right;"> 1.2 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 1.3 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 19 </td>
   <td style="text-align:left;"> Saudi Arabia </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 0.4 </td>
   <td style="text-align:right;"> 0.5 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 1.2 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 20 </td>
   <td style="text-align:left;"> Taiwan </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;"> 0.5 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 1.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 21 </td>
   <td style="text-align:left;"> Canada </td>
   <td style="text-align:left;"> CONCACAF </td>
   <td style="text-align:right;"> 0.5 </td>
   <td style="text-align:right;"> 0.5 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 1.0 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 22 </td>
   <td style="text-align:left;"> Colombia </td>
   <td style="text-align:left;"> CONMEBOL </td>
   <td style="text-align:right;"> 0.7 </td>
   <td style="text-align:right;"> 1.6 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.9 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 23 </td>
   <td style="text-align:left;"> Venezuela </td>
   <td style="text-align:left;"> CONMEBOL </td>
   <td style="text-align:right;"> 0.4 </td>
   <td style="text-align:right;"> 1.0 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.9 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 24 </td>
   <td style="text-align:left;"> South Africa </td>
   <td style="text-align:left;"> CAF </td>
   <td style="text-align:right;"> 0.7 </td>
   <td style="text-align:right;"> 1.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.8 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 25 </td>
   <td style="text-align:left;"> Malaysia </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 0.4 </td>
   <td style="text-align:right;"> 0.7 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.7 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 26 </td>
   <td style="text-align:left;"> Switzerland </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.1 </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.7 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 27 </td>
   <td style="text-align:left;"> Nigeria </td>
   <td style="text-align:left;"> CAF </td>
   <td style="text-align:right;"> 2.3 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.7 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 28 </td>
   <td style="text-align:left;"> Belgium </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.7 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 29 </td>
   <td style="text-align:left;"> Sweden </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.1 </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.7 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 30 </td>
   <td style="text-align:left;"> Vietnam </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 1.3 </td>
   <td style="text-align:right;"> 2.6 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 31 </td>
   <td style="text-align:left;"> Iran </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 1.1 </td>
   <td style="text-align:right;"> 0.7 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 32 </td>
   <td style="text-align:left;"> Chile </td>
   <td style="text-align:left;"> CONMEBOL </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;"> 0.6 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 33 </td>
   <td style="text-align:left;"> Romania </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;"> 0.7 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 34 </td>
   <td style="text-align:left;"> Austria </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.1 </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 35 </td>
   <td style="text-align:left;"> Singapore </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 0.1 </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.6 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 36 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 37 </td>
   <td style="text-align:left;"> Greece </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 38 </td>
   <td style="text-align:left;"> Portugal </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:right;"> 0.4 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 39 </td>
   <td style="text-align:left;"> India </td>
   <td style="text-align:left;"> AFC </td>
   <td style="text-align:right;"> 17.6 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 40 </td>
   <td style="text-align:left;"> Czech Republic </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:right;"> 0.3 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 41 </td>
   <td style="text-align:left;"> Egypt </td>
   <td style="text-align:left;"> CAF </td>
   <td style="text-align:right;"> 1.1 </td>
   <td style="text-align:right;"> 0.8 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.5 </td>
  </tr>
  <tr>
   <td style="text-align:right;"> 42 </td>
   <td style="text-align:left;"> Denmark </td>
   <td style="text-align:left;"> UEFA </td>
   <td style="text-align:right;"> 0.1 </td>
   <td style="text-align:right;"> 0.2 </td>
   <td style="text-align:right;background-color: #F5F5F5;"> 0.5 </td>
  </tr>
</tbody>
</table>

##### Treemap with `treemapify`

![](https://raw.githubusercontent.com/ChuliangXiao/tidytuesday/master/Week11/FIFA_TV.png)
