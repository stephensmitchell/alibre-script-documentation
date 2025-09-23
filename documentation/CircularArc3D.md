# CircularArc3D

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Properties

### Angle
Type: `Object`
Angle of arc

### Center
Type: `Object`
The center of the arc [x, y, z]

### EndPoint
Type: `Object`
The end point of the arc [x, y, z]

### IsReference
Type: `Object`
True if the arc is a reference arc, false if it is a regular arc

### Radius
Type: `Object`
Radius of arc

### StartPoint
Type: `Object`
The start point of the arc [x, y, z]

### Type
Type: `Object`
Type of arc

## Methods


### CircularArc3D

Creates an arc using the center, start point and end point

**Overload 1:**

```python
def CircularArc3D(center, start, end, is_reference):
"""
Creates an arc using the center, start point and end point

Args:
center (list): Center of the arc
start (list): Start point of the arc
end (list): End point of the arc
is_reference (bool): True to create a reference arc, false to create a regular arc

"""
```

**Overload 2:**

```python
def CircularArc3D(center, start, angle, is_reference):
"""
Creates an arc using the center, start point and an angle

Args:
center (list): Location of center of arc
start (list): Location of start of arc
angle (float): Angle of arc
is_reference (bool): True if a reference arc, false if a regular arc

"""
```

---
**[⬆ Back to Top](#circulararc3d)**
