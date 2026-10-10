# WispReach

Adjust mist clearance around wisplights and wisp torches, change mist density, or hide all Mistlands mist.

## Settings

| Setting | Default | Behavior |
| --- | --- | --- |
| Enabled | On | Enable your settings or smoothly return to ordinary mist. |
| Remove all Mistlands mist | Off | Hide all Mistlands mist, even without a wisplight. Overrides all radius, density and torch settings while enabled. |
| R1 - Clear radius (m) | 15 m | Clear mist clouds whose centers are inside this radius. |
| R2 - Full mist radius (m) | 15 m | End the gradual transition from clear space to the opacity selected with R3. |
| R3 - Mist density (%) | 100% | Set mist opacity: 100% is ordinary mist, 50% is half opacity, 0% hides it. Works without a wisplight too. |
| Link R1 and R2 | Off | Changing R1 moves R2 by the same amount, preserving the transition width up to the 100 m limit. |
| Wisp torches / Enabled | Off | Apply separate clearance settings to loaded wisp torches. |
| T1 - Clear radius (m) | 24 m | Clear radius around a wisp torch when its settings are enabled. |
| T2 - Full mist radius (m) | 24 m | End of the torch's transition to the density selected with R3. |

All radius sliders use whole meters from 0 to 100. R3 uses whole percentages from 0 to 100. R2 cannot be lower than R1, and T2 cannot be lower than T1. You can still change R2 independently while linking is enabled to choose a new transition width. Turning linking on leaves saved radii unchanged.

With a custom wisplight radius, clouds are clear inside R1 and gradually reach the selected density at R2. Without a wisplight, R3 adjusts mist throughout Mistlands. At 15/15 and 100%, the original wisplight behavior is retained.

When custom settings are active, enabling, disabling, equipping or removing a wisplight, changing the sliders and switching complete hiding use a half-second fade. Your saved settings are preserved. Clouds fade as a whole according to their center distance, so large clouds can cross the radius boundary.

Torch settings work without an equipped wisplight. Overlapping torch and wisplight zones use the stronger clearance. Disabling torch settings smoothly restores the torches' original behavior. Only loaded native wisp torches are selected; ordinary torches and other players' wisplight settings are unchanged.

The default torch radii are 24/24 m, matching the native 24 m clearance radius with no added transition band. Existing saved values are preserved; resetting the torch sliders applies these defaults.

Ordinary weather fog and light brightness/range are unchanged. R3 affects shared Mistlands mist, including clouds near other wisplights and torches.

After a rendering error, WispReach attempts to restore ordinary mist and retries up to three times, five seconds apart. If the problem persists, re-enable the mod or load a new scene to try again.

## Installation

Install through Thunderstore Mod Manager, or import `Slikfoul-WispReach-1.1.0.zip` using **Settings → Profile → Import local mod**. Start the game using **Start modded**.

Keep one WispReach DLL per profile. Remove an older manual copy before importing the package, and retain `BepInEx/config/Slikfoul.WispReach.cfg` to preserve settings.

The required dependency is BepInExPack_Valheim.
