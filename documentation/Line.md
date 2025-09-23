# Line

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index) | [Members](Members-Index)**

** Location:**[Geometry & Shapes](Classes#geometry) Line

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Line class provides functionality for creating and manipulating linear geometry within 2D sketches.

## Related Classes
- [Line3D](Line3D) - 3D line operations
- [Sketch](Sketch) - Contains line geometry
- [SketchPoint](SketchPoint) - Line endpoints
- [Polyline](Polyline) - Multi-segment lines
- [Circle](Circle), [CircularArc](CircularArc) - Curved geometry

## Quick Navigation
- [Properties](#properties) - Line properties and dimensions
- [Methods](#methods) - Available operations

## Properties

### End
Type: `Object`
The end point as a sketchpoint object

### EndPoint
Type: `Object`
The end point of the line [x, y]

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
The start point of the line [x, y]

## Methods


### Line

Creates a new 2D line

```python
def Line(start_point, end_point, is_reference):
"""
Creates a new 2D line

Args:
start_point (list): Location of the start point [x, y]
end_point (list): Location of the end point [x, y]
is_reference (bool): True if a reference line

"""
```

---
**[⬆ Back to Top](#line)**
