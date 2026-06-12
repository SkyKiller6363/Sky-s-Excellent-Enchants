# Sky's Excellent Enchantments

**Sky's Excellent Enchantments** is a custom enchantment pack built for **MythicMobs** and **Mythic Enchants**. It adds a large collection of custom enchantments for weapons, bows, armor, tools, tridents, fishing rods, and utility gameplay.

This repository is intended to track development, configuration changes, balancing notes, and future updates for the pack.

## Overview

This pack uses Mythic Enchants enchantment definitions paired with MythicMobs skills to create custom enchantment effects that go beyond vanilla Minecraft behavior.

Included enchantment categories:

| Category | Count | Folder |
|---|---:|---|
| Armor | 30 | [`enchantments/armor/`](MythicMobs/packs/Skys%20Excellent%20Enchants/enchantments/armor) |
| Bows | 15 | [`enchantments/bows/`](MythicMobs/packs/Skys%20Excellent%20Enchants/enchantments/bows) |
| Fishing Rods | 16 | [`enchantments/fishing_rods/`](MythicMobs/packs/Skys%20Excellent%20Enchants/enchantments/fishing_rods) |
| Tools | 9 | [`enchantments/tools/`](MythicMobs/packs/Skys%20Excellent%20Enchants/enchantments/tools) |
| Tridents | 5 | [`enchantments/tridents/`](MythicMobs/packs/Skys%20Excellent%20Enchants/enchantments/tridents) |
| Universal | 3 | [`enchantments/universal/`](MythicMobs/packs/Skys%20Excellent%20Enchants/enchantments/universal) |
| Weapons | 29 | [`enchantments/weapons/`](MythicMobs/packs/Skys%20Excellent%20Enchants/enchantments/weapons) |
| **Total** | **107** |  |

Full List: [Sky's Excellent Enchantments List](MythicMobs/packs/Skys%20Excellent%20Enchants/Enchantment_List.md)

## Requirements

Recommended server/plugin setup:

- Paper or compatible fork for Minecraft `1.21.11+`
- MythicMobs Free `5.12.2+`
- Mythic Enchants `5.12.0+`
- MythicCrucible `5.12.1+`

Some enchantments rely on MythicMobs skill mechanics, item drops, or custom utility skills. Make sure all included folders are installed together unless you intentionally remove or disable specific enchantments.

## Installation

1. Copy this pack into your MythicMobs packs folder.
2. Run `/mm reload` to load the pack into the plugin.
3. Restart the server to enable the enchantments.
4. Either run `/mench list see` to see a list of **S**ky's **E**xcellent **E**nchantments, or use the enchanting table or the vanilla `/enchant` command to get your enchantments.

A restart is recommended when changing enchantment definitions, datapack tags, or anything that affects what items can receive enchantments.

## File Structure

```text
Sky's Excellent Enchantments/
├── datapack/
│   └── mythicenchants/tags/item/
├── enchantments/
│   ├── armor/
│   ├── bows/
│   ├── fishing_rods/
│   ├── tools/
│   ├── tridents/
│   ├── universal/
│   └── weapons/
├── items/
├── mobs/
├── skills/
│   ├── armor/
│   ├── bows/
│   ├── fishing_rods/
│   ├── tools/
│   ├── tridents/
│   ├── universal/
│   ├── utilities/
│   └── weapons/
├── Enchantment_List.md
├── packinfo.yml
└── README.md
```

## Important Files

| File | Purpose |
|---|---|
| `packinfo.yml` | MythicMobs pack metadata, including name, description, author, version, and icon. |
| `Enchantment_List.md` | Human-readable enchantment table grouped by type. Includes descriptions, max levels, equipment tags, incompatibilities, and weights. |
| `datapack/mythicenchants/tags/item/see_enchant_tags.yml` | Custom item tag support used by Mythic Enchants. |
| `enchantments/` | Mythic Enchants configuration files. |
| `skills/` | MythicMobs skill files used by the enchantments. |
| `items/` | Custom item definitions used by certain enchantments. |
| `mobs/` | Custom mob definitions used by certain enchantments. |

## Enchantment Design Notes

### Primary vs. Secondary Items

Mythic Enchants can separate items that receive an enchantment directly from the enchantment table from items that can receive the enchantment through books or an anvil.

For example, an enchantment may use:

- **Primary Items**: items eligible from the enchantment table.
- **Secondary Items**: additional items that can accept the enchantment from an enchanted book.

This is useful for cases like weapon enchantments where swords and spears may be offered in the enchantment table, but axes or maces may still support the enchantment through books.

### Incompatibilities

Some enchantments are intentionally exclusive so they do not stack in ways that would be too strong or mechanically conflicting.

Examples include:

- Projectile-changing bow enchantments should generally be mutually exclusive.
- Poison and Wither arrow effects should not stack with each other.
- Curses may conflict with similar beneficial effects depending on balance needs.

Always check the individual enchantment file before changing compatibility rules.

### Enchantment Table Weight

The enchantment table weight controls how commonly an enchantment appears from the enchanting table. Higher weights make the enchantment more common. Some enchantments may intentionally have no enchanting table offer and may only be obtainable through other methods.

## Included Gameplay Features

This pack includes enchantments and supporting skills for features such as:

- Custom weapon effects
- Bow projectile effects
- Arrow status effects
- Armor passives
- Movement and utility effects
- Mining and tool upgrades
- Trident abilities
- Fishing rod upgrades
- Decapitator-style mob head drops
- Thrifty-style mob drop support
- Tunnel and Veinminer support
- Silk Spawner support
- MiniBlocks support

## Support / Contact

Created by **SkyKiller63**.

Support and questions: `discord.SkyKillerGames.com`
