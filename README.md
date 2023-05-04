Download Link: https://assignmentchef.com/product/solved-csc22100-assignment1-hierarchy-of-java-classes
<br>
Create a hierarchy of Java classes as demonstrated below:

MyLine is_a MyShape:

MyPolygon is_a MyShape:

MyCircle is_a MyShape:

MyShape is the hierarchy’s superclass and inherits the Java class Object. By using JavaFX graphics and the class hierarchy, the user should be able to draw a geometric configuration. For example, an image of alternating concentric circles and inscribed hexagons can be generated, as shown in the assignment sheet. The following additional requirements must be met:

<ul>

 <li>The code is applicable to canvases of variable height and width.</li>

 <li>The dimensions of the shapes are proportional to the smallest dimension of the canvas.</li>

 <li>The hexagons and circles are filled with different colors of your choice, specified through a MyColor enum reference type.</li>

</ul>




<h1>[2] Solution Methods</h1>

<strong> </strong>

<h2>Class MyShape</h2>

MyShape was built to be the superclass of MyLine, MyPolygon, and MyCircle. It initializes two private integer variables that hold an x and y coordinate, as well as a private color variable. The constructor gives a value to these private variables when called. The class contains 3 getter methods and 3 setter methods. The getter methods are getX(), getY(), and getColor(), which returns the x coordinate, y coordinate, and shape color respectively. The setter methods are setX(), setY(), and setColor(), which sets the x coordinate, y coordinate, and shape color respectively. The imports are for the graphics context, which helps draw the shape, and the color.

There are two more methods: toString(), which prints out the MyShape object and its properties in a certain format, and draw(GraphicsContext gc). The draw method takes a graphics context variable as its parameter and only fills the color of the shape.







<h2>Class MyLine</h2>

MyLine is an extension of MyShape, and it starts off with 4 private integers specifically for this class. These integers represent the x and y coordinates of two points. The constructor calls super in order to obtain a color for the line, and then continues to assign values for the coordinates of the two points of the line. The class contains 2 getter methods. The first is getLength(), which uses the distance formula and returns the distance between the two points, and the second method is get_xAngle(), which returns the angle in degrees via arc tangent formula. The imports are for the graphics context, which helps draw the shape, and the color.

There are two more methods: toString(), which prints out the MyLine object and its properties in a certain format, and draw(GraphicsContext gc). The draw method takes a graphics context variable as its parameter and draws a line between two points.







<h2>Class MyCircle</h2>

MyCircle is an extension of MyShape, and it has a private double variable for radius. The constructor sets up the center point and the color of the circle via the super call. It also sets the radius on the next line. There are 3 getter methods, each one involving the radius variable. The getArea() method returns the area of the circle using the standard pi multiplied by the radius squared. The getPerimeter() method returns the perimeter of the circle by multiplying the radius by 2 times pi. The getRadius() method simply returns the radius. The imports are for the graphics context, which helps draw the shape, and the color.

There are two more methods: toString(), which prints out the MyCircle object and its properties in a certain format, and draw(GraphicsContext gc). The draw method takes a graphics context variable as its parameter and fills the circle a certain color.







<h2>Class MyPolygon</h2>

MyPolygon is an extension of MyShape, and it goes more in depth than the other classes. It has 4 private variables: one double variable for the radius, one integer variable for the number of sides, and two arrays to store x and y coordinates. The constructor starts off with calling super in order to have a center point as well as a color for the polygon. Furthermore, the radius and sides are set accordingly, and two arrays are created to store the x and y coordinates respectively for each corner of the polygon. The angle is determined from dividing 2 times pi by the number of sides. By using this angle, the points around the polygon can be determined by using the appropriate trigonometric formulas. The imports are for the graphics context, which helps draw the shape, and the color.

There are 6 getter methods, each returning a double value that describes a property of the polygon. The first is getRadius(), which simply returns the distance from the center point to one corner of the polygon. Next is getArea(), which returns an area that was calculated using a formula that works for every normal polygon. The method getPerimeter() multiplies the side length by the number of sides, and returns the perimeter. The following method, getApothem(), returns the apothem, which is the distance from the center point to the middle of one side of the polygon. This is calculated by multiplying the radius by the cosine of 180 degrees divided by the number of sides. A simple getAngle() method returns the angle between two corners of the polygon. The final method, getSide(), returns the length of one side of the polygon. This is found by multiplying 2 times the radius by the sin of the angle between two corners of the polygon.

