# Line3D

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Properties

### End
Type: `Object`
The end point as a sketchpoint object

### EndPoint
Type: `Object`
The end point of the line [x, y, z]

### IsReference
Type: `Object`
True if the line is a reference line, false if it is a regular line

### Length
Type: `Object`
The length of the line in script units

### Start
Type: `Object`
The start point as a sketchpoint object

### StartPoint
Type: `Object`
The start point of the line [x, y, z]

## Methods


### Line3D

Creates a new 3D line

```python
def Line3D(start_point, end_point, is_reference):
"""
Creates a new 3D line

Args:
start_point (list): Location of the start point [x, y, z]
end_point (list): Location of the end point [x, y, z]
is_reference (bool): True if a reference line

"""
```

---
**[⬆ Back to Top](#line3d)**
