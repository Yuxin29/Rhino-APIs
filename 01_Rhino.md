# Rhino C++ API 8.30 — Classes Categorization Guide

This document organizes the Rhino C++ API 8.30 class list into functional groups for easier understanding. It preserves the original API structure while adding conceptual classification for learning and navigation.

---

# 1. Rhino Application Core & System Control
These classes manage the overall Rhino application lifecycle, configuration, and system behavior.

## Application Core
- CRhinoApp 📍 
- MRhinoApp
- CRhinoCoreAppActivity
- CRhinoCommandManager📍 
- CRhinoCommandContext📍 

**Purpose:**
Controls Rhino startup, runtime behavior, and command execution system.

## Settings & Configuration
- CRhinoAppSettings
- CRhinoAppGeneralSettings
- CRhinoAppViewSettings
- CRhinoAppMouseSettings
- CRhinoAppGridSettings
- CRhinoAppFileSettings

**Purpose:**
Stores global UI and system preferences.

---

# 🧩 2. Command System (User Interaction Engine)
Defines all executable commands in Rhino.

- CRhinoCommand ⭐ (base command class)
- CRhinoScriptCommand
- CRhinoTransformCommand
- CRhinoSelCommand
- CRhinoSelSubObjectCommand
- CRhinoTestCommand

**Purpose:**
Every Rhino command is implemented through this system.

## Command Utilities
- CRhinoCommandOption 📍 
- CRhinoCommandOptionValue 📍 
- CRhinoCommandOptionName 📍 

---

# 🧱 3. Document & Object Model (Scene Graph)
Manages all geometry and objects inside a Rhino file.

## Document
- CRhinoDoc ⭐📍 
- CRhinoDocIterator
- CRhinoDocProperties

## Objects
- CRhinoObject ⭐📍 (base class)
- CRhinoObjectAttributes
- CRhinoObjectIterator
- CRhinoProxyObject

**Purpose:**
Represents everything inside a .3dm file.

---

# 📐 4. Geometry Object Wrappers
These wrap OpenNURBS geometry into Rhino objects.

- CRhinoCurveObject
- CRhinoSurfaceObject
- CRhinoBrepObject 📍 
- CRhinoMeshObject
- CRhinoPointObject
- CRhinoExtrusionObject
- CRhinoInstanceObject

**Purpose:**
Connects Rhino UI objects with underlying ON_Geometry.

---

# 🧵 5. Curve & Surface Tools (Modeling Tools)
Interactive and analytical curve/surface tools.

- CRhinoCurveObject
- CRhinoLoftCurve
- CRhinoSurfaceFillet
- CRhinoFilletEdge
- CRhinoFitPatch

**Purpose:**
Modeling operations on curves and surfaces.

---

# 6. Brep / Solid Modeling Tools
- CRhinoBrepObject 📍 
- CRhinoEdgeContinuitySettings
- CRhinoKeepKinkySurfaces

**Purpose:**
Solid modeling operations and constraints.

---

# 7. Mesh System
- CRhinoMeshObject
- CRhinoMeshBooleanOptions
- CRhinoMeshDensity
- CRhinoMeshUnwrapper

**Purpose:**
Mesh editing, optimization, and analysis.

---

# 8. SubD System (Subdivision Modeling)
- CRhinoSubDObject
- CRhinoSubDDisplay
- CRhinoSubDPickSettings

**Purpose:**
Modern smooth subdivision modeling workflow.

---

# 9. Display & Rendering Pipeline
Handles viewport rendering and visualization.

## Display Pipeline
- CRhinoDisplayPipeline 📍 
- CRhinoDisplayPipeline_GDI
- CRhinoDisplayPipeline_OGL
- CRhinoDisplayEngine

## Attributes
- CRhinoDisplayAttributesMgr
- CRhinoDrawAttributes
- CRhinoDrawGripsSettings

**Purpose:**
Controls how geometry is drawn in viewports.

---

# 10. Viewport & UI System
- CRhinoView
- CRhinoViewport
- CRhinoViewIterator
- CRhinoModelViewIterator

**Purpose:**
Manages camera views and UI rendering.

---

# 11. Selection & Picking System
- CRhinoPickContext
- CRhinoPickFilter 📍 
- CRhinoObjRef 📍 
- CRhinoObjRefArray

**Purpose:**
Handles object selection and snapping.

---

# 12. Layers, Groups & Organization
- CRhinoLayer
- CRhinoLayerTable
- CRhinoGroup
- CRhinoGroupTable

**Purpose:**
Organizes scene hierarchy.

---

# 13. Materials, Lights & Rendering
- CRhinoMaterial
- CRhinoMaterialTable
- CRhinoLight
- CRhinoLightTable

**Purpose:**
Controls shading and lighting.

---

# 14. Annotation & Dimensions
- CRhinoAnnotation
- CRhinoDimension
- CRhinoDimStyle
- CRhinoLeader

**Purpose:**
Engineering drawings and documentation.

---

# 15. Analysis & Evaluation Tools
- CRhinoCurvatureGraphSettings
- CRhinoDirectionAnalysisSettings
- CRhinoEdgeAnalysisSettings
- CRhinoZebraAnalysisSettings

**Purpose:**
Surface quality analysis tools.

---

# 16. Transform & Space Morphing
- CRhinoSpaceMorph
- CRhinoBendSpaceMorph
- CRhinoTwistSpaceMorph
- CRhinoFlowSpaceMorph

**Purpose:**
Non-linear geometric deformation.

---

# 17. File I/O & Import/Export
- CRhinoFileImportPlugIn 📍
- CRhinoFileExportPlugIn 📍
- CRhinoFileUtilities
- CRhinoFileReadOptions

**Purpose:**
Handles file loading and saving.

---

# 18. Events & System Hooks
- CRhinoEventWatcher
- CRhinoUndoEventHandlerEx
- CRhinoOnTransformObject
- CRhinoOnChangeObjectSelectState

**Purpose:**
Responds to system and user events.

---

# 19. Interactive UI Components
- CRhinoDialog
- CRhinoPopupMenu
- CRhinoColorButton
- CRhinoLayerComboBox

**Purpose:**
User interface elements.

---

# 20. Plugins & Extensibility
- CRhinoPlugIn 📍
- CRhinoUtilityPlugIn
- CRhinoRenderPlugIn
- CRhinoFileExportPlugIn

**Purpose:**
Extends Rhino functionality.

---

# 21. Gumball & Manipulators
- CRhinoGumball
- CRhinoGumballDragger
- CRhinoGumballDisplayConduit

**Purpose:**
Interactive transform widgets.

---

# 22. Advanced Systems (Simulation / Analysis / Morphing)
- CRhinoMorphControl
- CRhinoEdgeSoftening
- CRhinoDisplacement
- CRhinoMeshEdgeSlider

**Purpose:**
Advanced modeling and simulation tools.

---

# 🚀 Summary

Rhino C++ API is structured into:

- Application Core (CRhinoApp)
- Document Model (CRhinoDoc)
- Geometry Wrappers (CRhinoBrepObject etc.)
- Display Pipeline (CRhinoDisplayPipeline)
- UI + Interaction System
- Plugins + Extensibility
- Analysis + Modeling Tools

---

# End of Document
