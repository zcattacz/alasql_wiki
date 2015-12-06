# Keyword ASCII

SQL command to get ASCII value of first char.

Please be aware that AlaSQL uses Javascript to find the char values. The traditional ASCII chars are all OK, but 25 of the extended ASCII table will give different result than expected in traditional DBs

The following chars gives a different value thank expected (here the expected value is shown)
```sql
    - SELECT ASCII('€'); -- 128 - Euro sign
    - SELECT ASCII('‚'); -- 130 - Single low-9 quotation mark
    - SELECT ASCII('ƒ'); -- 131 - Latin small letter f with hook
    - SELECT ASCII('„'); -- 132 - Double low-9 quotation mark
    - SELECT ASCII('…'); -- 133 - Horizontal ellipsis
    - SELECT ASCII('†'); -- 134 - Dagger
    - SELECT ASCII('‡'); -- 135 - Double dagger
    - SELECT ASCII('ˆ'); -- 136 - Modifier letter circumflex accent
    - SELECT ASCII('‰'); -- 137 - Per mille sign
    - SELECT ASCII('Š'); -- 138 - Latin capital letter S with caron
    - SELECT ASCII('‹'); -- 139 - Single left-pointing angle quotation
    - SELECT ASCII('Œ'); -- 140 - Latin capital ligature OE
    - SELECT ASCII('Ž'); -- 142 - Latin captial letter Z with caron
    - SELECT ASCII('“'); -- 147 - Left double quotation mark
    - SELECT ASCII('”'); -- 148 - Right double quotation mark
    - SELECT ASCII('•'); -- 149 - Bullet
    - SELECT ASCII('–'); -- 150 - En dash
    - SELECT ASCII('—'); -- 151 - Em dash
    - SELECT ASCII('˜'); -- 152 - Small tilde
    - SELECT ASCII('™'); -- 153 - Trade mark sign
    - SELECT ASCII('š'); -- 154 - Latin small letter S with caron
    - SELECT ASCII('›'); -- 155 - Single right-pointing angle quotation mark
    - SELECT ASCII('œ'); -- 156 - Latin small ligature oe
    - SELECT ASCII('ž'); -- 158 - Latin small letter z with caron
    - SELECT ASCII('Ÿ'); -- 159 - Latin capital letter Y with diaeresis
```

The return value is based on unicode. In the following you can see what is normally expected and what the library will return:

