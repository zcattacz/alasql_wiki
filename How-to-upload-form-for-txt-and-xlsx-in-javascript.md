# How to upload form for txt and xlsx in javascript?

Source: [StackOverflow.com](http://stackoverflow.com/questions/19211193/upload-form-for-txt-and-xlsx-in-javascript/27656225#27656225)

### Question

I would like to make a form that allow user upload .txt and .xlsx file and write this file's contents in a div.I don't know if i should go server side to handle uploaded files.

### Answer

You can read CSV or XLSX data with [Alasql][1] library. It uses [js-xlsx] library.

If you read data from server:

    alasql('SELECT * FROM XLSX("data.xlsx", {headers:true})',[],function(data){
        // process data array
    });

If you are reading data from the browser:

    <script src="alasql.min.js"></script>
    <script src="xlsx.core.min.js"></script>
    <p>Select CSV file to read:</p>
    <input id="readfile" type="file" onchange="loadFile(event)"/>
    <script>
        function loadFile(event) {
	        alasql('SELECT * FROM FILE(?,{headers:true})',[event],function(data){
		        // Process data here
	        });
         }
    </script>

Alasql automatically recognize file type by file extension.

You can try the working example of uploading data [here](http://alasql.org/demo/008file/).
