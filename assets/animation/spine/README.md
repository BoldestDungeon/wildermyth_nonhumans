# Animation Files

This folder contains the animation files used for your custom rigs. These are the skeleton files referenced by your `assets/data/generation/rigs.json` file. These are the files that determine where the head is drawn on your characters' bodies.

To start, **rename all of the files** by changing `customSpecies` to the name of your species.  The file names should exactly match the values in the `skeleton` fields in your `rigs.json` file.  (It is safe to delete any files that you are not using.)

To change the position of the head:

* Open the skeleton file with a text or code editor
* Find the entry that begins with `{"name":"bone3","parent":"bone2","length":72,`
* Edit the values for `"x"` and `"y"` to change where the head is positioned.
  - **NOTE:** Due to a quirk of how the animation is read, changing the `x` value moves the head _vertically_, and changing the `y` value moves the head _horizontally_.

## Advanced: Changing the size of the head's canvas

By default, all heads are drawn onto a canvas that is 192 x 257 pixels, and the results of that layering will be placed on top of the character's body at the specified coordinates.  Any image layer files that are a different size will be stretched/enlarged/shrunk to fit those dimensions. To change the canvas size for your custom species, you will need to find all instances of `"width":192,"height":257` in the skeleton file and change the width/height values to the desired ones.  **NOTE**: This will also cause theme heads to be stretched/enlarged/shrunk to match your new values. We recommend keeping the aspect ratio close to the original ratio (roughly 3:4) to ensure that theme heads are scaled up/down to fit your characters without distortion.