# Changes in this fork

Fork of [psiberx/cp2077-cyberware-ex](https://github.com/psiberx/cp2077-cyberware-ex)
(MIT, based on 1.5.6). Our work is on the `patch-2.5` branch; `main` tracks upstream.

## Game patch 2.5 compatibility

Patch 2.5 (Oct 22, 2026) changed two functions the mod hooks, which made redscript
compilation fail and disabled all script mods.

- `EquipmentSystemPlayerData.GetActiveItem` gained an optional `isLeftHandWeapon`
  argument (dual wielding). The wrapper now accepts and forwards it.
- `EquipmentSystemPlayerData.UpdateArmSlot` now takes `ref<gamePuppet>` instead of
  `ref<PlayerPuppet>`. The `IsJohnnyReplacer` check now casts to `PlayerPuppet` first.

## Dual wielding fixes

- `UpdateArmSlot`: since 2.5 the game calls it for every item entering or leaving either
  weapon slot, including off-hand weapons. It now only reacts to installed arm cyberware
  (any slot, so the Projectile Launcher counts) or fists, like vanilla.
- `EquippedDecisions.ToUnequipCycle`: the left-hand block that keeps the Projectile
  Launcher charged no longer blocks 2.5 `DualEquip` requests.

## Leg slots

- Extended mode adds 3 extra leg slots (4 total), all unlocked by
  `Reflexes_Central_Perk_1_3`.

## Build and install

```powershell
pwsh -File tools\dist\package-mod.ps1 -ProjectName CyberwareEx
```

Then extract `build\dist\CyberwareEx-*.zip` into the game folder.

Tested in-game on 2.5: scripts compile, the extra leg slots appear, and dual wielding
works with and without the Projectile Launcher.
