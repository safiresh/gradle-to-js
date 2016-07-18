# gradle-to-js

[![Build Status](https://travis-ci.org/ninetwozero/gradle-to-js.svg?branch=master)](https://travis-ci.org/ninetwozero/gradle-to-js)

# What's this `gradlejs` thing?
gradle-to-js is a quick & dirty Gradle build file to JavaScript object parser. It is quick & dirty in the sense that it doesn't give you an exact replica of whatever the build file represents during runtime, as evaluations and similar bits are (currently) too much of a hassle to accurately represent while parsing.
JavaScript object to Gradle file make
# Installation
Simply run the following command to include it into your project:
```
npm install gradlejs --save
```
# Usage

### Sample build  file
```
var fs = require('fs');
var gjs = require('gradle-to-js');

g2js.parseFile('./build.gradle').then(function (representation) {
    representation.android.defaultConfig.versionName = "'1.0.2'"; // value String means we need  put single quotes :(
    fs.writeFile('./build.gradle', gjs.makeGradleText(representation), function (e, r) {
        console.log(e, r);
    })

});

**Special thanks to [Karl Lindmark](https://github.com/karllindmark)**

# Author
[Safiresh](https://www.github.com/safiresh)

# License
Apache 2.0
