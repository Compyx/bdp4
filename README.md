# BDP 4.0+ deconstruction

This project is an attempt to deconstruct (and perhaps reconstruct) my old multicolor bitmap editor called "Boogie Down Paint 4.0+". I've used this editor exclusively during my C64 demo scene days since 1992 until I dropped out of the scene around 1995.
Since I only have this binary left, and it doesn't appear to contain any help screen, I decided to rip this apart.

## It has sub-editors

After pushing a lot of keys, I found out that the bitmap editor isn't all there is, there's a few other mini-editors as well, some of which explain how I did certain graphics/effects "back in the day"

### Bitmap fade editor

It appears it has a bitmap fade in/out editor (an effect pretty popular at some point), not sure if I used this much or at all, since doing it 'real-time' saves a lot of memory though perhaps the color ramps are slightly more ugly.

![Bitmap fade editor](https://raw.githubusercontent.com/compyx/bdp4/master/fade-editor-screenshot.png)


### Sprite (overlay) editor

BDP 4 also has a sprite editor which can be used to overlay sprites on the bitmap, and even save the sprites and their positions. Though I still have figure out how exactly the editor saves that data.

![Sprite editor](https://raw.githubusercontent.com/compyx/bdp4/master/sprite-editor-screenshot.png)

(Yup, I painted that sprite today, I still got it :))
