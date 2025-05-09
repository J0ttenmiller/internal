Perfect GBA Overlays (Instructions for muOS)

Updated 2025-04-04:
- Updated scaling settings for muOS 2502.0 Pixie. Noted that image brightness can be increased by reducing overlay opacity (at the cost of realism/accuracy)

Updated 2025-03-12:
- Revised shader recommendations and settings

Updated 2024-09-26:
- Added versions with the main (darker) Perfect GBA overlay
- Moved bright and 75% opacity versions to Bright subfolder

Updated 2024-09-21:
- Updated shader recommendation description
- Made the narrow gray bar at the top of the _mugwomp93 border darker

Updated 2024-09-14:
- added slightly improved border shadows (darker corners so bright colors show through less)
- added a few more no grid, no shadow, etc options
- added a few more border designs
- restructured folders to make the choices less overwhelming/difficult to navigate
- (marginally) shorter names

These files are adapted from u/1playerinsertcoin's Perfect GBA overlay for the Miyoo Mini Plus (https://www.reddit.com/r/MiyooMini/comments/18ovuld/i_made_a_game_boy_advance_overlay/?rdt=52022). All credit goes to them - my only contributions are the borders on the _mugwomp93 overlays. Versions using both the main and bright (brt) Perfect GBA overlays are included. Please refer to the original post for files and settings for the MM+, including Onion OS color correction settings not included here. Files for the original RG35XX with Garlic OS are on my Garlic OS Github repository (https://github.com/mugwomp93/GarlicOS_Customization).

Note that these overlays have been tested on the RG35XX Plus with muOS. I have no idea how they look on other devices or with different firmware. Given the differences I've seen so far ymmv (i.e., compared three devices, all three slightly different).

******

As mentioned, the zip includes both the main and bright version of the Perfect GBA grid. The bright version isn't quite as dark as the main, optimized version, though this comes at the expense of accuracy. I've also included _75 versions where the grid has been reduced to 75% opacity to help further increase brightness, though this further reduces accuracy. If you find the _75 version is still too dark, you could customize the overlay by adjusting the opacity in Retroarch, or reducing the opacity of the _noframe version below 75% in Photoshop, GIMP, etc. and then applying your preferred _nogrid version over top.

To apply the overlay:

1. Quick Menu > On-Screen Overlay

   Display Overlay > ON

   Overlay Preset...
     - Select <Parent Directory> to navigate to the main Overlays folder (you should see AntiKk, Jeltron, Perfect, and Stock folders)
     - Perfect > Perfect_GBA
     - Select your preferred overlay:
          - _bright indicates the bright (brt) version of the overlay; otherwise, the main version wsa used
          - _noframe indicates just the grid with no logos, shadows, etc.
          - _noshadow indicates no border shadows
          - _nogrid indicates just the borders +/- shadow with no grid
          - all other naming conventionss indicate different border decorations

   Overlay Opacity > 1.00


2. Quick Menu > Core Options:

    Color Correction > OFF

    Interframe Blending	> ON (NOTE: If you don't like the image ghosting, turn it OFF, but you may see flickering elements in games.)

    Manage Core Options > Save Content Directory Options


3. Main Menu (press B to back out of Quick Menu) > Settings > Video > Scaling

**muOS 2502.0 Pixie (Retroarch 1.20.0)**

   - Set Viewport Anchor Bias Y > 0.00 (that's it)

   Your final Scaling settings should be:

         Integer Scale				OFF

         Integer Scale Axis			Doesn't matter

	 Integer Scale Scaling		 	Doesn't matter

         Aspect Ratio 				Core provided OR 3:2
         
         Viewport Anchor Bias X 		0.50
         
         Viewport Anchor Bias Y 		0.00

         Bilinear Filtering 			OFF

         Crop Overscan 				OFF

   Note: If you're using Pixie and the top of the image is cutoff, setting Viewport Anchor Bias Y to 1.00 should hopefully resolve the issue. This happens if you try using the settings for earlier versions of muOS (see below).


**muOS 2410.3 AW Banana and earlier**

   - Turn Integer Scale ON
   - Set Aspect Ratio to Custom
   - Set aspect ratio:
         - Custom Aspect Ratio (Width) > 640
         - Custom Aspect Ratio (Height) > 427
   - Turn Integer Scale OFF

   (This moves the image to the top of the screen instead of having it centered)

   Your final Scaling settings should be:

         Integer Scale				OFF

         Integer Scale Overscale		OFF

         Aspect Ratio 				Custom
         
         Custom Aspect Ratio (X Position) 	0
         
         Custom Aspect Ratio (Y Position) 	0
         
         Custom Aspect Ratio (Width) 		640
         
         Custom Aspect Ratio (Height) 		427

         Bilinear Filtering 			OFF

         Crop Overscan 				OFF


4. Quick Menu > Shaders:

   Video Shaders ON

I haven't found a "best" solution. Sharp-bilinear and sharp-shimmerless are probably the clearest, but they over-emphasize blacks (i.e., black outlines appear thicker than in raw, integer-scaled screens). Pixellate and pixel_aa seems to perform better in this sense, but they appear slightly less focused.

Note that sharp-shimmerless is on by default for muOS 2502.0 Pixie and is less resource intensive than pixellate or pixel_aa, so you don't need to adjust the shaders unless you're unhappy with how the image looks.
     
   Shader #0: interpolation > shaders > sharp-bilinear.glsl OR pixellate.glsl

   OR

   Shader #0: pixel-art-scaling > shaders > pixel_aa.glsl

   OR

   Shader #0: shimmerless > shaders > sharp-shimmerless.glsl

For all of the above shaders:

   Filter: Linear

   Scale: Default
   
   
   Apply Changes

   Save Preset > Save Content Directory Preset


5. Once you've got everything configured the way you want it, save your settings:

   Quick Menu > Overrides > Save Content Directory Overrides

   Note: For whatever reason, my Viewport Anchor Bias Y setting wasn't saving with my override, even though all of my other settings did. I resolved this issue by removing the existing content directory and core overrides and saving a new content directory override.
 

***Note that these are DARK overlays. You'll need to increase the screen brightness to maximum for them to be usable (menu + volume up, or in Configuration > General Settings in the muOS menu). If it's still too dark, you can reduce the Overlay Opacity (see step 1) at the cost of realism/accuracy.***

There's a lot of interesting discussion in the comments of the Reddit post - I highly recommend reading through them if you're interested in the technical details and process that were used to create these overlays.

-mugwomp93