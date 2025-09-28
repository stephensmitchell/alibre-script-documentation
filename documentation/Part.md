# Part

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index)**

** Location:**[Assembly & Parts](Classes#assembly-and-parts) Part

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Part class provides comprehensive functionality for creating, manipulating, and managing individual parts within Alibre Design. This class handles part properties, geometry creation, sketching, and file operations.

## Practical Usage

Parts are the foundation of mechanical design. Common scripting applications include:
- **Automated part generation** from design parameters
- **Parametric modeling** with configurable dimensions
- **Feature creation** (extrudes, cuts, fillets, chamfers)
- **Sketch-based geometry** for complex shapes
- **Part validation** and property management
- **Batch operations** on multiple parts

## Common Coding Patterns

```python
# Create a new part
part = Part("MyPart.AD_PRT", "C:\\MyProject")

# Add a sketch for the base feature
base_sketch = part.AddSketch("BaseSketch", part.GetPlane("XY"))

# Create geometry in the sketch
base_sketch.AddRectangle(0, 0, 50, 30, False)
base_sketch.AddCircle(25, 15, 5, False) # Center hole

# Create an extrude feature
part.AddExtrudeBoss(
"BaseExtrude", # Feature name
base_sketch, # Sketch to extrude
10.0, # Extrude distance
Part.EndCondition.Blind, # End condition
0.0, # Taper angle
False # Not thin wall
)

# Add a fillet to edges
part.AddFillet("EdgeFillet", ["Edge1", "Edge2"], 2.0)

# Save the part
part.Save("Part creation complete")
```

## Related Classes
- [Assembly](Assembly) - Contains parts as components
- [AssembledPart](AssembledPart) - Part within an assembly context
- [Feature](Feature) - Part features and operations
- [Configuration](Configuration) - Part configurations
- [GlobalParameters](GlobalParameters) - Part parameters

## Quick Navigation
- [Properties](#properties) - Part properties and metadata
- [Methods](#methods) - Available operations
- [Sketching Methods](#sketching-methods) - Drawing and sketching
- [Feature Methods](#feature-methods) - Feature operations
- [File Operations](#file-operations) - Save, export, import

## Properties

### Comment
Type: `Object`
Comment property

### Configurations
Type: `Object`
List of configurations defined on the part

### CostCenter
Type: `Object`
Cost center property

### CreatedBy
Type: `Object`
Created By property

### CreatedDate
Type: `Object`
Created Date property

### CreatingApplication
Type: `Object`
Creating Application property

### Density
Type: `Object`
Density of the part

### Description
Type: `Object`
Description of the part

### DocumentNumber
Type: `Object`
Document Number property

### EngineeringApprovalDate
Type: `Object`
Engineering Approval Date property

### EngineeringApprovedBy
Type: `Object`
Engineering Approved By property

### EstimatedCost
Type: `Object`
Estimated Cost property

### ExtendedMaterialInformation
Type: `Object`
Material (extended information) property

### FileName
Type: `Object`
Path and filename of the part

### Keywords
Type: `Object`
Keywords property

### LastAuthor
Type: `Object`
Last Author property

### LastUpdateDate
Type: `Object`
Last Update Date property

### ManufacturingApprovedBy
Type: `Object`
Manufacturing Approved By property

### ManufacturingApprovedDate
Type: `Object`
Product property

### Mass
Type: `Object`
Mass of the part

### Material
Type: `Object`
Material of the part

### ModifiedInformation
Type: `Object`
Modified Information property

### Name
Type: `Object`
Name of the part

### Number
Type: `Object`
User-defined number for the part

### Origin
Type: `Object`
Gets the origin (language independent)

### Parameters
Type: `Object`
List of parameters defined on the part

### Product
Type: `Object`
Product property

### ReceivedFrom
Type: `Object`
Received From property

### Revision
Type: `Object`
Revision property

### Selections
Type: `Object`
Gets the currently selected items as [ItemA, ItemB, ...]
Supports faces, edges, vertices, planes, axes and points

### StockSize
Type: `Object`
Stock Size property

### Supplier
Type: `Object`
Supplier property

### Title
Type: `Object`
Title property

### Vendor
Type: `Object`
Vendor property

### WebLink
Type: `Object`
Web Link property

### XAxis
Type: `Object`
Gets the X-axis (language independent)

### XYPlane
Type: `Object`
Gets the XY-plane (language independent)

### YAxis
Type: `Object`
Gets the Y-axis (language independent)

### YZPlane
Type: `Object`
Gets the YZ-plane (language independent)

### ZAxis
Type: `Object`
Gets the Z-axis (language independent)

### ZXPlane
Type: `Object`
Gets the ZX-plane (language independent)

## Methods


### Part

Opens an existing part

**Overload 1:**

```python
def Part(folder, name):
"""
Opens an existing part

Args:
folder (str): Folder containing part
name (str): Name of part to open

"""
```

**Overload 2:**

```python
def Part(folder, name, hide_editor):
"""
Opens an existing part, optionally hiding the editor

Args:
folder (str): Folder containing part
name (str): Name of part to open
hide_editor (bool): True to hide the editor (only valid if part is not already open)

"""
```

**Overload 3:**

```python
def Part(name):
"""
Creates a new part

Args:
name (str): Name of new part

"""
```

**Overload 4:**

```python
def Part(name, create_new):
"""
Creates a new part or accesses an already opened part

Args:
name (str): Name of part to create or access
create_new (bool): True to create a new part, false to access an opened part

"""
```

**Overload 5:**

```python
def Part(name, create_new, hide_editor):
"""
Creates a new part or accesses an already opened part, optionally hiding the editor

Args:
name (str): Name of part to create or access
create_new (bool): True to create a new part, false to access an opened part
hide_editor (bool): True to hide the editor (only valid if CreateNew is true)

"""
```

**Overload 6:**

```python
def Part(file_name, type):
"""
Opens or imports an existing file for editing

Args:
file_name (str): Name of file to open
type (Part.FileTypes): Type of file (GeomagicDesignPart, STEP, IGES, ThreeDM, SAT, STL_in, STL_cm, STL_mm)

"""
```

**Overload 7:**

```python
def Part(file_name, type, hide_editor):
"""
Opens or imports an existing file for editing, optionally hiding the editor

Args:
file_name (str): Name of file to open
type (Part.FileTypes): Type of file (GeomagicDesignPart, STEP, IGES, ThreeDM, SAT, STL_in, STL_cm, STL_mm)
hide_editor (bool): True to hide the editor

"""
```


### Add3DSketch

Creates a new 3D sketch

```python
def Add3DSketch(name):
"""
Creates a new 3D sketch

Args:
name (str): Name of sketch

Returns:
Created sketch

"""
```


### AddAxis

Creates an axis based on the intersection of two planes/faces

**Overload 1:**

```python
def AddAxis(name, plane1, plane2):
"""
Creates an axis based on the intersection of two planes/faces

Args:
name (str): Name of axis
plane1 (ISketchSurface): First plane/face
plane2 (ISketchSurface): Second plane/face

Returns:
New Axis

"""
```

**Overload 2:**

```python
def AddAxis(name, point_a, point_b):
"""
Creates an axis based on two points

Args:
name (str): Name of axis
point_a (Point): First point object
point_b (Point): Second point object

Returns:
New axis

"""
```

**Overload 3:**

```python
def AddAxis(name, cylindrical_face):
"""
Creates an axis for a cylindrical face

Args:
name (str): Name of axis
cylindrical_face (Face): Cylindrical face

Returns:
New axis

"""
```

**Overload 4:**

```python
def AddAxis(name, point1, point2):
"""
Creates an axis based on two points

Args:
name (str): Name of axis
point1 (list): First point [X, Y, Z]
point2 (list): Second point [X, Y, Z]

Returns:
New axis

"""
```


### AddChamfer

Adds a chamfer to a face or edge

**Overload 1:**

```python
def AddChamfer(name, item, distance1, distance2, tangent_propagate):
"""
Adds a chamfer to a face or edge

Args:
name (str): Name of chamfer
item (IChamferable): Face or edge to chamfer
distance1 (float): First chamfer distance
distance2 (float): Second chamfer distance
tangent_propagate (bool): True to propagate the chamfer along connected edges

Returns:
Chamfer feature

"""
```

**Overload 2:**

```python
def AddChamfer(name, items, distance1, distance2, tangent_propagate):
"""
Adds a chamfer to a set of faces and edges

Args:
name (str): Name of chamfer
items (list): Faces and edges to chamfer
distance1 (float): First chamfer distance
distance2 (float): Second chamfer distance
tangent_propagate (bool): True to propagate the chamfer along connected edges

Returns:
Chamfer feature

"""
```

**Overload 3:**

```python
def AddChamfer(name, item, distance, tangent_propagate):
"""
Adds a chamfer to a face or edge

Args:
name (str): Name of chamfer
item (IChamferable): Face or edge to chamfer
distance (float): Chamfer distance
tangent_propagate (bool): True to propagate the chamfer along connected edges

Returns:
Chamfer feature

"""
```

**Overload 4:**

```python
def AddChamfer(name, items, distance, tangent_propagate):
"""
Adds a chamfer to a set of faces and edges

Args:
name (str): Name of chamfer
items (list): Faces and edges to chamfer
distance (float): Chamfer distance
tangent_propagate (bool): True to propagate the chamfer along connected edges

Returns:
Chamfer feature

"""
```


### AddChamferAngle

Adds a chamfer to a face or edge

**Overload 1:**

```python
def AddChamferAngle(name, item, distance, angle, tangent_propagate):
"""
Adds a chamfer to a face or edge

Args:
name (str): Name of chamfer
item (IChamferable): Face or edge to chamfer
distance (float): Chamfer distance
angle (float): Chamfer angle
tangent_propagate (bool): True to propagate the chamfer along connected edges

Returns:
Chamfer feature

"""
```

**Overload 2:**

```python
def AddChamferAngle(name, items, distance, angle, tangent_propagate):
"""
Adds a chamfer to a set of faces and edges

Args:
name (str): Name of chamfer
items (list): Faces and edges to chamfer
distance (float): Chamfer distance
angle (float): Chamfer angle
tangent_propagate (bool): True to propagate the chamfer along connected edges

Returns:
Chamfer feature

"""
```


### AddConfiguration

Adds a configuration to the part

**Overload 1:**

```python
def AddConfiguration(name):
"""
Adds a configuration to the part

Args:
name (str): Name of configuration

Returns:
New configuration

"""
```

**Overload 2:**

```python
def AddConfiguration(name, base_configuration_name):
"""
Adds a configuration to the part using another configuration as a base

Args:
name (str): Name of configuration
base_configuration_name (str): Name of base configuration to use

Returns:
New configuration

"""
```


### AddExtrudeBoss

Adds a simple extrude boss to a specific depth

**Overload 1:**

```python
def AddExtrudeBoss(name, sketch, depth, is_reversed):
"""
Adds a simple extrude boss to a specific depth

Args:
name (str): Name of extrusion
sketch (Sketch): Sketch to extrude
depth (float): Extrusion distance
is_reversed (bool): True if extrusion direction is reversed

Returns:
Extruded feature

"""
```

**Overload 2:**

```python
def AddExtrudeBoss(name, sketch, depth, is_reversed, end_condition, end_plane, end_offset, direction, sweep_path, draft_angle, outward_draft):
"""
Adds an extrude feature

Args:
name (str): Name of extrusion
sketch (Sketch): Sketch to extrude
depth (float): Depth of extrusion
is_reversed (bool): true if direction is reversed
end_condition (Part.EndCondition): End condition for extrusion
end_plane (ISketchSurface): Face or plane to terminate extrusion
end_offset (float): Offset from face or plane to terminate extrusion
direction (Part.DirectionType): Direction of extrusion
sweep_path (ISweepPath): Sketch or edge to follow when extruding
draft_angle (float): Angle of draft
outward_draft (bool): true if outward draft

Returns:
Extruded feature

"""
```


### AddExtrudeCut

Adds a simple extrude cut to a specific depth

**Overload 1:**

```python
def AddExtrudeCut(name, sketch, depth, is_reversed):
"""
Adds a simple extrude cut to a specific depth

Args:
name (str): Name of extrusion
sketch (Sketch): Sketch to extrude
depth (float): Extrusion distance
is_reversed (bool): True if extrusion direction is reversed

Returns:
Extruded feature

"""
```

**Overload 2:**

```python
def AddExtrudeCut(name, sketch, depth, is_reversed, end_condition, end_plane, end_offset, direction, sweep_path, draft_angle, outward_draft):
"""
Adds an extrude cut feature

Args:
name (str): Name of extrusion
sketch (Sketch): Sketch to extrude
depth (float): Depth of extrusion
is_reversed (bool): true if direction is reversed
end_condition (Part.EndCondition): End condition for extrusion
end_plane (ISketchSurface): Face or plane to terminate extrusion
end_offset (float): Offset from face or plane to terminate extrusion
direction (Part.DirectionType): Direction of extrusion
sweep_path (ISweepPath): Sketch or edge to follow when extruding
draft_angle (float): Angle of draft
outward_draft (bool): true if outward draft

Returns:
Extruded feature

"""
```


### AddFillet

Adds a constant radius fillet to a face or edge

**Overload 1:**

```python
def AddFillet(name, item, radius, tangent_propagate):
"""
Adds a constant radius fillet to a face or edge

Args:
name (str): Name of fillet
item (IFilletable): Face or edge to fillet
radius (float): Radius of fillet
tangent_propagate (bool): True to propagate the fillet along connected edges

Returns:
Fillet feature

"""
```

**Overload 2:**

```python
def AddFillet(name, items, radius, tangent_propagate):
"""
Adds a constant radius fillet to a set of faces and edges

Args:
name (str): Name of fillet
items (list): Faces and edges to fillet
radius (float): Radius of fillet
tangent_propagate (bool): True to propagate the fillet along connected edges

Returns:
Fillet feature

"""
```

**Overload 3:**

```python
def AddFillet(name, items, start_radii, end_radii, tangent_propagate):
"""
Adds a variable radius fillet to a set of faces and edges

Args:
name (str): Name of fillet
items (list): Faces and edges to fillet
start_radii (list): Start radii of fillets
end_radii (list): End radii of fillets
tangent_propagate (bool): True to propagate the fillet along connected edges

Returns:
Fillet feature

"""
```


### AddGear

Adds a gear sketch to the part

```python
def AddGear(name, numberof_teeth, pitch_diameter, pressure_angle, diametral_pitch, single_tooth, center_x, center_y, involute_points, plane):
"""
Adds a gear sketch to the part

Args:
name (str): Name of gear sketch
numberof_teeth (float): Number of teeth
pitch_diameter (int): Diameter of pitch circle in current units
pressure_angle (float): Pressure angle (14.5 is typical)
diametral_pitch (float): Diametral angle (tooth size) (25.4/module) in teeth per inch
single_tooth (bool): true to create only a single tooth profile
center_x (float): X-coordinate of gear center
center_y (float): Y-coordinate of gear center
involute_points (int): Number of points for involute curve. Decreasing this makes Cubify/Geomagic faster. Increasing makes tooth profiles more accurate and allows gears with more teeth to be generated.
plane (ISketchSurface): Plane or face to create gear sketch on

Returns:
Gear sketch

"""
```


### AddGearDN

Adds a gear sketch to the part using diametral pitch and number of teeth

**Overload 1:**

```python
def AddGearDN(name, numberof_teeth, pressure_angle, diametral_pitch, center_x, center_y, plane):
"""
Adds a gear sketch to the part using diametral pitch and number of teeth

Args:
name (str): Name of gear sketch
numberof_teeth (float): Number of teeth
pressure_angle (int): Pressure angle (14.5 is typical)
diametral_pitch (float): Diametral angle (tooth size) (1/module)
center_x (float): X-coordinate of center of gear
center_y (float): Y-coordinate of center of gear
plane (ISketchSurface): Plane or face to create gear sketch on

Returns:
Gear sketch

"""
```

**Overload 2:**

```python
def AddGearDN(name, numberof_teeth, pressure_angle, diametral_pitch, center_x, center_y, single_tooth, plane):
"""
Adds a gear sketch to the part using diametral pitch and number of teeth

Args:
name (str): Name of gear sketch
numberof_teeth (float): Number of teeth
pressure_angle (int): Pressure angle (14.5 is typical)
diametral_pitch (float): Diametral angle (tooth size) (1/module)
center_x (float): X-coordinate of center of gear
center_y (float): Y-coordinate of center of gear
single_tooth (bool): True to generate a single tooth
plane (ISketchSurface): Plane or face to create gear sketch on

Returns:
Gear sketch

"""
```


### AddGearDP

Adds a gear sketch to the part using diametral pitch and pitch diameter

**Overload 1:**

```python
def AddGearDP(name, pitch_diameter, pressure_angle, diametral_pitch, center_x, center_y, plane):
"""
Adds a gear sketch to the part using diametral pitch and pitch diameter

Args:
name (str): Name of gear sketch
pitch_diameter (float): Diameter of pitch circle
pressure_angle (float): Pressure angle (14.5 is typical)
diametral_pitch (float): Diametral angle (tooth size) (1/module)
center_x (float): X-coordinate of center of gear
center_y (float): Y-coordinate of center of gear
plane (ISketchSurface): Plane or face to create gear sketch on

Returns:
Gear sketch

"""
```

**Overload 2:**

```python
def AddGearDP(name, pitch_diameter, pressure_angle, diametral_pitch, center_x, center_y, single_tooth, plane):
"""
Adds a gear sketch to the part using diametral pitch and pitch diameter

Args:
name (str): Name of gear sketch
pitch_diameter (float): Diameter of pitch circle
pressure_angle (float): Pressure angle (14.5 is typical)
diametral_pitch (float): Diametral angle (tooth size) (1/module)
center_x (float): X-coordinate of center of gear
center_y (float): Y-coordinate of center of gear
single_tooth (bool): True to generate a single tooth
plane (ISketchSurface): Plane or face to create gear sketch on

Returns:
Gear sketch

"""
```


### AddGearNP

Adds a gear sketch to the part using number of teeth and pitch diameter

**Overload 1:**

```python
def AddGearNP(name, numberof_teeth, pitch_diameter, pressure_angle, center_x, center_y, plane):
"""
Adds a gear sketch to the part using number of teeth and pitch diameter

Args:
name (str): Name of gear sketch
numberof_teeth (int): Number of teeth
pitch_diameter (float): Diameter of pitch circle
pressure_angle (float): Pressure angle (14.5 is typical)
center_x (float): X-coordinate of center of gear
center_y (float): Y-coordinate of center of gear
plane (ISketchSurface): Plane or face to create gear sketch on

Returns:
Gear sketch

"""
```

**Overload 2:**

```python
def AddGearNP(name, numberof_teeth, pitch_diameter, pressure_angle, center_x, center_y, single_tooth, plane):
"""
Adds a gear sketch to the part using number of teeth and pitch diameter

Args:
name (str): Name of gear sketch
numberof_teeth (int): Number of teeth
pitch_diameter (float): Diameter of pitch circle
pressure_angle (float): Pressure angle (14.5 is typical)
center_x (float): X-coordinate of center of gear
center_y (float): Y-coordinate of center of gear
single_tooth (bool): True to generate a single tooth
plane (ISketchSurface): Plane or face to create gear sketch on

Returns:
Gear sketch

"""
```


### AddLoftBoss

Adds a loft extrusion

**Overload 1:**

```python
def AddLoftBoss(name, cross_sections, minimize_twist, minimize_curvature, simplify_surface, connect_ends):
"""
Adds a loft extrusion

Args:
name (str): Name of loft
cross_sections (list): Python list of cross sections (faces, 2D sketches, design points)
minimize_twist (bool): True to minimize twist
minimize_curvature (bool): True to minimize curvature
simplify_surface (bool): True to simplify the loft surface
connect_ends (bool): True to connect the start of the loft with the end

Returns:
Extruded feature

"""
```

**Overload 2:**

```python
def AddLoftBoss(name, cross_sections, guide_curves, guide_type, minimize_twist, minimize_curvature, simplify_surface, connect_ends):
"""
Adds a loft extrusion using guide curves

Args:
name (str): Name of loft
cross_sections (list): Python list of cross sections (faces, 2D sketches, design points)
guide_curves (list): Python list of guide curves (3D sketches)
guide_type (GuideCurveTypes): Type of guide curve
minimize_twist (bool): True to minimize twist
minimize_curvature (bool): True to minimize curvature
simplify_surface (bool): True to simplify the loft surface
connect_ends (bool): True to connect the start of the loft with the end

Returns:
Extruded feature

"""
```


### AddLoftCut

Adds a loft cut

**Overload 1:**

```python
def AddLoftCut(name, cross_sections, minimize_twist, minimize_curvature, simplify_surface, connect_ends):
"""
Adds a loft cut

Args:
name (str): Name of loft
cross_sections (list): Python list of cross sections (faces, 2D sketches, design points)
minimize_twist (bool): True to minimize twist
minimize_curvature (bool): True to minimize curvature
simplify_surface (bool): True to simplify the loft surface
connect_ends (bool): True to connect the start of the loft with the end

Returns:
Cut feature

"""
```

**Overload 2:**

```python
def AddLoftCut(name, cross_sections, guide_curves, guide_type, minimize_twist, minimize_curvature, simplify_surface, connect_ends):
"""
Adds a loft cut using guide curves

Args:
name (str): Name of loft
cross_sections (list): Python list of cross sections (faces, 2D sketches, design points)
guide_curves (list): Python list of guide curves (3D sketches)
guide_type (GuideCurveTypes): Type of guide curve
minimize_twist (bool): True to minimize twist
minimize_curvature (bool): True to minimize curvature
simplify_surface (bool): True to simplify the loft surface
connect_ends (bool): True to connect the start of the loft with the end

Returns:
Extruded feature

"""
```


### AddParameter

Adds a cm/mm/in/deg parameter to the part

**Overload 1:**

```python
def AddParameter(name, type, value):
"""
Adds a cm/mm/in/deg parameter to the part

Args:
name (str): Name of parameter
type (ParameterTypes): Type of parameter
value (float): Value for parameter

Returns:
New parameter

"""
```

**Overload 2:**

```python
def AddParameter(name, type, unitsto_use, value):
"""
Adds a parameter to the part with specific units

Args:
name (str): Name of parameter
type (ParameterTypes): Type of parameter
unitsto_use (ParameterUnits): Units to use
value (float): Value for parameter

Returns:
New parameter

"""
```

**Overload 3:**

```python
def AddParameter(name, type, equation):
"""
Adds a parameter to the part

Args:
name (str): Name of parameter
type (ParameterTypes): Type of parameter
equation (str): Equation for parameter

Returns:
New parameter

"""
```


### AddPlane

Creates a plane based on the offset from an existing plane

**Overload 1:**

```python
def AddPlane(name, source_plane, offset):
"""
Creates a plane based on the offset from an existing plane

Args:
name (str): Name of plane
source_plane (ISketchSurface): Plane/face to use as basis
offset (float): Offset from basis plane in currently chosen units

Returns:
Created plane

"""
```

**Overload 2:**

```python
def AddPlane(name, normal_vector, pointon_plane):
"""
Adds a plane using a normal vector and a point on the plane

Args:
name (str): Name of plane to add
normal_vector (list): Normal vector as a list [nx, ny, nz]. Does not need to be a unit vector
pointon_plane (list): A point on the plane as a list [px, py, pz]

Returns:
Created plane

"""
```

**Overload 3:**

```python
def AddPlane(name, axis, point):
"""
Creates a new plane contaning an axis and a point

Args:
name (str): Name of new plane
axis (Axis): Axis that lies on plane
point (Point): Point that lies on plane

Returns:
New plane

"""
```

**Overload 4:**

```python
def AddPlane(name, source_plane, rotation_axis, angle):
"""
Creates a new plane at an angle to an existing plane

Args:
name (str): Name of new plane
source_plane (ISketchSurface): Plane/face to use as basis for new plane
rotation_axis (Axis): Axis of rotation for new plane
angle (float): Angle of new plane in degrees

Returns:
New plane

"""
```

**Overload 5:**

```python
def AddPlane(name, point1, point2, point3):
"""
Creates a plane using three points. Each point is defined as list of [x, y, z]

Args:
name (str): Name of plane
point1 (list): Point on plane
point2 (list): Point on plane
point3 (list): Point on plane

Returns:
Created plane

"""
```


### AddPoint

Adds a point to the part

**Overload 1:**

```python
def AddPoint(name, point):
"""
Adds a point to the part

Args:
name (str): Name of the new point
point (list): Point location [x, y, z]

Returns:
The new point

"""
```

**Overload 2:**

```python
def AddPoint(name, point):
"""
Adds a point to the part

Args:
name (str): Name of the point
point (Point): Point to add

"""
```

**Overload 3:**

```python
def AddPoint(name, x, y, z):
"""
Adds a point to the part

Args:
name (str): Name of new point
x (float): X coordinate
y (float): Y coordinate
z (float): Z coordinate

Returns:
The new point

"""
```

**Overload 4:**

```python
def AddPoint(name, point_or_vertex, x_offset, y_offset, z_offset):
"""
Add a point at an offset to a point or a vertex

Args:
name (str): Name of point
point_or_vertex (IPoint): Point or vertex
x_offset (float): X offse
y_offset (float): Y offset
z_offset (float): Z offset

Returns:
The created point

"""
```

**Overload 5:**

```python
def AddPoint(name, point_or_vertex1, point_or_vertex2, ratio):
"""
Add a point between two points/vertices

Args:
name (str): Name of point
point_or_vertex1 (IPoint): First point or vertex
point_or_vertex2 (IPoint): Second point or vertex
ratio (float): Ratio of distance between points/vertices

Returns:
The created point

"""
```

**Overload 6:**

```python
def AddPoint(name, axis_or_edge1, axis_or_edge2):
"""
Add a point at the intersection or two axes or edges

Args:
name (str): Name of point
axis_or_edge1 (IAxis): First axis or edge
axis_or_edge2 (IAxis): Second axis or edge

Returns:
The created point

"""
```

**Overload 7:**

```python
def AddPoint(name, plane_or_face1, plane_or_face2, plane_or_face3):
"""
Add a point at the intersection of three planes or faces

Args:
name (str): Name of point
plane_or_face1 (IPlane): First plane or face
plane_or_face2 (IPlane): Second plane or face
plane_or_face3 (IPlane): Third plane or face

Returns:
The created point

"""
```

**Overload 8:**

```python
def AddPoint(name, axis_or_edge, plane_or_face):
"""
Add a point at the the intersection of a axis or edge and a plane or face

Args:
name (str): Name of point
axis_or_edge (IAxis): Axis or edge
plane_or_face (IPlane): Plane or face

Returns:
The created point

"""
```

**Overload 9:**

```python
def AddPoint(name, source_point_or_vertex, target_plane_or_face, x_offset, y_offset):
"""
Add a point by projecting a point or vertex onto a plane or face

Args:
name (str): Name of point
source_point_or_vertex (IPoint): Point or vertex to project
target_plane_or_face (IPlane): Plane or face to project onto
x_offset (float): X offset to apply to point once projected
y_offset (float): Y offset to apply to point once projected

Returns:
The created point

"""
```

**Overload 10:**

```python
def AddPoint(name, target_edge, ratio):
"""
Add a point on an edge

Args:
name (str): Name of point
target_edge (Edge): The edge to create the point on
ratio (float): Ratio along the edge from 0.0 -> 1.0

Returns:
The created point

"""
```


### AddPointFromCircularEdge

Adds a point at the center of a circular edge

```python
def AddPointFromCircularEdge(name, target_edge):
"""
Adds a point at the center of a circular edge

Args:
name (str): Name of point
target_edge (Edge): The edge to use for creating the point

Returns:
The created point

"""
```


### AddPointFromToroidalFace

Adds a point at the center of a toroidal face

```python
def AddPointFromToroidalFace(name, target_face):
"""
Adds a point at the center of a toroidal face

Args:
name (str): Name of point
target_face (Face): Toroidal face to use in creating the point

Returns:
The created point

"""
```


### AddPoints

Adds a set of points to the part

```python
def AddPoints(prefix, points):
"""
Adds a set of points to the part

Args:
prefix (str): Prefix for the point names
points (list): List of points [x1,y1,z1, ..., xn,yn,zn]

"""
```


### AddRevolveBoss

Creates a revolve boss feature

```python
def AddRevolveBoss(name, sketch, axis, angle):
"""
Creates a revolve boss feature

Args:
name (str): Name of feature
sketch (Sketch): Sketch to revolve
axis (Axis): Axis to rotate around
angle (float): Rotation angle in degrees

Returns:
Created feature

"""
```


### AddRevolveCut

Creates a revolve cut feature

```python
def AddRevolveCut(name, sketch, axis, angle):
"""
Creates a revolve cut feature

Args:
name (str): Name of feature
sketch (Sketch): Sketch to revolve
axis (Axis): Axis to rotate around
angle (float): Rotation angle in degrees

Returns:
Created feature

"""
```


### AddSketch

Creates a new sketch using a plane/face

```python
def AddSketch(name, plane):
"""
Creates a new sketch using a plane/face

Args:
name (str): Name of sketch
plane (ISketchSurface): Plane/face to use for sketch

Returns:
Created sketch

"""
```


### AddSweepBoss

Adds a sweep extrude feature

```python
def AddSweepBoss(name, profile_sketch, path_sketch, is_rigid, end_condition, end_plane, end_offset, draft_angle, outward_draft):
"""
Adds a sweep extrude feature

Args:
name (str): Name of extrusion
profile_sketch (Sketch): Sketch to extrude
path_sketch (ISweepPath): Sketch or edge to sweep along
is_rigid (bool): true if path is parallel to profile
end_condition (Part.EndCondition): End condition for extrusion
end_plane (ISketchSurface): Face or plane to terminate extrusion
end_offset (float): Offset from face or plane to terminate extrusion
draft_angle (float): Angle of draft
outward_draft (bool): true if outward draft

Returns:
Extruded feature

"""
```


### AddSweepCut

Adds a sweep extrude cut feature

```python
def AddSweepCut(name, profile_sketch, path_sketch, is_rigid, end_condition, end_plane, end_offset, draft_angle, outward_draft):
"""
Adds a sweep extrude cut feature

Args:
name (str): Name of extrusion
profile_sketch (Sketch): Sketch to extrude
path_sketch (ISweepPath): Sketch or edge to sweep along
is_rigid (bool): true if path is parallel to profile
end_condition (Part.EndCondition): End condition for extrusion
end_plane (ISketchSurface): Face or plane to terminate extrusion
end_offset (float): Offset from face or plane to terminate extrusion
draft_angle (float): Angle of draft
outward_draft (bool): true if outward draft

Returns:
Extruded feature

"""
```


### AddVertexChamfer

Adds a chamfer to a vertex

**Overload 1:**

```python
def AddVertexChamfer(name, item, distance1, distance2, distance3):
"""
Adds a chamfer to a vertex

Args:
name (str): Name of chamfer
item (Vertex): Vertex to chamfer
distance1 (float): First chamfer distance
distance2 (float): Second chamfer distance
distance3 (float): Third chamfer distance

Returns:
Chamfer feature

"""
```

**Overload 2:**

```python
def AddVertexChamfer(name, items, distance1, distance2, distance3):
"""
Adds a chamfer to a set of vertices

Args:
name (str): Name of chamfer
items (list): Vertices to chamfer
distance1 (float): First chamfer distance
distance2 (float): Second chamfer distance
distance3 (float): Third chamfer distance

Returns:
Chamfer feature

"""
```


### ExportBIP

Exports a keyshot file

```python
def ExportBIP(file_name):
"""
Exports a keyshot file

Args:
file_name (str): Path and name of keyshot file

"""
```


### ExportIGES

Exports the part as a IGES file

```python
def ExportIGES(file_name):
"""
Exports the part as a IGES file

Args:
file_name (str): Path and name of IGES file

"""
```


### ExportRotatedSTL

Exports the part as an STL rotated so that a specific face is on the bottom

```python
def ExportRotatedSTL(file_name, bottom_face, forceto_millimeters, use_custom_settings, max_cell_size, normal_deviation, surface_deviation):
"""
Exports the part as an STL rotated so that a specific face is on the bottom

Args:
file_name (str): Path and name of STL file
bottom_face (Face): Face to use as bottom of part
forceto_millimeters (bool): true to output STL in millimeters regardless of part units
use_custom_settings (bool): true to use custom STL settings, false to use settings in system properties
max_cell_size (float): Custom max cell size
normal_deviation (float): Custom normal deviation
surface_deviation (float): Custom surface deviation

"""
```


### ExportSAT

Exports the part as a SAT file

```python
def ExportSAT(file_name, version, save_colors):
"""
Exports the part as a SAT file

Args:
file_name (str): Path and name of SAT file
version (int): Exported SAT file version
save_colors (bool): true to preseve colors

"""
```


### ExportSTEP203

Exports the part as a STEP 203 file

```python
def ExportSTEP203(file_name):
"""
Exports the part as a STEP 203 file

Args:
file_name (str): Path and name of STEP 203 file

"""
```


### ExportSTEP214

Exports the part as a STEP 214 file

```python
def ExportSTEP214(file_name):
"""
Exports the part as a STEP 214 file

Args:
file_name (str): Path and name of STEP 214 file

"""
```


### ExportSTL

Exports the part as an STL file

```python
def ExportSTL(file_name):
"""
Exports the part as an STL file

Args:
file_name (str): Path and name of STL file

"""
```


### Get3DSketch

Gets a sketch using the name of the sketch

```python
def Get3DSketch(name):
"""
Gets a sketch using the name of the sketch

Args:
name (str): Name of sketch

Returns:
Sketch object

"""
```


### GetAxis

Gets an axis from an axis name

```python
def GetAxis(name):
"""
Gets an axis from an axis name

Args:
name (str): Name of axis to find

Returns:
Found axis

"""
```


### GetConfiguration

Gets a configuration with a specific name

```python
def GetConfiguration(name):
"""
Gets a configuration with a specific name

Args:
name (str): Name of confguration

Returns:
Configuration object

"""
```


### GetCustomProperty

Gets the value of a custonm property

```python
def GetCustomProperty(name):
"""
Gets the value of a custonm property

Args:
name (str): Name of the custom property

Returns:
The value of the property as a string

"""
```


### GetEdge

Gets an edge using it's name "Edge<n>"

```python
def GetEdge(name):
"""
Gets an edge using it's name "Edge<n>"

Args:
name (str): Name of edge

Returns:
Edge if found

"""
```


### GetFace

Gets a face using it's name "Face<n>"

```python
def GetFace(name):
"""
Gets a face using it's name "Face<n>"

Args:
name (str): Name of face

Returns:
Face if found

"""
```


### GetFeature

Gets a feature on the part

```python
def GetFeature(name):
"""
Gets a feature on the part

Args:
name (str): Name of the feature to get

Returns:
The feature or null if not found

"""
```


### GetParameter

Gets a parameter with a specific name

```python
def GetParameter(name):
"""
Gets a parameter with a specific name

Args:
name (str): Name of parameter

Returns:
Parameter object

"""
```


### GetPlane

Gets a plane using the name of the plane

```python
def GetPlane(name):
"""
Gets a plane using the name of the plane

Args:
name (str): Name of plane to find

Returns:
The plane

"""
```


### GetPoint

Gets a point on the part using the point name. The point must have been created in a script

```python
def GetPoint(name):
"""
Gets a point on the part using the point name. The point must have been created in a script

Args:
name (str): Name of point to get

Returns:
Point on the part

"""
```


### GetSketch

Gets a sketch using the name of the sketch

```python
def GetSketch(name):
"""
Gets a sketch using the name of the sketch

Args:
name (str): Name of sketch

Returns:
Sketch object

"""
```


### GetUserData

Gets user data

```python
def GetUserData(name):
"""
Gets user data

Args:
name (str): Name of data to get

Returns:
Data as a python dictionary or None if not found

"""
```


### GetVertex

Gets a vertex using it's name "Vertex<n>"

```python
def GetVertex(name):
"""
Gets a vertex using it's name "Vertex<n>"

Args:
name (str): Name of vertex

Returns:
Vertex if found

"""
```


### HideFeature

Hides a feature on the part

**Overload 1:**

```python
def HideFeature(name):
"""
Hides a feature on the part

Args:
name (str): Name of the feature to hide

"""
```

**Overload 2:**

```python
def HideFeature(feature):
"""
Hides a feature on the part

Args:
feature (Feature): Feature to hide

"""
```


### NonUniformScale

Non-uniform scaling of the part

```python
def NonUniformScale(name, scale_about_center, scale_factor_x, scale_factor_y, scale_factor_z):
"""
Non-uniform scaling of the part

Args:
name (str): Name of the scaling
scale_about_center (bool): true to scale around the center of the part
scale_factor_x (float): X scale factor
scale_factor_y (float): Y scale factor
scale_factor_z (float): Z scale factor

Returns:
Scale feature

"""
```


### RemoveFeature

Removes a feature from the part

**Overload 1:**

```python
def RemoveFeature(name):
"""
Removes a feature from the part

Args:
name (str): Name of the feature to remove

"""
```

**Overload 2:**

```python
def RemoveFeature(feature):
"""
Removes a feature from the part

Args:
feature (Feature): Feature to remove

"""
```


### RemovePlane

Removes a plane from the part

```python
def RemovePlane(plane):
"""
Removes a plane from the part

Args:
plane (Plane): Plane to remove

"""
```


### RemovePoint

Removes a point from the part

```python
def RemovePoint(point):
"""
Removes a point from the part

Args:
point (Point): Point to remove

"""
```


### RemoveSketch

Removes a sketch from the part

**Overload 1:**

```python
def RemoveSketch(name):
"""
Removes a sketch from the part

Args:
name (str): Name of sketch to remove

"""
```

**Overload 2:**

```python
def RemoveSketch(sketch):
"""
Removes a sketch from the part

Args:
sketch (Sketch): Sketch to remove

"""
```


### Save

Saves the part to a specific folder

```python
def Save(folder):
"""
Saves the part to a specific folder

Args:
folder (str): Folder to save to

"""
```


### SaveAs

Saves the part to a specific folder with a new name

```python
def SaveAs(folder, new_name):
"""
Saves the part to a specific folder with a new name

Args:
folder (str): Folder to save to
new_name (str): New name for part

"""
```


### SaveSnapshot

Saves the current view as a bitmap image

```python
def SaveSnapshot(file_name, width, height, use_aspect_ratio, use_widthand_height):
"""
Saves the current view as a bitmap image

Args:
file_name (str): Path and name of file to save to
width (int): Width in pixels
height (int): Height in pixels
use_aspect_ratio (bool): if true uses greater of width/height along with current aspect ratio
use_widthand_height (bool): if true uses current width/height of view

"""
```


### SaveThumbnail

Saves a thumbnail image of the part

```python
def SaveThumbnail(file_name, width, height):
"""
Saves a thumbnail image of the part

Args:
file_name (str): Path and name of file to save to
width (int): Width of thumbnail in pixels
height (int): Height of thumbnail in pixels

"""
```


### Scale

Uniform scaling of the part

```python
def Scale(name, scale_about_center, scale_factor):
"""
Uniform scaling of the part

Args:
name (str): Name of the scaling
scale_about_center (bool): true to scale around the center of the part
scale_factor (float): Scale factor

Returns:
Scale feature

"""
```


### Select

Selects a face, edge, vertex, point, axis, plane, sketch

**Overload 1:**

```python
def Select(faceor_edge):
"""
Selects a face, edge, vertex, point, axis, plane, sketch

Args:
faceor_edge (ISelectableGeometry): Face, edge, vertex, point, axis plane or sketch to select

"""
```

**Overload 2:**

```python
def Select(faces_edges_list):
"""
Selects a group of faces, edges, vertices, points, axes, planes and sketches

Args:
faces_edges_list (list): List of Faces, edges, vertices, points, axes, planes and sketches to select [FaceA, FaceB, EdgeA, EdgeB, ...]

"""
```


### SetColor

Sets the color of the part

```python
def SetColor(red, green, blue):
"""
Sets the color of the part

Args:
red (byte): Red component 0 - 255
green (byte): Green component 0 - 255
blue (byte): Blue component 0 - 255

"""
```


### SetCustomProperty

Sets the value of a custom property
The custom property must already be defined on the part or defined on the user's PC

```python
def SetCustomProperty(name, value):
"""
Sets the value of a custom property The custom property must already be defined on the part or defined on the user's PC

Args:
name (str): Name of the custom property
value (str): New value for the custom property

"""
```


### SetUserData

Sets user data

```python
def SetUserData(name, dict):
"""
Sets user data

Args:
name (str): Data name of the format companyname.projectname.dataname
dict (IronPython.Runtime.PythonDictionary): Python dictionary of data to store

"""
```


### ShowFeature

Shows a feature on the part

**Overload 1:**

```python
def ShowFeature(name):
"""
Shows a feature on the part

Args:
name (str): Name of the feature to show

"""
```

**Overload 2:**

```python
def ShowFeature(feature):
"""
Shows a feature on the part

Args:
feature (Feature): Feature to show

"""
```


### SuppressFeature

Suppresses a feature on the part

**Overload 1:**

```python
def SuppressFeature(name):
"""
Suppresses a feature on the part

Args:
name (str): Name of the feature to suppress

"""
```

**Overload 2:**

```python
def SuppressFeature(feature):
"""
Suppresses a feature on the part

Args:
feature (Feature): Feature to suppress

"""
```


### UnsuppressFeature

Unsuppresses a feature on the part

**Overload 1:**

```python
def UnsuppressFeature(name):
"""
Unsuppresses a feature on the part

Args:
name (str): Name of the feature to unsuppress

"""
```

**Overload 2:**

```python
def UnsuppressFeature(feature):
"""
Unsuppresses a feature on the part

Args:
feature (Feature): Feature to unsuppress

"""
```

---
**[⬆ Back to Top](#part)**

