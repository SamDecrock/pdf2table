# pdf2table

pdf2table is a node.js library that attempts to extract tables from a pdf.

The 'tables' are extracted as an array of rows.

It uses [pdf2json](https://github.com/modesty/pdf2json) to extract the pdf data.

## Install

You can install __pdf2table__ using the Node Package Manager (npm):

    npm install pdf2table

## Simple example
```js

var pdf2table = require('pdf2table');
var fs = require('fs');

fs.readFile('./test.pdf', function (err, buffer) {
    if (err) return console.log(err);

    pdf2table.parse(buffer, function (err, rows, rowsdebug) {
        if(err) return console.log(err);

        console.log(rows);
    });
});

```

## Note
Note that this is a simplistic implementation to extract tables. If your pdf contains other stuff that's not a table, pdf2table will still attempt to shape this data into a row. Feel free to improve and send pull requests.


