# Sky's Excellent Enchants - Sanity Check TODO

Use this as the working checklist for the AI-created enchantments that need extra validation before release.

## High Priority: Update / Verify Mechanics

### 1. Riptide Reach
- [ ] Test `see_riptide_reach-throw` from `~onProjectileHit` with thrown tridents.
- [ ] Confirm `@trigger` resolves to the hit entity during projectile hits.
- [ ] Confirm `throw{fromorigin=true}` pushes the target from the trident impact direction instead of behaving weirdly from the player/caster.
- [ ] Compare melee hit behavior against projectile hit behavior to make sure the two skills feel consistent.

Files:
- `enchantments/tridents/Riptide_Reach.yml`
- `skills/tridents/Riptide_Reach-skills.yml`

### 2. Stormcaller
- [ ] Identify whether the extra sound is only in the thrown-trident skill: `sound{s=entity.lightning_bolt.thunder;p=1.4;v=0.8} @self`.
- [ ] Test thrown Stormcaller with and without the sound line to see if it feels too loud, duplicated, or unnecessary alongside `fakelightning`.
- [ ] If the sound is removed and thrown/melee behavior should match, consider combining `see_stormcaller` and `see_stormcaller_melee`.
- [ ] If keeping separate skills, confirm the separate damage/chance values are intentional.

Files:
- `enchantments/tridents/Stormcaller.yml`
- `skills/tridents/Stormcaller-skills.yml`

### 3. Cyclone
- [ ] Check whether `@EntitiesNearOrigin{r=<math.enchant_level+2>;...}` supports placeholders/math in the radius field in the installed MythicMobs version.
- [ ] If radius placeholders do not work, split Cyclone into level-specific skills or use fixed radius values.
- [ ] Double-check `effect:particletornado{...}` syntax and visual result.
- [ ] Confirm the tornado appears at the impact/target location, not accidentally at the caster.
- [ ] Confirm knockback direction and radius feel fair for melee and thrown trident hits.

Files:
- `enchantments/tridents/Cyclone.yml`
- `skills/tridents/Cyclone-skills.yml`

### 4. Duelist
- [ ] Verify the `ATTACK_SPEED <math.enchant_level*0.12> ADD` attribute behaves as intended.
- [ ] Confirm whether positive `ADD` increases attack speed in Mythic Enchants/modern attribute handling.
- [ ] If positive values slow attacks or behave backwards, change the modifier direction/sign.
- [ ] Test levels 1-3 against a normal sword and confirm the difference is noticeable but not too strong.
- [ ] Confirm `#minecraft:enchantable/sword` is a valid tag in your current tag setup.

Files:
- `enchantments/weapons/Duelist.yml`
- `skills/weapons/Duelist-skills.yml`

### 5. Glass Cannon
- [ ] Decide whether the extra damage skill should stay disabled.
- [ ] Current active behavior is attribute-based bonus damage plus particles/sound on proc.
- [ ] Test whether `ATTACK_DAMAGE <math.enchant_level*1.25> ADD` already gives enough damage.
- [ ] If attribute damage feels good, leave the commented damage mechanic removed/disabled and keep the particle/sound feedback only.
- [ ] Confirm the negative max health modifier updates cleanly when equipping/unequipping.

Files:
- `enchantments/weapons/Glass_Cannon.yml`
- `skills/weapons/Glass_Cannon-skills.yml`

### 6. Soul Barrage
- [ ] Consider changing the area damage into one localized totem at the kill location.
- [ ] Suggested design: one totem, 2 charges, about 20 seconds lifetime, interval around 8 ticks.
- [ ] Make sure the damage is localized around the totem/kill location instead of repeatedly using broad `@EntitiesNearOrigin` bursts.
- [ ] Confirm players/faction members are ignored as intended.
- [ ] Test kill chaining so multiple Soul Barrage procs do not become too spammy.

Files:
- `enchantments/weapons/Soul_Barrage.yml`
- `skills/weapons/Soul_Barrage-skills.yml`

### 7. Curse of Lead
- [ ] Test that the curse loads without needing a separate skill file.
- [ ] Confirm all three attributes work on boots: movement speed reduction, step height reduction, knockback resistance increase.
- [ ] Confirm the negative `STEP_HEIGHT` value does not break movement or produce console warnings.
- [ ] Confirm the `~onTimer:12 ?moving` particle line runs only while moving and does not spam too hard.
- [ ] Decide whether this should have a dedicated skill file or stay fully inline in the enchantment file.

Files:
- `enchantments/armor/Curse_Of_Lead.yml`

### 8. Curse of Embers
- [ ] Check whether `@@EntitiesInRadius{r=<math.enchant_level+2>;...}` supports placeholders/math in the radius field in the installed MythicMobs version.
- [ ] Confirm the double `@@` targeter syntax is intentional and works in this context.
- [ ] If radius placeholders do not work, split into level-specific skills or use fixed radius values.
- [ ] Confirm self-ignite and nearby entity ignite durations are balanced.
- [ ] Confirm particles/sound appear at the cursed wearer or damaged location as intended.

Files:
- `enchantments/armor/Curse_Of_Embers.yml`
- `skills/armor/Curse_Of_Embers-skills.yml`

## Documentation / Pack Cleanup Completed

- [x] Removed the list-only `Death Bringer` entry from `Enchantment_List.md`.
- [x] Left missing/list-only enchants missing instead of creating placeholders.
- [x] Updated Dragon Heart max-health bonus from `enchant_level * 4` to `enchant_level * 2`.
- [x] Updated README category counts to match the actual enchantment files.
- [x] Updated `Enchantment_List.md` total and category counts to match the actual enchantment files.
- [x] Updated `packinfo.yml` version to `1.0.1`.

## Known Missing/List-Only Entries Removed From Documentation

These were listed in the docs but did not have matching enchantment files, so they were removed from the public list/counts rather than created:

- `Death Bringer`
- `Prospector`
- `Featherweight`
- `Iron Will`
- `Angler's Arm`
