# BDP 4.0+ deconstruction

This project is an attempt to deconstruct (and perhaps reconstruct) my old multicolor bitmap editor called "Boogie Down Paint 4.0+". I've used this editor exclusively during my C64 demo scene days since 1992 until I dropped out of the scene around 1995.
Since I only have this binary left, and it doesn't appear to contain any help screen, I decided to rip this apart.

## The main editor

Since there's no built in help, this is currently incomplete until I disassemble the main menu event handling:

- Color selection if via 'A' to 'P' (without shift)
- Space plots a pixel
- 0-3 plot the current bitpair pixel, so 0 is background, 1 = %01, 2 = %10 and 3 = %11.
- @ start the bitmap fade editor
- \* starts the sprite editor
- <- (left arrow) enters the disk menu

### Disk menu

The disk menu is extremely primitive:

![Disk nemu](https://raw.githubusercontent.com/compyx/bdp4/master/disk-menu-screenshot.png)

Options 1 & 2 seem to load/save Koala pictures, requiring the "/x81PIC" prefix, though not when entering the filename.
Options 3 & 4 use BDP4's own format: a very lame RLE implementation. But hey, back then I didn't have internet, so I was pretty proud of my "equal-byte-packer".


## It has sub-editors

After pushing a lot of keys, I found out that the bitmap editor isn't all there is, there's a few other mini-editors as well, some of which explain how I did certain graphics/effects "back in the day"

### Bitmap fade editor

Accesible via '@' on the real machine, most likely '\[' when using VICE's positional mapping.

It appears it has a bitmap fade in/out editor (an effect pretty popular at some point), not sure if I used this much or at all, since doing it 'real-time' saves a lot of memory though perhaps the color ramps are slightly more ugly.

![Bitmap fade editor](https://raw.githubusercontent.com/compyx/bdp4/master/fade-editor-screenshot.png)


### Sprite (overlay) editor

Accessible via '\*' on the real machine, most likely ']' when using VICE's positional mapping.

BDP 4 also has a sprite editor which can be used to overlay sprites on the bitmap, and even save the sprites and their positions. Though I still have figure out how exactly the editor saves that data.

![Sprite editor](https://raw.githubusercontent.com/compyx/bdp4/master/sprite-editor-screenshot.png)

<sub>Yup, I painted that sprite today, I still got it :)</sub>

#### Interface
- space = pixel
- 1-4 = select color (in multi color mode. 1 being $d020)
- F1 = goto placement mode: use cursor keys (and 1-8 to select sprites) to place a sprite on the bitmap. Haven't really figured this one out yet.
- F3 = switch to single color mode
- F5 = switch to multi color mode
- X = switch X-expand
= Y = switch Y-expand

There are more keys, such as mirroring sprites over X/Y axis


