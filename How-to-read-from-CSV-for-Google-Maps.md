# How to read from CSV for Google Maps?

Source: [StackOverflow.com](http://stackoverflow.com/questions/27654916/unable-to-read-data-from-csv-in-javascript/27655131#27655131)

### Question
There is a text file representing a wireless signal survey. It consists of lines each composed of a longitude, a latitude and the wireless signal strength in that location. I'm trying to read this file via Javascript then extract locations and mark them on Google Maps. The CSV file is as follows : data.csv

    'Chicago', 41.878113, -87.629798, 4
    'New York', 40.714352, -74.005973, 5 
    'Los Angeles', 34.052234, -118.243684, 3
    'Phoenix', 33.4483771, -112.0740373, 2 
    'Dallas', 32.7802618, -96.8009781, 5

I am reading the csv (data.csv) and copying it into an array data, and copying data to citymap. 

### Answer

I recommend use more complicated CVS parser for CVS parsing. AlaSQL library can loading and parsing CSV files (XLSX as well):

    alasql.promise('SELECT MATRIX * FROM CSV("data.csv", {headers:false})').then(function(data){
        // process data array
    });

This is working [at jsFiddle](http://jsfiddle.net/agershun/1o2xq1yh/2/).

