# How to find all parents elements in a JSON file?

Source: [StackOverflow](http://stackoverflow.com/questions/29937203/find-all-parents-elements-in-a-json-file-using-jquery/29937369#29937369
)

### Question

How to find all parents elements in a Json file? I'm currently working on a recursive menu which is built on top of jQuery which looks quite good already. The structure of the JSon file containing the menu looks as the following:

```js
[
   { 
       "Id": "menuOfficeWebControlsForWebApplication", 
       "Title": "Office Web Controls", 
       "Resource": "/Documentation/Data/index.html" },
   { 
       "Id": "menuGettingStarted", 
       "Title": "Getting Started", 
       "Resource": "/Documentation/Data/getting-started.html", 
       "Categories": [{ 
             "Id": "menuCompilingFromSource", 
             "Title": "Compiling From Source", 
             "Resource": "/Documentation/Data/Getting-Started/compiling-from-source.html" 
          },{ 
             "Id": "menuDownloadReleasePackage", 
             "Title": "Download Release Package", 
             "Resource": "/Documentation/Data/Getting-Started/downloading-release-package.html"
          },{ 
             "Id": "menuBuildingYourFirstApplication", 
             "Title": "Building your first application", 
             "Resource": "/Documentation/Data/Getting-Started/building-your-first-application.html" 
        }]
   }
]

Now, I want to retrieve all the elements which are at a higher level and all the items which are directly below that item.

### Answer

You can do it with AlaSQL [SEARCH](Search) operator:

```js
    var res = alasql('SEARCH /(Categories/)? WHERE(Id) FROM ?', [data]);
```

To list only valid keys you can use:
```js
    var res = alasql('SEARCH /(Categories/)? Id FROM ?', [data]);
```
