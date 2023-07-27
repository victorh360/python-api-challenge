# python-api-challenge

## Overview

This assignment is split into two parts, the first part is contained within the WeatherPy file and the second being VacationPy.

In the first part we were provided with code that helped us generate a list of random cities around the globe using the OpenWeatherMap API. We then were to generate graphs and linear regression models to study the data for each city.

In the second part we took the list of cities that were generated in part one and plotted them on a map, we then narrowed down the list to cities that had favorable weather conditions and found hotels within those cities.

This assignment did use a lot of code that was covered in class, I just referred to class examples for most of it. Below I will cover a few of the parts that I found challenging and had to use other sources to solve.

### WeatherPy

-  Right away when I started the assignment I found I did not have citipy installed within the Anaconda environment I was working in. SO I had to install it to continue.

    https://pypi.org/project/citipy/

- For my linear regression models I took the code I generated during the last assignment (Module 5) and created a function around it.

    '''
    def regression(x_value, y_value, x_label, y_label, title):
    
    (slope, intercept, rvalue, pvalue, stderr) = linregress(x_value, y_value)
    regress_values = x_value * slope + intercept
    line_eq = f"y = {str(round(slope,2))} x + {str(round(intercept,2))}"
    
    plt.scatter(x_value, y_value)
    plt.plot(x_value, regress_values, "r-")
        
    
    plt.xlabel(x_label)
    plt.ylabel(y_label)
    plt.title(title)

    print(f"The r-value is: {round(rvalue,2)}")
    print(f"The linear regression model formula is: {line_eq}")
    '''

### VacationPy

- To add values for city and country when hovering over a point on the plot I had to refer to the link below.

https://discourse.holoviz.org/t/add-an-extra-field-when-hovering-in-hvplot-scatter/2331

    '''
    hover_cols=["City", "Country"]
    '''
- I could not remember how to add a blank column to my dataframe, so I just did a search rather than trying to go through two month's worth of notes

https://www.geeksforgeeks.org/how-to-add-empty-column-to-dataframe-in-pandas/#
    
    '''
    hotel_df["Hotel Name"] = ""
    '''