There are two more methods: toString(), which prints out the MyPolygon object and its properties in a certain format, and draw(GraphicsContext gc). The draw method takes a graphics context variable as its parameter and fills the polygon a certain color. It also scribes each side of the polygon and creates a perimeter that is the same color as the inside of the polygon.







<h2>Class Main</h2>

Main is where objects from the other classes are created and drawn. There are multiple imports used here. The first import is javafx.application.Application, which is used to create a separate extended application that holds the graphics all together. Next is javafx.scene.Scene, which holds the content inside the window. The import javafx.stage.Stage is the window itself with functions such as minimize, maximize, resize, and close. Next is the import javafx.scene.canvas.Canvas, which is basically the drawing board. The graphics context comes from javafx.scene.canvas.GraphicsContext, and it behaves like a pen that draws and fills shapes, lines, and colors. The final import is javafx.scene.layout.StackPane, which is a layout for the elements that allows them to be stacked on top of each other instead of horizontally or vertically.

There are two final integer values in the beginning of the class, which are for determining the window width and height. These can be changed to whatever values the user likes, as long as it is an integer. A stage is set up with the title “Assignment 1”, as well as a canvas for the graphics context to draw on. The line width of the graphics context was set for 3 just because of preference.

A series of objects were made to mimic the figure shown on the assignment sheet. Alternating polygons and circles of different colors were made, each one using the radius or apothem of the shape before it. This was to insure that each shape was inscribed with the one outside of it. Lastly, two diagonal black lines were drawn on top of the sequence of shapes to complete the picture. The properties of each object were printed via their respective toString() methods.







<h2>Enum MyColor</h2>

MyColor imports javafx.scene.paint.Color in order to pass custom RGBA (red, green, blue, and opacity) values and obtain an actual value for the color in hexadecimal. The enum has multiple predefined colors ranging across the spectrum, each having its own unique RGBA values. The private integers r, g, b, a hold values for red, green, blue, and the opacity respectively. The constructor takes in custom values that will be assigned to the private variables.

The function getCol() returns a color by using the Color.rgb method from javafx.scene.paint.Color. An example of this being used is executing MyColor.CYAN.getCol(), which will return the color for cyan.




<h1>[3] Codes Developed</h1>

—– MyShape.java —–

