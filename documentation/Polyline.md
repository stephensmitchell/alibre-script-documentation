# Polyline

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Methods


### Polyline

Creates a new 2D polyline that can be later added to a 2D sketch

```python
def Polyline(points):
"""
Creates a new 2D polyline that can be later added to a 2D sketch

Args:
points (list): List of points in the polyline [X1, Y1, X2, Y2, ...]

"""
```


### AddArc

Adds an arc to the polyline. The arc is approcimated with straight line segments

```python
def AddArc(center, start, end, minimum_segments):
"""
Adds an arc to the polyline. The arc is approcimated with straight line segments

Args:
center (PolylinePoint): Point defining center of arc
start (PolylinePoint): Point defining start of arc
end (PolylinePoint): Point defining end of arc
minimum_segments (int): Minimum number of line segments to use to form arc

"""
```


### AddCircle

Adds a circle to the line

```python
def AddCircle(center_x, center_y, diameter, sides):
"""
Adds a circle to the line

Args:
center_x (float): X coordinate of circle center
center_y (float): Y coordinate of circle center
diameter (float): Diameter of circle
sides (int): Number of sides to use to approximate circle

"""
```


### AddPoint

Adds a new point to the polyline

```python
def AddPoint(point):
"""
Adds a new point to the polyline

Args:
point (PolylinePoint): Point to add

"""
```


### AddPolyline

Appends a line to the current line

```python
def AddPolyline(append_line):
"""
Appends a line to the current line

Args:
append_line (Polyline): Line to append

"""
```


### Clone

Creates an exact copy of a section of the line

```python
def Clone(start_index, end_index):
"""
Creates an exact copy of a section of the line

Args:
start_index (int): 0-based index of first point to include in copy
end_index (int): 0-based index of last point to include in copy

Returns:
Copied line

"""
```


### FindIntersection

Finds the first intersection point between two lines

**Overload 1:**

```python
def FindIntersection(l1, l2):
"""
Finds the first intersection point between two lines

Args:
l1 (Polyline): First line
l2 (Polyline): Second line

Returns:
First intersection point or null if none found

"""
```

**Overload 2:**

```python
def FindIntersection(a1, a2, b1, b2):
"""
Gets the intersection between the line segments A1A2 and B1B2

Args:
a1 (PolylinePoint): First segment start point
a2 (PolylinePoint): First segment end point
b1 (PolylinePoint): Second segment start point
b2 (PolylinePoint): Second segment end point

Returns:
Intersection point or null if not found

"""
```


### FindIntersectionWithCircle

Finds first intersection of line with a circle

```python
def FindIntersectionWithCircle(l1, circle_x, circle_y, radius):
"""
Finds first intersection of line with a circle

Args:
l1 (Polyline): Line to check
circle_x (float): X-coordinate of circle center
circle_y (float): Y-coordinate of circle center
radius (float): Radius of circle

Returns:
Intersection point or null if not found

"""
```


### InsertPoint

Inserts a point at a specific location

```python
def InsertPoint(index, point):
"""
Inserts a point at a specific location

Args:
index (int): 0-based index of location to insert
point (PolylinePoint): Point to insert

"""
```


### IsPointOnLine

Determines if a point is on a line segment

```python
def IsPointOnLine(a1, a2, point, tolerance):
"""
Determines if a point is on a line segment

Args:
a1 (PolylinePoint): First point of line segment
a2 (PolylinePoint): Last point of line segment
point (PolylinePoint): Point to check
tolerance (float): Fudge factor

Returns:
True if point is on line

"""
```


### Join

Joins a line onto the end of the current line and returns the new line

```python
def Join(append_line):
"""
Joins a line onto the end of the current line and returns the new line

Args:
append_line (Polyline): The line to join to the current line

Returns:
The new line created from this line plus the appended line

"""
```


### Offset

Applies an offset to all points on the line

```python
def Offset(offset_x, offset_y):
"""
Applies an offset to all points on the line

Args:
offset_x (float): X offset to apply
offset_y (float): Y offset to apply

"""
```


### RotateZ

Rotates the polyline around the Z axis

```python
def RotateZ(center_x, center_y, angle):
"""
Rotates the polyline around the Z axis

Args:
center_x (float): X coordinate of center of rotation
center_y (float): Y coordinate of center of rotation
angle (float): Number of degrees to rotate

"""
```


### SplitAtPoint

Splits a polyline at a point, creating two polylines

```python
def SplitAtPoint(split_point, tolerence):
"""
Splits a polyline at a point, creating two polylines

Args:
split_point (PolylinePoint): Point to split at
tolerence (float): Tolerance to determine if point is on/near line

Returns:
List of polylines [A, B]

"""
```

---
**[⬆ Back to Top](#polyline)**
