Multiselect (also known as multi-select) is a sandbox mode accessible from the "Change mode" menu in the top right corner of the sandbox, visible when advanced options are shown. The multiselect mode allows bulk selection and operation of objects in the sandbox.

## Selection
To select something, you can click on a group of objects. By default it will follow all connections of the object recursively, but there are different options to change the selection behaviour. From left-to-right the buttons are:

- Box select: Select based on a box selection rather than clicking on objects or groups of objects
- Additive selection (Shift on desktop): Whether to add to the current selection or replace it with a new selection when clicking on objects
- Follow connections: Whether to select objects that are connected to the selected objects via connections
- Follow cables: Whether to select objects that are connected to the selected objects via cables
- Select through layers: Whether to select objects that are connected to the selected objects via connections or cables that span across layers.

Once selected, you can move around the group of objects assuming it is not attached to any static object. Do note that you cannot select stationary objects like the [[Platform]] as part of a multi-selection.

## Export/Import
When something is selected you will have the option to export the selection to an object file, which can later be cloned or imported into another level. Once a descriptive name has been given to the object, it will be saved and can later imported.

Exported objects will retain all properties, including their relative positions and rotation. In addition to exporting larger contraptions, this feature can also be useful for exporting individual [[LuaScript]] or [[Digital Display]] objects allowing them to be reused in other levels.

When no object is selected, the leftmost button will allow you to import objects from a previously exported selection. Once an object is opened, a box will be made visible to show how large the object is. You can then place it down by double clicking. Do note that if there is not enough room for the object to be placed, it may be jumbled up with other objects.

Multi-select objects (also called "partials") are saved as `.pobj` files in the `levels/` folder in your [[User Data Directory]].

## Multi config
When selecting something, a cogwheel appears which allows you to perform certain bulk operations on the objects. Depending on what exists in the selection, the following tabs will be available:

- Joint strength: Change the joint strength of all selected objects to a given value
- Plastic color: Change the color of all plastic objects in the selection
- Plastic density: Change the density factor of all plastic objects in the selection
- Connections: Change the render type of connections
- Miscellaneous
	- Unlock all: Unlock all previously locked objects
	- Disconnect all: Remove all connections from the

## [[Multi-emitter]]
The Multi-emitter is a type of emitter object which can emit larger groups of objects at once. Once an object has been exported from the Multiselect mode, it can be selected in a Multi-emitter. The Multi-emitter will adjust its size to accommodate the size of the object.
