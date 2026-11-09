Stalliongrad Rework - Wave 3

Source: user-provided 324.pdf, 11 pages, dated 09.11.2026.
Scope: 153 assets = 1 shared frame + 115 focus icons + 23 events + 10 MIO emblems + 3 decision category pictures + 1 adviser.

Read manifest.json for completed and pending assets. An in_progress status means this is a partial delivery; missing assets are not represented as completed.

Installation: copy the contents of game/ into the mod directory. Wave 3 focus files intentionally replace earlier versions by using the same IDs. Sprite registration is handled by the project installation script and is not included here.

masters/STG_focus_frame.png is the immutable common wreath overlay, 1024x1024, transparent center and exterior. The dark steel disc is added below each central drawing. Final focus masters include disc, centre and the exact same frame pixels. Separate center layers are included in masters/centers/.

Game textures: DDS BC3/DXT5 RGBA, no mipmaps. Sizes: focus 89x80; event 210x176; MIO 64x64; decision 114x101; adviser 65x67. PNG master sizes are specified in manifest.json.

preview_*.jpg shows each asset large and decoded from DDS at exact game size. Labels appear only on preview sheets, never on game artwork.

Images created individually with built-in image_gen. Exact prompts and reference roles are in prompts.json. Post-processing assembles the common frame, resizes outputs and encodes DDS. spec.json contains the complete ID, priority and subject list transcribed from the source PDF.

quality_report.json covers generated files only and reports technical checks separately from completion.
