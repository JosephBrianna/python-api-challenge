# README: Hotel Search Script

## Overview

This script provides a means to search for hotels based on specified geographical parameters. Utilizing the Geoapify API, the script searches for accommodations within a specified radius of given latitude and longitude coordinates.

## Prerequisites

1. Ensure you have the required libraries installed. This script makes use of the `requests` library.
2. Obtain an API key from Geoapify.

## Script Details

### Set Parameters for Hotel Search

- `lat` and `lon`: Define the latitude and longitude range. 
  - Latitude is set between -90 and 90 degrees.
  - Longitude is set between -180 and 180 degrees.
  
- `radius`: Specifies the search radius in meters.

- `limit`: Determines the maximum number of results to return.

- `filters`: Provides a means to filter the search based on the defined circle with the given longitude, latitude, and radius.
 README contains a Python script that explores the relationship between weather variables and latitude for a list of cities. 

## **Dependencies and Setup**
1. The script begins by importing necessary libraries like `matplotlib`, `pandas`, `numpy`, `requests`, `time`, `pprint`, and `scipy.stats`.

2. It imports the OpenWeatherMap API key from a separate module `api_keys`.

3. The `citipy` library is imported to determine city names based on latitude and longitude coordinates.

## **Starter Code to Generate Random Geographic Coordinates and a List of Cities**
1. Empty lists are initialized for storing latitude-longitude combinations and city names.

2. Random latitude and longitude values are generated, which are then zipped together.

3. The `citipy` library is used to determine the nearest city for each latitude and longitude combination.

4. Unique city names are appended to the `cities` list.

5. The number of cities in the list is printed for confirmation.

## **Requirement 1: Create Plots to Showcase the Relationship Between Weather Variables and Latitude**
1. The OpenWeatherMap API is used to retrieve weather data for each city from the `cities` list.

2. An empty list `city_data` is initialized to store weather data for each city.

3. A loop processes each city, fetches its weather data, and appends the data to the `city_data` list.

4. If a city is not found in the OpenWeatherMap API, it is skipped.

5. The weather data for each city is converted into a pandas DataFrame and exported to a CSV file.

6. Scatter plots are created to showcase the relationship between:
   - Latitude vs. Temperature
   - Latitude vs. Humidity
   - Latitude vs. Cloudiness
   - Latitude vs. Wind Speed

   Each plot is saved as an image file.

## **Requirement 2: Compute Linear Regression for Each Relationship**
1. DataFrames are created for both the Northern Hemisphere (Latitude >= 0) and the Southern Hemisphere (Latitude < 0).

2. Linear regression plots are generated to showcase the relationship between Temperature and Latitude for both hemispheres.

The script ends after starting the linear regression for the Southern Hemisphere, and it seems that it would continue in a similar fashion for other weather variables.

The main objective of this script is to analyze how various weather parameters change with latitude, using data from OpenWeatherMap. The results are visualized using scatter plots, and linear regression is used to study the relationships further.

- `bias`: Prioritizes results based on their proximity to the given longitude and latitude.

- `categories`: Specifies the type of places you're searching for. This script focuses on accommodations such as hotels and holiday houses.

- `params`: A dictionary that contains all the parameters mentioned above and the API key.

### Searching for Hotels

- The script starts by printing the message "Starting hotel search".
  
- It then iterates through the `hotel_df` DataFrame. For each row in the DataFrame:
  
  - The latitude and longitude of the current city are retrieved.
  
  - The filter and bias parameters are updated in the `params` dictionary with the current city's latitude and longitude.
  
  - An API request is made to the Geoapify API using the `params` dictionary.
  
  - The API's response is parsed to extract the name of the first hotel in the result.
  
  - If no hotel is found, "No hotel found" is recorded for that city.
  
  - The name of the hotel (or "No hotel found") is logged alongside the city name.

### Output

- The script displays a sample of the `hotel_df` DataFrame, which will include the city name and the nearest hotel.

## Usage

1. Set the `geoapify_key` variable with your Geoapify API key.
2. Run the script.
3. Review the displayed data to see the nearest hotel for each city in the `hotel_df` DataFrame.

## Note

Ensure that you handle API rate limits and potential charges if your usage exceeds the free tier on Geoapify. Always check the API documentation for any updates or changes.
