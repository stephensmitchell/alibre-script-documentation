# Circle

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index) | [Members](Members-Index)**

** Location:**[Geometry & Shapes](Classes#geometry) Circle

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Circle class provides functionality for creating and manipulating circular geometry within sketches and 3D space.

## Practical Usage

Circles are fundamental geometric elements in Alibre Design scripting. They're commonly used for:
- **Holes and circular features** in mechanical parts
- **Circular patterns** and geometric layouts
- **Constraint references** for assembly positioning
- **Measurement and inspection** points

## Common Coding Patterns

```python
# Create a simple circle for a hole
center_point = [0, 0]
hole_radius = 5.0
hole_circle = Circle(center_point, hole_radius, False)
sketch.AddCircle(hole_circle)

# Create reference circles for constraints
ref_circle = Circle([10, 10], 2.5, True) # Reference circle
sketch.AddCircle(ref_circle)

# Access circle properties for calculations
circle_area = 3.14159 * (circle.Radius ** 2)
circumference = circle.Length
```

## Related Classes
- [Sketch](Sketch) - Contains circle geometry
- [CircularArc](CircularArc) - Arc-based circular geometry
- [Ellipse](Ellipse) - Elliptical geometry
- [Point](Point) - Center point handling
- [Line](Line) - Linear geometry

## Quick Navigation
- [Properties](#properties) - Circle properties and dimensions
- [Methods](#methods) - Available operations

## Properties

### Center
Type: `Object`
The center of the circle [x, y]

### CenterPoint
Type: `Object`
The center of the circle as a sketch point

### IsReference
Type: `Object`
True if the circle is a reference circle, false if it is a regular circle

### Length
Type: `Object`
The length of the circle circumference in script units

### Radius
Type: `Object`
Radius of the circle

## Methods


### Circle

Creates a 2D circle which can be added to sketches

```python
def Circle(center, radius, is_reference):
"""
Creates a 2D circle which can be added to sketches

Args:
center (list): Center of the circle as a python list [x, y]
radius (float): Radius of circle
is_reference (bool): True to create a reference circle

"""
```

---
**[⬆ Back to Top](#circle)**

