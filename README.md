# python-api-challenge
Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

## Part I - WeatherPy

Creatie a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. Create a representative model of weather across world cities.

First requirement is to create a series of scatter plots to showcase the following relationships:

After each plot, add a sentence or two explaining what the code is analyzing.

### Scatter Analysis

#### Temperature (F) vs. Latitude
![Temperature (F) vs. Latitude](Images/Fig1.png)


The above scatter plot analyzies the latitudes of cities (north or south) of the equator against their correponding maximum temperatures (in degrees fahrenheit). Temperatures rise the closer a city is in relation to the equator. Cities south of the equator have higher maximum temperatures in comparison to cities north of the equator. 

#### Humidity (%) vs. Latitude
![Humidity (%) vs. Latitude](Images/Fig2.png)

The above scatter plot analyzies percent humidity against the latitudinal of a city in relation to the equator. There seems to be no apparently noticeable relationship between humidity and geolocation.

#### Cloudiness (%) vs. Latitude
![Cloudiness (%) vs. Latitude](Images/Fig3.png)

The scatter plot of Cloudiness vs. Latitude does does not show any associations between cloud cover and latitudial location.

#### Wind Speed (mph) vs. Latitude
![Wind Speed (mph) vs. Latitude](Images/Fig4.png)

The Wind Speed vs Latitude Scatter Plot shows no apparent associations between wind speed and geolocation for cities north or south of the equator.


second requirement is to run linear regression on each relationship. Separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

After each pair of plots, take the time to explain what the linear regression is modeling. For example, describe any relationships you notice and any other analysis you may have.

### Linear Regression

The northern hemisphere has 383 cities out of 569 total, accounting for 67.3% of cities in the dataset.

The southern hemisphere has 186 cities out of 569 total, accounting for 32.7% of cities in the dataset.

#### Northern Hemisphere - Temperature (F) vs. Latitude
![Northern Hemisphere - Temperature (F) vs. Latitude](Images/Fig5_N.png)

Line of Best-Fit for linear regression is y=-1.44x+97.68
The r-squared correlation coefficient is -0.85

According to the linear regression of maximum temperature vs latitude for the cities in the northern hemisphere, there is a strong negative correlation. The farther away a city's geolocation is to the equator the colder the climate conditions.  


#### Southern Hemisphere - Temperature (F) vs. Latitude
![Southern Hemisphere - Temperature (F) vs. Latitude](Images/Fig6_S.png)

Equation for best-fit linear regression line is y=0.29x+81.08
r-squared correlation coefficient is 0.46

The above linear regression shows a positive relationship between geolocation of cities in the southern hemisphere relative to the equator and their cooresopnding climate conditions. The cities closer to the equator enjoy warmer climate conditions and therefore higher maximum temperatures. 

#### Northern Hemisphere - Humidity (%) vs. Latitude
![Northern Hemisphere - Humidity (%) vs. Latitud](Images/Fig7_N.png)

Equation for best-fit linear regression line is y=0.51x+50.34
r-squared correlation coefficient is 0.44

Dispite the somewhat positive correlation coefficient for the linear regression of Humidity (%) vs. Latitude for cities in the northern hemisphere, the outliers throughout makes the results for this particular dataset skewed. There should not be any noticable correlation between humidity for cities in respect to their geolocation from the equator. 

#### Southern Hemisphere - Humidity (%) vs. Latitude
![Southern Hemisphere - Humidity (%) vs. Latitude](Images/Fig8_S.png)

Equation for best-fit linear regression line is y=0.38x+80.92
r-squared correlation coefficient is 0.25

Likewise there should be little to no assoication between humidity and geolocation for cities in the southern hemisphere.

#### Northern Hemisphere - Cloudiness (%) vs. Latitude
![Northern Hemisphere - Cloudiness (%) vs. Latitude](Images/Fig9_N.png)

Equation for best-fit linear regression line is y=0.62x+28.74
r-squared correlation coefficient is 0.31

Judging from the overall data spread, there should be little to no correlation between cloud coverage and geolocation for cities in the northern hemisphere. 

#### Southern Hemisphere - Cloudiness (%) vs. Latitude
![Southern Hemisphere - Cloudiness (%) vs. Latitude](Images/Fig10_S.png)

Equation for best-fit linear regression line is y=1.07x+78.73
r-squared correlation coefficient is 0.38

Similarly, there should also be little to no correlation between cloud coverage and geolocation for cities in the southern hemisphere. 

#### Northern Hemisphere - Wind Speed (mph) vs. Latitude
![Northern Hemisphere - Wind Speed (mph) vs. Latitude](Images/Fig11_N.png)

Equation for best-fit linear regression line is y=0.08x+5.34
r-squared correlation coefficient is 0.23

According to the the correlation coefficient for the linear regression for Wind Speed (mph) vs. Latitude, there should be almost no or slightly weak positive correlation between wind speed and geolocation away from the equator. This data could be skewed by the outliers for a few very windy northern cities. 


#### Southern Hemisphere - Wind Speed (mph) vs. Latitude
![Southern Hemisphere - Wind Speed (mph) vs. Latitude](Images/Fig12_S.png)

Equation for best-fit linear regression line is y=-0.08x+6.31
r-squared correlation coefficient is -0.19

Reasonably should also not be any association between wind speed and geolocation away from the equator for cities in the southern hemisphere.  


#### Final notebook must have:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Use your skills in working with weather data to plan future vacations. Use jupyter-gmaps and the Google Places API for this part of the assignment.

* Create a heat map that displays the humidity for every city from Part I.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't contain all three conditions. You want to be sure the weather is ideal.

  Adjust to your specifications but be sure to limit the number of rows returned by your API requests to a reasonable number.

  * Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)

### Final Considerations/Observations:

After gathering and analyzing api data on weather conditions: temperture, humidity, cloud cover, wind speed, and geolocation (latitudinal distance from the equator) for 565 cities in both the northern (384) and southern (181) hemisphere for the month of Febuary 2022, there seems to be a strongly negative correlation between temperature (in degrees Fahrenheit) and geolocation from the equator for cities in the northern hemisphere and a slightly positive correlation for the same metrics for cities located in the southern hemisphere. The farther away a city is located from the equator (0 degrees latitude) the colder the climate, mainly for the ranges beyond the range of -20 to 20 (degrees latitude).

There seems to be little to no statistically relevent correlation between humidity, cloudiness, and wind speed with geolocation in respects to the equator as the data points are spreaded throughout and does not form a logical pattern that when not skewed by server outliers. Wind speed between over 30 mph can be found for a specific cities in the northern hemisphere located between 60 and 70 (degrees latitude) such as Sørland (67.6670, 32.26). There are also outliers like Isangel (40.18, -19.5500) and Vao (-22.6667, 30.29) for the southern hemisphere with also with over 30 mph wind speeds.

There is no observable correlation for cloudiness (cloud cover) and geolocation for all cities (both north and south of the equator). The data points appear to be randomly scattered all through out the linear regression plot with no obvious association that can be analyzed.

#### Additional Instructions 

* You must complete your analysis using a Jupyter notebook.
* You must use the Matplotlib or Pandas plotting libraries.
* For Part I, you must include a written description of three observable trends based on the data.
* For Part II, you must include a screenshot of the heatmap you create and include it in your submission.
* You must use proper labeling of your plots, including aspects like: Plot Titles (with date of analysis) and Axes Labels.
* For max intensity in the heat map, try setting it to the highest humidity found in the data set.
