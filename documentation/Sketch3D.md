# Sketch3D

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index) | [Members](Members-Index)**

** Location:**[Sketching & Drawing](Classes#sketching) Sketch3D

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Sketch3D class provides functionality for 3D sketching operations including creating spatial geometric figures and managing 3D sketch elements.

## Related Classes
- [Sketch](Sketch) - 2D sketching operations
- [SketchPoint3D](SketchPoint3D) - 3D sketch points
- [Line3D](Line3D), [CircularArc3D](CircularArc3D) - 3D sketch geometry
- [Bspline3D](Bspline3D) - 3D spline curves
- [Part](Part) - Contains 3D sketches

## Quick Navigation
- [Properties](#properties) - Sketch properties
- [Methods](#methods) - All available operations
- [Arc Methods](#arc-methods) - 3D arc operations
- [Line Methods](#line-methods) - 3D line creation
- [Spline Methods](#spline-methods) - 3D curve operations

## Properties

### Figures
Type: `Object`
A list of figures defines on the sketch, e.g. bspline

### Name
Type: `Object`
Name of the sketch

## Methods


### AddArc

Adds a circular arc to the sketch

```python
def AddArc(new_arc):
"""
Adds a circular arc to the sketch

Args:
new_arc (CircularArc3D): Arc to add

"""
```


### AddArcCenterStartEnd

Adds a circular arc using three points - center, start and end
Arc goes anti-clockwise from start to end

```python
def AddArcCenterStartEnd(center_x, center_y, center_z, start_x, start_y, start_z, end_x, end_y, end_z):
"""
Adds a circular arc using three points - center, start and end Arc goes anti-clockwise from start to end

Args:
center_x (float): X coordinate for center
center_y (float): Y coordinate for center
center_z (float): Z coordinate for center
start_x (float): X coordinate for start
start_y (float): Y coordinate for start
start_z (float): Z coordinate for start
end_x (float): X coordinate for end
end_y (float): Y cordinate for end
end_z (float): Z coordnate for end

"""
```


### AddBspline

Adds a Bspline to the sketch

**Overload 1:**

```python
def AddBspline(points):
"""
Adds a Bspline to the sketch

Args:
points (list): List of control points [X1, Y1, Z1, X2, Y2, Z2, ...]

Returns:
The Bspline object that was created

"""
```

**Overload 2:**

```python
def AddBspline(bspline):
"""
Adds a Bspline to the sketch

Args:
bspline (Bspline3D): Bspline to add

"""
```


### AddLine

Adds a line to the sketch

**Overload 1:**

```python
def AddLine(start_point, end_point):
"""
Adds a line to the sketch

Args:
start_point (list): Start of line [X, Y, Z]
end_point (list): End of line [X, Y, Z]

"""
```

**Overload 2:**

```python
def AddLine(new_line):
"""
Adds a line to the sketch

Args:
new_line (Line3D): 3D line to add

"""
```

**Overload 3:**

```python
def AddLine(x1, y1, z1, x2, y2, z2):
"""
Adds a line to the sketch

Args:
x1 (float): Start point X
y1 (float): Start point Y
z1 (float): Start point Z
x2 (float): End point X
y2 (float): End point Y
z2 (float): End point Z

"""
```


### AddLines

Adds a polyline to the sketch

```python
def AddLines(points):
"""
Adds a polyline to the sketch

Args:
points (list): Set of points [Point1X, Point1Y, Point1Z, Point2X, Point2Y, Point2Z, ...]

"""
```


### AddPoint

Adds a point to the sketch

**Overload 1:**

```python
def AddPoint(x, y, z):
"""
Adds a point to the sketch

Args:
x (float): Point X coordinate
y (float): Point Y coordinate
z (float): Point Z coordinate

"""
```

**Overload 2:**

```python
def AddPoint(new_point):
"""
Adds a point to the sketch

Args:
new_point (SketchPoint3D): Point to add

"""
```


### AddPolyline

Adds a polyline to the sketch

```python
def AddPolyline(line):
"""
Adds a polyline to the sketch

Args:
line (Polyline3D): Polyine to add

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


### SavetoXml

Saves the sketch to an XML file

```python
def SavetoXml(file_name):
"""
Saves the sketch to an XML file

Args:
file_name (str): Path and name of file to save to

"""
```

---
**[⬆ Back to Top](#sketch3d)**
