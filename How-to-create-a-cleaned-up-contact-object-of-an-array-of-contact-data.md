# How to create a cleaned up contact object of an array of contact data?

Source: [StackOverflow.com](http://stackoverflow.com/questions/26653638/create-a-cleaned-up-contact-object-of-an-array-of-contact-data/27628329#27628329)

### Question

There is an array with objects like this:
```js
	[
		{
			id: '1',
			name: 'Joe',
			description: 'Student',
			locations: [ {
				type: 'home',
				value: '123'
			} ]
		},
		{
			id: '1',
			name: 'Joe',
			description: 'Farmer',
			locations: [ {
				type: 'home',
				value: '456'
			} ]
		},
		{
			id: '1',
			name: 'Joe',
			description: '',
			locations: [ {
				type: 'home',
				value: '123'
			} ]
		}
	]
```
<strong>How to create the following? :</strong>
```js
	{
		id: '1',
		name: 'Joe',
		description: 'Farmer',
		locations: [ {
			type: 'home',
			value: '123'
		}, {
			type: 'home',
			value: '456'
		} ]
	}
```

### Answer

```js
    var res = alasql('SELECT id, FIRST(name) AS name, FIRST(description) AS description, \
                            ARRAY(locations->0) AS locations FROM ?',[data]);
```
See the example [at jsFiddle](http://jsfiddle.net/agershun/x110xhfc/1/)