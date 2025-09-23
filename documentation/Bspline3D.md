# Bspline3D

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [All Classes](Classes)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Properties

### ControlPoints
Type: `Object`
The control points [x1, y1, ..., xn, yn]

### IsReference
Type: `Object`
True if the bspline is a reference bspline, false if it is a regular bspline

### KnotVectors
Type: `Object`
The knot vectors [k1, k2, ..., kn]

### Length
Type: `Object`
Gets the length of the Bspline

### Order
Type: `Object`
The order of the bspline

### Weights
Type: `Object`
The weights [w1, w2, ..., wn]

## Methods


### Bspline3D

Creates a bspline

```python
def Bspline3D(order, control_points, knot_vectors, weights, is_reference):
"""
Creates a bspline

Args:
order (int): Order of the bspline
control_points (list): Value of control points [Point1X, Point1Y, ...]
knot_vectors (list): Knot vectors [KnotVector1, KnotVector2, ...]
weights (list): Point weights [Weight1, Weight2, ...]
is_reference (bool): True if a reference bspline, false if a regular bspline

"""
```


### GetNormalAt

Gets the normal vector at a point on the spline

```python
def GetNormalAt(u):
"""
Gets the normal vector at a point on the spline

Args:
u (float): Location along the spline. 0.0 = start, 1.0 = end

Returns:
Vector for point on the spline at the specified location (A, B, C)

"""
```


### GetPointAt

Gets a point on the spline

```python
def GetPointAt(u):
"""
Gets a point on the spline

Args:
u (float): Location along the spline. 0.0 = start, 1.0 = end

Returns:
Point on the spline at the specified location [X, Y, Z]

"""
```


### GetX

Gets the X value of the spline at a location along the spline

```python
def GetX(u):
"""
Gets the X value of the spline at a location along the spline

Args:
u (float): Location along the spline. 0.0 = start, 1.0 = end

Returns:
X value of spline at the specified location

"""
```


### GetY

Gets the Y value of the spline at a location along the spline

```python
def GetY(u):
"""
Gets the Y value of the spline at a location along the spline

Args:
u (float): Location along the spline. 0.0 = start, 1.0 = end

Returns:
Y value of spline at the specified location

"""
```


### GetZ

Gets the Z value of the spline at a location along the spline

```python
def GetZ(u):
"""
Gets the Z value of the spline at a location along the spline

Args:
u (float): Location along the spline. 0.0 = start, 1.0 = end

Returns:
Y value of spline at the specified location

"""
```


### Subdivide

Divides the Bspline up into segments

```python
def Subdivide(segments):
"""
Divides the Bspline up into segments

Args:
segments (int): Number of segments to obtain

Returns:
List of points between segments [X1, Y1, Z1, X2, Y2, Z2, ...]

"""
```


### SubdivideGetNormals

Divides the Bspline up into segments and gets the normal for each point

```python
def SubdivideGetNormals(segments):
"""
Divides the Bspline up into segments and gets the normal for each point

Args:
segments (int): Number of segments to obtain

Returns:
List of points between segments and normals [X1, Y1, Z1, A1, B1, C1, X2, Y2, Z2, A2, B2, C2, ...]

"""
```

---
**[⬆ Back to Top](#bspline3d)**
