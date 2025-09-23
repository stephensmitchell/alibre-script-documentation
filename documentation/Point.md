# Point

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index) | [Members](Members-Index)**

** Location:**[Core Elements](Classes#core-elements) Point

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Point class provides fundamental functionality for creating and manipulating 3D point geometry throughout the AlibreScript API.

## Related Classes
- [IPoint](IPoint) - Point interface definition
- [SketchPoint](SketchPoint) - 2D sketch points
- [SketchPoint3D](SketchPoint3D) - 3D sketch points
- [PolylinePoint](PolylinePoint) - Polyline points
- [Axis](Axis), [Plane](Plane) - Related geometric elements

## Quick Navigation
- [Properties](#properties) - Point coordinates and attributes
- [Methods](#methods) - Point operations

## Properties

### Name
Type: `Object`
Name of the point

### X
Type: `Object`
Point X coordinate

### Y
Type: `Object`
Point Y coordinate

### Z
Type: `Object`
Point Z coordinate

## Methods

### GetCoordinates
Gets the coordiates of the point as a list [X, Y, Z]

```python
Object GetCoordinates()
```

### GetPart
Gets the part that the point is defined in

```python
Object GetPart()
```

### GetSelectionAssembly
The assembly that the edge was selected on
Only valid when a selection has been made

```python
Object GetSelectionAssembly()
```

### Hide
Hides the point

```python
Object Hide()
```

### Show
Shows the point

```python
Object Show()
```

---
**[⬆ Back to Top](#point)**

