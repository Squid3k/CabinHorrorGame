# Modular Cabin Builder System

## Overview
This system lets you build and modify your cabin layout easily using snap-to-grid modular pieces.

## Setup Instructions

### Step 1: Create the Base Builder Blueprint
1. In Content Browser: Right-click → Blueprint Class → Actor
2. Name it: `BP_CabinBuilder`
3. Open it and add these components:
   - Scene Component (root)
   - Box Component (for grid visualization)

### Step 2: Create Wall Module Blueprints
Create these separate blueprints (all inherit from Actor):

1. **BP_Wall_Solid** - Basic wall piece
2. **BP_Wall_Window** - Wall with window opening  
3. **BP_Wall_Door** - Wall with door opening
4. **BP_Wall_Corner** - L-shaped corner piece
5. **BP_Floor_Tile** - Floor section
6. **BP_Ceiling_Tile** - Ceiling section

### Step 3: Variables for BP_CabinBuilder

Add these variables:
```
GridSize: Float = 200.0 (2 meter grid)
CabinWidth: Integer = 5 (grid units)
CabinLength: Integer = 4 (grid units)
WallHeight: Float = 300.0
WallThickness: Float = 20.0

Arrays:
WallModules: Array of Actor Class References
FloorModules: Array of Actor References  
SpawnedWalls: Array of Actor References
```

### Step 4: Construction Script Code

This code will generate your cabin based on a simple data table.

### Step 5: Data-Driven Layout
Create a DataTable with room layouts you can swap between:
- Layout_Standard
- Layout_Large
- Layout_Narrow
- Layout_TwoStory

## Quick Modification Guide

### To Change Cabin Size:
1. Select BP_CabinBuilder in level
2. Change CabinWidth/CabinLength in details
3. Hit Compile - cabin rebuilds instantly

### To Change Wall Types:
1. Select any spawned wall module
2. In details panel: "Module Type" dropdown
3. Switch between Solid/Window/Door
4. Wall updates immediately

### To Add Furniture Snap Points:
1. Open any wall blueprint
2. Add Arrow Components where furniture should attach
3. Name them "SnapPoint_Bed", "SnapPoint_Table", etc.

### To Test Different Layouts:
1. Create presets in the DataTable
2. In BP_CabinBuilder: Change "Active Layout"  
3. Cabin rebuilds with new configuration

## Benefits of This System:
- Change layouts in seconds
- Test window/door placements instantly
- Rooms can resize without rebuilding
- Save multiple layout versions
- Easy to add basement/attic later
- Furniture snaps to predefined points
- Works with any art style (just swap meshes)
