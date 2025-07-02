# Mod Injections

Mod Injections are files that allow mods to selectively add, remove or edit values in other files, allowing multiple mods to play nicely together when they need to edit the same files. To create or edit Mod Injections, use the in-game editor. For more information, see the [Mod Injections wiki page](https://wildermyth.com/wiki/Mod_Injections).

## Core ModInjections

The core framework includes two Mod Injection files: One for `aspects/humans.json` and one for `history/humanBase.json`. These are used to set up the the common human aspects that allow you to create your custom species separately from the standard human design. 

Please **DO NOT** change or remove the modifications in `modInjections/aspects/humans.json` or `modInjections/history/humanBase.json`, as doing so may break compatibility with other mods. 

## Head-Layer ModInjections

The files in `modInjections/themes/` as well as `modInjections/aspects/themeSkins.json` and `modInjections/aspects/themeSkins2.json` contain rules for suppressing certain transformation layers that may be drawn on the head in the wrong place if you are using a custom head.

In each of these files, **find** all instances of `customSpecies` and **replace** with the name of your species, leading with a lowercase letter.