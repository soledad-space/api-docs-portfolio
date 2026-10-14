# Open-Meteo Weather API: Quickstart

Open-Meteo is a free weather API for non-commercial use. You give it a location and it returns current details―like temperatures, wind speeds, and whether the sun is up.
A farming app can use this information to tell farmers when it's too hot to plant seeds or too windy to spray their fields safely.

## Make a request

Send a request to this address:
```
https://api.open-meteo.com/v1/forecast?latitude=6.5&longitude=3.4&current_weather=true
```

The `longitude` and `latitude` values pinpoint the 
exact spot on Earth you want to check, while setting `current_weather=true` tells the API to return the current conditions for that location.

## Read the response

The API sends back the current weather. Here are some of the values:

- `temperature`: The current temperature in degrees Celsius (°C). Example: 26.5°C.
- `windspeed`: How fast the wind is blowing, measured in kilometers per hour (km/h). Example: 7.6 km/h.
- `winddirection`: The compass direction the wind is coming from, measured in degrees (0-360°). Example: 236°, meaning the wind is coming from roughly the southwest.
- `is_day`: Indicates daylight status. A value of 1 means daytime, while a value of 0 means nighttime. Example: 0 indicates night.
- `weathercode`: A numerical code representing current conditions like clear, cloudy, or rainy. Example: 3 translates to overcast.

## Handle errors

If the API returns an error instead of weather data, it usually means there is a typo in your request. The error looks like this: 

```json
{"error":true,"reason":"Not Found"}
```

Quick fixes to try: 

- Check your spelling: Look closely at the web address. For example, make sure `forecast` isn't accidentially misspelled as `foreast`.
- Verify your formatting: Ensure each setting in your request is properly separated by an ampersand (`&`). 
