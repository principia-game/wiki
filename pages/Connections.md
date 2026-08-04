A core part of the game's sandbox is connecting objects together. Most objects have sides which can be connected to other objects, to create groups of objects that stick together. When putting two objects together on sides that can be connected, a flashing hammer icon will appear. On desktop platforms a keybind will also be visible for making the connection.

{{ image({
	"url": "images/connections/single-layer-connection.webp",
	"alt": "Two thick planks placed next to eachother with a hammer icon visible between the two."
}) }}

For single-layer connections, the only connection type is a static connection which will be the automatic choice when pressing the hammer icon. However if you try to connect objects across layers you have the ability to pick between a static connection (Left) or a pivot connection allowing angular movement between the two objects (Right).

{{ image({
	"url": "images/connections/multi-layer-connection.webp",
	"alt": "Two thick planks placed next to eachother on separate layers. The static and pivot connection icons are visible where they meet."
}) }}

Some objects, such as motors, will only allow a pivot connection. Typically this is what you want when building vehicles or other contraptions with free axis rotation.

Connections can not be made between objects in layer 1 and layer 3. You may use the [[Sublayer plank]] to create connections that allow other objects to pass through such as for rotating pipelines.

## Connection visibility
By default when making connections in the sandbox, they will use a fully visible connector to show them being nailed together. You can change this to a less visible connection by enabling the "Hide beam connections" level property, but this will only apply for any new connections that will be made.

To edit the render type of existing objects you can use the Multiselect mode to select a contraption and open the configuration dialog to change the render type between Default, Small and Hide.

{{ image({
	"url": "images/connections/connection-types.webp",
	"alt": "Three pairs of small thick planks demonstrating each connection render type (Default, Small and Hide)",
	"caption": "Top to bottom: Default, Small and Hide"
}) }}

## Connection strength
By default all connections will be made stiff and indestructible, being able to withstand infinite force without breaking. This is different from Apparatus, where all connections are slightly softer and have the ability of being broken.

You can use the Connection Edit mode to change this for individual connections, allowing them to be broken with a varying amount of force. When the connection strength is set to anything other than the max (Indestructible), the connection will be slightly softer allowing it to bend slightly before breaking if enough force is put on the connection.

{{ image({
	"url": "images/connections/connection-edit.webp",
	"alt": "A pivot connection is selected and the connection strength slider is visible in the bottom left."
}) }}

To apply this in bulk, you can use Multiselect mode which can apply a specific strength value for all connections in the selection.

In addition to breaking by force, non-destructible connections can also be broken on demand by using the [[FX Emitter]] with the "Destroy connections" effect. When the FX Emitter is active, this will destroy any connections connected to the emitter object, subject to the Radius and Count values. This allows you to trigger the destruction of something, for example to unlock a new area in an adventure level.
