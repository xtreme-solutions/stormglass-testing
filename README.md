# stormglass-testing
rough notes on how to make proper api.stormglass.io requests for comparing swellpro data with other apis
# tools
## browser extensions
for use with ms edge or any chromium based. for other browsers a method to submit header authorization will be needed.
### Mod Header extension
https://microsoftedge.microsoft.com/addons/detail/modheader-modify-http-h/opgbiafapkbbnbnjcdomjaghbckfkglc
### seven json viewer
https://microsoftedge.microsoft.com/addons/detail/seven-json-viewer/khfhokalnpdlmmfjocjgaaipenplemjo
# preps
## mod-header extension setup
![image](https://github.com/xtreme-solutions/stormglass-testing/assets/34108754/6f699d97-c7ba-489e-a756-75a52d96d1fb)
# steps
## prepare the link:
fill in the link:
##### https://api.stormglass.io/v2/weather/point?start=START&end=END&lat=LATITUDE&lng=LONGITUDE&params=PARAMS
##### where:
##### START = first hour from today MINUS the timezone offset. For instance, consider date 2023-05-27 and timezone offset -03:00. 00:00-(-3hrs) = 00:00 + 03:00 = 03:00. So the START would be 2023-05-27T03:00
##### END = last hour of the day MINUSthe timezone offset. For instance, consider date 2023-05-27 and timezone offset -03:00. 23:00-(-3hrs) = 23:00 + 03:00 = 02:00 of the next day. So the END would be 2023-05-28T02:00
##### LATITUDE AND LONGITUDE are coordinates like: 33.866577018052 and -118.596285497770.
##### PARAMS is a list of params you may find in docs.stormglass.io. Here's a list for the weather endpoint, used in this example: https://docs.stormglass.io/#/weather.
##### An example of link would be: https://api.stormglass.io/v2/weather/point?start=2023-05-27T03:00:00&end=2023-05-28T02:00:00&lat=33.866577018052&lng=-118.596285497770&params=swellHeight,swellDirection,swellPeriod.
##### And an expected result would look like:
![image](https://github.com/xtreme-solutions/stormglass-testing/assets/34108754/df846133-8191-49d6-8051-e0079a145a89).
##### use API docs to learn more about params, the source argument, and other endpoints beside weather (tide and astronomical, for example).
