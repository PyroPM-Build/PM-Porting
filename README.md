
########################################################################################
# PyroPM PSA Edits
## Original edits by Yohan1044,
## with credit to Draco_the, KingJigglyPuff, ds22, and DukeItOut
########################################################################################

Many PSA -- fighter.pac -- files have been modified to recieve minor cosmetic enhancements
or patched to prevent crashes. No changes to gameplay animations, attributes, frame data,
or non-cosmetic hitbox properties (locations, trajectories, damage, knockback) have occurred.

All edited PSAs use vPM3.6 as a base. Some cosmetic bugs present in vPM3.6 have not
been corrected.

If any differences in gameplay between the modified PSAs and vPM3.6 were accidentally
introduced, please report them as bugs. Any such differences are not representative of
the philosophy or quality of work presented by the Legacy TE development team as a
whole or any of its playtesters.

	1 - Memory Leak Fixes
	2 - Shiny Pokemon
	3 - Team Glow compatibility
	4 - Costume slot dependent effects
	5 - Removed Peach entry files
	6 - PSA Stability fixes
	7 - Fighter PAC Injection Changes

########################################################################################
### 1. The following fighter.pac files have been patched with ds22's memory leak fix.
Some fighters receive additional PSA edits, as noted later | Implemented by ds22 and Yohan1044.
These fixes will prevent certain crashes from prolonged gameplay sessions with these fighters:

	1 - Game & Watch
	2 - Ganondorf
	3 - Kirby
	4 - Lucario
	5 - Mewtwo
	6 - Pit
	7 - ROB
	8 - Snake
	9 - Sonic
	10 - Zero Suit Samus

########################################################################################
### 2. All Pokemon received sparkle during their entry animation for their shiny variant(s).
The subaction used for this (1C2-main-entry) is not full, so new slots can be added
with ease. The left entry has been changed to point to the right entry in every case,
so edits to only one location are required to remove or change which costumes are shiny.
  | This PMDT concept has been implemented by Yohan1044.

	1 - Charizard - Black
	2 - Ivysaur - Green Team
	3 - Jigglypuff - Blue Team (Green-eyed)
	4 - Lucario - Yellow & Red Gi
	5 - Mewtwo - Green Team & Brass Armored
	6 - Pikachu - Red Team & Ash Hat (Red-skinned)
	7 - Squirtle - Purple (Green-shelled)

########################################################################################
### 3. For compatibility with Team Glow, characters with "destroy all graphics" instructions
have been modified to avoid destroying Team Glow | Implemented by Yohan1044.

	1 - Diddy - Juggling balls and Shades
	2 - Sonic - Runtrails on side-taunt (redirected for space)
	3 - ROB   - Armtrails on grounded side-B 
	4 - Zelda - Erroneous terminate in the grab-wait

########################################################################################
### 4. Costume slot dependent effects | Implemented by Yohan1044 with credit

Ganondorf now uses the Trident for some costumes as originally implemented in
KingJigglyPuff's PSA provided with Nano and Corshmell's Pig Ganon.
		Slots 0-19, and AltR 	- Twilight Princess sword	
		Slots 20-39 		- Trident
		Otherwise		- Melee Sword
	This affects GFX and loaded articles on the Down Taunt.
	Conditional logic was improved reducing codesize.

Ivysaur has had her leaf colors and leaf trail logic optimized. Seed bomb now generates 
leaf colors corresponding to the costume.
	This affects GFX on an article.
	Subactions and subroutines were moved.
	Conditional logic was improved reducing codesize.

Lucas has had his adventurer sword effects moved to costume slots 20-29.
	This affects GFX, SFX, and hitbox types for Forward Smash.
	A subaction was moved.

Mario has had doctor effects moved to costume slots 20-29, with fire effects applied to higher slots.
	This affects GFX, SFX, and hitbox types on FSmash, DTaunt, Victory 2, and his Nuetral B article.
	Subactions and subroutines were moved.

MetaKnight has had the BetaKnight sword effects moved to all costume slots 20 and up.
	This affects GFX on many attacks.

Peach has had fire effects moved to costume slots 20-29 and shadow effects moved to slots 30-39.
	This affects GFX, SFX, and hitbox types on UpTilt, UpThrow, SideB, and Entry.
	SubActions were moved.

Pit has had a new pink glide added for costume slot 23 (Classic Pink) and new feather colors added
for costume slots 22 and 23 (Classic Mint). This uses assets from KingJigglyPuff's Cupid Pit PSA.
Pit's black feathers and purple glide have been moved to slots 5 and 21.
	This affects GFX on extra jumps, down taunt, and glide.

ROB has had his kart smoke effects moved to costume slots 20-29.
ROB has been modified to use costume specific gfx banks and MotionEtc files.
	This affects GFX on grounded side-B and most grounded movement.
	Armtrails moved to external MotionEtc files.
	Subactions and subroutines were moved and created.

Roy has had the Awakening sword effects moved to costume slots 20-29. Roy's sword glow lengths have
been restored to PM 3.6 values. This is a Legacy edit to KingJigglyPuff's PSA provided with
Nano, Pit, and Tock's Awakening Roy.
	This affects GFX on almost all attacks.
	Subactions were moved.

Samus received edits to her thrusters. New thruster locations were added corresponding to the
PED Suit Samus costumes by Nano, Allbait, and SJS. Thruster effects were fixed on Dash attack
and Victory 1. The costume slot ranges for different thrusters were modified:

		0 - 19: Default Power Suit
		20 - 24: Dark Suit
		25 - 29: Light Suit
		30 - 34: Fusion Suit
		35 - 39: Retro Power Suit
		40+ :	 PED Suit

	This affects GFX on jumps, dashAttack, rolls, UpTaunt, and Victory 1.
	A Subroutine was created.

Sonic has had his jet set smoke moved to costume slots 20-29.
Sonic has been modified to use costume specific gfx banks and MotionEtc files. Credit to DukeItOut.
	This affects GFX on running, dash attack, Win1, SideTaunt, Entry, specials,
		and an Easter egg.
	Runtrails, KickTrails, and PunchTrails moved to external MotionEtc files.
	Subactions and subroutines were moved and created.


Toon Link has had the Outset sword effects moved to all costume slots 20 and up.
	This affects GFX on almost all attacks
	Subactions and Subroutines were moved.

########################################################################################
### 5. Removed Peach entry files | Implemented by DukeItOut.

Edits to Peach's coding during her entry animation were made to remove her dependency
on Entry files, saving much hard drive space and avoiding crashes when adding costumes
without Entry files. Credit to DukeItOut.

########################################################################################
### 6. PSA Stability fixes | Implemented by DukeItOut and Yohan1044

Sonic and Lucario have had calls to bad data removed from their PSAs.

########################################################################################
### 7. Fighter PAC Injection Changes | Implemented by Pyro and KingJigglyPuff

Every character has had internal addresses relocated to work with P+'s codeset alterations.
