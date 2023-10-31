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
