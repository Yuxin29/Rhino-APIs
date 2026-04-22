# Rhino API Framework Overview
This is a repo trying to give a roadmap of the vast Rhino APIs

## 1. High-Level Architecture

```text
OpenNURBS (Geometry Kernel)
        ↓
Rhino Core (Document + Object System)
        ↓
RhinoGet (User Input System)
        ↓
Rhino UI (Display + Interaction)
        ↓
RDK (Rendering & Materials)
```

---

## 2. Layer Breakdown

### 2.1 OpenNURBS (ON_)

**Purpose:**
- Core geometry and math library
- File format (.3dm) handling

**Key Base Classes:**
- ON_Object
- ON_Geometry

**Derived Geometry Classes:**
- ON_Curve
- ON_Surface
- ON_Brep
- ON_Mesh

**Math Types:**
- ON_3dPoint
- ON_3dVector
- ON_Plane
- ON_Transform

**Characteristics:**
- No UI
- No document context
- Pure geometry

---

### 2.2 Rhino Core

**Purpose:**
- Manages document and scene
- Wraps geometry into usable objects

**Key Classes:**
- CRhinoDoc
- CRhinoObject

**Object Types:**
- CRhinoCurveObject
- CRhinoBrepObject
- CRhinoMeshObject
- CRhinoPointObject

**Supporting Systems:**
- Layers
- ObjectAttributes
- Selection
- Undo/Redo

**Relationship:**

```text
ON_Geometry → wrapped into → CRhinoObject
```

---

### 2.3 RhinoGet

**Purpose:**
- Handles user input and command interaction

**Base Class:**
- CRhinoGet

**Derived Classes:**
- CRhinoGetPoint
- CRhinoGetObject
- CRhinoGetCurve
- CRhinoGetNumber
- CRhinoGetString

**Responsibilities:**
- Mouse picking
- Object selection
- Command-line input
- Validation

---

### 2.4 Rhino UI

**Purpose:**
- Visualization and interface layer

**Components:**
- Viewport
- Display Pipeline
- Dialogs (Eto)

**Responsibilities:**
- Rendering geometry
- Handling user interaction visuals

---

### 2.5 RDK (Rendering Development Kit)

**Purpose:**
- Advanced rendering and material system

**Features:**
- Materials
- Lighting
- Environment
- Render plugins

---

## 3. Class Grouping (By Responsibility)

### Geometry Group
- ON_Object
- ON_Geometry
- ON_Curve / Surface / Brep / Mesh

### Document & Object Group
- CRhinoDoc
- CRhinoObject
- CRhinoAttributes

### Interaction Group
- CRhinoGet
- CRhinoCommand

### Display Group
- CRhinoView
- DisplayPipeline

### Rendering Group
- RDK classes (materials, environments)

---

## 4. Command Workflow (Execution Roadmap)

```text
User runs command
    ↓
CRhinoCommand::RunCommand()
    ↓
Use RhinoGet to collect input
    ↓
Process geometry (OpenNURBS)
    ↓
Add result to CRhinoDoc
    ↓
UI updates viewport
    ↓
(Optional) RDK applies materials/rendering
```

---

## 5. Data Flow

```text
User Input (RhinoGet)
        ↓
Rhino Command
        ↓
Geometry Creation (OpenNURBS)
        ↓
Wrap into CRhinoObject
        ↓
Store in CRhinoDoc
        ↓
Display via UI
        ↓
Render via RDK
```

---

## 6. Key Design Principles

- Separation of geometry and application logic
- Layered architecture
- Object wrapping (geometry → document object)
- Event-driven input system
- Extensible rendering system

---

## 7. Developer Roadmap

### Beginner
- Understand ON_Geometry
- Learn CRhinoObject and CRhinoDoc

### Intermediate
- Use RhinoGet for input
- Implement CRhinoCommand

### Advanced
- Custom display pipelines
- RDK integration
- Plugin architecture

---

## 8. Summary

The Rhino API is built as a layered system:
- OpenNURBS provides geometry
- Rhino Core manages objects and documents
- RhinoGet handles input
- UI displays results
- RDK handles rendering

This separation allows flexibility, performance, and extensibility for plugin developers.

---

# End of Document