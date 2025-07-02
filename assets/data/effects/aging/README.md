# Aging

This file contains effects related to how your custom speices ages, using a method similar to the hard-coded method used by humans: as the character ages, their stats are adjusted at discreet times using progressively 'older' aspects and removing the previous age tier.

The `customSpecies_setAgingStats` file contains the logic to actually apply the correct age tier tag.  The other files in this folder control the timing of when the age stats should be run and do not need to be edited directly once you have set the `id` and `sourceFile` fields correctly.

## Setup

* **Rename** all files, changing `customSpecies` to your species name
* **Edit** all files, changing all instances of `customSpecies` to your species name 

## Customization

Inside the `outcomes` section of `customSpecies_setAgingValues`, you will find a number of `Test` outcomes that check if a character's age is between certain values AND they do not already have the age aspect for that age bracket. 

To change the stat adjustments for each of the age brackets, you will need to edit the age-related aspects found in `data/aspects/customSpecies.json` - see the README in that folder for details.

* Open `customSpecies_setAgingStats`, either using the in-game editor or by using your favourite code editor
* Find the age range that you want to adjust and change the low/high endpoints for that age bracket. Be sure to adjust the next and previous age brackets as well to match.
* You can remove age brackets by deleting any of the `Test` outcome blocks. Be sure to adjust the age brackets on either side of the deleted one appropriately.
* You can add age brackets by inserting new `Test` blocks, using the existing ones as a guide. Be sure to adjust the age ranges of the brackets neighbouring the new one appropriately.
  * If creating new age brackets, you will also need to add a new aspect that contains the appropriate stat modifiers in `data/aspects/customSpecies.json`