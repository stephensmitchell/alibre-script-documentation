# Polyline3D

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Methods


### Polyline3D

Creates a new 3D polyline that can be later added to a 3D sketch

```python
def Polyline3D(points):
"""
Creates a new 3D polyline that can be later added to a 3D sketch

Args:
points (list): List of points in the polyline [X1, Y1, Z1, X2, Y2, Z2, ...]

"""
```


### AddPoint

Adds a new point to the polyline

```python
def AddPoint(point):
"""
Adds a new point to the polyline

Args:
point (PolylinePoint3D): Point to add

"""
```


### AddPolyline

Appends a line to the current line

```python
def AddPolyline(append_line):
"""
Appends a line to the current line

Args:
append_line (Polyline3D): Line to append

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


### InsertPoint

Inserts a point at a specific location

```python
def InsertPoint(index, point):
"""
Inserts a point at a specific location

Args:
index (int): 0-based index of location to insert
point (PolylinePoint3D): Point to insert

"""
```


### IsPointOnLine

Determines if a point is on a line segment

```python
def IsPointOnLine(a, b, p, tolerance):
"""
Determines if a point is on a line segment

Args:
a (PolylinePoint3D): First point of line segment
b (PolylinePoint3D): Last point of line segment
p (PolylinePoint3D): Point to check
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
append_line (Polyline3D): The line to join to the current line

Returns:
The new line created from this line plus the appended line

"""
```


### Offset

Applies an offset to all points on the line

```python
def Offset(offset_x, offset_y, offset_z):
"""
Applies an offset to all points on the line

Args:
offset_x (float): X offset to apply
offset_y (float): Y offset to apply
offset_z (float): Z offset to apply

"""
```


### SplitAtPoint

Splits a polyline at a point, creating two polylines

```python
def SplitAtPoint(split_point, tolerence):
"""
Splits a polyline at a point, creating two polylines

Args:
split_point (PolylinePoint3D): Point to split at
tolerence (float): Tolerance to determine if point is on/near line

Returns:
List of polylines [A, B]

"""
```

---
**[⬆ Back to Top](#polyline3d)**
