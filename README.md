# WispReach

Adjust wisplight mist clearance, or hide all Mistlands mist without a wisplight, using BepInEx Configuration Manager.

WispReach smoothly fades the game's native mist clouds. Their material, textures, lighting and shader are retained. No paid assets or shader bundle are required. Install on the client.

## Settings

| Setting | Default | Behavior |
| --- | --- | --- |
| General / Enabled | On | Disable to immediately restore native wisplight and mist behavior. Your chosen radii are retained. |
| General / Remove all Mistlands mist | Off | Hide all native Mistlands particle clouds even without a wisplight. Ignores the radius sliders; Enabled must be on. |
| R1 - Clear radius (m) | 15 m | Fully hide mist clouds whose centers are inside this radius. |
| R2 - Full mist radius (m) | 15 m | Restore full native opacity at this distance and farther. |

The global checkbox restores the native renderer when switched off, returning to the configured wisplight fade if applicable. Ordinary weather fog in other biomes is unchanged.

Both radius sliders range from 0 to 100 meters in whole-meter steps, with no decimal places. Existing fractional values round to the nearest meter (half meters round up) when the updated mod loads. The 100 m endpoint remains a finite radius. R2 cannot be lower than R1. Raising R1 above R2 raises R2; lowering R2 below R1 clamps it to R1.

With the global checkbox off, the default 15/15 preserves the game's original wisplight behavior. To add a gradual transition, try R1=15 and R2=25. Between the radii, each cloud's opacity changes smoothly according to its center distance. Large clouds fade as a whole rather than being cut at the radius boundary.

Changes apply without restarting the game. Existing saved settings are preserved on update; use Configuration Manager's reset controls to apply new defaults. With global hiding off, removing the wisplight restores original particle opacity. Disabling the mod restores both original opacity and rendering in either mode. The wisp's light range, stationary torches and other players' wisps retain their original settings.

## Install a local package

1. Select Valheim and your profile in Thunderstore Mod Manager.
2. Open **Settings → Profile → Import local mod**.
3. Select `Slikfoul-WispReach-1.0.0.zip`. Confirm author **Slikfoul**, name **WispReach**, version **1.0.0**, then import.
4. Start the game using **Start modded** and open WispReach in Configuration Manager. Equip a wisplight for radius control, or enable **General / Remove all Mistlands mist** without one.

If a DLL was previously installed by hand in `BepInEx/plugins/WispReach`, back up and remove that old manual copy before importing into the same profile. Keep `BepInEx/config/Slikfoul.WispReach.cfg` to preserve settings. Load one WispReach DLL per profile.

The dependencies are BepInExPack_Valheim and shudnal's ConfigurationManager. This ZIP does not include either dependency, game assemblies or user configuration. Ensure the declared dependencies are installed when using an offline import.

## Validation

The release is checked against the installed Valheim assemblies. Local checks cover integer radius constraints, legacy fractional config migration, both switches, persistence and particle alpha restoration. Earlier Unity integration checks covered global hiding without a wisplight, distant/new clouds, renderer restoration and unchanged weather/material state. In-game visual confirmation remains separate from these checks.
