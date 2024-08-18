Data Source: https://www.kaggle.com/datasets/andreinovikov/used-cars-dataset
- A dataset of web-scraped car listings from Cars.com, collected in April 2023.
- Contains over 760,000 rows of data.

Reproduction Steps:
1. Extract data from the data zip file to the Step 1 Directory.
2. Run the Step 1 Jupyter Notebook
3. Copy and paste the clean data file to the Step 2, and Step 3 directory(s)
4. Run the Jupyter Notebooks in the Step 2, and Step 3 directory(s)

Project Objective: After experiencing a recent car breakdown, this project aims to leverage Machine Learning algorithms, specifically K-Means Clustering and Linear Regression, to gain insights into the current used car market. By applying data mining techniques, the goal is to identify natural groupings related to car prices and analyze the relationships between various factors influencing these prices. The ultimate objective is to help inform a decision on purchasing a new car.

Step 1: Clean Data:
- Tool Used: Jupyter Notebook 
- The data is cleaned and any missing/(NA) values are removed
- Any car prices above 150,000 are removed from the data set. This analysis aims to analyze cars that can commonly be seen within the tri-state area.(The most expensive cars luxury cars for example Lexus can cost upwards of $100,000)
- Any car prices below 5,000 are removed to filter out salvage and negotiable listings.
- Cars are grouped their maximum possible mileage; if the car is electric, set MPG to "No Fuel Used."

Step 2: K-Means Analysis
- Tool Used: Jupyter Notebook. 
- Define a K-Means analysis class within the Python script for ease of reuse and visualization. 
- Perform K-Means clustering on the following variable combinations:
	1. Price And Mileage
	2. Price Drop And Price
	3. Price And Price Drop
	4. Max_Mpg, Price, Mileage, And Price Drop 

Step 3: Regression Analysis
- Tool Used: Jupyter Notebook. 
- Define a regression analysis class to streamline exploration and recall of statistics/visualizations.
- Conduct regression analyses using the following models:
	1. Price = 𝑓(Year, Mileage, Max MPG, Accidents or Damage, One Owner, Personal Use Only, Seller Rating, Price Drop)
	2. Price = 𝑓(Year, Mileage)
	3.  Price = 𝑓(Mileage)
	4. Perform Analysis On: Price = 𝑓(Manufacturer, Year, Mileage)
	5. Perform Analysis On: Price Price = 𝑓(Manufacturer, Year, Mileage)+(Excluding Models with < 100 Rows)
	6. Perform Analysis On: Price = 𝑓(Accidents or Damage, Year, Mileage)+(Controls: Make, Model)
- Train a final regression model based on the results, specifically:Price = 𝑓(Accidents or Damage, Year, Mileage)+(Filter the data by a specific make/model, and filter out models with less than 300 observations)
- Generate predictions to illustrate linear relationships between year, mileage, and accidents on price.
- Visualize both predicted values and actual market prices for comparison.

Key Insights:
- The most effective way to predict car prices using linear regression is by accounting for the car's make and model.
- K-Means clustering on mileage and price drop reveals three natural groupings; the most intriguing group consists of cars with low mileage but a significant price drop.
- Different car models exhibit varying pricing patterns. For instance, Dodge Caravans tend to have more consistent pricing compared to other models. Used Dodge Caravans typically have high mileage but maintain stable prices.
- Depending on the model, car prices can significantly decrease based on the year of manufacture. For example, a 2011 Toyota Camry is predicted to be significantly cheaper than a 2023 model, even with comparable mileage.
- The developed linear regression model can be used to give ball park ideas of what used cars should be priced as. 
- My ideal car-buying strategy would be to purchase a used car with extremely low mileage and a significant price drop, as this combination generally offers the best value compared to buying a new vehicle.  