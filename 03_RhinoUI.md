# Rhino UI SDK – Structured Guide

## Overview
This document organizes the Rhino UI SDK into logical groups and explains what each part is used for. It is designed as a **learning + reference guide**.

⭐ base class for all
📍 what I used for my plugin

---

## 1. Core UI Managers

These classes control the overall UI system.

### Key Classes
- CRhinoUiManager → Central access point for UI system
- CRhinoUiDockBarManager → Manages dockbars (panels that can dock)
- CRhinoUiPageDockBarManager → Handles page-based dockbars
- CRhinoUiPaintManager → Handles drawing and theming
- CRhinoUiResourceManager → Loads UI resources (icons, dialogs)

### When to use
Use these when:
- Creating plugins with UI
- Managing panels/dockbars globally

---

## 2. Dockbars & Panels (VERY IMPORTANT)

This is the core of Rhino UI customization.

### Dockbar Classes
- CRhinoUiDockBar
- CRhinoUiDockBarTab
- CRhinoUiDockBarClientWnd

### Panel Classes
- CRhinoUiPanel
- CRhinoUiPanelFactory

### Key Idea
- Dockbar = container
- Panel = your custom UI

### Typical Workflow
1. Create a panel class
2. Register it using CRhinoUiPanelFactory
3. Open it using RhinoUiOpenDockbarTab()

---

## 3. Dialog System

Used for popups and windows.

### Classes
- CRhinoUiDialog → Base dialog
- CRhinoUiDialogSub → Sub-dialog
- CRhinoUiDirDialog → Folder picker
- CRhinoUiDockBarDialog → Dialog inside dockbar

### Use Cases
- Settings window
- File selection
- Tool dialogs

---

## 4. UI Controls

### Basic Controls
- CRhinoUiButton
- CRhinoUiCheckBox
- CRhinoUiEdit
- CRhinoUiStatic
- CRhinoUiSliderCtrl

### Advanced Controls
- CRhinoUiComboBox
- CRhinoUiColorComboBox
- CRhinoUiLayerComboBox

### Grid / List Controls
- CRhinoUiGridListCtrl
- CRhinoUiGridListEdit
- CRhinoUiListBoxEx

### Tab Controls
- CRhinoUiTabCtrl
- CRhinoUiTabbedSheetCtrl
- CRhinoUiExpandableTabCtrl

### Use Cases
Build UI layouts similar to:
- Forms
- Property panels
- Editors

---

## 5. Graphics & Drawing

### Classes
- CRhinoDib → Bitmap handling
- CRhinoUiImageList → Image collections
- CRhinoUiMemDC → Offscreen drawing

### Use Cases
- Custom rendering
- Icons
- UI previews

---

## 6. Profile & Registry System

Used for saving settings.

### Classes
- CRhinoProfileContext
- CRhinoIniProfileContext
- CRhinoRegProfileContext

### Use Cases
- Save user preferences
- Store plugin configuration

---

## 7. Utility Classes

- CRhinoUiProgressBar → Progress UI
- CRhinoUiToolTip → Tooltips
- CRhinoUiHyperlink → Clickable links
- CRhinoUiFile → File helpers

---

## Structs (Data Containers)

These hold UI-related data.

- RhinoUiColorComboBoxItemData
- RhinoUiFontComboBoxItemData
- RhinoUiLayerComboBoxItemData
- RhinoUiPrintWidthComboBoxItemData

---

## Macros

Macros provide shortcuts and compatibility.

### Examples
- CRmaUiDialog → Alias for CRhinoUiDialog
- DIBWidth → Bitmap width helper
- RHINO_UI_COUNT_OF → Array size helper

---

## Functions (Important APIs)

### Dockbars & Panels
- RhinoUiOpenDockbarTab()
- RhinoUiCloseDockbarTab()
- RhinoUiShowDockbarTab()

### Layout Management
- RhinoImportWindowLayout()
- RhinoRestoreWindowLayout()
- RhinoDeleteWindowLayout()

### General UI
- RhinoUiManager()
- RhinoUiPaintManager()
- RhGetDialogBackgroundColor()

---

## GUIDs

Used to uniquely identify panels and dockbars.

### Examples
- RHINO_COMMAND_DOCK_BAR_ID
- RHINO_LAYER_DOCK_BAR_ID
- RHINO_PROPERTIES_DOCK_BAR_ID

### Important Concept
Every panel you create needs a UNIQUE GUID.

---

## Built-in Panel IDs

These represent default Rhino panels.

- uuidPanelLayers
- uuidPanelMaterials
- uuidPanelRenderSettings
- uuidPanelObjectProps
- uuidPanelTextures

---

# Final Notes

## Key Takeaways
- Dockbars + Panels = MOST IMPORTANT
- UI is based on MFC
- Use PanelFactory to register UI
- Use GUIDs to identify panels

## Learning Order (Recommended)
1. Panels & Dockbars
2. Dialogs
3. Controls
4. Managers
5. Advanced (graphics, registry)

---

# END OF FILE
