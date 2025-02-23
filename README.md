# Bike Traffic in Boston Area

This project visualizes bike traffic data using an interactive map and a time-based filtering slider. The visualization displays the number of arrivals and departures at bike stations throughout the day. Users can filter bike trip data by time, providing a dynamic view of bike traffic based on user-defined time intervals. The project utilizes JavaScript, D3.js, and HTML/CSS for a smooth and responsive user experience.

## Features

- Interactive Map: Displays bike stations and their corresponding traffic data on an interactive map.
- Time Filter Slider: Users can filter bike trips by time of day (in minutes), with a slider ranging from -1 (no filter) to 1440 (representing each minute of the day).
- Dynamic Data Updates: The map dynamically updates based on the selected time filter, adjusting the traffic data and circle sizes for each station.
- Optimized Performance: With over a quarter of a million trips, the app leverages data filtering and performance optimizations such as pre-bucketing trips by minute to ensure smooth interactions.

## Usage

1. Time Slider: Adjust the slider to filter bike trips by time. The slider allows you to view trips that occurred within 60 minutes of the selected time.
2. Map Interaction: Hover over or click on stations to see detailed information about bike traffic, including arrivals, departures, and total trips.
3. Performance: As you adjust the time filter, the map and station circles dynamically update based on the selected filter, ensuring smooth performance even with large datasets.

## Tools

- D3.js: A powerful library for data visualization in JavaScript.
- Mapbox GL JS: For interactive maps and geospatial data visualization.

## How It Works

1. Data Loading: The bike trip data (bluebikes-traffic-2024-03.csv) is loaded via d3.csv(), and the started_at and ended_at fields are converted into JavaScript Date objects.
2. Time Filtering: A slider is used to filter bike trips by time. When the slider is adjusted, the map updates to show stations that have bike arrivals or departures within a 60-minute window from the selected time.
3. Station Traffic Calculation: The computeStationTraffic() function calculates the number of arrivals and departures for each bike station. The map then dynamically adjusts the size of the station markers based on the filtered traffic data.
4. Optimization: The project optimizes performance by pre-sorting trips into 1440 "buckets" (one for each minute of the day), reducing the filtering time for each slider adjustment.
