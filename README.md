PhoneGap-iOS-Background-Location-Tracking-Plugin
================================================

If you need to track a user's location in background this plugin does exactly that. The location updates with accuracy: kCLLocationAccuracyNearestTenMeters and distanceFilter = 10.0 (in meters). Baically the plugin will return new location any 10 meters. 

#Installing the plugin

Copy <code>BGLocationTrackingPlugin.h</code> and <code>BGLocationTrackingPlugin.m</code> files to your Classes folder and <code>BGLocationTrackingPlugin.js</code> file to www/js folder.

Add js file to your index.html. Then add the following code to your config.xml:

	<feature name="BGLocationTracking">
		<param name="ios-package" value="BGLocationTracking" />
		<param name="onload" value="true" />
	</feature>

#Using the plugin

When the apps recives <code>Pause</code> event you need to call <code>startUpdatingLocation()</code> function. 
######Example
	function onPause() {
		startUpdatingLocation(yourCallbackFunction);	
	}

	function yourCallbackFunction( result ) {
		console.log( result.coords.latitude );
		console.log( result.coords.longitude );
	}

You can specify the callback by name or just pass an anonymous function. It will work fine either way.

After getting <code>Resume</code> event just call <code>stopUpdatingLocation()</code> function.

#License

The MIT License

Copyright (c) 2013 Stas Gorodnichenko, Alex Shmaliy

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.