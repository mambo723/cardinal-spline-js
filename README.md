﻿Cardinal spline
===============

A `curve()` (cardinal spline) extension for HTML5 Canvas (JavaScript).

This library extends the 2D context with a new optimized `curve()` method
to enable drawing of cardinal splines - splines that goes through the defined
points.

The method is passed a simple array of points and a line is drawn through
them at given or default tension and segment resolution, open or closed loop.

![Demo snapshot](http://i.imgur.com/5e69T5C.png)

*Not to be confused with Bezier splines which uses end points and one 
or two control points, whereas the line is drawn somewhere between. 
With a cardinal spline the smooth curve goes through every point 
defined and you can have as many point as you wish in a single spline.*


Usage
-----

Make sure the script is loaded before a 2D context is retrieved from the
canvas element.

**Example**

    ctx.moveTo(points[0], points[1]);  // optionally move to first point
    ctx.curve(points);                 // add cardinal spline to path
    ctx.stroke();                      // rasterize path

will draw the points in the array which is arranged in this manner:

    [x1, y1, x2, y2, ... xn, yn]

Optionally a tension value can be given *(default: 0.5)*:

    ctx.curve(points, 0.5);            // set tension [0.0, 1.0] +/-

as well as a segment resolution value *(default: 20)*:

    ctx.curve(points, 0.5, 20);       // points in each segment

The curve can also be drawn closed. All arguments must be given in this
case *(default: false (open))*:

    ctx.curve(points, 0.5, 20, true); // make a closed loop

The methods returns an array with the spline points which can be used for
tracking, calculate length and so forth:

    var splinePoints = ctx.curve(points);

License
-------

Released under [MIT license](http://choosealicense.com/licenses/mit/). You can use this class in both commercial and non-commercial projects provided that full header (minified and developer versions) is included.

*&copy; 2013-2014 Epistemex*

![Epistemex](http://i.imgur.com/YxO8CtB.png)
