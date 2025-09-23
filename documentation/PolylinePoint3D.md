# PolylinePoint3D

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Methods


### PolylinePoint3D

Creates a new 3D polyline point

```python
def PolylinePoint3D(x, y, z):
"""
Creates a new 3D polyline point

Args:
x (float): X coordinate
y (float): Y coordinate
z (float): Z coordinate

"""
```


### Offset

Applies an offset to the point and creates a new point

```python
def Offset(x, y, z):
"""
Applies an offset to the point and creates a new point

Args:
x (float): X offset to apply
y (float): Y offset to apply
z (float): Z offset to apply

Returns:
New point with offset applied

"""
```


### Scale

Scales the point location based on an origin for the scaling

```python
def Scale(scale_origin_x, scale_origin_y, scale_origin_z, scale_factor):
"""
Scales the point location based on an origin for the scaling

Args:
scale_origin_x (float): X-coordinate for scaling origin
scale_origin_y (float): Y-coordinate for scaling origin
scale_origin_z (float): Z-coordinate for scaling origin
scale_factor (float): Factor for scaling as a percentage

Returns:
New point with scaling applied

"""
```

---
**[⬆ Back to Top](#polylinepoint3d)**
