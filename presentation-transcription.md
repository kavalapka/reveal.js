# Canvas

In this presentation we will consider common information about canvas element, it’s properties, drawing possibilities 
and simple animation.
### Canvas API
The Canvas API provides a means for drawing graphics via JavaScript and the HTML<canvas> element. Among other things, 
it can be used for animation, game graphics, data visualization, photo manipulation, and real-time video processing.

### Browser compatibility
Canvas supported by all new version of browsers also IE from version 9.
### The <canvas> element
The <canvas>element requires the closing tag (</canvas>). If this tag is not present, the rest of the document would be 
considered the fallback content and wouldn't be displayed.
The <canvas> element has only two attributes, width and height. These are both optional and can also be set using 
DOMproperties. Default size of canvas is 300 pixels wide and 150 pixels high.
### Context
The canvas is initially blank. To display something, a script first needs to access the rendering context and draw on it. 
The <canvas> element has a method called getContext(). getContext() takes one parameter - the type of context. For 2D 
graphics you specify "2d"to get a CanvasRenderingContext2D.

## Drawing
Lets talk about drawings
<canvas> only supports one primitive shape: rectangles. All other shapes must be created by combining one or more paths, 
lists of points connected by lines. Luckily, we have an assortment of path drawing functions which make it possible to 
compose very complex shapes.
First let's look at the rectangle. There are three functions that draw rectangles on the canvas:

~~~~
fillRect - draws a filled rectangle.

strokeRect - draws a rectangular outline.

clearRect - clears the specified rectangular area, making it fully transparent.
~~~~

### Drawing rectangle example
In the example you can see drawing two nested rectangles using functions above.

### Drawing paths
The other primitive shapes are paths. A path is a list of points, connected by segments of lines. A path can be closed. 
You need three steps to make a shape with it:

    1. First, you create the path.
    2. Then you use drawing commands to draw into the path.
    3. Once the path has been created, you can stroke or fill the path to render it.
Here are the functions used to perform these steps:

~~~~
beginPath() - creates a new path. 
Path methods - methods to set different paths for objects.
closePath() - connect end point with start point.
stroke() or fill()
~~~~

### Drawing path example
The expample shows drawing a triangle with path functions.

### Colors
If we want to apply colors to a shape, there are two important properties we can use: fillStyle and strokeStyle.

## Animation
Since we're using JavaScript to control <canvas> elements, it's also very easy to make animations. Let’s take a look 
at how to do some basic animations.
Probably the biggest limitation is, that once a shape gets drawn, it stays that way. If we need to move it, we have to 
redraw it and everything that was drawn before it. 

### Save & Restore
Let’s look at two other methods which are indispensable once you start generating complex drawings.

~~~~
save() - saves the entire state of the canvas.

restore() - restores the most recently saved canvas state.
~~~~

Canvas states are stored on a stack. Every time the save() method is called, the current drawing state is pushed onto 
the stack.


### Basic animation steps
These are the steps you need to take to draw a frame:

    1. Clear the canvas
The easiest way to do this is using the clearRect() method.

    2. Save the canvas state
If you're changing any setting and you want to make sure the original state is used each time a frame is drawn, you 
need to save that original state.

    3. Draw animated shapes
The step where you do the actual frame rendering.

    4. Restore the canvas state
If you've saved the state, restore it before drawing a new frame.

### Controlling an animation
Shapes are drawn to the canvas by using the canvas methods directly or by calling custom functions. 
That means we need a way to execute our drawing functions over a period of time. 

First there's the **window.setInterval()**, **window.setTimeout()**, **and window.requestAnimationFrame()** functions, 
which can be used to call a specific function.

If we don't want any user interaction we can use the **setInterval()** function which repeatedly executes the supplied code. 

If we wanted to make a game, we could use keyboard or mouse events to control the animation and use **setTimeout()**.
 
By setting EventListeners, we catch any user interaction and execute our animation functions.
But it is better to use **requestAnimationFrame()** to tells the browser that you wish to perform an animation.  

The browser call a specified function to update an animation before the next repaint.
 
#### Example of animation steps
In the example you can see steps of animation – clear canvas, save state, draw something, restore state, and 
requestAnimationFrame;

### Libraries 
In the conclusion, the Canvas API is extremely powerful, but not always simple to use. The libraries listed below 
can make the creation of canvas-based projects faster and easier. 

### More
More information and examples you can find on developer.mozilla.org