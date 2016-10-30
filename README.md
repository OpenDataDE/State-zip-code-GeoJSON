# State-zip-code-GeoJSON

Zip code boundaries for each of the 50 states

This is a collection of zip code boundrary files for each of the 50 states, plus DC. Thanks to Github user
[jgoodall for his us-maps example](https://github.com/jgoodall/us-maps)! His example was how I found where to
download the shape files.

Each file from the Census is of the format: 

tl_2010_<STATE CODE>_zcta510.zip

Where <STATE CODE> is a two-digit number. The numbers follow an alphebetic order, but some numbers are skipped. 
Each file was then unzipped, and converted to GeoJSON. Here's an example for Delaware:


#### Zip codes
* In a browser, visit: https://www.census.gov/cgi-bin/geo/shapefiles2010/main
* Choose 'Zip Code Tabulation Areas' and 'Submit'
* Choose 'Delware' for '5-Digit ZIP Code Tabulation Area (2010)' and click 'Download'

Then unzip the files, and run 
[ogr2ogr](http://www.gdal.org/)! 


```
ogr2ogr -f "GeoJSON" de_zipcode_boundaries.json tl_2010_10_zcta510.shp
```

The file was minified like above, then the file 'de_zipcode_boundaries.min.json' was added to the project. 

