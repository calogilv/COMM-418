In joining the 2015_murders_final dataset and 2016_murders_prelim dataset, I opted to use the 2016_murders_prelim data for 2015 murder data. This is based primarily on the [READ ME documentation](https://github.com/fivethirtyeight/data/blob/master/murder_2016/README.md) of the [GitHub file](http://fivethirtyeight.com/features/a-handful-of-cities-are-driving-2016s-rise-in-murders/) where the two databases are stored and the [538 story]([http://fivethirtyeight.com/features/a-handful-of-cities-are-driving-2016s-rise-in-murders/]) for which the data was compiled.

According to the [READ ME file](https://github.com/fivethirtyeight/data/blob/master/murder_2016/README.md), the 2015 data in the 2016_murders_prelim dataset are the number of murders that occured in each city in the same time period for which 2016 murder data was available. So, the 2015 data in the 2016_murders_prelim dataset is not the number murders that happened in each city in 2015, but rather the number of murders that happened in each city through at least the middle of 2015, according to the [538 article](https://fivethirtyeight.com/features/a-handful-of-cities-are-driving-2016s-rise-in-murders/). 

The 2016 data is the data that is most recent and obviously should be included in the database I created with Datasette. But it is inaccurate and unhelpful to compare the number of murders occuring in the first six months of 2016 to the number of murders occuring in the whole 12 months of 2015. So, I decided to use the 2016_murders_prelim 2015 data and not the 2015_murders_final 2015 data. The 2014 data serves as a good reference point for how many murders occured in a full year in recent history.

I used the following SQL query to obtain the table in the CSV file below.

SELECT "2015"."city", "2015"."state", "2015"."2014_murders", "2015"."2015_murders", "2016"."2015_murders", "2016"."2016_murders" FROM murder_2015_final AS "2015"
JOIN murder_2016_prelim AS "2016" ON "2015"."city" = "2016"."city" AND "2015"."state" = "2016"."state"

| city                  | state          | 2014_murders | 2015_murders | 2015_murders | 2016_murders |
|-----------------------|----------------|--------------|--------------|--------------|--------------|
| Baltimore             | Maryland       | 211          | 344          | 249          | 230          |
| Chicago               | Illinois       | 411          | 478          | 378          | 536          |
| Houston               | Texas          | 242          | 303          | 191          | 212          |
| Cleveland             | Ohio           | 63           | 120          | 96           | 89           |
| Washington            | D.C.           | 105          | 162          | 119          | 105          |
| Milwaukee             | Wisconsin      | 90           | 145          | 105          | 84           |
| Philadelphia          | Pennsylvania   | 248          | 280          | 209          | 213          |
| Kansas City           | Missouri       | 78           | 109          | 77           | 90           |
| Nashville             | Tennessee      | 41           | 72           | 47           | 49           |
| St. Louis             | Missouri       | 159          | 188          | 136          | 133          |
| Oklahoma City         | Oklahoma       | 45           | 73           | 28           | 30           |
| Louisville            | Kentucky       | 56           | 81           | 52           | 79           |
| Denver                | Colorado       | 31           | 53           | 32           | 33           |
| Los Angeles           | California     | 260          | 282          | 209          | 205          |
| Dallas                | Texas          | 116          | 136          | 95           | 118          |
| New York              | New York       | 333          | 352          | 266          | 252          |
| Orlando               | Florida        | 15           | 32           | 19           | 73           |
| Minneapolis           | Minnesota      | 31           | 47           | 34           | 26           |
| Omaha                 | Nebraska       | 32           | 48           | 34           | 20           |
| Sacramento            | California     | 28           | 43           | 31           | 21           |
| Anchorage             | Alaska         | 12           | 26           | 19           | 26           |
| Charlotte-Mecklenburg | North Carolina | 47           | 61           | 27           | 25           |
| New Orleans           | Louisiana      | 150          | 164          | 130          | 127          |
| Albuquerque           | New Mexico     | 30           | 43           | 35           | 46           |
| Aurora                | Colorado       | 11           | 24           | 13           | 16           |
| Fort Wayne            | Indiana        | 12           | 25           | 17           | 34           |
| Long Beach            | California     | 23           | 36           | 25           | 29           |
| Durham                | North Carolina | 21           | 34           | 25           | 30           |
| Indianapolis          | Indiana        | 136          | 148          | 102          | 117          |
| Newark                | New Jersey     | 93           | 104          | 76           | 72           |
| Tulsa                 | Oklahoma       | 46           | 55           | 43           | 52           |
| Portland              | Oregon         | 26           | 34           | 19           | 14           |
| San Francisco         | California     | 45           | 53           | 35           | 32           |
| Cincinnati            | Ohio           | 60           | 66           | 50           | 50           |
| Bakersfield           | California     | 17           | 22           | 21           | 22           |
| Colorado Springs      | Colorado       | 20           | 25           | 12           | 15           |
| Las Vegas             | Nevada         | 122          | 127          | 90           | 125          |
| Oakland               | California     | 80           | 85           | 65           | 52           |
| San Diego             | California     | 32           | 37           | 23           | 30           |
| Anaheim               | California     | 14           | 18           | 10           | 4            |
| Greensboro            | North Carolina | 23           | 26           | 15           | 20           |
| Jersey City           | New Jersey     | 24           | 27           | 11           | 14           |
| Fort Worth            | Texas          | 54           | 56           | 61           | 49           |
| Virginia Beach        | Virginia       | 17           | 19           | 17           | 13           |
| Atlanta               | Georgia        | 93           | 94           | 68           | 85           |
| Henderson             | Nevada         | 3            | 4            | 1            | 3            |
| Jacksonville          | Florida        | 96           | 97           | 67           | 78           |
| Raleigh               | North Carolina | 16           | 17           | 8            | 7            |
| Wichita               | Kansas         | 26           | 27           | 13           | 10           |
| Chandler              | Arizona        | 1            | 1            | 2            | 3            |
| Plano                 | Texas          | 4            | 4            | 2            | 5            |
| Stockton              | California     | 49           | 49           | 30           | 38           |
| Toledo                | Ohio           | 24           | 24           | 5            | 8            |
| Chula Vista           | California     | 7            | 6            | 5            | 1            |
| Phoenix               | Arizona        | 114          | 112          | 72           | 111          |
| Riverside             | California     | 12           | 10           | 6            | 7            |
| San Jose              | California     | 32           | 30           | 22           | 35           |
| Detroit               | Michigan       | 298          | 295          | 216          | 221          |
| Seattle               | Washington     | 26           | 23           | 17           | 14           |
| El Paso               | Texas          | 21           | 17           | 12           | 14           |
| Tucson                | Arizona        | 35           | 31           | 23           | 18           |
| Arlington             | Texas          | 13           | 8            | 4            | 17           |
| Lexington             | Kentucky       | 20           | 15           | 13           | 16           |
| Memphis               | Tennessee      | 140          | 135          | 114          | 158          |
| St. Petersburg        | Florida        | 19           | 14           | 9            | 14           |
| Columbus              | Ohio           | 83           | 77           | 71           | 70           |
| Honolulu              | Hawaii         | 21           | 15           | 12           | 9            |
| Laredo                | Texas          | 14           | 8            | 7            | 9            |
| Lincoln               | Nebraska       | 7            | 1            | 0            | 9            |
| Miami                 | Florida        | 81           | 75           | 62           | 45           |
| Santa Ana             | California     | 18           | 12           | 10           | 20           |
| Mobile                | Alabama        | 31           | 24           | 6            | 12           |
| Fresno                | California     | 47           | 39           | 30           | 19           |
| Austin                | Texas          | 32           | 23           | 13           | 28           |
| San Antonio           | Texas          | 103          | 94           | 78           | 111          |
| Corpus Christi        | Texas          | 27           | 17           | 10           | 9            |
| Pittsburgh            | Pennsylvania   | 69           | 57           | 46           | 46           |
| Boston                | Massachusetts  | 53           | 38           | 28           | 28           |
| Buffalo               | New York       | 60           | 41           | 31           | 38           |
