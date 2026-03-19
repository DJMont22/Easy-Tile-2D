# Easy-Tile-2D 
A Simple asset maker working off a grid from a loaded png .
( Open Source Free ) Beta v1
User friendly super easy tile art maker / collision adder for pygame ( can export png for other games, Ui design and much more...)

***right now you can only use one loaded png per project so if you want to edit/add from a different tile sheet export png then load up a new project with the new png you wish to utilize.(Update for this in the next beta , just wanted to get it out there.)
**
================================================================


I am still fairly new to coding this is my 2nd official project :) 



This tool was made so I can simply have one tool to edit and create tile maps quickly.

User Friendly design to make it so anyone could make maps/uis from tile sets...

i made this program so it would export png as well as the python code to make and link assets up to easier in python.

also an easy way to generate png for new marketable assets.

Please leave comments for any recommendations or simply how you hate or love the program...



Keep on the look out for new updates here Official Easy Tile 2d Page

====================================================================


Tips & How to use:

Example meanings:

Collision Seclection Explained:

- solid

blocks from all sides

- top_only_platform
player lands on top only

- invisible_wall
blocks movement but may have no visible gameplay art purpose

- prop_blocker
blocks player like a solid prop/object

- trigger
used for overlap events, usually not full blocking collision

______

Layer Selection Explained:

- Background layer for scenery

- Art layer for visible gameplay tiles

- Platform layer for standable surfaces

- Collision layer for invisible blockers or trigger zones

- Prop layer for set dressing or blockers



-----

==================================================

GOOD SETUP RULE

==================================================

One behavior = one layer

If tiles need different gameplay behavior:

MAKE A NEW LAYER

=================

Easy Tile 2D - How To Use

==================================

1. Getting started

------------------

1. Launch the program.

2. Click "Load PNG Tilesheet".

3. Choose your tilesheet image.

4. In the Tilesheet Inspector, drag over one tile.

5. Click:

   - "Use Selection W/H" to set tile width and height.

   - "Use Selection X/Y as Margin" if the first tile starts after blank padding.

6. Enter spacing if your sheet has gaps between tiles.

7. Click "Slice Tilesheet".

2. Palette

----------

- After slicing, every tile appears in the Palette panel.

- Click any tile to make it the current paint tile.

- The status bar shows the tile ID and its source position from the tilesheet.

3. Map setup

------------

- Set Columns and Rows for the map grid.

- Set Zoom % for the map canvas.

- Click "Create / Resize Map" to apply the size.

- Use "Clear Map" to wipe all layers.

4. Tools

--------

Paint

- Left click and drag to place the selected tile.

- Right click while in Paint to erase.

Delete

- Left click and drag to erase tiles.

Select

- Drag to create a selection rectangle.

- You can also hold Ctrl and drag for selection while in other workflows.

Move

- Select an area first.

- Switch to Move.

- Drag the selection to a new location.

Copy / Cut / Paste

- Select an area.

- Click Copy or Cut.

- Click Paste, then click on the map to place the copied block.

5. Layers

---------

- Click Add Layer to create a new layer.

- Click Remove Layer to delete the active layer.

- Use Move Up / Move Down to reorder layers.

- Click a layer row to make it the active edit layer.

- Use the checkbox beside a layer to show or hide it.

- Multiple checked layers can stay visible together.

- The active layer gets the strongest highlight.

- Other visible checked layers remain visible and lightly highlighted.

6. Layer right-click options

----------------------------

Right click a layer to assign:

- Layer Type:

  - art

  - background

  - decoration

  - platform

  - prop

  - collision

- Collision Type:

  - none

  - solid

  - top_only_platform

  - invisible_wall

  - prop_blocker

  - trigger

Important behavior

------------------

Collision is stored at the layer level.

That means any painted tile on that layer inherits that layer's collision meaning in the export.

Suggested workflow

------------------

- Background layer for scenery

- Art layer for visible gameplay tiles

- Platform layer for standable surfaces

- Collision layer for invisible blockers or trigger zones

- Prop layer for set dressing or blockers

7. Grid viewing behavior

------------------------

- Checked layers can be viewed together.

- Clicking a layer makes it the active layer for editing.

- Only actually placed tiles are highlighted.

- Empty layers do not highlight random cells.

8. Export options

-----------------

Click Export to open the export popup.

From there you can:

- Copy Code

- Save Python File

- Export PNG

9. What the Python export contains

----------------------------------

The exported Python file includes:

- TILESET_PATH pointing to your linked tilesheet

- TILESET_DIR for convenience

- tile dimensions, margins, and spacing

- TILE_CATALOG with source cut positions for each tile ID

- LAYERS_DATA with:

  - name

  - visible

  - layer_type

  - collision

  - data grid

- helper functions:

  - slice_tileset()

  - tile_id_to_source()

  - build_map_pixmap()

  - draw_map()

  - get_collision_tiles()

  - get_collision_rects()



These are building blocks. They tell your game:


- where the tilesheet is

- what tile id points to what tilesheet position

