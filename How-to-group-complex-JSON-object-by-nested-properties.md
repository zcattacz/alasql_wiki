# How to group complex JSON object by nested properties?

Source: [StackOverflow.com](http://stackoverflow.com/questions/8706735/group-map-points-by-their-category-in-javascript/27619062#27619062)

### Question

There are points on a map by parsing through a dynamically created GeoJSON file.  I'd like to group these points by it's category attribute (each point has a category property). What I'd prefer to do is to parse through each point (already doing that part), and do a check to see if a group for category X exists, and either add the point to that group or make a group and add the point.  This would allow me to turn all points of a certain category on/off at once.  

An example GeoJSON point:

    {
        "crs": null,
        "type": "FeatureCollection",
        "features": [
            {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        -122.382626,
                        47.6657641
                    ]
                },
                "type": "Feature",
                "id": 18,
                "properties": {
                    "event_set__all": [
                        {
                            "category__category": "Live",
                            "title": "the Tallboys",
                            "cost": "$5",
                            "description": "",
                            "slug": "the-tallboys"
                        }
                    ],
                    "neighborhood__slug": "ballard",
                    "venue": "Tractor Tavern",
                    "neighborhood__neighborhood": "Ballard",
                    "address": "5213 Ballard Ave NW, Seattle, WA 98107, USA",
                    "slug": "tractor-tavern"
                }
            }
        ]
    }

The attribute to be used to group each point is `e.properties.event_set__all[0].category__category`.

### Answer

You can group all points with Alasql library:

    var res = alasql('SELECT features->0->properties->event_set__all->0->category__category \
                          AS category, ARRAY(_) AS points FROM ? GROUP BY category',[data]);

It groups all points with category selected from this long point name like:

    [
        {category:"Live1", points: [{point},{point},...] },
        {category:"Live2", points: [{point},{point},...] }
    ]

Try this example [at jsFiddle](http://jsfiddle.net/agershun/2c8njgqw/2/)