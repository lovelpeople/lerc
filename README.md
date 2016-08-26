# Lerc2-js - Read Lerc2 v3 in javascript

## What is LERC?

LERC is an open-source image or raster format which supports rapid encoding and decoding for any pixel type (not just RGB or Byte) designed by [esri](https://github.com/Esri/lerc).

## Why this project?

The original project just provides Lerc2 encoder and Lerc1 decoder(js), so I migrate its C++ implementation(part of) to TypeScript.

## How to use

Copy *.js files from lib/src folder to use on backend or use browserify to build a bundle on front end, the demo in demo folder shows an example of using command `browserify main.js > lerc.js` to build a bundle js and use it in canvas.

```Javascript
    var Lerc2Decoder = require('../lib/src/lercdecoder2').Lerc2Decoder;
    var fs = require("fs");

    var lercData = fs.readFileSync("data/test_const_image.lerc");
    var arrayBuffer = new Uint8Array(lercData).buffer;
    var lerc2Decoder = new Lerc2Decoder(arrayBuffer);
    var result = lerc2Decoder.parse();
    // do something with result.pixelData
```

## Test

Run mocha to test.