- what layers exist

- what collision type each layer uses

- how to build the map visually

- how to get collision rectangles for gameplay




10. Keyboard shortcuts

----------------------

- Ctrl+C = Copy selection

- Ctrl+V = Paste mode

- Delete = Delete selection

- D = Delete selection

- Ctrl + Mouse Wheel on the map = zoom map

- Ctrl + Mouse Wheel on the tilesheet inspector = zoom inspector

- Middle Mouse Drag on the map = pan view


​====
Test game mode:
when you export code it will auto spit out the collision and positions , you can test with a simple tester from the button to see your collisions highlighted and check if code is working 
=====




==================================================

WHAT THE EXPORTED FILE IS NOT

==================================================

By itself, the export is NOT:

- a full pygame game

- a full player movement system

- a camera system

- a physics engine

- an enemy system

- a menu system

It is the map and map helpers only and a gui / menu maker.





EXAMPLES: (videos will come soon if wanted)

==================================================

EXAMPLE 1 - NORMAL VISIBLE FLOOR / WALL SETUP

==================================================

Right-click Layer: Set Layer Type -> platform

Set Collision -> solid

Meaning:

- This layer is gameplay terrain

- Every painted tile on this layer is fully solid

- Player cannot pass through it

- Good for floors, walls, ledges, blocks

Example layer: Layer name: Ground Layer type: platform Collision: solid

Use this layer for:

- dirt floor

- stone floor

- cave walls

- solid blocks

- buildings player stands on

Result in game:

- tiles draw normally

- collision boxes are created

- player can stand on top

- player is blocked from left/right/below too

==================================================

EXAMPLE 2 - JUMP-THROUGH PLATFORM SETUP

==================================================

Right-click Layer: Set Layer Type -> platform

Set Collision -> top_only_platform

Meaning:

- This layer is still a platform layer

- But every painted tile only collides from the TOP

- Player can jump up through it

- Player lands on it from above

Example layer: Layer name: One Way Platforms Layer type: platform Collision: top_only_platform

Use this layer for:

- floating wooden platforms

- cloud platforms

- thin ledges

- bridge tops you jump onto

Result in game:

- tiles draw normally

- collision boxes are created

- player lands when falling from above

- player passes upward through the tile

==================================================

EXAMPLE 3 - PROP OBJECT THAT BLOCKS MOVEMENT

==================================================

Right-click Layer: Set Layer Type -> prop

Set Collision -> prop_blocker

Meaning:

- This layer is for objects

- Every painted tile on this layer blocks the player

- Best used for obstacle objects instead of terrain

Example layer: Layer name: Crates Layer type: prop Collision: prop_blocker

Use this layer for:

- crates

- barrels

- tables

- machines

- rocks

- furniture

Result in game:

- tiles draw normally

- collision boxes are created

- player cannot walk through object

- helps separate prop collision from terrain collision

==================================================

EXAMPLE 4 - INVISIBLE BOUNDARY WALL

==================================================

Right-click Layer: Set Layer Type -> collision

Set Collision -> invisible_wall

Meaning:

- This layer is for logic/blocking only

- It may have no visible art purpose

- Every painted tile blocks player movement

- Good for map limits and hidden blockers

Example layer: Layer name: Map Bounds Layer type: collision Collision: invisible_wall

Use this layer for:

- screen boundaries

- hidden blockers

- stop player leaving map

- invisible rails

Result in game:

- may or may not have visible art depending on your design

- collision boxes are created

- player is blocked

- best for invisible gameplay walls

==================================================

EXAMPLE 5 - TRIGGER ZONE

==================================================

Right-click Layer: Set Layer Type -> collision

Set Collision -> trigger

Meaning:

- This layer is for events

- Every painted tile on this layer becomes a trigger zone

- Usually does NOT block movement

- Used for scripted events

Example layer: Layer name: Level Exit Trigger Layer type: collision Collision: trigger

Use this layer for:

- checkpoint area

- cutscene start

- level exit

- damage zone

- item pickup zone

- message popup zone

Result in game:

- trigger rectangles are created

- player overlap can run code

- usually does not physically block player

==================================================

EXAMPLE 6 - PURE VISUAL BACKGROUND

==================================================

Right-click Layer: Set Layer Type -> background

Set Collision -> none

Meaning:

- This layer is visual only

- It draws art

- It does not affect gameplay collision

Example layer: Layer name: Sky Background Layer type: background Collision: none

Use this layer for:

- sky

- clouds

- distant mountains

- cave back wall

- decorative backdrop

Result in game:

- tiles draw normally

- no collision is created

==================================================

EXAMPLE 7 - DECORATION ONLY

==================================================

Right-click Layer: Set Layer Type -> decoration

Set Collision -> none

Meaning:

- This layer is for details only

- It should not block movement

Example layer: Layer name: Wall Decor Layer type: decoration Collision: none

Use this layer for:

- vines

- signs

- cracks

- trim

- torches

- small wall details

Result in game:

- tiles draw normally

- no collision is created



Thank you !
