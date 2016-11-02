# State-zip-code-GeoJSON

Zip code boundaries for each of the 50 states

This is a collection of zip code boundrary files for each of the 50 states, plus DC. Thanks to Github user
[jgoodall for his us-maps example](https://github.com/jgoodall/us-maps)! His example was how I found where to
download the shape files.

Each file from the Census is of the format: 

tl_2010_STATE_FIPS_CODE_zcta510.zip

Where STATE_FIPS_CODE is the two-digit [Federal Information Processing Standard state code]
(https://en.wikipedia.org/wiki/Federal_Information_Processing_Standard_state_code). 

Each file was then unzipped, converted to GeoJSON with [ogr2ogr](http://www.gdal.org/), and minified
with [json-minify](https://www.npmjs.com/package/json-minify). Here's an example for Delaware:

#### Zip codes
* In a browser, visit: https://www.census.gov/cgi-bin/geo/shapefiles2010/main
* Choose 'Zip Code Tabulation Areas' and 'Submit'
* Choose 'Delware' for '5-Digit ZIP Code Tabulation Area (2010)' and click 'Download'

Then unzip the files, and run:

```
ogr2ogr -f "GeoJSON" de_delaware_zip_codes_geo.json tl_2010_10_zcta510.shp

json-minify de_delaware_zip_codes_geo.json > de_delaware_zip_codes_geo.min.json

```


