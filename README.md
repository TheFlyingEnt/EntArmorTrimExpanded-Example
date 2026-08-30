![eate_logo](https://cdn.modrinth.com/data/cached_images/1f3801e32d45af631da7e75d57699bac944cd47f.png)


# Raw Copper - Animated Trim Example

A complete, working example that adds the **Raw Copper** animated armor trim material for
[Ent's Armor Trim Expanded](https://modrinth.com/project/ents-armor-trim-expanded). Use it as a
starting point for your own animated trim, or drop it straight into a world to see the mod in action.

It's split into the two packs Minecraft needs:

```
template/
├── datapack/        →  world's  datapacks/   (registers the material + smithing ingredient)
└── resourcepack/    →  resourcepacks/         (the animated colours)
```

> ⚠️ Requires **Ent's Armor Trim Expanded** installed. Without it the material still exists but shows
> as a plain static trim - the mod is what plays the animation.

## Install

1. Copy `datapack/` into your world's `datapacks/` folder (rename it if you like), then `/reload`.
2. Copy `resourcepack/` into your `.minecraft/resourcepacks/` folder, then enable it in
   **Options → Resource Packs** and press **F3 + T** to reload.

## Try it

Smithing table: **any armor trim template + a piece of armor + a Raw Copper item**.

Or test instantly with a command:

```
/give @s minecraft:iron_chestplate[minecraft:trim={pattern:"minecraft:coast",material:"example:raw_copper"}]
```

## What's inside

**datapack/**
- `data/example/trim_material/raw_copper.json` - the trim material (`asset_name: raw_copper`).
- `data/minecraft/tags/item/trim_materials.json` - adds `minecraft:raw_copper` as a smithing ingredient.

**resourcepack/**
- `assets/example/textures/trims/color_palettes/raw_copper{,_1,_2,_3}.png` - the 4 palette frames (8×1).
- `assets/minecraft/atlases/armor_trims.json` - builds the trim sprites from those palettes.
- `assets/example/trim_animations/raw_copper.json` - the animation (4 frames, `frametime: 4`, interpolated).
- `assets/example/lang/en_us.json` - the tooltip name.

## Make it your own

1. Pick a new name and replace **`example`** (namespace) and **`raw_copper`** (id) everywhere - file
   names, folder names, and inside the JSONs.
2. Swap the four palette PNGs for your own colours (keep them **8×1**; frame 0's file must be named
   after your material's `asset_name`).
3. Update the `permutations` in `armor_trims.json` and the `frames` in `trim_animations` to your names.
4. Change the ingredient in `trim_materials.json` and the tooltip in `lang/en_us.json`.

Full walkthrough and reference: the **[wiki](https://github.com/TheFlyingEnt/EntArmorTrimExpanded/)**.

## Pack formats

- Resource pack: `pack_format` **88** (Minecraft 26.2)
- Data pack: `pack_format` **107** (Minecraft 26.2)

Update these if you target a different Minecraft version.
