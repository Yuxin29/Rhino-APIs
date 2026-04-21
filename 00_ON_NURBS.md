# OpenNURBS `ON_` Classes Categorization Guide

This document organizes the large set of `ON_` classes from the OpenNURBS / Rhino geometry kernel into functional groups. It preserves the full conceptual structure of the system and explains how each part contributes to CAD and 3D modeling.

⭐ base class for all
📍 what I used for my plugin

---

# 1. Fundamental Mathematics / Core Geometry Primitives
These are the lowest-level building blocks used across all geometry types.

## Points and Vectors (2D / 3D / 4D)
- ON_2dPoint, ON_3dPoint, ON_4dPoint
- ON_2dVector, ON_3dVector
- ON_2fPoint, ON_3fVector
- ON_Interval (numeric ranges)
- ...

**Purpose:**
Define positions, directions, and ranges in space.

## Numeric & Engineering Units
- ON_AngleValue
- ON_LengthValue
- ON_MassProperties
- ON_ScaleValue
- ON_UnitSystem
- ...

**Purpose:**
Handles real-world engineering units (mm, inches, degrees, etc.).

## Math Utilities
- ON_Matrix
- ON_Quaternion
- ON_Xform (transformation matrix)
- ON_RandomNumberGenerator

**Purpose:**
Used for transformations, rotations, scaling, and random sampling.

---

# 2. Core Geometry Base System
The root of all geometric objects.

- ON_Geometry ⭐ (base class for all geometry)
- ON_Object 📍  (serialization base class)
- ON_BoundingBox

**Purpose:**
Provides common interface and bounding box computation.

---

# 3. Curve System (1D Geometry)
Represents curves and paths in space.

## Basic Curves
- ON_Curve ⭐ (base class)
- ON_Line
- ON_Circle
- ON_Arc
- ON_Ellipse
- ON_Polyline

## NURBS / Parametric Curves
- ON_NurbsCurve
- ON_BezierCurve
- ON_PolynomialCurve

**Purpose:**
Main representation for CAD-quality curves.

## Composite Curves
- ON_PolyCurve
- ON_LineCurve
- ON_ArcCurve

**Purpose:**
Represents multi-segment or hybrid curves.

---

# 4. Surface System (2D Parametric Geometry)
Surfaces defined in (u, v) parameter space.

- ON_Surface ⭐ (base class)
- ON_PlaneSurface
- ON_Sphere
- ON_Cylinder
- ON_Cone
- ON_Torus
- ON_BezierSurface
- ON_NurbsSurface

**Purpose:**
Used for smooth modeling of surfaces in CAD.

---

# 5. 📍 BREP System (Boundary Representation - Solid Modeling)
Core structure for solid CAD modeling.

## Core BREP Components
- ON_Brep 📍⭐ (main solid object)
- ON_BrepFace
- ON_BrepEdge 📍
- ON_BrepVertex
- ON_BrepLoop
- ON_BrepTrim

**Purpose:**
Defines solids using faces, edges, and vertices.

---

# 6. Mesh System (Discrete Geometry)
Used for rendering and simulation.

- ON_Mesh ⭐
- ON_MeshFace
- ON_MeshVertex
- ON_MeshTopology

**Purpose:**
GPU rendering, physics simulation, collision detection.

---

# 7. SubD (Subdivision Surface Modeling)
Modern smooth modeling system.

- ON_SubD ⭐
- ON_SubDVertex
- ON_SubDEdge
- ON_SubDFace

**Purpose:**
Used in high-quality organic modeling (cars, characters).

---

# 8. Transformation System
Handles spatial transformations.

- ON_Xform
- ON_Plane
- ON_Quaternion
- ON_SpaceMorph

**Purpose:**
Rotation, translation, scaling, and deformation.

---

# 9. Scene / Model Organization System
Manages CAD scene structure.

- ON_ModelComponent
- ON_Layer
- ON_Group
- ON_InstanceDefinition
- ON_InstanceRef

**Purpose:**
Organizes objects into layers, groups, and reusable instances.

---

# 10. Rendering System
Controls appearance and visual output.

- ON_Material
- ON_Texture
- ON_Light
- ON_RenderMeshInfo

**Purpose:**
Defines shading, lighting, and textures.

---

# 11. Annotation / Drafting System
Used in technical drawings.

- ON_Text 📍
- ON_Dimension
- ON_Leader
- ON_Annotation

**Purpose:**
Adds engineering annotations and labels.

---

# 12. File I/O System (Serialization)
Handles file saving/loading (.3dm format).

- ON_BinaryArchive
- ON_BinaryFile
- ON_Read3dmBufferArchive
- ON_Write3dmBufferArchive

**Purpose:**
Serialization of full CAD models.

---

# 13. Geometry Analysis System
Used for measurement and computation.

- ON_MassProperties
- ON_SurfaceCurvature
- ON_MeshCurvatureStats
- ON_Intersection tools

**Purpose:**
Computes area, volume, curvature, and intersections.

---

# 14. Core Utilities / System Tools
Low-level infrastructure tools.

- ON_String / ON_wString 📍
- ON_UUID 📍
- ON_ErrorLog
- ON_StopWatch

**Purpose:**
Debugging, logging, identifiers, and string handling.

---

# Overall Architecture Summary

The OpenNURBS system can be understood as:

```
ON_Object
   ↓
ON_Geometry
   ↓
 ├── Curve (1D)
 ├── Surface (2D)
 ├── Mesh (discrete)
 ├── SubD (modern smooth)
 └── Brep (solid modeling)
```

And extended by:

```
Model / Material / Annotation / IO / Transform systems
```

---

# Key Insight
OpenNURBS is essentially a full CAD geometry kernel that supports:

- Precise mathematical modeling (NURBS)
- Solid modeling (Brep)
- Discrete meshes (rendering)
- Modern subdivision surfaces (SubD)
- Full scene and file management (Rhino 3DM)

---

# End of Document