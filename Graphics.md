### Use pixels, x, y coordinates
### - Origin(0, 0) is at top left

### JFrame, creates a frame


canvas.drawLine(x, y, x(1), y(1)) draws a line between the points x, y and x(1), y(1)
canvas.drawRect(x, y, a, b) draws a rectangle starting at x, y with the length in pixels, a, and width of pixels, b
canvas.drawOval(x, y, a, b) draws an oval at the square corner starting at x, y with length in pixels, a, and width of pixels, b

Color \*enter color\*= new Color(x, y, z) creates a new color with the rgb values x, y, z



Color fireTruckRed = new Color(206, 32, 41);
canvas.setColor(fireTruckRed);
canvas.drawOval(x, y, a, b);
#### ^ draws a fireTruckRed color oval 

Canvas.setColor(Color.black);
canvas.fillRect(360, 65, 40, 40);
#### ^ creates a black filled in rectangle


canvas.setColor(Color.yellow);
canvas.drawRect(360, 45, 40, 40)
#### ^ creates a yellow border around the black rectangle


#### super.paint(canvas);
#### setBackground(x) - sets the background the color x

