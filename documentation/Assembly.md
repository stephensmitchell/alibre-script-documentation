# Assembly

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index)**

** Location:**[Assembly & Parts](Classes#assembly-and-parts) Assembly

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Assembly class provides comprehensive functionality for creating, manipulating, and managing assemblies within Alibre Design. This class handles assembly constraints, component management, and assembly-level operations.

## Practical Usage

Assemblies are core to mechanical design and automation. Common scripting scenarios include:
- **Automated assembly generation** from part libraries
- **Parametric assemblies** that adapt to design changes
- **Constraint management** for proper component positioning
- **Assembly validation** and interference checking
- **Configuration management** for design variants

## Common Coding Patterns

```python
# Create new assembly
assembly = Assembly("MyAssembly.AD_ASM", "C:\\MyProject")

# Add parts to assembly
part1 = assembly.AddPart("Bracket.AD_PRT", "C:\\Parts")
part2 = assembly.AddPart("Shaft.AD_PRT", "C:\\Parts")

# Create alignment constraint between parts
assembly.AddAlignConstraint(
0.0, # Distance (flush alignment)
part1, # First part
part1.GetPlane("XY"), # Reference plane on first part
part2, # Second part
part2.GetPlane("XY"), # Reference plane on second part
False, # Not reversed
"FlushConstraint" # Constraint name
)

# Save assembly
assembly.Save("Final assembly saved")
```

## Related Classes
- [AssembledPart](AssembledPart) - Individual parts within assembly
- [AssembledSubAssembly](AssembledSubAssembly) - Sub-assemblies within assembly
- [Part](Part) - Base part functionality
- [Assembly.ConstraintBoundsType](Assembly.ConstraintBoundsType) - Constraint definitions
- [Configuration](Configuration) - Assembly configurations

## Quick Navigation
- [Properties](#properties) - Assembly properties and metadata
- [Methods](#methods) - Available operations
- [Constraint Methods](#constraint-methods) - Assembly constraints
- [Component Methods](#component-methods) - Managing parts and sub-assemblies
- [File Operations](#file-operations) - Save, export, import

## Properties

### Comment
Type: `Object`
Comment property

### Configurations
Type: `Object`
A list of configurations defined on the assembly

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
Path and filename of the assembly

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

### Material
Type: `Object`
Material of the part

### ModifiedInformation
Type: `Object`
Modified Information property

### Name
Type: `Object`
Name of the assembly

### Number
Type: `Object`
User-defined number for the part

### Origin
Type: `Object`
Gets the origin (language independent)

### Parameters
Type: `Object`
A list of parameters defined on the assembly

### Parts
Type: `Object`
A list of parts defined on the assembly

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
Supports subassemblies, parts, faces, edges, vertices, planes, axes and points

### StockSize
Type: `Object`
Stock Size property

### SubAssemblies
Type: `Object`
A list of subassemblies defined on the assembly

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


### Assembly

Opens an existing assembly

**Overload 1:**

```python
def Assembly(folder, name):
"""
Opens an existing assembly

Args:
folder (str): Folder containing assembly
name (str): Name of assembly to open

"""
```

**Overload 2:**

```python
def Assembly(folder, name, hide_editor):
"""
Opens an existing assembly, optionally hiding the editor

Args:
folder (str): Folder containing assembly
name (str): Name of assembly to open
hide_editor (bool): True to hide the editor

"""
```

**Overload 3:**

```python
def Assembly(name):
"""
Creates a new assembly

Args:
name (str): Name of new assembly

"""
```

**Overload 4:**

```python
def Assembly(name, create_new):
"""
Creates a new assembly or accesses an already opened assembly

Args:
name (str): Name of assembly to create or access
create_new (bool): True to create a new assembly, false to access an opened assembly

"""
```

**Overload 5:**

```python
def Assembly(name, create_new, hide_editor):
"""
Creates a new assembly or accesses an already opened assembly, optionally hiding the editor

Args:
name (str): Name of assembly to create or access
create_new (bool): True to create a new assembly, false to access an opened assembly
hide_editor (bool): True to hide the editor (only valid if assembly is not already open)

"""
```


### AddAlignConstraint

Adds a simple alignment constraint between two planes/faces/axes/edges/points

**Overload 1:**

```python
def AddAlignConstraint(distance, partor_assembly_a, item_a, partor_assembly_b, item_b):
"""
Adds a simple alignment constraint between two planes/faces/axes/edges/points

Args:
distance (float): Alignment distance
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain

"""
```

**Overload 2:**

```python
def AddAlignConstraint(distance, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds a simple alignment constraint between two planes/faces/axes/edges/points

Args:
distance (float): Alignment distance
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddAlignConstraint2

Adds an alignment constraint between two planes/faces/axes/edges/points
Uses bounds type

```python
def AddAlignConstraint2(distance1, distance2, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name, bounds_type):
"""
Adds an alignment constraint between two planes/faces/axes/edges/points Uses bounds type

Args:
distance1 (float): Align distance
distance2 (float): Second distance for 'between' bounds type or zero if not used
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint
bounds_type (Assembly.ConstraintBoundsType): The bounds type to use

"""
```


### AddAngleConstraint

Adds an angle constraint between two planes/faces/axes/edges/points

**Overload 1:**

```python
def AddAngleConstraint(angle, partor_assembly_a, item_a, partor_assembly_b, item_b):
"""
Adds an angle constraint between two planes/faces/axes/edges/points

Args:
angle (float): Angle in degrees
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain

"""
```

**Overload 2:**

```python
def AddAngleConstraint(angle, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds a simple angle constraint between two planes/faces/axes/edges/points

Args:
angle (float): Angle in degrees
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddAngleConstraint2

Adds an angle constraint between two planes/faces/axes/edges/points
Uses bounds type

```python
def AddAngleConstraint2(angle1, angle2, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name, bounds_type):
"""
Adds an angle constraint between two planes/faces/axes/edges/points Uses bounds type

Args:
angle1 (float): Angle for constraint
angle2 (float): Second angle for 'between' bounds type or zero if not used
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint
bounds_type (Assembly.ConstraintBoundsType): The bounds type to use

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
def AddAxis(name, point1, point2):
"""
Creates an axis based on two points

Args:
name (str): Name of axis
point1 (list): First point
point2 (list): Second point

Returns:
New axis

"""
```


### AddConfiguration

Adds a configuration to the assembly

**Overload 1:**

```python
def AddConfiguration(name):
"""
Adds a configuration to the assembly

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
Adds a configuration to the assembly using another configuration as a base

Args:
name (str): Name of configuration
base_configuration_name (str): Name of base configuration to use

Returns:
New configuration

"""
```


### AddFastenerConstraint

Adds a fastner constraint

```python
def AddFastenerConstraint(distance, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds a fastner constraint

Args:
distance (float): Fastener to surface mate distance
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddFastenerConstraint2

Adds a fastner constraint

```python
def AddFastenerConstraint2(distance1, distance2, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name, bounds_type):
"""
Adds a fastner constraint

Args:
distance1 (float): Fastener to surface mate distance
distance2 (float): Second distance for 'between' bounds type or zero if not used
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint
bounds_type (Assembly.ConstraintBoundsType): The bounds type to use

"""
```


### AddGearConstraint

Adds a gear constraint using ratio RatioA:RatioB

```python
def AddGearConstraint(ratio_a, ratio_b, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds a gear constraint using ratio RatioA:RatioB

Args:
ratio_a (float): First value in gear ratio
ratio_b (float): Second value in gear ratio
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddMateConstraint

Adds a simple mate constraint between two planes/faces/axes/edges/points

**Overload 1:**

```python
def AddMateConstraint(distance, partor_assembly_a, item_a, partor_assembly_b, item_b):
"""
Adds a simple mate constraint between two planes/faces/axes/edges/points

Args:
distance (float): Mate distance
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain

"""
```

**Overload 2:**

```python
def AddMateConstraint(distance, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds a simple mate constraint between two planes/faces/axes/edges/points

Args:
distance (float): Mate distance
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddMateConstraint2

Adds a mate constraint between two planes/faces/axes/edges/points
Uses bounds type

```python
def AddMateConstraint2(distance1, distance2, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name, bounds_type):
"""
Adds a mate constraint between two planes/faces/axes/edges/points Uses bounds type

Args:
distance1 (float): Mate distance
distance2 (float): Second distance for 'between' bounds type or zero if not used
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint
bounds_type (Assembly.ConstraintBoundsType): The bounds type to use

"""
```


### AddNewPart

Adds a new part to the assembly

```python
def AddNewPart(name, x, y, z):
"""
Adds a new part to the assembly

Args:
name (str): Name of the new part
x (float): X location of part
y (float): Y location of part
z (float): Z location of part

Returns:
New part

"""
```


### AddNewSubAssembly

Adds a new sub-assembly to the assembly

```python
def AddNewSubAssembly(name, x, y, z):
"""
Adds a new sub-assembly to the assembly

Args:
name (str): Name of the new assembly
x (float): X location of assembly
y (float): Y location of assembly
z (float): Z location of assembly

Returns:
New part

"""
```


### AddOrientConstraint

Adds an orient constraint between two planes/faces/axes/edges/points

**Overload 1:**

```python
def AddOrientConstraint(value, partor_assembly_a, item_a, partor_assembly_b, item_b):
"""
Adds an orient constraint between two planes/faces/axes/edges/points

Args:
value (float): Value
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain

"""
```

**Overload 2:**

```python
def AddOrientConstraint(value, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds an orient constraint between two planes/faces/axes/edges/points

Args:
value (float): Value
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddParameter

Adds a parameter to the assembly

**Overload 1:**

```python
def AddParameter(name, type, value):
"""
Adds a parameter to the assembly

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
def AddParameter(name, type, equation):
"""
Adds a parameter to the assembly NOTE: DOESN'T SEEM TO WORK IN GD V16 - THROWS EXCEPTION ABOUT TRANSACTION ALREADY BEING OPEN

Args:
name (str): Name of parameter
type (ParameterTypes): Type of parameter
equation (str): Equation for parameter

Returns:
New parameter

"""
```


### AddPart

Adds a part to the assembly at the origin

**Overload 1:**

```python
def AddPart(folder, name):
"""
Adds a part to the assembly at the origin

Args:
folder (str): Folder containing part
name (str): Name of part to open

Returns:
The added part

"""
```

**Overload 2:**

```python
def AddPart(folder, name, offset_x, offset_y, offset_z):
"""
Adds a part to the assembly

Args:
folder (str): Folder containing part
name (str): Name of part to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The added part

"""
```

**Overload 3:**

```python
def AddPart(folder, name, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Adds a part to the assembly

Args:
folder (str): Folder containing part
name (str): Name of part to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The added part

"""
```

**Overload 4:**

```python
def AddPart(part):
"""
Adds a part to the assembly at the origin

Args:
part (Part): Part to add

Returns:
The added part

"""
```

**Overload 5:**

```python
def AddPart(part, offset_x, offset_y, offset_z):
"""
Adds a part to the assembly

Args:
part (Part): Part to add
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The added part

"""
```

**Overload 6:**

```python
def AddPart(file_name):
"""
Adds a part to the assembly at the origin

Args:
file_name (str): Path and name of part to open

Returns:
The added part

"""
```

**Overload 7:**

```python
def AddPart(file_name, offset_x, offset_y, offset_z):
"""
Adds a part to the assembly

Args:
file_name (str): Path and name of part to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The added part

"""
```

**Overload 8:**

```python
def AddPart(file_name, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Adds a part to the assembly

Args:
file_name (str): Path and name of part to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The added part

"""
```

**Overload 9:**

```python
def AddPart(part, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Adds a part to the assembly

Args:
part (Part): Part to add
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The added part

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

**Overload 4:**

```python
def AddPlane(name, point1, point2, point3):
"""
Creates a plane using three points

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

Add a point at an offset to a point or a vertex

**Overload 1:**

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

**Overload 2:**

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

**Overload 3:**

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

**Overload 4:**

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

**Overload 5:**

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

**Overload 6:**

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

**Overload 7:**

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

**Overload 8:**

```python
def AddPoint(name, x, y, z):
"""
Adds a point to the assembly

Args:
name (str): Name of new point
x (float): X coordinate
y (float): Y coordinate
z (float): Z coordinate

Returns:
The new point

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


### AddRackAndPinionConstraint

Adds a rack and pinion constraint

```python
def AddRackAndPinionConstraint(pitch_diameter, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds a rack and pinion constraint

Args:
pitch_diameter (float): Pitch diameter
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddScrewConstraint

Adds a screw constraint

```python
def AddScrewConstraint(thread_pitch, partor_assembly_a, item_a, partor_assembly_b, item_b, is_reversed, name):
"""
Adds a screw constraint

Args:
thread_pitch (float): Pitch of thread
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AddSubAssembly

Adds a sub-assembly to the assembly

**Overload 1:**

```python
def AddSubAssembly(file_name, offset_x, offset_y, offset_z):
"""
Adds a sub-assembly to the assembly

Args:
file_name (str): Path and name of sub-assembly to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The added sub-assembly

"""
```

**Overload 2:**

```python
def AddSubAssembly(file_name, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Adds a sub-assembly to the assembly

Args:
file_name (str): Path and name of sub-asembly to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The added assembly

"""
```

**Overload 3:**

```python
def AddSubAssembly(assembly):
"""
Adds a sub-assembly to the assembly at the origin

Args:
assembly (Assembly): Assembly to add

Returns:
The added assembly

"""
```

**Overload 4:**

```python
def AddSubAssembly(assembly, offset_x, offset_y, offset_z):
"""
Adds a sub-assembly to the assembly

Args:
assembly (Assembly): Assembly to add
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The added assembly

"""
```

**Overload 5:**

```python
def AddSubAssembly(assembly, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Adds a sub-assembly to the assembly

Args:
assembly (Assembly): Sub-assembly to add
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The added sub-assembly

"""
```

**Overload 6:**

```python
def AddSubAssembly(folder, name):
"""
Adds a sub-assembly to the assembly at the origin

Args:
folder (str): Folder containing sub-assembly
name (str): Name of sub-assembly to open

Returns:
The added sub-assembly

"""
```

**Overload 7:**

```python
def AddSubAssembly(folder, name, offset_x, offset_y, offset_z):
"""
Adds a sub-assembly to the assembly

Args:
folder (str): Folder containing sub-assembly
name (str): Name of sub-assembly to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The added sub-assembly

"""
```

**Overload 8:**

```python
def AddSubAssembly(folder, name, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Adds a sub-assembly to the assembly

Args:
folder (str): Folder containing sub-assembly
name (str): Name of sub-assembly to open
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The added sub-assembly

"""
```

**Overload 9:**

```python
def AddSubAssembly(file_name):
"""
Adds a sub-assembly to the assembly at the origin

Args:
file_name (str): Path and name of sub-assembly to open

Returns:
The added sub-assembly

"""
```


### AddTangentConstraint

Adds a tangent constraint between two planes/faces/axes/edges/points

**Overload 1:**

```python
def AddTangentConstraint(distance, partor_assembly_a, item_a, partor_assembly_b, item_b, outside):
"""
Adds a tangent constraint between two planes/faces/axes/edges/points

Args:
distance (float): Alignment distance
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
outside (bool): true for an outside tangent constraint, false for an inside tangent constraint

"""
```

**Overload 2:**

```python
def AddTangentConstraint(distance, partor_assembly_a, item_a, partor_assembly_b, item_b, outside, is_reversed, name):
"""
Adds a tangent constraint between two planes/faces/axes/edges/points

Args:
distance (float): Alignment distance
partor_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
partor_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
outside (bool): true for an outside tangent constraint, false for an inside tangent constraint
is_reversed (bool): true to reverse constraint
name (str): Name of constraint

"""
```


### AnchorPart

Anchors a part

**Overload 1:**

```python
def AnchorPart(name):
"""
Anchors a part

Args:
name (str): Name of part to anchor

"""
```

**Overload 2:**

```python
def AnchorPart(part):
"""
Anchors a part

Args:
part (AssembledPart): Part to anchor

"""
```


### AnchorSubAssembly

Anchors a sub-assembly

```python
def AnchorSubAssembly(name):
"""
Anchors a sub-assembly

Args:
name (str): Name of sub-assembly to anchor

"""
```


### CreateUniqueName

Creates a unique name that can be used to safely add a part or subassembly to the assembly
if the names used in the assembly are not known in advance

```python
def CreateUniqueName(base_name):
"""
Creates a unique name that can be used to safely add a part or subassembly to the assembly if the names used in the assembly are not known in advance

Args:
base_name (str): Base name to use

Returns:
Unique name

"""
```


### DuplicatePart

Duplicates a part in the assembly

**Overload 1:**

```python
def DuplicatePart(name, offset_x, offset_y, offset_z):
"""
Duplicates a part in the assembly

Args:
name (str): Name of part to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The duplicate part

"""
```

**Overload 2:**

```python
def DuplicatePart(part, offset_x, offset_y, offset_z):
"""
Duplicates a part in the assembly

Args:
part (AssembledPart): Part to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The duplicate part

"""
```

**Overload 3:**

```python
def DuplicatePart(name, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Duplicates a part in the assembly

Args:
name (str): Name of part to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The duplicate part

"""
```

**Overload 4:**

```python
def DuplicatePart(part, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Duplicates a part in the assembly

Args:
part (AssembledPart): Part to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The duplicate part

"""
```


### DuplicateSubAssembly

Duplicates a sub-assembly in the assembly

**Overload 1:**

```python
def DuplicateSubAssembly(sub_assembly, offset_x, offset_y, offset_z):
"""
Duplicates a sub-assembly in the assembly

Args:
sub_assembly (AssembledSubAssembly): Sub-assembly to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The duplicate sub-assembly

"""
```

**Overload 2:**

```python
def DuplicateSubAssembly(name, offset_x, offset_y, offset_z):
"""
Duplicates a sub-assembly in the assembly

Args:
name (str): Name of sub-assembly to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset

Returns:
The duplicate sub-assembly

"""
```

**Overload 3:**

```python
def DuplicateSubAssembly(sub_assembly, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Duplicates a sub-assembly in the assembly

Args:
sub_assembly (AssembledSubAssembly): Sub-assembly to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The duplicate sub-assembly

"""
```

**Overload 4:**

```python
def DuplicateSubAssembly(name, offset_x, offset_y, offset_z, angle_x, angle_y, angle_z, translation_first):
"""
Duplicates a sub-assembly in the assembly

Args:
name (str): Name of sub-assembly to duplicate
offset_x (float): X offset
offset_y (float): Y offset
offset_z (float): Z offset
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
translation_first (bool): if true translation occurs before rotation, if false rotation occurs before translation

Returns:
The duplicate sub-assembly

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

Exports the assembly as a IGES file

```python
def ExportIGES(file_name):
"""
Exports the assembly as a IGES file

Args:
file_name (str): Path and name of IGES file

"""
```


### ExportSAT

Exports the assembly as a SAT file

```python
def ExportSAT(file_name, version, save_colors):
"""
Exports the assembly as a SAT file

Args:
file_name (str): Path and name of SAT file
version (int): Exported SAT file version
save_colors (bool): true to preseve colors

"""
```


### ExportSTEP203

Exports the assembly as a STEP 203 file

```python
def ExportSTEP203(file_name):
"""
Exports the assembly as a STEP 203 file

Args:
file_name (str): Path and name of STEP 203 file

"""
```


### ExportSTEP214

Exports the assembly as a STEP 214 file

```python
def ExportSTEP214(file_name):
"""
Exports the assembly as a STEP 214 file

Args:
file_name (str): Path and name of STEP 214 file

"""
```


### ExportSTL

Exports the assembly as an STL file

```python
def ExportSTL(file_name):
"""
Exports the assembly as an STL file

Args:
file_name (str): Path and name of STL file

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


### GetPart

Gets a part in the assembly

```python
def GetPart(name):
"""
Gets a part in the assembly

Args:
name (str): Name of part instance to get

Returns:
The part

"""
```


### GetPartOrientation

Gets the orientation of a part in an assembly

**Overload 1:**

```python
def GetPartOrientation(part):
"""
Gets the orientation of a part in an assembly

Args:
part (AssembledPart): Part in an assembly

Returns:
Part orientation as [OffsetX, OffsetY, OffsetZ, AngleX, AngleY, AngleZ], translation before rotation

"""
```

**Overload 2:**

```python
def GetPartOrientation(part_name):
"""
Gets the orientation of a part in an assembly

Args:
part_name (str): Name of part to get orientation

Returns:
Part orientation as [OffsetX, OffsetY, OffsetZ, AngleX, AngleY, AngleZ], translation before rotation

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

Gets a point on the assembly using the point name. The point must have been created in a script

```python
def GetPoint(name):
"""
Gets a point on the assembly using the point name. The point must have been created in a script

Args:
name (str): Name of point to get

Returns:
The point

"""
```


### GetSubAssembly

Gets a sub-assembly in the assembly

```python
def GetSubAssembly(name):
"""
Gets a sub-assembly in the assembly

Args:
name (str): Name of sub-assembly instance to get

Returns:
The sub-assembly

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


### HidePart

Hides a part

**Overload 1:**

```python
def HidePart(name):
"""
Hides a part

Args:
name (str): Name of part to hide

"""
```

**Overload 2:**

```python
def HidePart(part):
"""
Hides a part

Args:
part (AssembledPart): Part to hide

"""
```


### HideSubAssembly

Hides a sub-assembly

```python
def HideSubAssembly(name):
"""
Hides a sub-assembly

Args:
name (str): Name of sub-assembly to hide

"""
```


### MovePart

Moves a part

**Overload 1:**

```python
def MovePart(name, offset_x, offset_y, offset_z, apply_constraints):
"""
Moves a part

Args:
name (str): Name of part to move
offset_x (float): X offset to apply
offset_y (float): Y offset to apply
offset_z (float): Z offset to apply
apply_constraints (bool): true to apply constraints

"""
```

**Overload 2:**

```python
def MovePart(part, offset_x, offset_y, offset_z, apply_constraints):
"""
Moves a part

Args:
part (AssembledPart): Part to move
offset_x (float): X offset to apply
offset_y (float): Y offset to apply
offset_z (float): Z offset to apply
apply_constraints (bool): true to apply constraints

"""
```


### MoveParts

Moves a set of parts

```python
def MoveParts(names, offset_x, offset_y, offset_z, apply_constraints):
"""
Moves a set of parts

Args:
names (list): Names of parts to move
offset_x (float): X offset to apply
offset_y (float): Y offset to apply
offset_z (float): Z offset to apply
apply_constraints (bool): true to apply constraints

"""
```


### MoveSubAssemblies

Moves a set of sub-assemblies

```python
def MoveSubAssemblies(names, offset_x, offset_y, offset_z, apply_constraints):
"""
Moves a set of sub-assemblies

Args:
names (list): Names of sub-assemblies to move
offset_x (float): X offset to apply
offset_y (float): Y offset to apply
offset_z (float): Z offset to apply
apply_constraints (bool): true to apply constraints

"""
```


### MoveSubAssembly

Moves a sub-assembly

**Overload 1:**

```python
def MoveSubAssembly(name, offset_x, offset_y, offset_z, apply_constraints):
"""
Moves a sub-assembly

Args:
name (str): Name of sub-assembly to move
offset_x (float): X offset to apply
offset_y (float): Y offset to apply
offset_z (float): Z offset to apply
apply_constraints (bool): true to apply constraints

"""
```

**Overload 2:**

```python
def MoveSubAssembly(sub_assembly, offset_x, offset_y, offset_z, apply_constraints):
"""
Moves a sub-assembly

Args:
sub_assembly (AssembledSubAssembly): Sub-assembly to move
offset_x (float): X offset to apply
offset_y (float): Y offset to apply
offset_z (float): Z offset to apply
apply_constraints (bool): true to apply constraints

"""
```


### RotatePart

Rotates a part

**Overload 1:**

```python
def RotatePart(name, angle_x, angle_y, angle_z, apply_constraints):
"""
Rotates a part

Args:
name (str): Name of part to rotate
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
apply_constraints (bool): true to apply constraints

"""
```

**Overload 2:**

```python
def RotatePart(part, angle_x, angle_y, angle_z, apply_constraints):
"""
Rotates a part

Args:
part (AssembledPart): Part to rotate
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
apply_constraints (bool): true to apply constraints

"""
```


### RotateParts

Rotates a set of parts

```python
def RotateParts(names, angle_x, angle_y, angle_z, apply_constraints):
"""
Rotates a set of parts

Args:
names (list): Names of parts to rotate
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
apply_constraints (bool): true to apply constraints

"""
```


### RotateSubAssemblies

Rotates a set of sub-assemblies

```python
def RotateSubAssemblies(names, angle_x, angle_y, angle_z, apply_constraints):
"""
Rotates a set of sub-assemblies

Args:
names (list): Names of sub-assemblies to rotate
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
apply_constraints (bool): true to apply constraints

"""
```


### RotateSubAssembly

Rotates a sub-assembly

**Overload 1:**

```python
def RotateSubAssembly(name, angle_x, angle_y, angle_z, apply_constraints):
"""
Rotates a sub-assembly

Args:
name (str): Name of sub-assembly to rotate
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
apply_constraints (bool): true to apply constraints

"""
```

**Overload 2:**

```python
def RotateSubAssembly(sub_assembly, angle_x, angle_y, angle_z, apply_constraints):
"""
Rotates a sub-assembly

Args:
sub_assembly (AssembledSubAssembly): Sub-assembly to rotate
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
apply_constraints (bool): true to apply constraints

"""
```

**Overload 3:**

```python
def RotateSubAssembly(assem_occ, angle_x, angle_y, angle_z, apply_constraints):
"""
Rotates a sub-assembly

Args:
assem_occ (AlibreX.IADOccurrence): Occurence of sub-assembly to rotate
angle_x (float): X rotation angle in degrees
angle_y (float): Y rotation angle in degrees
angle_z (float): Z rotation angle in degrees
apply_constraints (bool): true to apply constraints

"""
```


### Save

Saves the assembly to a specific folder

```python
def Save(folder):
"""
Saves the assembly to a specific folder

Args:
folder (str): Folder to save to

"""
```


### SaveAll

Save the assembly and all parts/sub-assemblies to a folder

```python
def SaveAll(folder):
"""
Save the assembly and all parts/sub-assemblies to a folder

Args:
folder (str): Folder to save to

"""
```


### SaveAs

Saves the assembly to a specific folder with a new name

```python
def SaveAs(folder, new_name):
"""
Saves the assembly to a specific folder with a new name

Args:
folder (str): Folder to save to
new_name (str): New name for assembly

"""
```


### SaveSnapshot

Saves the current view as a bitmap image

```python
def SaveSnapshot(file_name, width, height, use_aspect_ratio, use_widthand_height):
"""
Saves the current view as a bitmap image

Args:
file_name (str): Path and mame of file to save to
width (int): Width in pixels
height (int): Height in pixels
use_aspect_ratio (bool): if true uses greater of width/height along with current aspect ratio
use_widthand_height (bool): if true uses current width/height of view

"""
```


### SaveThumbnail

Saves a thumbnail image of the assembly

```python
def SaveThumbnail(file_name, width, height):
"""
Saves a thumbnail image of the assembly

Args:
file_name (str): Path and name of file to save to
width (int): Width of thumbnail in pixels
height (int): Height of thumbnail in pixels

"""
```


### SetCustomProperty

Sets the value of a custom property
The custom property must already be defined on the assembly or defined on the user's PC

```python
def SetCustomProperty(name, value):
"""
Sets the value of a custom property The custom property must already be defined on the assembly or defined on the user's PC

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


### ShowPart

Shows a part

**Overload 1:**

```python
def ShowPart(name):
"""
Shows a part

Args:
name (str): Name of part to show

"""
```

**Overload 2:**

```python
def ShowPart(part):
"""
Shows a part

Args:
part (AssembledPart): Part to show

"""
```


### ShowSubAssembly

Shows a sub-assembly

```python
def ShowSubAssembly(name):
"""
Shows a sub-assembly

Args:
name (str): Name of sub-assembly to show

"""
```


### SuppressPart

Suppresses a part

**Overload 1:**

```python
def SuppressPart(name):
"""
Suppresses a part

Args:
name (str): Name of part to suppress

"""
```

**Overload 2:**

```python
def SuppressPart(part):
"""
Suppresses a part

Args:
part (AssembledPart): Part to suppress

"""
```


### SuppressSubAssembly

Suppresses a sub-assembly

```python
def SuppressSubAssembly(name):
"""
Suppresses a sub-assembly

Args:
name (str): Name of sub-assembly to suppress

"""
```


### UnanchorPart

Un-anchors a part

**Overload 1:**

```python
def UnanchorPart(name):
"""
Un-anchors a part

Args:
name (str): Name of part to un-anchor

"""
```

**Overload 2:**

```python
def UnanchorPart(part):
"""
Un-anchors a part

Args:
part (AssembledPart): Part to un-anchor

"""
```


### UnanchorSubAssembly

Un-anchors a sub-assembly

```python
def UnanchorSubAssembly(name):
"""
Un-anchors a sub-assembly

Args:
name (str): Name of sub-assembly to un-anchor

"""
```


### UnsuppressPart

Un-suppresses a part

**Overload 1:**

```python
def UnsuppressPart(name):
"""
Un-suppresses a part

Args:
name (str): Name of part to un-suppress

"""
```

**Overload 2:**

```python
def UnsuppressPart(part):
"""
Un-suppresses a part

Args:
part (AssembledPart): Part to un-suppress

"""
```


### UnsuppressSubAssembly

Un-suppresses a sub-assembly

```python
def UnsuppressSubAssembly(name):
"""
Un-suppresses a sub-assembly

Args:
name (str): Name of sub-assembly to un-suppress

"""
```


### AddAlignConstraint

Adds a simple alignment constraint between two planes/faces/axes/edges/points

**Overload 1:**

```python
def AddAlignConstraint(distance, part_or_assembly_a, item_a, part_or_assembly_b, item_b):
"""
Adds a simple alignment constraint between two planes/faces/axes/edges/points

Args:
distance (float): Alignment distance
part_or_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
part_or_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain

"""
```

**Overload 2:**

```python
def AddAlignConstraint(distance, part_or_assembly_a, item_a, part_or_assembly_b, item_b, is_reversed, name):
"""
Adds a simple alignment constraint between two planes/faces/axes/edges/points

Args:
distance (float): Alignment distance
part_or_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
part_or_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): True to reverse constraint
name (str): Name of constraint

"""
```


### AddAlignConstraint2

Adds an alignment constraint between two planes/faces/axes/edges/points using bounds type

```python
def AddAlignConstraint2(distance1, distance2, part_or_assembly_a, item_a, part_or_assembly_b, item_b, is_reversed, name, bounds_type):
"""
Adds an alignment constraint between two planes/faces/axes/edges/points
Uses bounds type for advanced constraint control

Args:
distance1 (float): Align distance
distance2 (float): Second distance for 'between' bounds type or zero if not used
part_or_assembly_a (IAssembled): First part/assembly to constrain
item_a (IConstrainable): Plane/face/axis/edge/point on first part/assembly to constrain
part_or_assembly_b (IAssembled): Second part/assembly to constrain
item_b (IConstrainable): Plane/face/axis/edge/point on second part/assembly to constrain
is_reversed (bool): True to reverse constraint
name (str): Name of constraint
bounds_type (Assembly.ConstraintBoundsType): Bounds type for constraint

"""
```

---
**[⬆ Back to Top](#assembly)**

