This builds on 7_fancyfont, to display a background image.

Open a suitable source image in GIMP. Adjust the resolution to 320x224, and set the image mode to indexed, 16 colours.

Define the image file in gfx.res, in the res folder.
IMAGE background "background.png" BEST

Include gfx.h in main.c
#include "gfx.h"

Megadrive has 3 planes - Plane B - Background plane, Plane A - Foreground plane, sprite plane. We will use plane B.

Within int main(), draw the image
VDP_drawImageEx(BG_B, &background, TILE_ATTR_FULL(PAL1, 0, 0, 0, 1), 0, 0, 1, DMA);
