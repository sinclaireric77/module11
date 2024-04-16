# module11
This is the second practical application of the program

This is a short summary of the work involved in this project. There are 6 parts to the Jupyter Notebook.
•	Business understanding
•	Data understanding
•	Data preparation
•	Modeling
•	Evaluation
•	Deployment

There are a total of 4 files in this repository (1 readme.md; 1 jupyter notebook – Used_Car_Prices_PA2.ipynb in the notebook folder and 2 images in the image folder)
The notebook can be found at: 
https://github.com/sinclaireric77/module11/blob/main/notebook/Used_Car_Prices_PA2.ipynb

1st part – Business understanding
Are there qualitative or quantitative parameters that affect the price of a car?
We will look at the database of used cars and try to find relationships between the price and various other features. We will also look at patterns in the data to try to create a model that can predict prices based on those features.

2nd part – Data understanding
The second part consists of understanding how the data is structured so we can work on target features and clean the data that is necessary for our analysis. Here, price will be our target (‘y’) and the rest of the features will be data we will apply different models on.

3rd part – Data Preparation
-	Removed unnecessary columns. 
-	Removed outliers from the price, year, and odometer features.
-	Removed NaN rows from manufacturer and model.
-	Applied the median to year and odometer NaN (median is better, as the graph is skewed)
-	Applied the median to transmission, fuel, title status and condition.
-	Changed cylinders from string to numeric (after conversion to numbers)

4th part – Modeling 
In this section, we tried 4 different models:
-	Linear Regression
-	Ridge Model (with GridSearch)
-	Lasso Model (with GridSearch)
-	Sequential Feature Selector with Polynomial Features
All the above were ran with a standard scaler function in a pipeline.
The best model ended up being the simpler, which is Linear Regression with the following coefficients:

![Coefs](https://github.com/sinclaireric77/module11/assets/160784197/9e9bc958-1163-4e03-9d48-551b032ac835)

 
5th part – Evaluation
So, our best model in this exercise is the linear regression model and it seems like the price of a car is correlated with the year and inversely correlated with the odometer. Then if we trickle down, we can see that the number of cylinders and the fuel will also affect the price but at a lesser level.
 
![Corr_matrix](https://github.com/sinclaireric77/module11/assets/160784197/e7612b21-b411-4ce3-9233-2279a9fea0cc)


6th part – Deployment 
So, during the course of our analysis, we found that the following parameters affect the price of a used car:


Positive impacts
- Year impacts the price of a car the highest with a direct correlation; the younger the car -> the higher the price
- The number of cylinders also impacts the price but in a smaller fashion; the more cylinders -> the higher the price

Negative impacts
- Odometer impacts the price in a negative way; the higher the mileage -> the lower the price
- The type of fuel also impacts the price; it seems like hybrid and electric cars tend to lose value faster than the other types
So, the recommendation is to get used cars that are younger, lower odometer with a higher number of cylinders and stay away from electric or hybrid vehicles.
In the next steps, we'll examine the impact of re-instating the state and the car manufacturer, possibly also looking at the paint color only on pricing fluctuation.
