# Keyword `SEARCH`

AlaSQL ```SEARCH``` operator is designed to traverse over JSON objects and graphs and is inspired by the [OrientDB graph search](https://github.com/agershun/alasql/issues/131#issuecomment-94413228)

Syntax:
```sql
    SEARCH selectors [FROM (table|object)]
```

You can use it with graphs:
```js
    var res = alasql('SEARCH / "Harry" PATH("Roger") VERTEX name');
```
or with JSON files:
```js
   var catalog = { 
     Europe: {
       fruits: [
         {fruit:'Apple'},
         {fruit:'Peach'},          
       ]
     },
     Asia: {
         fruit:'Pineapple'          
     },
     Africa: {
         fruit:'Banana'          
     }
   };

    var res = alasql('SEARCH Europe FROM ?',[catalog]);
    // [{fruits: [
    //    {fruit:'Apple'},
    //    {fruit:'Peach'},          
    //  ]}]);

    var res = alasql('SEARCH /fruits/ FROM ?',[catalog]);
    // [{fruit:'Apple'}, {fruit:'Peach'}]

    var res = alasql('SEARCH /fruits/fruit FROM ?',[catalog]);
    // ['Apple','Peach']

    var res = alasql('SEARCH /fruits/WHERE(fruit="Apple") FROM ?',[catalog]);
    // [{fruit:'Apple'}]

    var res = alasql('SEARCH ///WHERE(fruit="Apple") FROM ?',[catalog]);
    // [{fruit:'Apple'}]
```

Have a look at [[RETURN]] to modify the output when wanting to finetune `SEARCH` outputs 

### More relevant example:
```js
var alasql = require('alasql');

var data = [
	{
		teamname:'Alpha',
		members: [
			{
				membername:'Andrey',
				categories: ['JavaScript','C++']
			},
			{
				membername:'Mathias',
				categories: ['JavaScript','PHP']
			},
		]
	},
	{
		teamname:'Beta',
		members: [
			{
				membername:'Ole',
				categories: ['JavaScript']
			}
		]
	},
];

var res = alasql('SEARCH / AS @team \
		members / AS @member \
		categories / AS @category  \
		RETURN(@team->teamname AS team, @member->membername AS member, @category AS category) \
		FROM ?',[data]);
console.log(res);
```
returns
```js
[ { team: 'Alpha', member: 'Andrey', category: 'JavaScript' },
  { team: 'Alpha', member: 'Andrey', category: 'C++' },
  { team: 'Alpha', member: 'Mathias', category: 'JavaScript' },
  { team: 'Alpha', member: 'Mathias', category: 'Java' },
  { team: 'Beta', member: 'Ole', category: 'JavaScript' } ]
```

Here:
* `SEARCH` - search keyword
* `/` - walk over all members of array
* `AS @team` - save result into temporary variable `team`
*` members` - take member property of previous result
* `/` - walk over all members of members array
* `AS @member` - save result into temporary variable `member`
*` categories` - take category property of previous result
* `/`- walk over categories array
* `RETURN(...)` - pseudo-function to create result record
* `RETURN(@team->teamname AS team,...)` - take temporary variable 'team', take its teamname property and store it as team property of result object
* `FROM ?` - standard source from array clause
* `alasql('...',[data])` - take source data from `data` array

### Other examples of ```SEARCH``` operator:
* [How to parse a Json with array and objects and export the data into Excel file](How to parse a Json with array and objects and export the data into Excel file)



See also: [[RETURN]]