# Wildermyth: Nonhuman Player Character Tempalte

This project has been created to help the Wildermyth community create new, nonhuman hero characters as part of the Wildermyth game. The scaffolding in this project will help you introduce new types of characters that are fully compatible with all of the game's many systems, including transformations, scars, background NPCs, armour, and more. 

This template is brought to you by the minds behind the Drauven PCs project and is built on the many lessons the team has learned along the way.

## Setup

1. **[Create a new mod](https://wildermyth.com/wiki/Modding_Guide)** using Wildermyth's in-game editor.
1. **Download** this sample project.
1. **Unzip** the contents of this package.
1. **Copy** the unzipped `assets` folder to the root folder your mod. (Found at `[wildermyth-base-directory]/mods/user/[your-mod-name]`)
1. **Rename** _all_ files in this project by changing all instances of `customSpecies` to your new species name, leading with a lowercase letter. (For example: if making playable Gorgons, `customSpeciesBase.json` becomes `gorgonBase.json`)
    - **Note:** Files without `customSpecies` in the name do not have to be renamed. 
1. **Find/Replace** in _all_ files, changing `customSpecies` (case-sensitive) to your species name (leading with a lowercase letter), then finding all instances of `CustomSpecies` (case-sensitive, only found in `assets/data/generation/humanNames.json` and `assets/text/aspects/aspects.properties`) with your species name (leading with a capital letter).
    - **Tip:** Using a code editor, such as [VS Code](https://code.visualstudio.com/download), will allow you to find/replace across all files in a project folder very quickly. ([Tutorial](https://stackoverflow.com/questions/37346481/how-do-i-find-and-replace-all-occurrences-in-all-files-in-visual-studio-code))

You are now ready to design your own nonhuman characters to add to the game!

To get started with some sample data:

1. **Prepare** the 'simple' rig setup by following the instructions found in `assets/data/generation`
1. **Export** the sample image layers by following the instructions found in `assets/figures/source`

## Artwork and Image Layers

Creating the image layers is by far the heaviest lift in making a new type of character. Sample `.psd` documents are included with this project in `assets/figures/source` to help you create all the layers that the game requires. See the README file in that folder for instructions.

## Game Data

Additional instructions for how to customize each part of your nonhuman heroes can be found in the respective folders.

* **Adjusting Percentages** of characters that are generated as your custom species, including male/female ratios and attractions: See `assets/data/history`
* **Base Stats:** See `assets/data/aspects`
* **Aging, Age Adjustments**: See `assets/data/effects/aging` and `assets/data/aspects`
* **Heads, Faces and Face Customizations:** See `assets/data/peopleParts`
* **Name Generation:** See `assets/data/generation`
* **Rigs:** You can visually distinguish characters based on class, gender, neither, or both by choosing the appropriate rig setup. See `assets/data/generation` and `assets/animation/spine`

## HELP!

Don't panic! If you need help setting anything up, or if any of the parts are unclear, drop a line either at the [Wildermyth Discord Server](https://discord.gg/ZQcmPtf) in the `#tools-and-modding` channel, or at the [Drauven PCs Discord Server](https://discord.gg/uftGyUa8GS)
