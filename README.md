This is used to demo an issue I found with browserify.

Clone this repo and do `npm install`.

Under `tmp` folder there are two browserify-ied files `good.js` and `bad.js`.

`good.js` comes from `index.js`, which exports `request` module. It has 500 lines.

`bad.js` comes from `wrapper.js` which exports `my-module`, and `my-module` exports same `request` module. It has 63k lines when using node v4.4.0.

Basically `require('index.js')` and `require('wrapper.js')` are same functionality to `require('request')`.