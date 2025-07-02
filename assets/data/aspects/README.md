# Aspects

This project contains three files to help you get started:

* `customSpecies.json` contains the core statistics and interfusion recipe set for your new faction.
* `customSpecies_headDetails.json` contains image layer definitions to make the heads and faces of your new species compatible with all of the scars, tattoos, and other details that your heroes can acquire.
* `humans.json` contains supporting aspect information that ensures cross-mod compatibility. **DO NOT** make changes to this file directly.


## Configuring your Custom Species - Stats and Interfusions

To make your custom species feel distinct from regular humans, you have the ability to give them their own suite of base stats as well as their own custom set of interfusion abilities.

### Minimum Setup

* Open the `customSpecies.json` file and change all instances of `customSpecies` to your species name
* Rename the `customSpecies.json` file in this folder to something that makes sense for your new species

**Note:** The IDs of the renamed aspects are used in the `history` file for your custom species. Ensure that the aspects in both places match.

### Customizing Your Species

By default, this project gives your custom species the same base stats, age adjustments, and interfusion list that humans get. To make changes:

* You may freely edit the stat values in the renamed `customSpeciesBaseStats` aspect (either using the in-game editor or your text editor) to any values you want
* You may freely edit the stat values in the age-related aspects (`customSpecies_young`, `customSpecies_middleAge`, etc.).
  * To adjust when characters move from one life stage to the next, see `data/effects/aging/customSpecies_setAgingStats.json`
  * You may add or remove age bracket aspects, but to make them apply you will need to edit `data/effects/aging/customSpecies_setAgingStats` appropriately. 
* You may add or remove effects to the list in the renamed `customSpeciesInterfusionRecipes` aspect (either using the in-game editor or your text editor) to change the interfusion list.

