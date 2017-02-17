# Keyword `RETURN`

Used with the [[SEARCH]] keyword. Defines what to return. 

Example: 

```js
var res =   alasql("SEARCH / AS @user Members / AS @member \
	RETURN(@user->Id AS UserId, @user->Name AS UserName, \
       @member->Name AS MemberName, @member->Age AS MemberAge) \
	INTO XLSX('member_Track.xlsx',{headers:true,sheetid:'member_Track'}) \
	FROM $0 ",[users]);
```

See https://github.com/agershun/alasql/issues/826 for more details

----

See also: [[SEARCH]]
