# Disable Animated Marsh | Clean Textures - VTE, Regrowth Compatibility Patch

## Description
Disables the animated marsh from [Vanilla Textures Expanded](https://steamcommunity.com/sharedfiles/filedetails/?id=2016436324) and [Regrowth: Core](https://steamcommunity.com/sharedfiles/filedetails/?id=2260097569) so that the [Clean Textures](https://steamcommunity.com/sharedfiles/filedetails/?id=2865361569) marsh texture works properly.

This is done by reverting the `EdgeType` of the `Marsh` `TerrainDef` back to `FadeRough`.

Vanilla Textures Expanded and Regrowth: Core both change `Marsh`'s `TerrainDef`'s `EdgeType` to `Water`, which gives it the same animated, sloshing look as rivers, lakes, and the ocean. That's neat! It also has the side effect of making the texture unrecognizable and look like green sludge. That's not neat. This is because the water shader that Rimworld uses interprets its texture as a ramp texture, which basically means that it mainly interprets it along just the X axis, and it also applies a bunch of distortion. This works when you have a very simple texture that's really just 2-3 shades of the same color, arranged in a pattern, but it doesn't work when you have a texture that's meant to look pretty on its own.

To have the Clean Texture Marsh texture as well as a watery effect, you'd need to write a different shader and package it and patch it into the game. I might do that some day, as I know GLSL and HLSL (shader code languages) and enjoy writing shaders, but today is not that day. For now, enjoy the pretty marsh. :)

## Credits

Created by Kobe Riddle. <https://koberiddle.dev/>

Big thanks to the members of the members of the Rimworld discord for helping me decompile Rimworld's `TerrainWater` shader in order to investigate the issue.