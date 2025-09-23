# AssembledPart

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [All Classes](Classes)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Properties

### Configurations
Type: `Object`
List of configurations defined on the part

### Name
Type: `Object`
Name of the assembled part

## Methods


### AddPoint

Adds a point at an offset to a point or a vertex

**Overload 1:**

```python
def AddPoint(name, point_or_vertex, x_offset, y_offset, z_offset):
"""
Adds a point at an offset to a point or a vertex

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
Adds a point between two points/vertices

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
Adds a point at the intersection or two axes or edges

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
Adds a point at the intersection of three planes or faces

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
Adds a point at the the intersection of a axis or edge and a plane or face

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
Adds a point by projecting a point or vertex onto a plane or face

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
Adds a point on an edge

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


### AssemblyPointtoPartPoint

Converts a point in the assembly coordinate system into a point in the part
coordinate system

```python
def AssemblyPointtoPartPoint(assembly_point):
"""
Converts a point in the assembly coordinate system into a point in the part coordinate system

Args:
assembly_point (list): Point [X, Y, Z] in the assembly coordinate system

Returns:
Point [X, Y, Z] in the part coordinate system

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


### GetMappedOccurrence

Gets the occurrence of the part mapped into the
occurrence structure of a specific assembly
This occurrence can be used to create constraints in the specific
assembly using the part

```python
def GetMappedOccurrence(assembly):
"""
Gets the occurrence of the part mapped into the occurrence structure of a specific assembly This occurrence can be used to create constraints in the specific assembly using the part

Args:
assembly (AlibreX.IADAssemblySession): Assembly for occurrence structure

Returns:
Mapped occurrence or null if not found

"""
```


### PartPointtoAssemblyPoint

Converts a point in the part coordinate system into a point in the assembly
coordinate system

```python
def PartPointtoAssemblyPoint(part_point):
"""
Converts a point in the part coordinate system into a point in the assembly coordinate system

Args:
part_point (list): Point [X, Y, Z] in the part coordinate system

Returns:
Point [X, Y, Z] in the assembly coordinate system

"""
```

---
**[⬆ Back to Top](#assembledpart)**
