# Character-Generation Files

These files are used by the game when generating new characters, including name generation and character rigs.

## Custom names for your non-human custom species

To create name-generation data for your custom species:

* Open `human.names.json` in any text or code editor
* Find all instances of `customSpecies` (case-sensitive) and replace with the name of your species, beginning with a lowercase letter.
* Find all instances of `CustomSpecies` (case-sensitive) and replace with the name of your species, beginning with a capital letter.
* Edit the lists of predefined names and name parts (starting on line 15) to values that are appropriate for your custom species. (The initial values have been copied from the human name generation.)

Entries in your lists must follow these rules to be valid JSON (_JavaScript Object Notation_) that the game can read:
* The list must be wrapped with square brackets `[]`
* Each entry in the list must be enclosed with (double) quotation marks - eg: `"Alex"`
* You *must* include a comma `,` between each entry in the list
* You *must not* include a comma after the final entry of the list
* Similarly, you *must* include a comma `,` after the closing square-bracket `]` of each list _except_ for the last list in the entry.

## Custom rigs (poses) for your non-human custom species

Creating custom rigs allows you to pose your species however you like, but can require intensive work to create all of the required image layers. See the [wiki entry on Image Layers](https://wildermyth.com/wiki/Image_layers) for more information about how the image layering system works.

A custom rig is given to a character using either the `rigOverride` or `rigOverridePriority` aspect (in the format `rigOverride|customSpecies`), which is already included in the `history/customSpecies` entry. Custom rigs allow you to have full control over the visual appearance of your custom characters.

When the game looks for image layers to draw for a character, it uses the character's current rig and the name of the layer to look for the appropriate image in the `figures/images/human/misc` folder. The game determines the name of the rig by combining the `rigOverride` value with the character's class and gender to find the best match in your `rigs.json` file, then uses that full rig name as a prefix to find the image.

For example, if your rig is `customSpecies` and the game wants to draw a layer named `torso` for a Female Hunter:

* If your `rigs.json` file includes `customSpeciesHunterF`, find `customSpeciesHunterF_torso.png`
* Otherwise, if `rigs.json` includes `customSpeciesHunter`, find `customSpeciesHunter_torso.png`
* Otherwise, if `rigs.json` includes `customSpeciesF`, find `customSpeciesF_torso.png`
* Otherwise, if `rigs.json` includes `customSpecies`, find `customSpecies_torso.png`

\* Note that `Farmer` is considered a blank class for the purposes of `rigOverride`. If the character in the above example was a farmer instead of a hunter, the game would look for a rig called `customSpeciesF`, followed by `customSpecies`.

This folder contains four example files to help get you started:

* `rigs.example_all.json` includes placeholder definitions for all 8 possible combinations of class (Warrior/Hunter/Mystic/Farmer) and gender (M/F)
* `rigs.example_class_only.json` includes placeholder definitions for classes (Warrior/Hunter/Mystic/Farmer) ONLY
* `rigs.example_gender_only.json` includes placeholder definitions for gender (M/F) ONLY
* `rigs.example_simple.json` includes a placeholder definition for a single generic rig to be applied to all characters regardless of class or gender.

Choose one of the four styles of rig, then:
* **rename the chosen example file to `rigs.json`**
* Open the rig file with a text or code editor (the in-game editor does not support rig files)
* Find all instances of `customSpecies` and replace with your species name.

You may then edit the numeric values in your chosen `rigs.json` file to edit some aspects of how your characters will be drawn:
* The hand/grip position and rotation fields affect how weapons and offhand items are positioned on the character. Adjust these values to line items up with the characters' hands properly.
* The back position and rotation fields affect how stowed items are positioned behind the character. Adjust these values if you need to reposition the inactive weapons.
* The head/face position values **only** affect where the face preview is drawn (for character icons, hero selection for tasks, etc.). These values do **not** change where the head is actually drawn! To change the head position, you will need to edit the appropriate files in the `assets/animation/spine` folder. See the README in that folder for more information.

Creating a custom rig that supports all of the potential layers that a character may have can be a daunting task, as the game has thousands of image layers that could potentially be supported. Consider starting with the `simple` example, as you can always add the class- and/or gender-specific rigs later.

An example `.psd` file can be found in this project's `assets/images/source` folder that is set up with blank, pre-named layers that you can use with your favourite image editing software to create your custom species. If your editor does not have a built-in bulk export feature, we recommend pairing this file with a tool such as the [ImageMagick command line tool](imagemagick.org) to quickly export each layer as its own `.png` file. (See the README in the `assets/images/source` folder for more information.)