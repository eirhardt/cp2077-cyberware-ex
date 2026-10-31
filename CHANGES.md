# Changes in this fork

Fork of [psiberx/cp2077-cyberware-ex](https://github.com/psiberx/cp2077-cyberware-ex)
(MIT). Our work is on the `patch-2.5` branch; `main` tracks upstream.

## Upstreamed

Patch 2.5 compatibility, the dual wielding fixes and the 3 extra leg slots were merged
upstream via [PR #14](https://github.com/psiberx/cp2077-cyberware-ex/pull/14)
(Oct 25, 2026). Upstream now requires Codeware 1.21.0+ and TweakXL 1.12.0+.
On Oct 31, 2026 this branch was rebased onto upstream; the old history is in
`backup/patch-2.5-pre-rebase-2026-10-31` (local only).

## Only in this fork: a third arm slot

Extended mode adds 2 extra arm slots (3 total; upstream adds 1), both unlocked by
`Tech_Central_Perk_3_2`. Use [Arm Wheel](https://github.com/eirhardt/cp2077-arm-wheel)
(private) to switch between the arm weapons.

## Build and install

```powershell
pwsh -File tools\dist\package-mod.ps1 -ProjectName CyberwareEx
```

Then extract `build\dist\CyberwareEx-*.zip` into the game folder.
`CyberwareEx.ExtendedMode.reds` is not in the package; it stays installed separately.

Tested in-game on 2.5 (before the rebase): scripts compile, the extra leg slots appear,
and dual wielding works with and without the Projectile Launcher.
