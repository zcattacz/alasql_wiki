
### Google Maps + AlaSQL

Pinpointing data on a map should be easy. Here is an example of AlaSQL used to prepare source data for Google Maps


```js
    alasql('SELECT * FROM CSV("https://cdn.rawgit.com/albertyw/avenews/master/old/data/average-latitude-longitude-countries.csv",{headers:true})', [], function(country){
        var mapOptions = { zoom : 3, center : new google.maps.LatLng(40, 0),
            mapTypeId : google.maps.MapTypeId.ROADMAP
        };
        var map = new google.maps.Map(document.getElementById('map-canvas'), mapOptions);
        for (i = 0; i < country.length; i++) {
            var opts = {
                strokeColor : '#000000',
                fillColor : ["red","green","blue","brown"][i%4],
                fillOpacity : 0.35,
                map : map,
                center : new google.maps.LatLng(country[i].Latitude,country[i].Longitude),
                radius : 100000
            };
        new google.maps.Circle(opts);
    });
```
You can [play with an example](http://alasql.org/demo/009geo) or [poke around with this other example](http://jsfiddle.net/agershun/1o2xq1yh/2/) of intergrating AlaSQL and Google Maps