<table width="624">

 <tbody>

  <tr>

   <td width="624">/* ———————————————————-</td>

  </tr>

  <tr>

   <td width="624">Class MyShape is the hierarchy’s superclass and inherits the</td>

  </tr>

  <tr>

   <td width="624">Java class Object. An implementation of the class defines a</td>

  </tr>

  <tr>

   <td width="624">reference point (x, y) and the color of the shape.</td>

  </tr>

  <tr>

   <td width="624">———————————————————- */</td>

  </tr>

  <tr>

   <td width="624">package ​sample​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.canvas.GraphicsContext​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.paint.Color​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">public class ​MyShape {</td>

  </tr>

  <tr>

   <td width="624">   ​private int ​x​, ​y​; ​// Point of shape in pixels</td>

  </tr>

  <tr>

   <td width="624">   ​private ​Color ​color​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​MyShape​(​int ​x​, int ​y​, ​Color color){</td>

  </tr>

  <tr>

   <td width="624">       ​this​.​x ​= x​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​y ​= y​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​color ​= color​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​public int ​getX​(){ ​return ​x​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public int ​getY​(){ ​return ​y​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public ​Color ​getColor​(){ ​return ​color​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​setX​(​int ​x){ ​this​.​x ​= x​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​setY​(​int ​y){ ​this​.​y ​= y​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​setColor​(Color color){ ​this​.​color ​= color​; ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​public ​String ​toString​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​String.​<em>format</em>​(​”—– Shape Properties —–​
​%15s (%d,%d)​
​%15s “</td>

  </tr>

  <tr>

   <td width="624">+ getColor(),​</td>

  </tr>

  <tr>

   <td width="624">               ​”Start Point:”​,​x​,​y​,​”Color:”​)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​draw​(GraphicsContext gc){</td>

  </tr>

  <tr>

   <td width="624">       gc.setFill(​color​)​;</td>

  </tr>

  <tr>

   <td width="624">       ​gc.fill()​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">}</td>

  </tr>

 </tbody>

</table>




—– MyLine.java —–

<table width="624">

 <tbody>

  <tr>

   <td width="624">/* ———————————————————-</td>

  </tr>

  <tr>

   <td width="624">Class MyLine inherits class MyShape. The MyLine object is a</td>

  </tr>

  <tr>

   <td width="624">straight line defined by the endpoints (x1, y1) and (x2, y2).</td>

  </tr>

  <tr>

   <td width="624">The MyLine object may be of any color.</td>

  </tr>

  <tr>

   <td width="624">———————————————————- */</td>

  </tr>

  <tr>

   <td width="624">package ​sample​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.canvas.GraphicsContext​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.paint.Color​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">public class ​MyLine ​extends ​MyShape {</td>

  </tr>

  <tr>

   <td width="624">   ​private int ​x1​, ​y1​, ​x2​, ​y2​; ​// Coordinates of two points of line</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​MyLine​(​int ​x1​, int ​x2​, int ​y1​, int ​y2​, ​Color color){</td>

  </tr>

  <tr>

   <td width="624">       ​super​(​0​, ​0​, ​color)​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​x1 ​= x1​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​x2 ​= x2​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​y1 ​= y1​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​y2 ​= y2​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getLength​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​Math.​<em>sqrt</em>​(Math.​<em>pow</em>​(​x2​-​x1​,​2​) + Math.​<em>pow</em>​(​y2​-​y1​,​2​))​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​get_xAngle​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​Math.​<em>toDegrees</em>​(Math.​<em>atan</em>​((​y2​-​y1​)/(​x2​-​x1​)))​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​@Override</td>

  </tr>

  <tr>

   <td width="624">   ​public ​String ​toString​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​String.​<em>format</em>​(​”—– Line Properties —–​
​%15s (%d,%d)​
​%15s</td>

  </tr>

  <tr>

   <td width="624">(%d,%d)​
​%15s %f​
​%15s %f​
​%15s “​+​super​.getColor()​,</td>

  </tr>

  <tr>

   <td width="624">               ​”Point 1:”​,​x1​,​y1​,​”Point 2:”​,​x2​,​y2​,​”Line</td>

  </tr>

  <tr>

   <td width="624">Length:”​,​getLength()​,​”Angle:”​,​get_xAngle()​,​”Color:”​)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">   ​@Override</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​draw​(GraphicsContext gc){</td>

  </tr>

  <tr>

   <td width="624">       gc.setStroke(​super​.getColor())​;</td>

  </tr>

  <tr>

   <td width="624">       ​gc.strokeLine(​x1​,​y1​,​x2​,​y2​)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">}</td>

  </tr>

 </tbody>

</table>




—– MyCircle.java —–

<table width="624">

 <tbody>

  <tr>

   <td width="624">/* ———————————————————-</td>

  </tr>

  <tr>

   <td width="624">Class MyCircle inherits class MyShape.  The MyCircle object</td>

  </tr>

  <tr>

   <td width="624">is defined by its center (x, y) and radius r, and may be</td>

  </tr>

  <tr>

   <td width="624">filled with a color.</td>

  </tr>

  <tr>

   <td width="624">———————————————————- */</td>

  </tr>

  <tr>

   <td width="624">package ​sample​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.canvas.GraphicsContext​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.paint.Color​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">public class ​MyCircle ​extends ​MyShape {</td>

  </tr>

  <tr>

   <td width="624">   ​private double ​radius​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​MyCircle​(​int ​x​, int ​y​, double ​radius​, ​Color color){</td>

  </tr>

  <tr>

   <td width="624">       ​super​(x​,​y​,​color)​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​radius ​= radius​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getArea​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​Math.​<em>PI </em>​* Math.​<em>pow</em>​(​radius​, ​2​)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getPerimeter​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​2 ​* Math.​<em>PI </em>​* ​radius​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getRadius​(){ ​return ​radius​; ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​@Override</td>

  </tr>

  <tr>

   <td width="624">   ​public ​String ​toString​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​String.​<em>format</em>​(​”—– Circle Properties —–​
​%15s %f​
​%15s</td>

  </tr>

  <tr>

   <td width="624">%f​
​%15s %f​
​%15s “​+​super​.getColor()​,</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">“Radius:”​,​getRadius()​,​”Area:”​,​getArea()​,​”Perimeter:”​,​getPerimeter()​,​”Color:”​)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">   ​@Override</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​draw​(GraphicsContext gc){</td>

  </tr>

  <tr>

   <td width="624">       gc.setFill(​super​.getColor())​;</td>

  </tr>

  <tr>

   <td width="624">       ​gc.fillOval(​super​.getX() – ​radius​, super​.getY() – ​radius​, ​2 ​* ​radius​, ​2</td>

  </tr>

  <tr>

   <td width="624">* ​radius​)​;</td>

  </tr>

  <tr>

   <td width="624">       ​//gc.strokeRect(super.getX() – radius, super.getY() – radius, 2 *</td>

  </tr>

  <tr>

   <td width="624">radius, 2 * radius);</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">}</td>

  </tr>

 </tbody>

</table>




—– MyPolygon.java —–

<table width="624">

 <tbody>

  <tr>

   <td width="624">/* ———————————————————-</td>

  </tr>

  <tr>

   <td width="624">Class MyPolygon inherits class MyShape. The MyPolygon object</td>

  </tr>

  <tr>

   <td width="624">is a regular polygon defined by the integer parameter, N—</td>

  </tr>

  <tr>

   <td width="624">the number of the polygon’s equal side lengths and equal</td>

  </tr>

  <tr>

   <td width="624">interior angles, and the center (x, y) and radius, r, of the</td>

  </tr>

  <tr>

   <td width="624">circle in which it is inscribed. The MyPolygon object may</td>

  </tr>

  <tr>

   <td width="624">be filled with a color.</td>

  </tr>

  <tr>

   <td width="624">———————————————————- */</td>

  </tr>

  <tr>

   <td width="624">package ​sample​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.canvas.GraphicsContext​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.paint.Color​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">public class ​MyPolygon ​extends ​MyShape {</td>

  </tr>

  <tr>

   <td width="624">   ​private double ​radius​;</td>

  </tr>

 </tbody>

</table>




<table width="624">

 <tbody>

  <tr>

   <td width="624">   private int ​sides​;</td>

  </tr>

  <tr>

   <td width="624">   double ​xp​[]​;</td>

  </tr>

  <tr>

   <td width="624">   double ​yp​[]​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​MyPolygon​(​int ​x​, int ​y​, double ​radius​, int ​sides​, ​Color color){</td>

  </tr>

  <tr>

   <td width="624">       ​super​(x​,​y​,​color)​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​radius ​= radius​;</td>

  </tr>

  <tr>

   <td width="624">       this​.​sides ​= sides​;</td>

  </tr>

  <tr>

   <td width="624">       ​xp ​= ​new double​[sides]​;</td>

  </tr>

  <tr>

   <td width="624">       ​yp ​= ​new double​[sides]​;</td>

  </tr>

  <tr>

   <td width="624">       double ​ang = (​2 ​* Math.​<em>PI</em>​)/sides​;</td>

  </tr>

  <tr>

   <td width="624">       for ​(​int ​i = ​0​; ​i &lt; sides​; ​++i){</td>

  </tr>

  <tr>

   <td width="624">           ​xp​[i] = x + (radius*(-​1 ​* Math.​<em>sin</em>​(i*ang)))​;</td>

  </tr>

  <tr>

   <td width="624">           ​yp​[i] = y + (radius*(-​1 ​* Math.​<em>cos</em>​(i*ang)))​;</td>

  </tr>

  <tr>

   <td width="624">       ​}</td>

  </tr>

  <tr>

   <td width="624">   }</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getRadius​(){ ​return ​radius​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getArea​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​Math.​<em>pow</em>​(​radius​,​2​) * ​sides ​* Math.​<em>sin</em>​(getAngle()) * ​0.5​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getPerimeter​(){ ​return ​sides ​* getSide()​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getApothem​(){ ​return ​radius ​* Math.​<em>cos</em>​(Math.​<em>toRadians</em>​(​180 ​/</td>

  </tr>

  <tr>

   <td width="624">sides​))​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getAngle​(){ ​return ​Math.​<em>PI</em>​/​sides​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public double ​getSide​(){ ​return ​2 ​* ​radius ​* Math.​<em>sin</em>​(Math.​<em>PI</em>​/​sides​)​; ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​@Override</td>

  </tr>

  <tr>

   <td width="624">   ​public ​String ​toString​(){</td>

  </tr>

  <tr>

   <td width="624">       ​return ​String.​<em>format</em>​(​”—– Polygon Properties —–​
​%15s %f​
​%15s</td>

  </tr>

  <tr>

   <td width="624">%f​
​%15s %f​
​%15s %f​
​%15s %f​
​%15s “​+​super​.getColor()​,</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">“Radius:”​,​getRadius()​,​”Area:”​,​getArea()​,​”Perimeter:”​,​getPerimeter()​,</td>

  </tr>

  <tr>

   <td width="624">               ​”Angle:”​,​getAngle()​,​”Apothem:”​,​getApothem()​,​”Color:”​)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​@Override</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​draw​(GraphicsContext gc){</td>

  </tr>

  <tr>

   <td width="624">       gc.setFill(​super​.getColor())​;</td>

  </tr>

  <tr>

   <td width="624">       ​gc.setStroke(​super​.getColor())​;</td>

  </tr>

  <tr>

   <td width="624">       ​gc.setLineWidth(​3​)​;</td>

  </tr>

  <tr>

   <td width="624">       ​gc.strokePolygon(​xp​, ​yp​, ​sides​)​;</td>

  </tr>

  <tr>

   <td width="624">       ​gc.fillPolygon(​xp​, ​yp​, ​sides​)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​public void ​border​(GraphicsContext gc){</td>

  </tr>

  <tr>

   <td width="624">       gc.setStroke(Color.​<em>BLACK</em>​)​;</td>

  </tr>

  <tr>

   <td width="624">       for ​(​int ​i = ​1​; ​i &lt; ​sides​; ​++i){</td>

  </tr>

  <tr>

   <td width="624">           gc.strokeLine(​xp​[i-​1​]​, ​yp​[i-​1​]​, ​xp​[i]​, ​yp​[i])​;</td>

  </tr>

  <tr>

   <td width="624">       ​}</td>

  </tr>

  <tr>

   <td width="624">       gc.strokeLine(​xp​[​sides​-​1​]​, ​yp​[​sides​-​1​]​, ​xp​[​0​]​, ​yp​[​0​])​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">}</td>

  </tr>

 </tbody>

</table>




—– Main.java —–

<table width="624">

 <tbody>

  <tr>

   <td width="624">/* Ashraq Khan // CS 22100 Assignment 1 // 09/21/2020 */</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">package ​sample​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">/* Imports */</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.application.Application​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.Scene​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.canvas.Canvas​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.canvas.GraphicsContext​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.layout.StackPane​;</td>

  </tr>

  <tr>

   <td width="624">import ​javafx.stage.Stage​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">/* Driver class */</td>

  </tr>

  <tr>

   <td width="624">public class ​Main ​extends ​Application {</td>

  </tr>

  <tr>

   <td width="624">   ​// Sets boundaries of stage</td>

  </tr>

  <tr>

   <td width="624">   ​final int ​WIDTH ​= ​1000​;</td>

  </tr>

  <tr>

   <td width="624">   final int ​HEIGHT ​= ​600​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​@Override</td>

  </tr>

  <tr>

   <td width="624">   ​public void ​start​(Stage primaryStage) {</td>

  </tr>

  <tr>

   <td width="624">       ​try ​{</td>

  </tr>

  <tr>

   <td width="624">           ​// Sets up primary stage, canvas, and graphics context</td>

  </tr>

  <tr>

   <td width="624">           ​primaryStage.setTitle(​”Assignment 1″​)​;</td>

  </tr>

  <tr>

   <td width="624">           ​Canvas canvas = ​new ​Canvas(​WIDTH​, ​HEIGHT​)​;</td>

  </tr>

  <tr>

   <td width="624">           ​GraphicsContext gc = canvas.getGraphicsContext2D()​;</td>

  </tr>

  <tr>

   <td width="624">           ​gc.setLineWidth(​3​)​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">           ​// Prints alternate hexagons and circles of different colors</td>

  </tr>

  <tr>

   <td width="624">           ​MyPolygon hexGray = ​new ​MyPolygon(​WIDTH​/​2​,​HEIGHT​/​2​,</td>

  </tr>

  <tr>

   <td width="624">200​,​6​,​MyColor.​<em>GREY</em>​.getCol())​;</td>

  </tr>

  <tr>

   <td width="624">           ​hexGray.draw(gc)​;</td>

  </tr>

  <tr>

   <td width="624">           ​MyCircle circleY = ​new ​MyCircle(​WIDTH​/​2​,​HEIGHT​/​2​,</td>

  </tr>

  <tr>

   <td width="624">hexGray.getApothem()​, ​MyColor.​<em>YELLOW</em>​.getCol())​;</td>

  </tr>

  <tr>

   <td width="624">           ​circleY.draw(gc)​;</td>

  </tr>

  <tr>

   <td width="624">           ​MyPolygon hexGreen = ​new ​MyPolygon(​WIDTH​/​2​,​HEIGHT​/​2​,</td>

  </tr>

  <tr>

   <td width="624">circleY.getRadius()​, ​6​,​MyColor.​<em>LIME</em>​.getCol())​;</td>

  </tr>

  <tr>

   <td width="624">           ​hexGreen.draw(gc)​;</td>

  </tr>

  <tr>

   <td width="624">           ​MyCircle circleP = ​new ​MyCircle(​WIDTH​/​2​,​HEIGHT​/​2​,</td>

  </tr>

  <tr>

   <td width="624">hexGreen.getApothem()​, ​MyColor.​<em>HOTPINK</em>​.getCol())​;</td>

  </tr>

  <tr>

   <td width="624">           ​circleP.draw(gc)​;</td>

  </tr>

  <tr>

   <td width="624">           ​MyPolygon hexBlue = ​new ​MyPolygon(​WIDTH​/​2​,​HEIGHT​/​2​,</td>

  </tr>

  <tr>

   <td width="624">circleP.getRadius()​,​6​,​MyColor.​<em>CYAN</em>​.getCol())​;</td>

  </tr>

  <tr>

   <td width="624">           ​hexBlue.draw(gc)​;</td>

  </tr>

  <tr>

   <td width="624">           ​hexGray.border(gc)​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">           ​// Lists properties of all shapes</td>

  </tr>

  <tr>

   <td width="624">           ​System.​<em>out</em>​.println(hexGray + ​”​

​” ​+ circleY + ​”​

​” ​+ hexGreen +</td>

  </tr>

  <tr>

   <td width="624">“​

​” ​+ circleP + ​”​

​” ​+ hexBlue + ​”​

​”​)​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">           ​MyLine line1 = ​new ​MyLine(​0​,​WIDTH​,​0​,​HEIGHT​,​MyColor.​<em>BLACK</em>​.getCol())​;</td>

  </tr>

  <tr>

   <td width="624">           ​MyLine line2 = ​new ​MyLine(​0​,​WIDTH​,​HEIGHT​,​0​,​MyColor.​<em>BLACK</em>​.getCol())​;</td>

  </tr>

  <tr>

   <td width="624">           ​line1.draw(gc)​;</td>

  </tr>

  <tr>

   <td width="624">           ​line2.draw(gc)​;</td>

  </tr>

  <tr>

   <td width="624">           ​gc.strokeRect(​0​, ​0​, ​WIDTH​, ​HEIGHT​)​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">           ​// Lists properties of all lines</td>

  </tr>

  <tr>

   <td width="624">           ​System.​<em>out</em>​.println(line1 + ​”​

​” ​+ line2 + ​”​

​”​)​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">           ​// Sets stack pane and scene for image to appear on</td>

  </tr>

  <tr>

   <td width="624">           ​StackPane root = ​new ​StackPane(canvas)​;</td>

  </tr>

  <tr>

   <td width="624">           ​Scene scene = ​new ​Scene(root​,​WIDTH​,​HEIGHT​)​;</td>

  </tr>

  <tr>

   <td width="624">           ​primaryStage.setScene(scene)​;</td>

  </tr>

  <tr>

   <td width="624">           ​primaryStage.show()​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">       ​} ​catch​(Exception e) {</td>

  </tr>

  <tr>

   <td width="624">           e.printStackTrace()​;</td>

  </tr>

  <tr>

   <td width="624">       ​}</td>

  </tr>

  <tr>

   <td width="624">   }</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​public static void ​main​(String[] args) {</td>

  </tr>

  <tr>

   <td width="624">       ​<em>launch</em>​(args)​;</td>

  </tr>

  <tr>

   <td width="624">   ​}</td>

  </tr>

  <tr>

   <td width="624">}</td>

  </tr>

 </tbody>

</table>




—– MyColor.java —–

<table width="624">

 <tbody>

  <tr>

   <td width="624">/* ———————————————————-</td>

  </tr>

  <tr>

   <td width="624">Enum MyColor sets up pre-made colors of varying RGB values</td>

  </tr>

  <tr>

   <td width="624">and opacities. These will be used to color shapes and lines.</td>

  </tr>

  <tr>

   <td width="624">———————————————————- */</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">package ​sample​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">import ​javafx.scene.paint.Color​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">public enum ​MyColor{</td>

  </tr>

  <tr>

   <td width="624">   ​<em>RED</em>​(​255​,​0​,​0​,​255​)​, ​<em>BLUE</em>​(​0​,​0​,​255​,​255​)​,</td>

  </tr>

  <tr>

   <td width="624">   ​<em>LIME</em>​(​0​,​255​,​0​,​255​)​, ​<em>CYAN</em>​(​0​,​255​,​255​,​255​)​,</td>

  </tr>

  <tr>

   <td width="624">   ​<em>GREEN</em>​(​0​,​128​,​0​,​255​)​, ​<em>GREY</em>​(​128​,​128​,​128​,​255​)​,</td>

  </tr>

  <tr>

   <td width="624">   ​<em>MAGENTA</em>​(​255​,​0​,​255​,​255​)​, ​<em>PURPLE</em>​(​128​,​0​,​128​,​255​)​,</td>

  </tr>

  <tr>

   <td width="624">   ​<em>VIOLET</em>​(​148​,​0​,​211​,​255​)​, ​<em>YELLOW</em>​(​255​,​255​,​0​,​255​)​,</td>

  </tr>

  <tr>

   <td width="624">   ​<em>WHITE</em>​(​255​,​255​,​255​,​255​)​, ​<em>BLACK</em>​(​0​,​0​,​0​,​255​)​,</td>

  </tr>

  <tr>

   <td width="624">   ​<em>HOTPINK</em>​(​255​,​105​,​180​,​255​)​;</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   private int ​r​,​g​,​b​,​a​; ​// Value for red, green, blue, and opacity</td>

  </tr>

  <tr>

   <td width="624"></td>

  </tr>

  <tr>

   <td width="624">   ​MyColor​(​int ​r​, int ​g​, int ​b​, int ​a){ ​this​.​r ​= r​; this​.​g ​= g​; this​.​b ​= b​;</td>

  </tr>

  <tr>

   <td width="624">this​.​a ​= a​; ​}</td>

  </tr>

  <tr>

   <td width="624">   ​public ​Color ​getCol​() { ​return ​Color.​<em>rgb</em>​(​r​, ​g​, ​b​, ​(​double​)(​a​/​255​))​; ​}</td>

  </tr>

  <tr>

   <td width="624">}</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<h1>[4] Outputs Produced</h1>

<strong> </strong>