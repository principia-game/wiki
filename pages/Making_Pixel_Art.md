Principia features the [[Pixel]] object, which is a static box which you can change the colour of. It has many uses, one of which is the creation of so-called [pixel art](https://en.wikipedia.org/wiki/Pixel_art) within Principia. The process of creating pixel art in Principia can be likened to the process of piecing together pixel art using [fuse beads](https://en.wikipedia.org/wiki/Fuse_beads) and is generally a very satisfying experience.

There are plenty of examples of pixel art other players have created and uploaded to the community site, and [a search](https://archive.principia-web.se/search?query=%22pixel%20art%22&page=1&boolean=1) will turn up a lot of varyingly elaborate pixel art.

This wiki tutorial focuses mainly on the construction of pixel art from a fixed square grid, though more elaborate pixel art may want to use subpixel precision for more detail.

## Pixel sizes
The pixel object has four different sizes. For future reference, we will call them size 1 through size 4.

{{ image({
	"url": "images/making_pixel_art/pixel_sizes.webp",
	"alt": "Four sizes of pixels coloured red, each doubles itself in length"
}) }}

The default two-sized pixels are usually the most common for pixel art, but you could just as well use the one-sized pixels or a combination of pixel sizes for the pixel art.

## Positioning of pixels
By default moving pixels aligns them to a grid one tiny pixel in size. It will also never make two pixels overlap each other. Holding down Shift will change the positioning mode to one with more precision and allow you to place pixels such that they overlap each other.

When Orthographic mode (the sandbox grid) is enabled, this behaviour is reversed.

## Finding or making a reference
It's very useful to have a reference image that you have open to the side while making pixel art in Principia. If you're making pixel art from pre-existing things then there are likely plenty of templates with a visible grid already available on the Internet, or fuse bead patterns other people have made of it. Sites like [The Spriters Resource](https://www.spriters-resource.com/) contain a lot of extracted spritesheets which you can also base a template on.

To create a grid from a plain 1:1 pixel art image so you can see each individual pixel, you can for example open up the image in [GIMP](https://www.gimp.org/) and enable the grid with *View -> Show Grid*.

{{ image({
	"url": "images/making_pixel_art/gimp_pixel_grid.webp",
	"alt": "An image opened in GIMP and the grid being enabled. There is a grid showing each individual pixel in the image."
}) }}

You can also customise the grid cell size and colour in GIMP with *Image -> Configure Grid*, for example if each pixel unit is larger than one pixel in the actual image.

## Creating a palette
It is useful to have a palette of pixel colours that you can copy from when drawing the pixel art. The more colours the art will have, the larger the palette will be. Place out as many pixels as there will be colours in the palette and set them to the colour you want them to have.

{{ image({
	"url": "images/making_pixel_art/palette.webp",
	"alt": "Four pixels of different colours, representing a palette"
}) }}

If you have an existing pixel art image that you want to create a palette from, or to reduce the amount of colours needed, you can open it in GIMP and select *Image -> Mode -> Indexed*. The dialog will allow you to select the maximum amount of colours it will put in the palette, and optionally dither the image if the colour depth is reduced. The resulting palette can be found in the "Palette" panel.

## Drawing the pixel art
Using the palette you have created, you can then begin to "paint" the pixel art by selecting a pixel for the colour and then pressing the Comma (`,`) key on your keyboard, pointing your mouse at where it should paint. 

Generally it is a good idea to start with the outline, as it gives you a guideline for filling out the details within.

{{ image({
	"url": "images/making_pixel_art/outline.webp",
	"alt": "An outline of a sprite being painted",
	"max_width": 500
}) }}

When placing new pixels using the clone keybind, they will be aligned to the regular pixel grid and will also be placed such that they don't overlap with another pixel. This means holding your cursor still will keep placing pixels around it, creating a fill-like effect.

{{ image({
	"url": "images/making_pixel_art/copying_pixels.webp",
	"alt": "Animated image showing pixels being placed around the center where the cursor is."
}) }}

## Upload the level
The fun part! When you're finished, you can upload your finished creation to the community site. Be sure to add a [[Cam Marker]] that showcases it in its entirety for the level screenshot.
