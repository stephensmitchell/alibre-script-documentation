# PolylinePoint

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Methods


### PolylinePoint

Creates a new polyline point

```python
def PolylinePoint(x, y):
"""
Creates a new polyline point

Args:
x (float): X coordinate
y (float): Y coordinate

"""
```


### Offset

Applies an offset to the point and creates a new point

```python
def Offset(x, y):
"""
Applies an offset to the point and creates a new point

Args:
x (float): X offset to apply
y (float): Y offset to apply

Returns:
New point with offset applied

"""
```


### RotateZ

Rotates the point around the Z axis

```python
def RotateZ(center_x, center_y, angle):
"""
Rotates the point around the Z axis

Args:
center_x (float): X coordinate of center of rotation
center_y (float): Y coordinate of center of rotation
angle (float): Number of degrees to rotate

"""
```


### Scale

Scales the point location based on an origin for the scaling

```python
def Scale(scale_origin_x, scale_origin_y, scale_factor):
"""
Scales the point location based on an origin for the scaling

Args:
scale_origin_x (float): X-coordinate for scaling origin
scale_origin_y (float): Y-coordinate for scaling origin
scale_factor (float): Factor for scaling as a percentage

Returns:
New point with scaling applied

"""
```

---
**[⬆ Back to Top](#polylinepoint)**
