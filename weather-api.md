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