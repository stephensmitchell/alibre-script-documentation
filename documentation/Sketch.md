# Sketch

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index)**

** Location:**[Sketching & Drawing](Classes#sketching) Sketch

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Sketch class provides functionality for 2D sketching operations including creating geometric figures, applying constraints, and managing sketch elements.

## Related Classes
- [Sketch3D](Sketch3D) - 3D sketching operations
- [Sketch.Constraints](Sketch.Constraints) - Sketch constraint management
- [SketchPoint](SketchPoint) - 2D sketch points
- [Line](Line), [Circle](Circle), [CircularArc](CircularArc) - Sketch geometry
- [Part](Part) - Contains sketches

## Quick Navigation
- [Properties](#properties) - Sketch properties
- [Methods](#methods) - All available operations
- [Arc Methods](#arc-methods) - Circular arc operations
- [Line Methods](#line-methods) - Line creation and manipulation
- [Circle Methods](#circle-methods) - Circle operations
- [Constraint Methods](#constraint-methods) - Apply sketch constraints

## Properties

### Figures
Type: `Object`
A list of figures (line, circle, circulararc, bspline, ellipse, elliptical arc) defined on the sketch

### Name
Type: `Object`
Name of the sketch

### Origin
Type: `Object`
The point that defines the origin

## Methods


### AddArc

Adds a circular arc to the sketch

```python
def AddArc(new_arc):
"""
Adds a circular arc to the sketch

Args:
new_arc (CircularArc): Arc to add

Returns:
The added circular arc

"""
```


### AddArcCenterStartAngle

Adds a circular arc using center, start and angle
Arc goes anti-clockwise from start

```python
def AddArcCenterStartAngle(center_x, center_y, start_x, start_y, angle, is_reference):
"""
Adds a circular arc using center, start and angle Arc goes anti-clockwise from start

Args:
center_x (float): X coordinate for center
center_y (float): Y coordinate for center
start_x (float): X coordinate for start
start_y (float): Y coordinate for start
angle (float): Arc angle in degrees
is_reference (bool): True if arc is a reference figure

Returns:
The added circular arc

"""
```


### AddArcCenterStartEnd

Adds a circular arc using three points - center, start and end
Arc goes anti-clockwise from start to end

```python
def AddArcCenterStartEnd(center_x, center_y, start_x, start_y, end_x, end_y, is_reference):
"""
Adds a circular arc using three points - center, start and end Arc goes anti-clockwise from start to end

Args:
center_x (float): X coordinate for center
center_y (float): Y coordinate for center
start_x (float): X coordinate for start
start_y (float): Y coordinate for start
end_x (float): X coordinate for end
end_y (float): Y cordinate for end
is_reference (bool): True if arc is a reference figure

Returns:
The added circular arc

"""
```


### AddBspline

Adds a Bspline to the sketch

**Overload 1:**

```python
def AddBspline(order, control_points, knot_vectors, weights, is_reference):
"""
Adds a Bspline to the sketch

Args:
order (int): Order of the Bspline (Degree - 1)
control_points (list): List of control points
knot_vectors (list): List of knot vectors
weights (list): List of control point weights
is_reference (bool): True to create a reference bspline

Returns:
The created Bspline

"""
```

**Overload 2:**

```python
def AddBspline(points, is_reference):
"""
Adds a Bspline to the sketch through a set of points

Args:
points (list): List of points
is_reference (bool): True to create a reference bspline

Returns:
The created Bspline

"""
```

**Overload 3:**

```python
def AddBspline(new_bspline):
"""
Adds a new bspline to the sketch

Args:
new_bspline (Bspline): Bspline to add to the sketch

Returns:
The added Bspline

"""
```


### AddCircle

Adds a circle to the sketch

**Overload 1:**

```python
def AddCircle(center_x, center_y, diameter, is_reference):
"""
Adds a circle to the sketch

Args:
center_x (float): X coordinate of circle center
center_y (float): Y coordinate of circle center
diameter (float): Circle diameter
is_reference (bool): True to create a reference circle

Returns:
A circle object

"""
```

**Overload 2:**

```python
def AddCircle(new_circle):
"""
Adds a circle to the sketch

Args:
new_circle (Circle): Circle to add to sketch

Returns:
The added circle

"""
```


### AddConstraint

Adds a constraint to the sketch

**Overload 1:**

```python
def AddConstraint(figure, constraint):
"""
Adds a constraint to the sketch

Args:
figure (ISketchFigure): Figure to constrain (e.g. Line)
constraint (Sketch.Constraints): Constraint to apply

Returns:
True if constraint was added

"""
```

**Overload 2:**

```python
def AddConstraint(figures, constraint):
"""
Adds a constraint to the sketch

Args:
figures (list): List of Sketch figures to constrain [Figure1, Figure2, ...] (Circle, Line, CircularArc, etc.)
constraint (Sketch.Constraints): Constraint to apply

Returns:
Returns True if constraint was added

"""
```


### AddDimension

Adds a dimension to the sketch between two points

**Overload 1:**

```python
def AddDimension(p1, p2):
"""
Adds a dimension to the sketch between two points

Args:
p1 (SketchPoint): First point
p2 (SketchPoint): Second point

"""
```

**Overload 2:**

```python
def AddDimension(circle):
"""
Adds a dimension to the radius of a circle

Args:
circle (Circle): Circle to dimension

"""
```

**Overload 3:**

```python
def AddDimension(arc):
"""
Adds a dimension to the radius of an arc

Args:
arc (CircularArc): Arc to dimension

"""
```


### AddEllipse

Adds an ellipse to the sketch using three points

**Overload 1:**

```python
def AddEllipse(center_x, center_y, major_x, major_y, minor_x, minor_y, is_reference):
"""
Adds an ellipse to the sketch using three points

Args:
center_x (float): X coordinate of ellipse center
center_y (float): Y coordinate of ellipse center
major_x (float): X coordinate of ellipse on major axis
major_y (float): Y coordinate of ellipse on major axis
minor_x (float): X coordinate of ellipse on minor axis
minor_y (float): Y coordinate of ellipse on minor axis
is_reference (bool): True to create a reference ellipse

Returns:
An ellipse object

"""
```

**Overload 2:**

```python
def AddEllipse(center_x, center_y, major_axis_diameter, minor_major_ratio, major_axis_angle, is_reference):
"""
Adds an ellipse to the sketch

Args:
center_x (float): X coordinate of ellipse center
center_y (float): Y coordinate of ellipse center
major_axis_diameter (float): Diameter of ellipse on major axis
minor_major_ratio (float): Ratio of minor diameter to major diameter
major_axis_angle (float): Angle of major axis
is_reference (bool): True to create a reference ellipse

Returns:
An ellipse object

"""
```

**Overload 3:**

```python
def AddEllipse(new_ellipse):
"""
Adds an ellipse to the sketch

Args:
new_ellipse (Ellipse): Ellipse to add

Returns:
Added ellipse

"""
```


### AddEllipticalArc

Adds an elliptical arc to the sketch

**Overload 1:**

```python
def AddEllipticalArc(center_x, center_y, start_x, start_y, end_x, end_y, major_axis_diameter, minor_major_ratio, major_axis_angle, is_reference):
"""
Adds an elliptical arc to the sketch

Args:
center_x (float): X coordinate of arc center
center_y (float): Y coordinate of arc center
start_x (float): X coorindate of arc start
start_y (float): Y coordinate of arc start
end_x (float): X coordinate of arc end
end_y (float): Y coordinate of arc end
major_axis_diameter (float): Diameter of ellipse on major axis
minor_major_ratio (float): Ratio of minor diameter to major diameter
major_axis_angle (float): Angle of major axis
is_reference (bool): True to create a reference elliptical arc

Returns:
An elliptical arc object

"""
```

**Overload 2:**

```python
def AddEllipticalArc(new_elliptical_arc):
"""
Adds an elliptical arc to the sketch

Args:
new_elliptical_arc (EllipticalArc): Elliptical arc to add

Returns:
Added elliptical arc

"""
```


### AddFigure

Adds a figure to the sketch

```python
def AddFigure(new_figure):
"""
Adds a figure to the sketch

Args:
new_figure (ISketchFigure): Figure to add

Returns:
The added figure

"""
```


### AddLine

Adds a line to the sketch

**Overload 1:**

```python
def AddLine(start_point, end_point, is_reference):
"""
Adds a line to the sketch

Args:
start_point (list): Start of line [X, Y]
end_point (list): End of line [X, Y]
is_reference (bool): true if line is a reference line

Returns:
The added line

"""
```

**Overload 2:**

```python
def AddLine(new_line):
"""
Adds a line to the sketch

Args:
new_line (Line): 2D line to add

Returns:
The added line

"""
```

**Overload 3:**

```python
def AddLine(x1, y1, x2, y2, is_reference):
"""
Adds a line to the sketch

Args:
x1 (float): Start point X
y1 (float): Start point Y
x2 (float): End point X
y2 (float): End point Y
is_reference (bool): true to create a reference line

Returns:
The added line

"""
```


### AddLines

Adds a polyline to the sketch

```python
def AddLines(points, is_reference):
"""
Adds a polyline to the sketch

Args:
points (list): Set of points [Point1X, Point1Y, Point2X, Point2Y, ...]
is_reference (bool): true if line is a reference line

"""
```


### AddPoint

Adds a point to the sketch

**Overload 1:**

```python
def AddPoint(x, y):
"""
Adds a point to the sketch

Args:
x (float): Point X coordinate
y (float): Point Y coordinate

Returns:
The created sketch point

"""
```

**Overload 2:**

```python
def AddPoint(x, y, is_reference):
"""
Adds a point to the sketch [DEPRECATED - DO NOT USE]

Args:
x (float): Point X coordinate
y (float): Point Y coordinate
is_reference (bool): Set to false

Returns:
The added point

"""
```

**Overload 3:**

```python
def AddPoint(new_point):
"""
Adds a point to the sketch

Args:
new_point (SketchPoint): Point to add

Returns:
The added point

"""
```


### AddPolygon

Adds a regular polygon to the sketch

```python
def AddPolygon(center_x, center_y, diameter, sides, is_reference):
"""
Adds a regular polygon to the sketch

Args:
center_x (float): X coordinate for polygon center
center_y (float): Y coordinate for polygon center
diameter (float): Diameter of polygon
sides (int): Number of sides
is_reference (bool): True to create a reference polygon

"""
```


### AddPolyhole

Adds a polyhole to the sketch
Create a "circle" whose size should be accurate regardless of the 3D printing method
See: http://hydraraptor.blogspot.co.uk/2011/02/polyholes.html

```python
def AddPolyhole(center_x, center_y, diameter, is_reference):
"""
Adds a polyhole to the sketch Create a "circle" whose size should be accurate regardless of the 3D printing method See: http://hydraraptor.blogspot.co.uk/2011/02/polyholes.html

Args:
center_x (float): X coordinate for hole center
center_y (float): Y coordinate for hole center
diameter (float): Diameter of hole
is_reference (bool): true if line is a reference line

"""
```


### AddPolyline

Adds a polyline to the sketch

```python
def AddPolyline(line, is_reference):
"""
Adds a polyline to the sketch

Args:
line (Polyline): Polyine to add
is_reference (bool): true if line is a reference line

"""
```


### AddRectangle

Adds a rectangle to the sketch

```python
def AddRectangle(bottom_left_x, bottom_left_y, top_right_x, top_right_y, is_reference):
"""
Adds a rectangle to the sketch

Args:
bottom_left_x (float): X coordinate of bottom left corner
bottom_left_y (float): Y coordinate of bottom left corner
top_right_x (float): X coordinate of top right
top_right_y (float): Y coordinate of top right
is_reference (bool): True to create a reference rectangle

"""
```


### CopyFrom

Copies a sketch into this sketch

**Overload 1:**

```python
def CopyFrom(source):
"""
Copies a sketch into this sketch

Args:
source (Sketch): Sketch to copy from

"""
```

**Overload 2:**

```python
def CopyFrom(source, angle, rotation_center_x, rotation_center_y, translate_x, translate_y, scale_origin_x, scale_origin_y, scale_factor):
"""
Copies a sketch into this sketch

Args:
source (Sketch): Sketch to copy from
angle (float): Rotation angle
rotation_center_x (float): X-coodinate for center of rotation
rotation_center_y (float): Y-coordinate for center of rotation
translate_x (float): Amount to move sketch in X direction
translate_y (float): Amount to move sketch in Y direction
scale_origin_x (float): X-coordinate for scaling origin
scale_origin_y (float): Y-coordinate for scaling origin
scale_factor (float): Factor for scaling as a percentage

"""
```


### ExportSVG

Exports the sketch to an SVG

**Overload 1:**

```python
def ExportSVG(file_name):
"""
Exports the sketch to an SVG

Args:
file_name (str): Path and name of SVG file to export to

"""
```

**Overload 2:**

```python
def ExportSVG(file_name, include_references):
"""
Exports the sketch to an SVG

Args:
file_name (str): Path and name of SVG file to export to
include_references (bool): true to include reference figures in export

"""
```

**Overload 3:**

```python
def ExportSVG(file_name, include_references, stroke_width, stroke_color, stroke_line_cap, stroke_dashed, stroke_dash_length, reference_stroke_width, reference_stroke_color, reference_stroke_line_cap, reference_stroke_dashed, reference_stroke_dash_length):
"""
Exports the sketch to an SVG with specific styling

Args:
file_name (str): Path and name of SVG file to export to
include_references (bool): true to include reference figures in export
stroke_width (float): Stroke width
stroke_color (str): String containing name of stroke color
stroke_line_cap (str): String containing name of stroke line cap type
stroke_dashed (bool): true if stroke dashed, false if solid
stroke_dash_length (float): Length of stroke dashes if dashed
reference_stroke_width (float): Reference stroke width
reference_stroke_color (str): String containing name of reference stroke color
reference_stroke_line_cap (str): String containing name of reference stroke line cap type, can be: butt, round, square
reference_stroke_dashed (bool): true if reference stroke dashed, false if solid
reference_stroke_dash_length (float): Length of reference stroke dashes if dashed

"""
```


### FromXml

Adds elements to the sketch from XML

```python
def FromXml(xml):
"""
Adds elements to the sketch from XML

Args:
xml (str): XML to parse

"""
```


### GlobaltoPoint

Projects a 3D point in the part coordinate system into a point on the sketch

```python
def GlobaltoPoint(x, y, z):
"""
Projects a 3D point in the part coordinate system into a point on the sketch

Args:
x (float): X coordinate of 3D point
y (float): Y coordinate of 3D point
z (float): Z coordinate of 3D point

Returns:
Python list [x, y]

"""
```


### ImportSVG

Imports an SVG into the sketch

**Overload 1:**

```python
def ImportSVG(file_name):
"""
Imports an SVG into the sketch

Args:
file_name (str): Path and name of SVG file

"""
```

**Overload 2:**

```python
def ImportSVG(file_name, translate_x, translate_y, rotation_angle, translate_then_rotate, native_figures):
"""
Imports an SVG into the sketch

Args:
file_name (str): Path and name of SVG file
translate_x (float): Amount to translate in the X direction
translate_y (float): Amount to translate in the Y direction
rotation_angle (float): Amount to rotate in degrees
translate_then_rotate (bool): true to perform translation passed to this function before rotation passed to this function, false to reverse order
native_figures (bool): true to create native circles and arcs when possible, false to always use Bezier curves

"""
```


### LoadXml

Loads the sketch from an XML file

```python
def LoadXml(file_name):
"""
Loads the sketch from an XML file

Args:
file_name (str): Path and name of file to load from

"""
```


### PointtoGlobal

Converts a point on the sketch into a 3D point in the part coordinate system

```python
def PointtoGlobal(x, y):
"""
Converts a point on the sketch into a 3D point in the part coordinate system

Args:
x (float): X coordinate of point on sketch
y (float): Y coordinate of point on sketch

Returns:
Python list [x, y, z]

"""
```


### SavetoXml

Saves the sketch to an XML file
Does not support ellipses and elliptical arcs

```python
def SavetoXml(file_name):
"""
Saves the sketch to an XML file Does not support ellipses and elliptical arcs

Args:
file_name (str): Path and name of file to save to

"""
```


### StartFaceMapping

Starts mapping the face so that the specified edge is at [0, 0]

**Overload 1:**

```python
def StartFaceMapping(edge_vertex1, edge_vertex2):
"""
Starts mapping the face so that the specified edge is at [0, 0]

Args:
edge_vertex1 (Vertex): Firrt vertex of edge
edge_vertex2 (Vertex): Second vertex of edge

"""
```

**Overload 2:**

```python
def StartFaceMapping(edge_end_point1, edge_end_point2):
"""
Starts mapping the face so that the specified edge is at [0, 0] Affects only the operation of the AddXXX functions and the GlobaltoPoint and PointtoGlobal functions, which will now use mapped X and Y values

Args:
edge_end_point1 (list): First end point of edge [X, Y, Z]
edge_end_point2 (list): Second end point of edge [X, Y, Z]

"""
```


### StartMapping

Starts mapping the sketch so that the specified line is at [0, 0]
Affects only the operation of the AddXXX functions and the
GlobaltoPoint and PointtoGlobal functions, which will now use mapped X and Y values

```python
def StartMapping(point1, point2, point_above_axis):
"""
Starts mapping the sketch so that the specified line is at [0, 0] Affects only the operation of the AddXXX functions and the GlobaltoPoint and PointtoGlobal functions, which will now use mapped X and Y values

Args:
point1 (list): First line end point [X, Y, Z]
point2 (list): Second line end point [X, Y, Z]
point_above_axis (list): Point to be located above the X-axis

"""
```

---
**[⬆ Back to Top](#sketch)**

