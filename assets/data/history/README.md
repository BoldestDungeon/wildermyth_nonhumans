# History Entries

This folder includes a sample history file to allow the game to randomly generate members of your custom species any time a character is created (Greenhorn heroes, NPCs, etc.).

To set up this feature:

* Open `customSpecies.json` with a text or code editor and change all instances of `customSpecies` to your species name.
* Rename the file, changing `customSpecies` to your species name.

The `humanBase.customSpecies` history entry contains the basic aspects that create your nonhuman hero. The setup assumes that you want to use completely different heads/faces from ordinary humans. If you want to use the default human heads instead, replace the line `customSpecies_naturalHead` with `humanSkin_naturalHead`.

The `customSpecies_5XX` history entries specify the weights for the various combinations of gender and attractions, and can be freely edited without affecting the corresponding entries for human characters.