```sql
  2) 376. ASCII tests: SELECT ASCII('€'); -- 128 - Euro sign:

      AssertionError: '128' == '8364'
      + expected - actual

      -128
      +8364
      
      at Context.<anonymous> (test/test376.js:260:19)

  3) 376. ASCII tests: SELECT ASCII('‚'); -- 130 - Single low-9 quotation mark:

      AssertionError: '130' == '8218'
      + expected - actual

      -130
      +8218
      
      at Context.<anonymous> (test/test376.js:260:19)

  4) 376. ASCII tests: SELECT ASCII('ƒ'); -- 131 - Latin small letter f with hook:

      AssertionError: '131' == '402'
      + expected - actual

      -131
      +402
      
      at Context.<anonymous> (test/test376.js:260:19)

  5) 376. ASCII tests: SELECT ASCII('„'); -- 132 - Double low-9 quotation mark:

      AssertionError: '132' == '8222'
      + expected - actual

      -132
      +8222
      
      at Context.<anonymous> (test/test376.js:260:19)

  6) 376. ASCII tests: SELECT ASCII('…'); -- 133 - Horizontal ellipsis:

      AssertionError: '133' == '8230'
      + expected - actual

      -133
      +8230
      
      at Context.<anonymous> (test/test376.js:260:19)

  7) 376. ASCII tests: SELECT ASCII('†'); -- 134 - Dagger:

      AssertionError: '134' == '8224'
      + expected - actual

      -134
      +8224
      
      at Context.<anonymous> (test/test376.js:260:19)

  8) 376. ASCII tests: SELECT ASCII('‡'); -- 135 - Double dagger:

      AssertionError: '135' == '8225'
      + expected - actual

      -135
      +8225
      
      at Context.<anonymous> (test/test376.js:260:19)

  9) 376. ASCII tests: SELECT ASCII('ˆ'); -- 136 - Modifier letter circumflex accent:

      AssertionError: '136' == '710'
      + expected - actual

      -136
      +710
      
      at Context.<anonymous> (test/test376.js:260:19)

  10) 376. ASCII tests: SELECT ASCII('‰'); -- 137 - Per mille sign:

      AssertionError: '137' == '8240'
      + expected - actual

      -137
      +8240
      
      at Context.<anonymous> (test/test376.js:260:19)

  11) 376. ASCII tests: SELECT ASCII('Š'); -- 138 - Latin capital letter S with caron:

      AssertionError: '138' == '352'
      + expected - actual

      -138
      +352
      
      at Context.<anonymous> (test/test376.js:260:19)

  12) 376. ASCII tests: SELECT ASCII('‹'); -- 139 - Single left-pointing angle quotation:

      AssertionError: '139' == '8249'
      + expected - actual

      -139
      +8249
      
      at Context.<anonymous> (test/test376.js:260:19)

  13) 376. ASCII tests: SELECT ASCII('Œ'); -- 140 - Latin capital ligature OE:

      AssertionError: '140' == '338'
      + expected - actual

      -140
      +338
      
      at Context.<anonymous> (test/test376.js:260:19)

  14) 376. ASCII tests: SELECT ASCII('Ž'); -- 142 - Latin captial letter Z with caron:

      AssertionError: '142' == '381'
      + expected - actual

      -142
      +381
      
      at Context.<anonymous> (test/test376.js:260:19)

  15) 376. ASCII tests: SELECT ASCII('“'); -- 147 - Left double quotation mark:

      AssertionError: '147' == '8220'
      + expected - actual

      -147
      +8220
      
      at Context.<anonymous> (test/test376.js:260:19)

  16) 376. ASCII tests: SELECT ASCII('”'); -- 148 - Right double quotation mark:

      AssertionError: '148' == '8221'
      + expected - actual

      -148
      +8221
      
      at Context.<anonymous> (test/test376.js:260:19)

  17) 376. ASCII tests: SELECT ASCII('•'); -- 149 - Bullet:

      AssertionError: '149' == '8226'
      + expected - actual

      -149
      +8226
      
      at Context.<anonymous> (test/test376.js:260:19)

  18) 376. ASCII tests: SELECT ASCII('–'); -- 150 - En dash:

      AssertionError: '150' == '8211'
      + expected - actual

      -150
      +8211
      
      at Context.<anonymous> (test/test376.js:260:19)

  19) 376. ASCII tests: SELECT ASCII('—'); -- 151 - Em dash:

      AssertionError: '151' == '8212'
      + expected - actual

      -151
      +8212
      
      at Context.<anonymous> (test/test376.js:260:19)

  20) 376. ASCII tests: SELECT ASCII('˜'); -- 152 - Small tilde:

      AssertionError: '152' == '732'
      + expected - actual

      -152
      +732
      
      at Context.<anonymous> (test/test376.js:260:19)

  21) 376. ASCII tests: SELECT ASCII('™'); -- 153 - Trade mark sign:

      AssertionError: '153' == '8482'
      + expected - actual

      -153
      +8482
      
      at Context.<anonymous> (test/test376.js:260:19)

  22) 376. ASCII tests: SELECT ASCII('š'); -- 154 - Latin small letter S with caron:

      AssertionError: '154' == '353'
      + expected - actual

      -154
      +353
      
      at Context.<anonymous> (test/test376.js:260:19)

  23) 376. ASCII tests: SELECT ASCII('›'); -- 155 - Single right-pointing angle quotation mark:

      AssertionError: '155' == '8250'
      + expected - actual

      -155
      +8250
      
      at Context.<anonymous> (test/test376.js:260:19)

  24) 376. ASCII tests: SELECT ASCII('œ'); -- 156 - Latin small ligature oe:

      AssertionError: '156' == '339'
      + expected - actual

      -156
      +339
      
      at Context.<anonymous> (test/test376.js:260:19)

  25) 376. ASCII tests: SELECT ASCII('ž'); -- 158 - Latin small letter z with caron:

      AssertionError: '158' == '382'
      + expected - actual

      -158
      +382
      
      at Context.<anonymous> (test/test376.js:260:19)

  26) 376. ASCII tests: SELECT ASCII('Ÿ'); -- 159 - Latin capital letter Y with diaeresis:

      AssertionError: '159' == '376'
      + expected - actual

      -159
      +376
      
      at Context.<anonymous> (test/test376.js:260:19)
```
