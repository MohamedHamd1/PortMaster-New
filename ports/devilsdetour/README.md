## Notes

Devil's Detour is an original game written for PortMaster: a pixel-art trick platformer where every level lies to you. Each level tells you 8-13 things about itself, as icons you can open with R1: "the exit is on the left", "the spikes are fake", "the floor is solid". Most of them are lies, and the guide shows what lied after each level. Signs point the wrong way, some flags kill, the controls and the floor change with the clock, and some levels are blocked by a wall that only a lucky gate can throw you past (touch it at the wrong moment and it kills you, so try again).

550 levels in 11 worlds. Every 10th level is a trick screen. Progress is saved in `ports/devilsdetour/save.txt`.

Thanks to everyone who tested the game on their handhelds.

## Controls

| Button | Action |
|--|--|
| D-pad / Left stick | Move |
| A / B / X / Y | Jump |
| R1 | Icon guide: what the level says, and what lied last time |
| Start | Pause |
| Start + Select (hold) | Quit |

## Compile

Source: https://github.com/MohamedHamd1/devils-detour

Single C file plus an embedded font, SDL2 only. Cross-compile for aarch64 (glibc 2.17):

```shell
pip install ziglang
python3 -m ziglang cc -target aarch64-linux-gnu.2.17 -O2 -I/usr/include/SDL2 -Isrc -c src/trust.c src/font_data.c
```

Then link against the device's `libSDL2-2.0.so.0` (do not bundle SDL2).
