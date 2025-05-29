# People Parts

The files in this folder are used to create customization options for your characters - head shapes, hairstyles, etc.  When creating your own nonhuman species, you will need to create your own suite of `peopleParts` to replace the standard human head pieces.

**NOTE:** The `peopleParts` files cannot be edited through the in-game editor and must be created through a separate text or code editor instead. 

Nonhuman characters will have a `customSpecies_naturalHead` aspect instead of the normal `humanSkin_naturalHead` aspect, which means that all of your `peopleParts` files will need to define custom `extra` slots. The included files provide an example. Files located in the base game's `assets/data/peopleParts` folder can also be used as references.

If you want to show scars, tattoos, etc. on your custom faces, you can use the head templates found in `/figures/source`, which has pre-named layers for all of the head and facial feature layers that can be granted to characters over the course of play as well as all of the different supported facial expressions. 

**For best results**, please name the files representing the base head selection to match the suffix that you appended to the image layers (ignoring leading underscore, if any) when exporting them from the template. For example, if you exported layers from the template to end with `_mySpecies_squareHead`, then name the base head selection file `mySpecies_squareHead.json`. This will make it easier to update the `data/aspects/customSpecies_headDetails.json` file to show all of the extra details.