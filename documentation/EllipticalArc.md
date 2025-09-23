# EllipticalArc

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Properties

### Center
Type: `Object`
The center of the elliptical arc [x, y]

### CenterPoint
Type: `Object`
The center point as a sketchpoint object

### End
Type: `Object`
The end point as a sketchpoint object

### EndPoint
Type: `Object`
The end point of the arc [x, y]

### IsReference
Type: `Object`
True if the elliptical arc is a reference elliptical arc, false if it is a regular elliptical arc

### MajorAxisAngle
Type: `Object`
Angle of major axis

### MinorMajorRatio
Type: `Object`
Ratio of minor radius to major radius

### Radius
Type: `Object`
Radius on major axis

### Start
Type: `Object`
The start point as a sketchpoint object

### StartPoint
Type: `Object`
The start point of the arc [x, y]

## Methods


### EllipticalArc

Creates an elliptical arc

```python
def EllipticalArc(center, start, end, major_radius, major_axis_angle, minor_major_ratio, is_reference):
"""
Creates an elliptical arc

Args:
center (list): Center of the elliptical arc
start (list): The start point for the arc
end (list): The end point for the arc
major_radius (float): Radius on the major axis
major_axis_angle (float): Angle of the major axis in degrees
minor_major_ratio (float): Radius on the minor axis as a ratio of the major radius
is_reference (bool): True to create a reference arc, false to create a regular arc

"""
```

---
**[⬆ Back to Top](#ellipticalarc)**
