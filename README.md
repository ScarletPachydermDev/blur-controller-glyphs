# Blur controller glyph textures

Replacement button-prompt textures for **Blur (2010)**, for use with the `tex` feature of
[blur-hooks-rs](https://github.com/tobii-dev/blur-hooks-rs) — the d3d9 layer used by the
[amax-emu](https://github.com/Amax-Emu) community server.

Blur draws every on-screen button prompt from a single 512x512 atlas. Replacing that one
texture converts the whole game from keyboard prompts to controller prompts.

## Requirements

A build of `blur-hooks-rs` with texture replacement (`-F tex`). At time of writing this lives
on the [`patch_texmod`](https://github.com/tobii-dev/blur-hooks-rs/tree/patch_texmod) branch —
see [issue #7](https://github.com/tobii-dev/blur-hooks-rs/issues/7).

## Install

Copy the `F6FA7B91.png` of the set you want to:

```
<Blur>/amax/gfx/tex/F6FA7B91.png
```

`F6FA7B91` is the TexMod CRC of the atlas. Restart the game.

| Set | Prompts |
|---|---|
| `xbox-one/` | A B X Y, LB RB LT RT, View / Menu |
| `xbox-360/` | A B X Y, LB RB LT RT, Back / Start |
| `ps3/` | Cross Circle Square Triangle, L1 R1 L2 R2, Select / Start |

Tested in game: `xbox-one` (SteamOS / Proton 9 / DXVK). The other two are built by the same
process on identical tile geometry but have not been verified in game.

## Credits and permissions

Base artwork is from **[Controller Icons](https://www.nexusmods.com/blur/mods/2)** on Nexus
Mods by its original author, extracted from that mod's `.tpf` packages. It is not my work and
is included here only as a modified derivative — check that mod's own permissions before
redistributing.

The original packs left four prompts drawn as keyboard keycaps (`F1`/`F2`): TexMod mods
replace whole textures, and those tiles were simply never redrawn. Those four have been
replaced with the matching controller buttons from
[Xelu's FREE Controller Prompts](https://github.com/DJLink/Xelu_Free_Controller-Key_Prompts)
(CC0 / public domain, original at <https://thoseawesomeguys.com/prompts/>).

Only those four tiles differ from the originals — the game samples fixed UV rectangles from
this atlas, so anything that shifted would misalign.

Two prompts remain as keyboard keys (`+` and `Space`); it isn't clear what they map to on a
pad and they have not been observed in game.
