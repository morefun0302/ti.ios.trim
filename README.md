# ti.ios.trim Module

## Description

This module extends the Appcelerator Titanium Mobile framework and allows trimming videos on iOS. This is currently not possible using Titanium's VideoPlayer:

[[#TIMOB-1816] iOS: Phone &gt; Record Video, edit/trimming is not shown in playback - Appcelerator JIRA](https://jira.appcelerator.org/browse/TIMOB-1816)
[[#TIMOB-4200] iOS - Edit mode on record video returns entire video - Appcelerator JIRA](https://jira.appcelerator.org/browse/TIMOB-4200)

### Getting the module

Find the newest version in the dist folder.

### Referencing the module

Simply add the following lines to your `tiapp.xml` file:

    <modules>
        <module platform="iphone" version="0.1">ti.ios.trim</module>
    </modules>

### Accessing the module

To access this module from JavaScript, you would do the following:

    var trimmer = require('ti.ios.trim');

The trimmer variable is a reference to the Module object.

## Reference

### trimVideo({Object} options)

`options` can have the following keys:

* *input* - the path to video file to be trimmed
* *startTime* - beginning of the trimmed movie (in seconds)
* *endTime* - end of the trimmed movie (in seconds)
* *success* - callback to be invoked after successful trimming
* *error* - callback to be invoked in case of an error

```javascript
var inputFile = Ti.Filesystem.getFile('path/to/videoFile');
trimmer.trimVideo({
    input: inputFile.resolve(),
    startTime: 0,
    endTime: 10,
    success: function(e) {
        alert('SUCCESS, path to trimmed file: '+ e.videoURL);
    },
    error: function(e) {
        alert('ERROR, information: '+ JSON.stringify(e));
    }
});
```

## Author

**Martin Tietz**
web: [http://www.martin-tietz.com](http://www.martin-tietz.com)
email: info@martin-tietz.com

## License

    Copyright (c) 2013 Martin Tietz

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.
