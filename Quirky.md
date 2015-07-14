# Quirky things about AlaSQL

### Column names

You can use

    [column] 

or 

    `column` 

for columns with spaces, special symbols, etc. This also applys to **column named with [reserved keywords](AlaSQL Keywords)** independent of the letter case. So names like `date`, `begin`, `content`, `last`, `max`, `min`, `natural`, `path`, `right`, `show`, `temp`, `timeout`, `target`, `top`, `value`, and `work` needs to be wrapped.