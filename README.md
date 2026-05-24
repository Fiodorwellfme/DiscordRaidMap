# Discord Raid Map

Pure client BepInEx mod that posts a raid map image to Discord while a raid is running.

## Displayed

- Players: rotated `player.png` marker with name under it
- Player-killed enemies: `skull_enemy.png`
- Player-killed bosses: `skull_boss.png`
- Airdrop: crate icon
- Active extracts: green extract marker
- Requirement-blocked extracts: `extract_requirements.png`
- Raid time remaining: top-left image text

## Notes

- Set `Discord > Webhook Url` in the generated BepInEx config.
- Add `.ttf` or `.otf` files to `Assets\Fonts`, restart the game, then choose one with `Map Text > Map Text Font`. `Default` uses the built-in bitmap font.
- The mod creates one webhook message at raid start, edits it on an interval, and deletes it at raid end.
- Rendering uses the original bundled PNG map resolution; it does not stretch maps into a fixed aspect ratio.
- Marker images are loaded from `Assets\Markers`. Replace `player.png`, `skull_enemy.png`, `skull_boss.png`, `airdrop.png`, `extract.png`, or `extract_requirements.png` to customize them.
- `Markers > Marker Display Size` controls how large markers appear on the map. Source PNGs can be larger than this value for sharper downsampling.
- Rendering is CPU-side from bundled PNG assets; it does not use a Unity canvas, camera, or RenderTexture.