Creating new interfusion spells requires making new `effects` and adding them to your mod. Please refer to the [Wildermyth modding wiki](https://wildermyth.com/wiki/Category:Modding) or visit the community [Discord Server](https://discord.gg/ZQcmPtf) for more information.

## Face/Head Details

There are many possible head/face details that a human hero can obtain. The layer definitions in `customDetails_headDetails.json` is set up to allow you to make your custom species compatibile with all such details that exist in the base game.

Making these head details visible on whatever custom heads you create for your new playable species requires two main steps:

1. Create and export all of the applicable image files _(See the README in `assets/figures/source` for full details)_
1. Edit `customSpecies_headDetails.json` to create the correct layer definitions

The `customSpecies_headDetails.json` file initially contains full definitions for two head variations. 

To enable your **first** head variation:
1. Open `customSpecies_headDetails.json` with a text or code editor. 
1. Use the Find/Replace All tool to **Find** all instances of **`_customSpecies_head1`** and **Replace** with the same suffix that you used when exporting your image layers.

To enable your **second** head variation:
1. Open `customSpecies_headDetails.json` with a text or code editor. 
1. Use the Find/Replace All tool to **Find** all instances of **`_customSpecies_head2`** and **Replace** with the same suffix that you used when exporting your image layers.

For **additional** head variations:
1. Copy the sample code block below.
1. Open `customSpecies_headDetails.json` with a text or code editor.
1. Find the line `"skinLayers": [`
1. Add a new line after the `[`
1. Paste the copied code block.
1. Use your Find/Replace tool to **Find** all instances of **`_customSpecies_headType`** and **Replace** with the same suffix that you used when exporting your image layers.

<details>
<summary>Sample code block for additional head image layer sets</summary>

```json
      {
        "name": "head_tattooFireDraconic_customSpecies_headType",
        "depth": 4052,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_tattoo", "themeSkin_fireDraconic", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooBearTattooB_tint1_30_customSpecies_headType",
        "tint": "primary",
        "tintAmount": 0.3,
        "depth": 4051,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_bear_tattoo", "themeSkin_bearTattoo", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_scar1_customSpecies_headType",
        "depth": 4050,
        "rigUsage": "rigGeneral",
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["human_scar", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "hair_starsGold_customSpecies_headType",
        "depth": 4240,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_star_hairStars", "themeSkin_starGold", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "hair_starsGalaxy_customSpecies_headType",
        "depth": 4240,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_star_hairStars", "themeSkin_starGalaxy", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_vinesCarnivorousB_untinted_customSpecies_headType",
        "depth": 4251,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_vine_head", "themeSkin_vinesCarnivorous", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_vinesCarnivorousA_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4250,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_vine_head", "themeSkin_vinesCarnivorous", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_vineForeheadMythicalB_untinted_customSpecies_headType",
        "depth": 4251,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_vine_head", "themeSkin_vinesMythical", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_vineForeheadMythicalA_tint_customSpecies_headType",
        "tint": "secondary",
        "tintAmount": 0.8,
        "depth": 4250,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects":[ "themePiece_vine_head", "themeSkin_vinesMythical", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_vineForeheadB_tint1_customSpecies_headType",
				"depth": 4251,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_vine_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
				"ifNoOwnerAspect": "themeSkin_vine*"
      },
      {
        "name": "face_vineForeheadA_untinted_customSpecies_headType",
				"tint": "secondary",
				"depth": 4250,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_vine_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
				"ifNoOwnerAspect": "themeSkin_vine*"
      },
      {
        "name": "face_gorgonCrustPetri_customSpecies_headType",
        "depth": 4260, 
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_gorgonPetriglass", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_gorgonCrust_customSpecies_headType",
        "depth": 4260, 
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
				"ifNoOwnerAspect": "themeSkin_gorgon*",
        "ifOwnerAspects": ["themePiece_gorgon_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_fireBloomB_untinted_customSpecies_headType",
        "depth": 4251,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_tattoo", "themeSkin_fireBloom", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_fireBloomA_tint2_60_customSpecies_headType",
        "tint": "secondary",
        "tintAmount": 0.6,
        "depth": 4250,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_tattoo", "themeSkin_fireBloom", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemShardRB_untinted_customSpecies_headType",
        "depth": 4251,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemShard", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemShardRA_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4250,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemShard", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemRB_untinted_customSpecies_headType",
				"depth": 4151,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
				"ifNoOwnerAspect": "themeSkin_gem*"
      },
      {
        "name": "face_eyeGemRA_tint1_customSpecies_headType",
				"tint": "primary",
				"depth": 4150,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
				"ifNoOwnerAspect": "themeSkin_gem*"
      },
      {
        "name": "face_eyeGemKnightRB_untinted_customSpecies_headType",
        "depth": 4151,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemKnight", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemKnightRA_tint1_75_customSpecies_headType",
        "tint": "primary",
        "depth": 4150,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemKnight", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemGlassRD_untinted_customSpecies_headType",
        "depth": 4153,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemGlass", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemGlassRC_tint2_customSpecies_headType",
        "tint": "secondary",
        "depth": 4152,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemGlass", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemGlassRB_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4151,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemGlass", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemGlassRA_untinted_customSpecies_headType",
        "depth": 4150,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemGlass", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemCaveRB_untinted_customSpecies_headType",
        "depth": 4551,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemCave", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeGemCaveRA_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4550,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gem_head", "themeSkin_gemCave", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooStormSea_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_storm_head", "themeSkin_stormSea", "humanSkin_extra|customSpecies_head|customSpecies_headType" ]
      },
      {
        "name": "head_tattooStorm_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifNoOwnerAspect": "themeSkin_storm*",
        "ifOwnerAspects": ["themePiece_storm_head", "humanSkin_extra|customSpecies_head|customSpecies_headType" ]
      },
      {
        "name": "head_tattooStormJagged_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_storm_head", "themeSkin_stormJagged", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooStormGold_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_storm_head", "themeSkin_stormGold", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooStormCuffs_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_storm_head", "themeSkin_stormCuffs", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooSpelltouched_customSpecies_headType",
        "bodyPart": "head",
        "depth": 4005,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_spellTouchedTattoo", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooGreenKnot_customSpecies_headType",
        "depth": 4050,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_green_tattoo", "themeSkin_greenKnot", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooGreen_customSpecies_headType",
				"depth": 4050,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
				"ifNoOwnerAspect": "themeSkin_green*",
        "ifOwnerAspects": ["themePiece_green_tattoo", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooGreenDeer_customSpecies_headType",
        "depth": 4050,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_green_tattoo", "themeSkin_greenDeer", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFoothillObsidian_customSpecies_headType",
        "tint": "secondary",
        "tintAmount": 0.4,
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_foothill_head", "themeSkin_foothillObsidian", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFoothillMossy_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_foothill_head", "themeSkin_foothillMossy", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFoothill_customSpecies_headType",
				"depth": 4010,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
				"ifNoOwnerAspect": "themeSkin_foothill*",
        "ifOwnerAspects": ["themePiece_foothill_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFoothillCanyon_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_foothill_head", "themeSkin_foothillCanyon", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFireHelix_customSpecies_headType",
        "depth": 4052,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_tattoo", "themeSkin_fireHelix", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFire_customSpecies_headType",
        "depth": 4052,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_tattoo", "themeSkin_fireLava", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFire_customSpecies_headType",
				"depth": 4052,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
				"rigMode": "maleHead",
				"ifNoOwnerAspect": "themeSkin_fire*",
        "ifOwnerAspects": ["themePiece_fire_tattoo", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooFireBloom_customSpecies_headType",
        "depth": 4052,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_tattoo", "themeSkin_fireBloom", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooDeepistMole_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_deepistMole_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooDeepist_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_deepist_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooBearTattooA_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4050,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_bear_tattoo", "themeSkin_bearTattoo", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooBearGhost_customSpecies_headType",
        "depth": 4050,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_bear_tattoo", "themeSkin_bearGhost", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_tattooBear_customSpecies_headType",
				"depth": 4050,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
				"ifNoOwnerAspect": "themeSkin_bear*",
        "ifOwnerAspects": ["themePiece_bear_tattoo", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_scarFire_customSpecies_headType",
        "bodyPart": "head",
        "depth": 4050,
        "rigUsage": "rigGeneral",
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["human_fireBurn", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_scarFire_customSpecies_headType",
        "bodyPart": "head",
        "depth": 4050,
        "rigUsage": "rigGeneral",
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["human_scarFire", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_scarAcid_customSpecies_headType",
        "bodyPart": "head",
        "depth": 4050,
        "rigUsage": "rigGeneral",
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["human_acidBurn", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_scarAcid_customSpecies_headType",
        "bodyPart": "head",
        "depth": 4050,
        "rigUsage": "rigGeneral",
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["human_scarAcid", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_gorgonColorPetri_customSpecies_headType",
        "depth": 4010,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_gorgonPetriglass", "themePiece_gorgon_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "head_gorgonColor_customSpecies_headType",
				"depth": 4010,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_gorgon_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_shadowMouthyC_untinted_customSpecies_headType",
        "depth": 4252,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects":[ "themePiece_shadow_head", "themeSkin_shadowMouthy", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_shadowMouthyB_tint2_customSpecies_headType",
        "tint": "secondary",
        "depth": 4251,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowMouthy", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_shadowMouthyA_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4250,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowMouthy", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_shadowFlameD_tint2_customSpecies_headType",
        "tint": "secondary",
        "depth": 4255,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowFlame", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_shadowFlameC_untinted_customSpecies_headType",
        "depth": 4254,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowFlame", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_shadowFlameB_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4253,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowFlame", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_shadowFlameA_untinted_customSpecies_headType",
        "depth": 4252,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowFlame", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_fireDraconic_customSpecies_headType",
        "depth": 4250,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_tattoo", "themeSkin_fireDraconic", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyepatch_customSpecies_headType",
        "depth": 4150,
        "rigUsage": "rigGeneral",
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["human_eyepatch", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeFireR_customSpecies_headType",
				"depth": 4250,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_rightEye", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_eyeFireL_customSpecies_headType",
				"depth": 4250,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_fire_rightEye", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_demonHornsWildB_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4251,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowWild", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_demonHornsWildA_untinted_customSpecies_headType",
        "depth": 4250,
        "headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themePiece_shadow_head", "themeSkin_shadowWild", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_demonHornsB_tint1_customSpecies_headType",
				"tint": "secondary",
				"depth": 4251,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
				"ifNoOwnerAspect": "themeSkin_shadow*",
        "ifOwnerAspects": ["themePiece_shadow_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "face_demonHornsA_untinted_customSpecies_headType",
				"depth": 4250,
				"headOffset": true, 
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
				"ifNoOwnerAspect": "themeSkin_shadow*",
        "ifOwnerAspects": ["themePiece_shadow_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "replaceHead_skullWrappedC_untinted_customSpecies_headType",
        "depth": 4002,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonWrapped", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "replaceHead_skullWrappedB_tint1_customSpecies_headType",
        "tint": "primary",
        "depth": 4001,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonWrapped", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },
      {
        "name": "replaceHead_skullWrappedA_untinted_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonWrapped", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [
          "neutral",
          "interested",
          "grim",
          "skeptical",
          "dubious",
          "happy",
          "sad",
          "angry",
          "rage",
          "scheming"
        ]
      },
      {
        "name": "replaceHead_skullWrappedA_untinted_surprised_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonWrapped", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "hit", "dead", "surprised", "scared" ]
      },
      {
        "name": "replaceHead_skullWrappedA_untinted_open_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonWrapped", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "open", "joke", "joy" ]
      },
      {
        "name": "replaceHead_skullMonster_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonMonster", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [
          "neutral",
          "interested",
          "grim",
          "skeptical",
          "dubious",
          "happy",
          "sad",
          "angry",
          "rage",
          "scheming",
          "hit",
          "dead"
        ]
      },
      {
        "name": "replaceHead_skullMonster_talk_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonMonster", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "open", "joke", "joy" ]
      },
      {
        "name": "replaceHead_skullMonster_surprised_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonMonster", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "surprised", "scared" ]
      },
      {
        "name": "replaceHead_skull_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifNoOwnerAspect": "themeSkin_skeleton*",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": [ "themePiece_skeleton_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "neutral", "interested", "grim", "skeptical", "dubious", "happy", "sad", "angry", "rage", "scheming", "hit", "dead" ]
      },
      {
        "name": "replaceHead_skull_talk_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifNoOwnerAspect": "themeSkin_skeleton*",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": [ "themePiece_skeleton_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "open", "joke", "joy" ]
      },
      {
        "name": "replaceHead_skull_surprised_customSpecies_headType",
        "depth": 4000,
        "headOffset": true,
        "ifNoOwnerAspect": "themeSkin_skeleton*",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": [ "themePiece_skeleton_head", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "surprised", "scared" ]
      },
      {
        "name": "replaceHead_skullChainB_untinted_customSpecies_headType",
        "depth": 4001,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonChain", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [
          "neutral",
          "angry",
          "dubious",
          "grim",
          "happy",
          "interested",
          "rage",
          "sad",
          "scheming",
          "skeptical"
        ]
      },
      {
        "name": "replaceHead_skullChainB_untinted_surprised_customSpecies_headType",
        "depth": 4001,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonChain", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "hit", "dead", "scared", "surprised" ]
      },
      {
        "name": "replaceHead_skullChainB_untinted_open_customSpecies_headType",
        "depth": 4001,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonChain", "humanSkin_extra|customSpecies_head|customSpecies_headType"],
        "facialExpression": [ "open", "joy", "joke" ]
      },
      {
        "name": "replaceHead_skullChainA_tint2_customSpecies_headType",
        "tint": "secondary",
        "depth": 4000,
        "headOffset": true,
        "ifOwnerAspect": "themePiece_skeleton_head",
        "ifNoOwnerAspects": ["themePiece_crow_head", "themePiece_turtle_head", "themePiece_wolf_head", "themePiece_tree_head", "themePiece_frog_head", "themePiece_fishman_head"],
        "ifOwnerAspects": ["themeSkin_skeletonChain", "humanSkin_extra|customSpecies_head|customSpecies_headType"]
      },

```
</details>