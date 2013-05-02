Forecast - Weather information for Node.js
=================================================

The aim of this module is to provide a common API for multiple weather providers and to return the results as a normalized Object.

However [Forecast.io](http://forecast.io) is the only provider supported at the moment. More coming soon!

##Install
```bash
$ npm install forecast
```

##Usage
```javascript
var Forecast = require('forecast');

var forecast = new Forecast({
    service: 'forecast.io'
  , key: 'your-api-key'
  , units: 'celcius' // Only the first letter is parsed so you can type Fahrenheit, Celcius, centigrade, FahrenPoop, etc.
  , cache: true      // Cache API requests?
  , ttl: {           // How long to cache requests. Uses syntax from moment.js: http://momentjs.com/docs/#/durations/creating/
        minutes: 27
      , seconds: 45
    }
});

forecast.get([-33.8683, 151.2086], function(err, weather) {
  if(err) console.dir(err);
  else console.dir(weather);
});
```

##Example Output
```javascript
{ latitude: -33.8683,
  longitude: 151.2086,
  timezone: 'Australia/Sydney',
  offset: 10,
  currently: 
   { time: 1367471626,
     summary: 'Partly Cloudy',
     icon: 'partly-cloudy-day',
     precipIntensity: 0.088,
     precipProbability: 0.07,
     precipType: 'rain',
     temperature: 20.4,
     dewPoint: 12.24,
     windSpeed: 5.83,
     windBearing: 178,
     cloudCover: 0.32,
     humidity: 0.65,
     pressure: 1024.35,
     ozone: 275.6 },
  hourly: 
   { summary: 'Partly cloudy until tomorrow morning.',
     icon: 'partly-cloudy-day',
     data: 
      [ { time: 1367470800,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-day',
          precipIntensity: 0.087,
          precipProbability: 0.07,
          precipType: 'rain',
          temperature: 20.42,
          dewPoint: 12.26,
          windSpeed: 5.89,
          windBearing: 179,
          cloudCover: 0.32,
          humidity: 0.65,
          pressure: 1024.31,
          ozone: 275.72 },
        { time: 1367474400,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-day',
          precipIntensity: 0.091,
          precipProbability: 0.08,
          precipType: 'rain',
          temperature: 20.32,
          dewPoint: 12.16,
          windSpeed: 5.66,
          windBearing: 177,
          cloudCover: 0.31,
          humidity: 0.66,
          pressure: 1024.47,
          ozone: 275.17 },
        { time: 1367478000,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-day',
          precipIntensity: 0.089,
          precipProbability: 0.08,
          precipType: 'rain',
          temperature: 19.92,
          dewPoint: 12.2,
          windSpeed: 5.42,
          windBearing: 178,
          cloudCover: 0.22,
          humidity: 0.67,
          pressure: 1024.87,
          ozone: 274.62 },
        { time: 1367481600,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0.082,
          precipProbability: 0.07,
          precipType: 'rain',
          temperature: 19.23,
          dewPoint: 12.24,
          windSpeed: 5.15,
          windBearing: 180,
          cloudCover: 0.1,
          humidity: 0.69,
          pressure: 1025.42,
          ozone: 274.04 },
        { time: 1367485200,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0.074,
          precipProbability: 0.06,
          precipType: 'rain',
          temperature: 18.42,
          dewPoint: 12.27,
          windSpeed: 4.85,
          windBearing: 181,
          cloudCover: 0.02,
          humidity: 0.71,
          pressure: 1025.94,
          ozone: 273.66 },
        { time: 1367488800,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0.066,
          precipProbability: 0.04,
          precipType: 'rain',
          temperature: 17.61,
          dewPoint: 12.24,
          windSpeed: 4.51,
          windBearing: 182,
          cloudCover: 0.03,
          humidity: 0.72,
          pressure: 1026.37,
          ozone: 273.54 },
        { time: 1367492400,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0.058,
          precipProbability: 0.02,
          precipType: 'rain',
          temperature: 16.79,
          dewPoint: 12.2,
          windSpeed: 4.15,
          windBearing: 183,
          cloudCover: 0.08,
          humidity: 0.72,
          pressure: 1026.7,
          ozone: 273.62 },
        { time: 1367496000,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0.051,
          precipProbability: 0.01,
          precipType: 'rain',
          temperature: 16.02,
          dewPoint: 12.16,
          windSpeed: 3.8,
          windBearing: 184,
          cloudCover: 0.14,
          humidity: 0.72,
          pressure: 1026.86,
          ozone: 273.86 },
        { time: 1367499600,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0,
          temperature: 15.23,
          dewPoint: 12.12,
          windSpeed: 3.42,
          windBearing: 188,
          cloudCover: 0.19,
          humidity: 0.72,
          pressure: 1026.81,
          ozone: 274.44 },
        { time: 1367503200,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 14.4,
          dewPoint: 12.06,
          windSpeed: 3.05,
          windBearing: 192,
          cloudCover: 0.24,
          humidity: 0.72,
          pressure: 1026.61,
          ozone: 275.17 },
        { time: 1367506800,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 13.6,
          dewPoint: 12.03,
          windSpeed: 2.76,
          windBearing: 197,
          cloudCover: 0.28,
          humidity: 0.72,
          pressure: 1026.37,
          ozone: 275.52 },
        { time: 1367510400,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.91,
          dewPoint: 12.05,
          windSpeed: 2.62,
          windBearing: 204,
          cloudCover: 0.31,
          humidity: 0.73,
          pressure: 1026.13,
          ozone: 275.22 },
        { time: 1367514000,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.39,
          dewPoint: 12.09,
          windSpeed: 2.56,
          windBearing: 211,
          cloudCover: 0.32,
          humidity: 0.73,
          pressure: 1025.92,
          ozone: 274.52 },
        { time: 1367517600,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.1,
          dewPoint: 12.16,
          windSpeed: 2.5,
          windBearing: 219,
          cloudCover: 0.32,
          humidity: 0.74,
          pressure: 1025.77,
          ozone: 273.63 },
        { time: 1367521200,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.05,
          dewPoint: 12.27,
          windSpeed: 2.38,
          windBearing: 231,
          cloudCover: 0.31,
          humidity: 0.75,
          pressure: 1025.74,
          ozone: 272.45 },
        { time: 1367524800,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.29,
          dewPoint: 12.4,
          windSpeed: 2.23,
          windBearing: 247,
          cloudCover: 0.29,
          humidity: 0.77,
          pressure: 1025.78,
          ozone: 271.06 },
        { time: 1367528400,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-day',
          precipIntensity: 0,
          temperature: 12.96,
          dewPoint: 12.41,
          windSpeed: 2.09,
          windBearing: 265,
          cloudCover: 0.26,
          humidity: 0.77,
          pressure: 1025.77,
          ozone: 269.92 },
        { time: 1367532000,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-day',
          precipIntensity: 0,
          temperature: 14.06,
          dewPoint: 12.14,
          windSpeed: 1.94,
          windBearing: 279,
          cloudCover: 0.21,
          humidity: 0.74,
          pressure: 1025.68,
          ozone: 269.25 },
        { time: 1367535600,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 15.41,
          dewPoint: 11.75,
          windSpeed: 1.83,
          windBearing: 289,
          cloudCover: 0.16,
          humidity: 0.69,
          pressure: 1025.47,
          ozone: 268.82 },
        { time: 1367539200,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 16.81,
          dewPoint: 11.57,
          windSpeed: 1.85,
          windBearing: 297,
          cloudCover: 0.13,
          humidity: 0.65,
          pressure: 1025.04,
          ozone: 268.38 },
        { time: 1367542800,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 18.48,
          dewPoint: 11.86,
          windSpeed: 2.08,
          windBearing: 312,
          cloudCover: 0.13,
          humidity: 0.62,
          pressure: 1024.24,
          ozone: 267.77 },
        { time: 1367546400,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 20.32,
          dewPoint: 12.37,
          windSpeed: 2.44,
          windBearing: 332,
          cloudCover: 0.16,
          humidity: 0.59,
          pressure: 1023.2,
          ozone: 267.15 },
        { time: 1367550000,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 21.73,
          dewPoint: 12.74,
          windSpeed: 2.8,
          windBearing: 348,
          cloudCover: 0.17,
          humidity: 0.57,
          pressure: 1022.16,
          ozone: 266.68 },
        { time: 1367553600,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 22.4,
          dewPoint: 12.78,
          windSpeed: 3.08,
          windBearing: 356,
          cloudCover: 0.15,
          humidity: 0.56,
          pressure: 1021.21,
          ozone: 266.45 },
        { time: 1367557200,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 22.51,
          dewPoint: 12.68,
          windSpeed: 3.31,
          windBearing: 2,
          cloudCover: 0.13,
          humidity: 0.57,
          pressure: 1020.39,
          ozone: 266.36 },
        { time: 1367560800,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 22.26,
          dewPoint: 12.57,
          windSpeed: 3.51,
          windBearing: 4,
          cloudCover: 0.11,
          humidity: 0.58,
          pressure: 1019.82,
          ozone: 266.26 },
        { time: 1367564400,
          summary: 'Clear',
          icon: 'clear-day',
          precipIntensity: 0,
          temperature: 21.6,
          dewPoint: 12.54,
          windSpeed: 3.72,
          windBearing: 2,
          cloudCover: 0.12,
          humidity: 0.6,
          pressure: 1019.59,
          ozone: 266.03 },
        { time: 1367568000,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0,
          temperature: 20.53,
          dewPoint: 12.51,
          windSpeed: 3.92,
          windBearing: 356,
          cloudCover: 0.14,
          humidity: 0.63,
          pressure: 1019.59,
          ozone: 265.78 },
        { time: 1367571600,
          summary: 'Clear',
          icon: 'clear-night',
          precipIntensity: 0,
          temperature: 19.33,
          dewPoint: 12.43,
          windSpeed: 4.08,
          windBearing: 348,
          cloudCover: 0.18,
          humidity: 0.66,
          pressure: 1019.63,
          ozone: 265.7 },
        { time: 1367575200,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 18.16,
          dewPoint: 12.27,
          windSpeed: 4.16,
          windBearing: 339,
          cloudCover: 0.25,
          humidity: 0.67,
          pressure: 1019.61,
          ozone: 265.88 },
        { time: 1367578800,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 17.07,
          dewPoint: 12.07,
          windSpeed: 4.2,
          windBearing: 329,
          cloudCover: 0.33,
          humidity: 0.68,
          pressure: 1019.55,
          ozone: 266.22 },
        { time: 1367582400,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 16.1,
          dewPoint: 11.9,
          windSpeed: 4.21,
          windBearing: 322,
          cloudCover: 0.41,
          humidity: 0.69,
          pressure: 1019.33,
          ozone: 266.65 },
        { time: 1367586000,
          summary: 'Partly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 15.13,
          dewPoint: 11.75,
          windSpeed: 4.17,
          windBearing: 319,
          cloudCover: 0.46,
          humidity: 0.7,
          pressure: 1018.88,
          ozone: 267.29 },
        { time: 1367589600,
          summary: 'Mostly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 14.14,
          dewPoint: 11.62,
          windSpeed: 4.11,
          windBearing: 317,
          cloudCover: 0.51,
          humidity: 0.71,
          pressure: 1018.28,
          ozone: 268.03 },
        { time: 1367593200,
          summary: 'Mostly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 13.28,
          dewPoint: 11.52,
          windSpeed: 4.12,
          windBearing: 315,
          cloudCover: 0.54,
          humidity: 0.72,
          pressure: 1017.64,
          ozone: 268.49 },
        { time: 1367596800,
          summary: 'Mostly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.61,
          dewPoint: 11.47,
          windSpeed: 4.28,
          windBearing: 312,
          cloudCover: 0.54,
          humidity: 0.72,
          pressure: 1016.98,
          ozone: 268.4 },
        { time: 1367600400,
          summary: 'Mostly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.16,
          dewPoint: 11.46,
          windSpeed: 4.51,
          windBearing: 309,
          cloudCover: 0.54,
          humidity: 0.72,
          pressure: 1016.4,
          ozone: 268.03 },
        { time: 1367604000,
          summary: 'Mostly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.07,
          dewPoint: 11.46,
          windSpeed: 4.61,
          windBearing: 305,
          cloudCover: 0.56,
          humidity: 0.72,
          pressure: 1016.1,
          ozone: 267.78 },
        { time: 1367607600,
          summary: 'Mostly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 12.48,
          dewPoint: 11.52,
          windSpeed: 4.42,
          windBearing: 300,
          cloudCover: 0.65,
          humidity: 0.71,
          pressure: 1016.24,
          ozone: 267.84 },
        { time: 1367611200,
          summary: 'Mostly Cloudy',
          icon: 'partly-cloudy-night',
          precipIntensity: 0,
          temperature: 13.32,
          dewPoint: 11.58,
          windSpeed: 4.09,
          windBearing: 292,
          cloudCover: 0.77,
          humidity: 0.69,
          pressure: 1016.67,
          ozone: 268.01 },
        { time: 1367614800,
          summary: 'Mostly Cloudy',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 14.42,
          dewPoint: 11.44,
          windSpeed: 3.92,
          windBearing: 284,
          cloudCover: 0.86,
          humidity: 0.66,
          pressure: 1017.11,
          ozone: 268.15 },
        { time: 1367618400,
          summary: 'Overcast',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 15.62,
          dewPoint: 10.83,
          windSpeed: 4.13,
          windBearing: 276,
          cloudCover: 0.9,
          humidity: 0.62,
          pressure: 1017.46,
          ozone: 268.05 },
        { time: 1367622000,
          summary: 'Overcast',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 16.83,
          dewPoint: 10.04,
          windSpeed: 4.52,
          windBearing: 268,
          cloudCover: 0.91,
          humidity: 0.58,
          pressure: 1017.76,
          ozone: 267.92 },
        { time: 1367625600,
          summary: 'Overcast',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 18.02,
          dewPoint: 9.67,
          windSpeed: 4.84,
          windBearing: 259,
          cloudCover: 0.91,
          humidity: 0.54,
          pressure: 1017.92,
          ozone: 268.2 },
        { time: 1367629200,
          summary: 'Overcast',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 19.44,
          dewPoint: 10.1,
          windSpeed: 4.96,
          windBearing: 245,
          cloudCover: 0.9,
          humidity: 0.53,
          pressure: 1017.88,
          ozone: 269.25 },
        { time: 1367632800,
          summary: 'Mostly Cloudy',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 20.96,
          dewPoint: 10.97,
          windSpeed: 5.02,
          windBearing: 224,
          cloudCover: 0.86,
          humidity: 0.52,
          pressure: 1017.72,
          ozone: 270.72 },
        { time: 1367636400,
          summary: 'Mostly Cloudy',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 21.99,
          dewPoint: 11.81,
          windSpeed: 5.17,
          windBearing: 201,
          cloudCover: 0.83,
          humidity: 0.53,
          pressure: 1017.63,
          ozone: 271.91 },
        { time: 1367640000,
          summary: 'Mostly Cloudy',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 22.18,
          dewPoint: 12.5,
          windSpeed: 5.53,
          windBearing: 182,
          cloudCover: 0.83,
          humidity: 0.56,
          pressure: 1017.68,
          ozone: 272.56 },
        { time: 1367643600,
          summary: 'Mostly Cloudy',
          icon: 'cloudy',
          precipIntensity: 0,
          temperature: 21.83,
          dewPoint: 13.1,
          windSpeed: 5.94,
          windBearing: 169,
          cloudCover: 0.82,
          humidity: 0.6,
          pressure: 1017.86,
          ozone: 272.93 } ] },
  daily: 
   { summary: 'Sprinkling today; temperatures bottoming out at 19° on Sunday.',
     icon: 'rain',
     data: 
      [ { time: 1367416800,
          summary: 'Breezy in the morning.',
          icon: 'wind',
          sunriseTime: 1367440294,
          sunsetTime: 1367478912,
          precipIntensity: 0.061,
          precipIntensityMax: 0.009,
          precipIntensityMaxTime: 1367428500,
          precipType: 'rain',
          temperatureMin: 12.66,
          temperatureMinTime: 1367438400,
          temperatureMax: 20.42,
          temperatureMaxTime: 1367470800,
          dewPoint: 12.27,
          windSpeed: 5.79,
          windBearing: 194,
          cloudCover: 0.29,
          humidity: 0.72,
          pressure: 1023.87,
          ozone: 272.63 },
        { time: 1367503200,
          summary: 'Partly cloudy throughout the day.',
          icon: 'partly-cloudy-day',
          sunriseTime: 1367526740,
          sunsetTime: 1367565255,
          precipIntensity: 0,
          precipIntensityMax: 0,
          temperatureMin: 12.05,
          temperatureMinTime: 1367521200,
          temperatureMax: 22.51,
          temperatureMaxTime: 1367557200,
          dewPoint: 12.24,
          windSpeed: 2.99,
          windBearing: 303,
          cloudCover: 0.23,
          humidity: 0.67,
          pressure: 1022.98,
          ozone: 269.09 },
        { time: 1367589600,
          summary: 'Mostly cloudy throughout the day.',
          icon: 'partly-cloudy-day',
          sunriseTime: 1367613187,
          sunsetTime: 1367651598,
          precipIntensity: 0,
          precipIntensityMax: 0,
          temperatureMin: 12.07,
          temperatureMinTime: 1367604000,
          temperatureMax: 22.18,
          temperatureMaxTime: 1367640000,
          dewPoint: 11.9,
          windSpeed: 4.84,
          windBearing: 233,
          cloudCover: 0.73,
          humidity: 0.65,
          pressure: 1018.41,
          ozone: 270.38 },
        { time: 1367676000,
          summary: 'Overcast throughout the day.',
          icon: 'partly-cloudy-day',
          sunriseTime: 1367699633,
          sunsetTime: 1367737943,
          precipIntensity: 0.017,
          precipIntensityMax: 0,
          precipType: 'rain',
          temperatureMin: 12.14,
          temperatureMinTime: 1367690400,
          temperatureMax: 18.56,
          temperatureMaxTime: 1367730000,
          dewPoint: 11.58,
          windSpeed: 2.41,
          windBearing: 169,
          cloudCover: 0.88,
          humidity: 0.72,
          pressure: 1021.8,
          ozone: 268.52 },
        { time: 1367762400,
          summary: 'Partly cloudy throughout the day.',
          icon: 'partly-cloudy-day',
          sunriseTime: 1367786079,
          sunsetTime: 1367824289,
          precipIntensity: 0.038,
          precipIntensityMax: 0,
          precipType: 'rain',
          temperatureMin: 8.84,
          temperatureMinTime: 1367776800,
          temperatureMax: 20.89,
          temperatureMaxTime: 1367812800,
          dewPoint: 11.9,
          windSpeed: 1.68,
          windBearing: 118,
          cloudCover: 0.34,
          humidity: 0.76,
          pressure: 1022.23,
          ozone: 270.33 },
        { time: 1367848800,
          summary: 'Partly cloudy in the morning.',
          icon: 'partly-cloudy-night',
          sunriseTime: 1367872525,
          sunsetTime: 1367910636,
          precipIntensity: 0.029,
          precipIntensityMax: 0,
          temperatureMin: 9.05,
          temperatureMinTime: 1367863200,
          temperatureMax: 22.66,
          temperatureMaxTime: 1367899200,
          dewPoint: 13.04,
          windSpeed: 1.52,
          windBearing: 34,
          cloudCover: 0.12,
          humidity: 0.79,
          pressure: 1022.53,
          ozone: 273.94 },
        { time: 1367935200,
          summary: 'Clear throughout the day.',
          icon: 'clear-day',
          sunriseTime: 1367958971,
          sunsetTime: 1367996984,
          precipIntensity: 0.031,
          precipIntensityMax: 0,
          temperatureMin: 10.38,
          temperatureMinTime: 1367949600,
          temperatureMax: 24.37,
          temperatureMaxTime: 1367985600,
          dewPoint: 13.24,
          windSpeed: 1.78,
          windBearing: 352,
          cloudCover: 0,
          humidity: 0.74,
          pressure: 1024.32,
          ozone: 264.9 },
        { time: 1368021600,
          summary: 'Clear throughout the day.',
          icon: 'clear-day',
          sunriseTime: 1368045417,
          sunsetTime: 1368083334,
          precipIntensity: 0.016,
          precipIntensityMax: 0,
          temperatureMin: 10.79,
          temperatureMinTime: 1368036000,
          temperatureMax: 25.55,
          temperatureMaxTime: 1368068400,
          dewPoint: 13.82,
          windSpeed: 1.99,
          windBearing: 4,
          cloudCover: 0,
          humidity: 0.78,
          pressure: 1025.88,
          ozone: 259.18 } ] },
  flags: 
   { sources: [ 'isd', 'fnmoc', 'naefs', 'cmc', 'gfs' ],
     'isd-stations': 
      [ '947670-99999',
        '947675-99999',
        '947680-99999',
        '957640-99999',
        '957660-99999' ],
     units: 'si' },
  expires: 1367473292205 }

```

##LICENCE

**MIT LICENCE**

*Copyright (c) 2013 James Wyse <james@jameswyse.net>*

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
