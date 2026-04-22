# Rhino SDK – RhinoGet Module (README)

⭐ base class for all
📍 what I used for my plugin

## Core Idea

The **RhinoGet system** is all about **interactive user input** inside Rhino:
- picking points
- drawing geometry
- entering numbers / strings
- selecting objects

 Think of it as:
> “Everything the user *clicks, types, or draws* in a command”

---

## 1. Argument Classes (`CArgsRhinoGet*`) ⭐ 📍

### Purposes
These classes **configure how input is collected**.
They control:
- prompts
- options
- constraints
- modes (center-radius, 3-point, etc.)

### Basic Geometry Input
- CArgsRhinoGetLine
- CArgsRhinoGetCircle
- CArgsRhinoGetArc
- CArgsRhinoGetEllipse
- CArgsRhinoGetPlane

### Solid / Surface Input
- CArgsRhinoGetBox 
- CArgsRhinoGetBrep ⭐ 📍 
- CArgsRhinoGetCylinder
- CArgsRhinoGetCone
- CArgsRhinoGetSphere
- CArgsRhinoGetTorus
- CArgsRhinoGetTube

### Curve Input
- CArgsRhinoGetCurve
- CArgsRhinoGetPolyline
- CArgsRhinoGetSpiral
- CArgsRhinoGetParabola

### Advanced / Special Input
- CArgsRhinoGetSubCurve
- CArgsRhinoRailRevolve
- CArgsRhinoRevolve
- CArgsRhinoAnnotationLeader

---

## 2. Core Getter Classes (`CRhinoGet*`)

### Purpose
Low-level interactive tools for full control.

### Basic Input
- CRhinoGetPoint
- CRhinoGetLine
- CRhinoGetString
- CRhinoGetNumber
- CRhinoGetInteger

### Measurement Input
- CRhinoGetDistance
- CRhinoGetAngle
- CRhinoGetDirection

### Object Selection
- CRhinoGetObject ⭐ 📍
- CRhinoGetMeshes
- CRhinoGetSubCurvePoint

### UI / Options
- CRhinoGetOption ⭐ 📍
- CRhinoGetColor
- CRhinoGetView
- CRhinoGetFileDialog

---

## 3. High-Level Utility Functions (`RhinoGet*`)

### Purpose
Ready-to-use helpers.

### Simple Input
- RhinoGetPoint
- RhinoGetNumber
- RhinoGetInteger
- RhinoGetString
- RhinoGetColor

###  Curves
- RhinoGetLine
- RhinoGetPolyline
- RhinoGetInterpolatedCurve
- RhinoGetControlPointCurve

### Circles
- RhinoGetCircle
- RhinoGetCircle2Point
- RhinoGetCircle3Point
- RhinoGetCircleCenterRadius
- RhinoGetCircleFitPoints
- RhinoGetCircleTTT

### Ellipses
- RhinoGetEllipse
- RhinoGetEllipseCenter
- RhinoGetEllipseCorner
- RhinoGetEllipseFromFoci

### Solids
- RhinoGetBox
- RhinoGetCylinder
- RhinoGetCone
- RhinoGetSphere
- RhinoGetTorus
- RhinoGetTube

### Advanced Shapes
- RhinoGetSpiral
- RhinoGetHelix
- RhinoGetParabola
- RhinoGetParaboloid

### Plane & Transform
- RhinoGetPlane
- RhinoGetRectangle
- RhinoGet2dRectangle

### Selection
- RhinoGetSubCurve
- GetSubCurveRange
- RhinoChooseOneObject

---

## 4. Geometry Calculation Utilities

### Circle Math
- RhinoCalculateCircleTanTan
- RhinoCalculateCircleTanTanTan

### Spiral / Helix
- RhinoCreateSpiral

### Plane / Surface
- RhinoPlaneThroughBox
- RhinoCutPlane

### Revolve
- RhinoRevolve
- RhinoRailRevolve

---

## 5. File & Path Utilities

- RhinoGetFileReaderIdFromFileName
- RhinoGetFileWriterIdFromFileName
- RhinoPathFindFileExtension
- RhinoIs3dmBackupFileName

---

## 6. Misc Utilities

- GetAnnotationLeader
- RhinoGetInterpolatedCurveOnSurface
- RhinoGetRailRevolveInput

---

# End of Document
