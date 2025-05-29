# Image Layer Source Files

The files in this folder are intended to help you set up your custom-species heroes.  Each file is set up with all of the named layers required to be compatible with all of the base game features.

**You Will Need:**

* An image editor capable of reading and writing to the `.psd` file format (Such as Krita, GIMP, Affinity Photo, Photopea, or other compatible program).
* A method of exporting all layers as individual `.png` files that preserves the canvas size.
  - If your editor of choice does not have a suitable built-in option, you can install the [ImageMagick command-line tool](https://imagemagick.org/script/download.php) to handle the export part. 

When exporting your image files, all files need to be saved to `/assets/figures/images/human/misc`

## CustomSpeciesLayerTemplate

This file contains all of the layers needed to create the body of your character. **Before editing this file, we recommend creating a copy and renaming it based on the rig you are designing for.**

Layers in this template file are grouped by type. The `Body` group contains all of the basic image layers used to make the hero, and the `Armor and Clothing` group contains all of the image layers used for normal clothing/armour, sorted into sub-groups based on class. You will also find layer groups for all of the different transformation limbs and augment types.

When exporting these layers to individual files, you will need to **prefix** the layer names with the name of the rig, followed by an underscore. _(See the README in the `assets/data/generation/` folder for more information about rigs.)_ For example: If you are working on a rig named `mySpeciesWarriorF`, you will need to export each layer as `mySpeciesWarriorF_{layername}.png`

<details>
<summary>Command for ImageMagick users</summary>

Open a new console window and navigate to this folder (Which should be found under `[Wildermyth-base-directory]/mods/user/[your-mod-name]/assets/figures/source`), then run the following command. Replace `[FILENAME]` with the name of the document containing the layers you wish to export, and replace `[RIGNAME]` with the name of your rig.

```
convert -dispose Background [FILENAME].psd -layers coalesce -set filename:layers %l '../images/human/misc/[RIGNAME]_%[filename:layers].png'
```
</details>

## CustomSpeciesHeadLayerTemplate

This file contains all of the layers needed to make the heads for your custom species compatibile with all of the transformations, scars, and other details that can appear on a character's head or face. **Before editing this file, we recommend making a copy and renaming it based on the name of the head style.** For best results, use a separate file for each head style (such as `squareJawline`, `roundedHead`, etc.)

Normal head and face layers for your custom species must be set up in the `assets/data/peopleParts` folder to appear on your heroes. You can set up an arbitrary number of different categories that can be selected from, such as `head`, `face`, `feathers`, `whiskers`, `tentacles`, or whatever else you need. See the README in the `peopleParts` folder for more information.

The `Details` group of layers inside the template includes all of the layers that come from aspects and transformations, such as scars and tattoos. 

When exporting these layers to individual files, you will need to **append** the layers names with an underscore, followed by the name of your species and the name of the base head style.  For example, if your custom species is called `mySpecies` and your head style is `squareJawline`, append `_mySpecies_squareJawline` to the layer name to make the file name.

<details>
<summary>Command for ImageMagick users</summary>

Open a new console window and navigate to this folder (Which should be found under `[Wildermyth-base-directory]/mods/user/[your-mod-name]/assets/figures/source`), then run the following command. Replace `[FILENAME]` with the name of the document containing the layers you wish to export, `[SPECIES_NAME]` with the name of your custom species, and `[HEAD_STYLE]` with the name of the head.

```
convert -dispose Background [FILENAME].psd -layers coalesce -set filename:layers %l '../images/human/misc/%[filename:layers]_[SPECIES_NAME]_[HEAD_STYLE].png'
```
</details>