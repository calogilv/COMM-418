In joining the 2015_murders_final dataset and 2016_murders_prelim dataset, I opted to use the 2016_murders_prelim data for 2015 murder data. This is based primarily on the [READ ME documentation](https://github.com/fivethirtyeight/data/blob/master/murder_2016/README.md) of the [GitHub file](http://fivethirtyeight.com/features/a-handful-of-cities-are-driving-2016s-rise-in-murders/) where the two databases are stored and the [538 story](http://fivethirtyeight.com/features/a-handful-of-cities-are-driving-2016s-rise-in-murders/) for which the data was compiled.

According to the [READ ME file](https://github.com/fivethirtyeight/data/blob/master/murder_2016/README.md), the 2015 data in the 2016_murders_prelim dataset are the number of murders that occured in each city in the same time period for which 2016 murder data was available. So, the 2015 data in the 2016_murders_prelim dataset is not the number of murders that happened in each city in 2015, but rather the number of murders that happened in each city through at least the middle of 2015, according to the [538 article](https://fivethirtyeight.com/features/a-handful-of-cities-are-driving-2016s-rise-in-murders/). 

The 2016 data is the data that is most recent and obviously should be included in the combined dataset I created with Datasette. But, it is inaccurate and unhelpful to compare the number of murders occuring in the first six months of 2016 to the number of murders occuring in the whole 12 months of 2015. So, I decided to use the 2016_murders_prelim 2015 data and not the 2015_murders_final 2015 data. The 2014 data serves as a good reference point for how many murders occured in a full year in recent history.

I used the following SQL query to obtain the table in the CSV file below.

SELECT "2015"."city", "2015"."state", "2015"."2014_murders", "2016"."2015_murders", "2016"."2016_murders" FROM murder_2015_final AS "2015"
JOIN murder_2016_prelim AS "2016" ON "2015"."city" = "2016"."city" AND "2015"."state" = "2016"."state"
ORDER BY "2016"."2016_murders" desc

| city                  | state          | 2014_murders | 2015_murders | 2016_murders |
|-----------------------|----------------|--------------|--------------|--------------|
| Chicago               | Illinois       | 411          | 378          | 536          |
| New York              | New York       | 333          | 266          | 252          |
| Baltimore             | Maryland       | 211          | 249          | 230          |
| Detroit               | Michigan       | 298          | 216          | 221          |
| Philadelphia          | Pennsylvania   | 248          | 209          | 213          |
| Houston               | Texas          | 242          | 191          | 212          |
| Los Angeles           | California     | 260          | 209          | 205          |
| Memphis               | Tennessee      | 140          | 114          | 158          |
| St. Louis             | Missouri       | 159          | 136          | 133          |
| New Orleans           | Louisiana      | 150          | 130          | 127          |
| Las Vegas             | Nevada         | 122          | 90           | 125          |
| Dallas                | Texas          | 116          | 95           | 118          |
| Indianapolis          | Indiana        | 136          | 102          | 117          |
| Phoenix               | Arizona        | 114          | 72           | 111          |
| San Antonio           | Texas          | 103          | 78           | 111          |
| Washington            | D.C.           | 105          | 119          | 105          |
| Kansas City           | Missouri       | 78           | 77           | 90           |
| Cleveland             | Ohio           | 63           | 96           | 89           |
| Atlanta               | Georgia        | 93           | 68           | 85           |
| Milwaukee             | Wisconsin      | 90           | 105          | 84           |
| Louisville            | Kentucky       | 56           | 52           | 79           |
| Jacksonville          | Florida        | 96           | 67           | 78           |
| Orlando               | Florida        | 15           | 19           | 73           |
| Newark                | New Jersey     | 93           | 76           | 72           |
| Columbus              | Ohio           | 83           | 71           | 70           |
| Tulsa                 | Oklahoma       | 46           | 43           | 52           |
| Oakland               | California     | 80           | 65           | 52           |
| Cincinnati            | Ohio           | 60           | 50           | 50           |
| Nashville             | Tennessee      | 41           | 47           | 49           |
| Fort Worth            | Texas          | 54           | 61           | 49           |
| Albuquerque           | New Mexico     | 30           | 35           | 46           |
| Pittsburgh            | Pennsylvania   | 69           | 46           | 46           |
| Miami                 | Florida        | 81           | 62           | 45           |
| Stockton              | California     | 49           | 30           | 38           |
| Buffalo               | New York       | 60           | 31           | 38           |
| San Jose              | California     | 32           | 22           | 35           |
| Fort Wayne            | Indiana        | 12           | 17           | 34           |
| Denver                | Colorado       | 31           | 32           | 33           |
| San Francisco         | California     | 45           | 35           | 32           |
| Oklahoma City         | Oklahoma       | 45           | 28           | 30           |
| Durham                | North Carolina | 21           | 25           | 30           |
| San Diego             | California     | 32           | 23           | 30           |
| Long Beach            | California     | 23           | 25           | 29           |
| Austin                | Texas          | 32           | 13           | 28           |
| Boston                | Massachusetts  | 53           | 28           | 28           |
| Minneapolis           | Minnesota      | 31           | 34           | 26           |
| Anchorage             | Alaska         | 12           | 19           | 26           |
| Charlotte-Mecklenburg | North Carolina | 47           | 27           | 25           |
| Bakersfield           | California     | 17           | 21           | 22           |
| Sacramento            | California     | 28           | 31           | 21           |
| Omaha                 | Nebraska       | 32           | 34           | 20           |
| Greensboro            | North Carolina | 23           | 15           | 20           |
| Santa Ana             | California     | 18           | 10           | 20           |
| Fresno                | California     | 47           | 30           | 19           |
| Tucson                | Arizona        | 35           | 23           | 18           |
| Arlington             | Texas          | 13           | 4            | 17           |
| Aurora                | Colorado       | 11           | 13           | 16           |
| Lexington             | Kentucky       | 20           | 13           | 16           |
| Colorado Springs      | Colorado       | 20           | 12           | 15           |
| Portland              | Oregon         | 26           | 19           | 14           |
| Jersey City           | New Jersey     | 24           | 11           | 14           |
| Seattle               | Washington     | 26           | 17           | 14           |
| El Paso               | Texas          | 21           | 12           | 14           |
| St. Petersburg        | Florida        | 19           | 9            | 14           |
| Virginia Beach        | Virginia       | 17           | 17           | 13           |
| Mobile                | Alabama        | 31           | 6            | 12           |
| Wichita               | Kansas         | 26           | 13           | 10           |
| Honolulu              | Hawaii         | 21           | 12           | 9            |
| Laredo                | Texas          | 14           | 7            | 9            |
| Lincoln               | Nebraska       | 7            | 0            | 9            |
| Corpus Christi        | Texas          | 27           | 10           | 9            |
| Toledo                | Ohio           | 24           | 5            | 8            |
| Raleigh               | North Carolina | 16           | 8            | 7            |
| Riverside             | California     | 12           | 6            | 7            |
| Plano                 | Texas          | 4            | 2            | 5            |
| Anaheim               | California     | 14           | 10           | 4            |
| Henderson             | Nevada         | 3            | 1            | 3            |
| Chandler              | Arizona        | 1            | 2            | 3            |
| Chula Vista           | California     | 7            | 5            | 1            |
