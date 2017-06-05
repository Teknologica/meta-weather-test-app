# meta-weather-test-app
Simple Test App using the MetaWeather API

## Task Details
- Consume the [MetaWeather  API](https://www.metaweather.com/api/) to fetch the city results matching your search query (JSON).
- Create an interface with at least one input field to be used to search for cities by name.
- Present the results in real time and update the interface as the user types his search query.
- Once the results are displayed allow the user to click on any particular city to view its current weather forecast.
- On the city details view display at least the current temperature and state name (e.g. rain, snow, etc.) and the picture representation of the state. You can include any other information provided by the API if you want.
- Make your code and UI as clean as possible, be creative!
- *You have five business days from the moment you received the email linking to this repository to complete your task.*

## Requirements
- You can fork this repo or make your own.
- Please use ES6, Typescript or ES5. *No CoffeeScript*.
- You must create a SPA.
- You can use any version of Angular, React or [Vue](https://vuejs.org/) (alternatively any framework you are most comfortable with).
- You can include a `package.json` or other build tools and processors (Webpack, Babel, SASS tools, etc.).
- You can use any CSS framework or make your own styles.
- Please provide any install or runtime instructions in the `readme.md`, make sure we can actually run your project.

---
## MetaWeather API Examples
Please note that the MetaWeather API does not require any form of authentication. See the [MetaWeather API documentation](https://www.metaweather.com/api/) for all supported methods and parameters.

### Search city by query

```
https://www.metaweather.com/api/location/search/?query=tor
```
- Returns an array of JSON objects with the city title (name) and its `woeid`
- Use the `woeid` to get the weather details for that particular city


#### Query Result Structure
```json
[{
	"title": "Toronto",
	"location_type": "City",
	"woeid": 4118,
	"latt_long": "43.648560,-79.385368"
}, {
	"title": "Santorini",
	"location_type": "City",
	"woeid": 56558361,
	"latt_long": "36.406651,25.456530"
}, {
	"title": "Torino",
	"location_type": "City",
	"woeid": 725003,
	"latt_long": "45.070290,7.667680"
}]
```

### View city forecast by `woeid`
```
https://www.metaweather.com/api/location/4118/
```
- Using the `woeid` provided by the search results will let you fetch the forecast of a particular city.
- Use `weather_state_name` and `the_temperature` to display the weather state and current temperature. 
- Use `weather_state_abbr` to display an SVG of the current weather state.

#### Query Result Structure
```json
{
	"consolidated_weather": [{
		"id": 5164477443997696,
		"weather_state_name": "Light Rain",
		"weather_state_abbr": "lr",
		"wind_direction_compass": "NE",
		"created": "2017-06-05T17:28:23.939780Z",
		"applicable_date": "2017-06-05",
		"min_temp": 12.515714285714285,
		"max_temp": 17.098571428571429,
		"the_temp": 16.436666666666667,
		"wind_speed": 6.9220919499210334,
		"wind_direction": 40.308252778015692,
		"air_pressure": 1004.4549999999999,
		"humidity": 88,
		"visibility": 10.320043446273761,
		"predictability": 75
	}, {
		"id": 5545789673701376,
		"weather_state_name": "Heavy Rain",
		"weather_state_abbr": "hr",
		"wind_direction_compass": "NNE",
		"created": "2017-06-05T17:28:26.161050Z",
		"applicable_date": "2017-06-06",
		"min_temp": 11.298333333333334,
		"max_temp": 14.473333333333334,
		"the_temp": 14.07,
		"wind_speed": 11.769189697474749,
		"wind_direction": 17.370385971029176,
		"air_pressure": 1005.775,
		"humidity": 88,
		"visibility": 7.5276013083591824,
		"predictability": 77
	}, {
		"id": 5341258297901056,
		"weather_state_name": "Heavy Cloud",
		"weather_state_abbr": "hc",
		"wind_direction_compass": "ENE",
		"created": "2017-06-05T17:28:28.613370Z",
		"applicable_date": "2017-06-07",
		"min_temp": 10.775,
		"max_temp": 16.079999999999998,
		"the_temp": 14.959999999999999,
		"wind_speed": 9.1475660281582218,
		"wind_direction": 66.231623591824246,
		"air_pressure": 1013.925,
		"humidity": 77,
		"visibility": 13.811217489859223,
		"predictability": 71
	}, {
		"id": 5355935006457856,
		"weather_state_name": "Heavy Cloud",
		"weather_state_abbr": "hc",
		"wind_direction_compass": "E",
		"created": "2017-06-05T17:28:32.283310Z",
		"applicable_date": "2017-06-08",
		"min_temp": 12.549999999999999,
		"max_temp": 18.956666666666667,
		"the_temp": 18.949999999999999,
		"wind_speed": 4.0728328822556277,
		"wind_direction": 87.511769455655298,
		"air_pressure": 1008.2850000000001,
		"humidity": 70,
		"visibility": 13.349849379623002,
		"predictability": 71
	}, {
		"id": 6250233029722112,
		"weather_state_name": "Showers",
		"weather_state_abbr": "s",
		"wind_direction_compass": "SW",
		"created": "2017-06-05T17:28:35.340410Z",
		"applicable_date": "2017-06-09",
		"min_temp": 13.395000000000001,
		"max_temp": 21.071666666666669,
		"the_temp": 20.106666666666666,
		"wind_speed": 6.7286720071475914,
		"wind_direction": 235.16988507771015,
		"air_pressure": 1009.61,
		"humidity": 70,
		"visibility": 15.104912312097351,
		"predictability": 73
	}, {
		"id": 5132786692259840,
		"weather_state_name": "Showers",
		"weather_state_abbr": "s",
		"wind_direction_compass": "SW",
		"created": "2017-06-05T17:28:38.179210Z",
		"applicable_date": "2017-06-10",
		"min_temp": 14.776666666666666,
		"max_temp": 21.376666666666665,
		"the_temp": 19.189999999999998,
		"wind_speed": 6.9461976457488266,
		"wind_direction": 219.07452456269428,
		"air_pressure": 1009.6799999999999,
		"humidity": 78,
		"visibility": null,
		"predictability": 73
	}],
	"time": "2017-06-05T15:41:59.426930-04:00",
	"sun_rise": "2017-06-05T05:37:06.290358-04:00",
	"sun_set": "2017-06-05T20:54:47.098507-04:00",
	"timezone_name": "LMT",
	"parent": {
		"title": "Canada",
		"location_type": "Country",
		"woeid": 23424775,
		"latt_long": "56.954681,-98.308968"
	},
	"sources": [{
		"title": "BBC",
		"slug": "bbc",
		"url": "http://www.bbc.co.uk/weather/",
		"crawl_rate": 180
	}, {
		"title": "Forecast.io",
		"slug": "forecast-io",
		"url": "http://forecast.io/",
		"crawl_rate": 480
	}, {
		"title": "HAMweather",
		"slug": "hamweather",
		"url": "http://www.hamweather.com/",
		"crawl_rate": 360
	}, {
		"title": "Met Office",
		"slug": "met-office",
		"url": "http://www.metoffice.gov.uk/",
		"crawl_rate": 180
	}, {
		"title": "OpenWeatherMap",
		"slug": "openweathermap",
		"url": "http://openweathermap.org/",
		"crawl_rate": 360
	}, {
		"title": "Weather Underground",
		"slug": "wunderground",
		"url": "https://www.wunderground.com/?apiref=fc30dc3cd224e19b",
		"crawl_rate": 720
	}, {
		"title": "World Weather Online",
		"slug": "world-weather-online",
		"url": "http://www.worldweatheronline.com/",
		"crawl_rate": 360
	}, {
		"title": "Yahoo",
		"slug": "yahoo",
		"url": "http://weather.yahoo.com/",
		"crawl_rate": 180
	}],
	"title": "Toronto",
	"location_type": "City",
	"woeid": 4118,
	"latt_long": "43.648560,-79.385368",
	"timezone": "America/Toronto"
}
```
### View weather state image
MetaWeather provides state images in SVG format to represent different states (rain, snow, etc.). Append the value of `weather_state_abbr` from the results above and `.svg` to `https://www.metaweather.com/static/img/weather/` to get it.
<br><br>_e.g if `weather_state_abbr` is `s` then `s.svg` is the intended image_
```
https://www.metaweather.com/static/img/weather/s.svg
```
<img src="https://www.metaweather.com/static/img/weather/s.svg" width="100" />

## Credits
- Thanks to [MetaWeather](https://www.metaweather.com/) for providing an Open API to the Internet. 
- Find more Public APIs in this repo: https://github.com/toddmotto/public-apis
