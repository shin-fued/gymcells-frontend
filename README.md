This Project is imported from Databrick platform, which use Delta Lake volume to store sql tables, so we cant import to github

However, we have convert all the data aside from weather station data into .csv file 
From the data_and_store.ipynb, line_man and file. There are over 54 api calls for each table of the database: 

this include:

	- hourly data from weather stations around asean countries from 2001 to 2024 roughly (200k rows per cities, 47 cities total)
 
 	- traffic report in Bangkok from 2012 to 2024 (roughly 100k each year)
	
	- traffic incident description from 2012 to 2024 (roughly 100k each year)
 
 	- food delivery in south east asia (300k)
	
	- Total of 12.8M rows
 
Main questions:

	- How do you know when should you bring an umbrella? (using hourly weather data)
 
 	- How does weather affect line man order (we order a lot of coffee/tea via line man) (using hourly weather data v food delivery data)
	
	- Can we predict weather pattern base on another location? (using pearson correlation and lag time analysis from weather data)
 
 	- Is there any correlation between traffic incident's severity and weather conditions
	
	- How does weather conditons affect type of traffic incidents

Conclusion:

	- How do you know when should you bring an umbrella? (using hourly weather data)
 		- There seems to be a slight correlation between rain and cloud which makes sense, or when there is a spike in clouds
   		- There seems to be no correlation between rainfall and temperature, as most of the temperature data are between 26-34
   
 
 	- How does weather affect line man order (we order a lot of coffee/tea via line man) (using hourly weather data v food delivery data)
   		- There's a mistake in data collection which sadly make the food delievery order unable to be used with the weather data.
     	 	- This is because all of the delivery dates are in the same day
	
	- Can we predict weather pattern base on another location? (using pearson correlation and lag time analysis from weather data)
     		- By using the Weather Region EDA, we can see a strong trend in temperature and temperature's change in time analysis within one hour range. 
		- For every 24 hours later, there's a strong chances that the changes in temperature and temperature value will be similar to each other 			nearby locations
		- some cities with close range may have similar temperatures, in both value and rate of changes
	 	- For time analysis of rainfall, there's little to no correlation in both rate and value between different locations.Though, cities with 		"very" close range will share simialr correaltion, 
    		in both one hour range, and up until 24 hours later
	 
 
 	- Is there any correlation between traffic incident's severity and weather conditions
	   	- Looking from the Traffic EDA, we can see that, for when traffic index is 10, there seems to be high rainfall, low temperature, and higher 			cloud 	coverage, medianly and averagely more than condition where traffic index is lower
    		- using kruskal test, there's a significant median difference of rainfall between one of the traffic index
    	   	- However, when using logistic regression, there seems to be little to no correlation at all
	
	- How does weather conditons affect type of traffic incidents?
 		-using Word Cloud EDA, when the rainfall is higher than usual, most traffic accidents happens around intersection.
	
# gymcells
