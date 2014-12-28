# How to extend and merge two arrays containing objects?

Source: [StackOverflow.com](http://stackoverflow.com/questions/16828864/extend-and-merge-two-arrays-that-contain-objects-in-js/27618271#27618271)

### Question

There is an array A:

       var arrA = [{
          name: 'twitter',
          location: 0,
          hidden: false,
          href: "https://twitter.com/i/connect"
        }, {
          name: 'medium',
          location: 1,
          hidden: false,
          href: "https://medium.com/me/activity"
        }
      ];

And array B:

    var arrB = [{
          name: 'twitter',
          location: 1,
          hidden: false
        }, {
          name: 'medium',
          location: 0,
          hidden: false
        }
      ];

How can I end up with an array that looks like this:

    var newArr = [{
          name: 'twitter',
          location: 1,
          hidden: false,
          href: "https://twitter.com/i/connect"
        }, {
          name: 'medium',
          location: 0,
          hidden: false,
          href: "https://medium.com/me/activity"
        }
      ];

The algorithm is the following:

1. the `location` values have been taken from `arrB`, not `arrA`, 
2. that `newArr`'s objects now contain `href` keys, taken from `arrA`.

Values should be from the second array, but new keys are maintained from the first array.

### Answer

You can join two arrays and select proper attributes with these statements:

    var res1 = alasql('SELECT arrA.name, arrB.location, arrA.href, arrB.hidden \
                FROM ? arrA JOIN ? arrB USING name', [arrA,arrB]);

Or you can use ENTEND() function from standard library:

    var res2 = alasql('SELECT COLUMN extend(arrA._, arrB._) 
                       FROM ? arrA JOIN ? arrB USING name', [arrA,arrB]);

Try these examples [at jsFiddle](http://jsfiddle.net/agershun/b7ofozjr/2/)