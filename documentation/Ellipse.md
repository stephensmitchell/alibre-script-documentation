# Ellipse

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Properties

### Center
Type: `Object`
The center of the ellipse [x, y]

### CenterPoint
Type: `Object`
The center point as a sketchpoint object

### IsReference
Type: `Object`
True if the ellipse is a reference ellipse, false if it is a regular ellipse

### MajorAxisAngle
Type: `Object`
Angle of major axis

### MinorMajorRatio
Type: `Object`
Ratio of minor radius to major radius

### Radius
Type: `Object`
Radius on major axis

## Methods


### Ellipse

Creates an ellipse

```python
def Ellipse(center, major_radius, major_axis_angle, minor_major_ratio, is_reference):
"""
Creates an ellipse

Args:
center (list): Center of the ellipse
major_radius (float): Radius on the major axis
major_axis_angle (float): Angle of the major axis in degrees
minor_major_ratio (float): Radius on the minor axis as a ratio of the major radius
is_reference (bool): True to create a reference arc, false to create a regular arc

"""
```

---
**[⬆ Back to Top](#ellipse)**
