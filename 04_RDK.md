# Rhino C++ API – RDK (Render Development Kit) Overview

⭐ base class for all
📍 what I used for my plugin

## What is RDK?

The **RDK (Render Development Kit)** in Rhino C++ API provides a full framework for:
* Materials
* Textures
* Environments
* Rendering pipelines
* Post-processing effects
* Custom render plugins
It is the backbone of Rhino’s rendering system and allows developers to extend or replace rendering behavior.

---

# Core Architecture

## 1. Content System (MOST IMPORTANT)

This is the heart of RDK. Everything visual is a **Content**.

### Base Classes
* `CRhRdkContent` → Base class for all render content
* `CRhRdkCoreContent` → Core implementation
* `CRhRdkContentArray`, `CRhRdkEditableContentArray` → Containers

### Types of Content
* `CRhRdkMaterial` → Materials
* `CRhRdkTexture` → Textures
* `CRhRdkEnvironment` → Environments

### Factories & Creation
* `CRhRdkContentFactory`
* `CRhRdkMaterialFactory`
* `CRhRdkTextureFactory`
* `CRhRdkEnvironmentFactory`

### Content Creation Helpers
* `CRhRdkContentCreatorNew`
* `CRhRdkContentCreatorExisting`
* `CRhRdkContentCreatorLoad`

### Content Fields (Parameters)
* `CRhRdkContentField`
* `CRhRdkDynamicContentField`
* `CRhRdkFilenameContentField`
* `CRhRdkTexturedContentField`

👉 These define editable parameters like color, file paths, etc.

## 2. Materials, Textures, Environments

### Materials
* `CRhRdkBasicMaterial`
* `CRhRdkMaterialArray`
* `CRhRdkMaterialKindList`

### Textures
* `CRhRdkOneColorTextureBase`
* `CRhRdkTwoColorTextureBase`
* `CRhRdkTextureEvaluator`
* `CRhRdkTextureCache`

### Environments
* `CRhRdkEnvironment`
* `CRhRdkEnvironmentArray`
* `CRhRdkSimulatedEnvironment`

## 3. Rendering System

### Core Rendering Classes
* `CRhRdkRenderPlugIn` → Create custom render engines
* `CRhRdkSdkRender` → SDK-based rendering
* `CRhRdkRenderMesh` → Mesh used for rendering

### Render Window & UI
* `CRhRdkRenderWindowCustomDlg`
* `CRhRdkRenderWindowEventSink`

### Rendering Settings
* `CRhRdkRenderingSettings`
* `CRhRdkRenderingFileInfo`

## 4. Post Effects (Image Processing)
Applied after rendering.

### Core Classes
* `CRhRdkPostEffect`
* `CRhRdkToneMappingPostEffect`

### Factories & Plugins
* `CRhRdkPostEffectFactory`
* `CRhRdkPostEffectPlugIn`
* `CRhRdkPostEffectPlugInManager`

### Pipeline Interfaces
* `IRhRdkPostEffectPipeline`
* `IRhRdkPostEffectImage`

## 5. Plugin System

### Main Plugin Entry
* `CRhRdkPlugIn`

### Extension System
* `CRhRdkExtension`
* `IRhRdkCustomPlugIn`

### Content IO Plugins
* `CRhRdkContentIOPlugIn`
* `CRhRdkContentIOPlugInEx`

## 6. Interfaces (IRhRdk*)
These define extensibility points.

### Content Interfaces
* `IRhRdkContent`
* `IRhRdkContentUI`
* `IRhRdkContentEditor`

### Rendering Interfaces
* `IRhRdkRenderSession`
* `IRhRdkRenderWindow`

### Texture & Evaluation
* `IRhRdkTextureEvaluator`

### Post Effects
* `IRhRdkPostEffect`
* `IRhRdkPostEffectUI`

👉 Rule of thumb:

* `CRhRdk*` → Implementation
* `IRhRdk*` → Interface (you implement these)

## 7. Document & Scene Integration

* `CRhRdkDocument` → RDK data attached to Rhino document
* `CRhRdkObject` → Links RDK content to Rhino objects
* `CRhRdkObjectDataAccess` → Access object render data

## 8. Lighting & Sun System

* `CRhRdkSun`
* `CRhRdkSunDialog`
* `CRhRdkSunStorage`
* `CRhRdkSkylight`

## 9. Preview System

Used for thumbnails and previews.
* `CRhRdkPreviewGeometry`
* `CRhRdkPreviewLighting`
* `CRhRdkPreviewSceneElement`

Interfaces:
* `IRhRdkPreviewSceneServer`
* `IRhRdkPreviewCallbacks`

## 10. Events & Undo System

### Events
* `CRhRdkEventSink`
* `CRhRdkEventWatcher`

### Undo
* `CRhRdkContentUndo`
* `CRhRdkUndoableEvent`

## 11. Utility & Helpers

* `CRhRdkColor`
* `CRhRdkVariant`
* `CRhRdkUuid`
* `CRhRdkInstanceIdArray`

---

# How Everything Fits Together

## Typical Workflow:

1. Create a **Material**
   → `CRhRdkMaterial`

2. Attach **Textures**
   → `CRhRdkTexture`

3. Assign to Object
   → `CRhRdkObject`

4. Render using Plugin
   → `CRhRdkRenderPlugIn`

5. Apply Post Effects
   → `CRhRdkPostEffect`

---

# Key Takeaways

* **Content system is central** (materials, textures, environments)
* Everything is **factory-driven and extensible**
* Interfaces (`IRhRdk*`) define customization points
* RDK enables building **full custom render engines**

---

# End of Document