gpx-parse [![NPM Version](https://badge.fury.io/js/gpx-parse.png)](https://badge.fury.io/js/gpx-parse) [![Build Status](https://travis-ci.org/elliotstokes/gpx-parse.png?branch=master)](https://travis-ci.org/elliotstokes/gpx-parse) [![Coverage Status](https://coveralls.io/repos/elliotstokes/gpx-parse/badge.png?branch=master)](https://coveralls.io/r/elliotstokes/gpx-parse?branch=master) [![Code Climate](https://codeclimate.com/github/elliotstokes/gpx-parse.png)](https://codeclimate.com/github/elliotstokes/gpx-parse)
========

A library for parsing gpx data. Works against most of the Gpx v1.0 spec and Gpx v1.1. Feel free to fork if you need something specific.

More information available on the [Project Page](http://www.vapidspace.com/gpx-parse)

#Installation for Vuejs v3
See https://github.com/eltorio/CFDTrackJoiner/tree/modularize for a sample use
Look at https://github.com/eltorio/CFDTrackJoiner/blob/modularize/src/module/trackjoiner.js
and https://github.com/eltorio/CFDTrackJoiner/blob/modularize/src/views/TrackJoinerView.vue

```bash
	# at the root of the Vue3 project
	git clone https://github.com/eltorio/gpx-parse.git
	# in the Vue3 package.json add the dependencie
	"gpx-parser": "file:./gpx-parse"
````

```javascript
	//in the vue.config.js configure WebPack 5
	module.exports = {
		runtimeCompiler: true,
		configureWebpack: {
			devtool: 'source-map',
			resolve: {
			fallback: {
				"fs": false,
				"http": require.resolve("stream-http"),
				"https": require.resolve("https-browserify"),
				"timers": require.resolve("timers-browserify"),
				"stream": require.resolve("stream-browserify")
				}
			}
		},
	};
```
#Or with bower

	$ bower install gpx-parse

#Usage

The module has been designed to work within node but you can also use it on the client side using the browserfy version that can be found in the dist folder.

```javascript
var gpxParse = require("gpx-parse");

//from file
gpxParse.parseGpxFromFile("/path/to/gpxFile", function(error, data) {
	//do stuff
});

//or from string
gpxParse.parseGpx("<gpx></gpx>", function(error, data) {
	//do stuff
});

// or an external file via HTTP(S)
gpxParse.parseRemoteGpxFile("http://host.tld/my.gpx", function(error, data) {
    //do stuff
});

```

#Tests

Tests are written with nodeunit. To test make sure you have the dev dependencies installed and just run:

	$ npm test
