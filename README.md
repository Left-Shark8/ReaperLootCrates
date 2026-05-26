# ReaperLootCrates

RocketMod Unturned plugin that randomly spawns configurable tiered loot crates.

## Install

Drop this into your server's Rocket folder:

```text
Rocket\
  Plugins\
    ReaperLootCrates.dll
```

Restart the server once so Rocket creates the config.

## Commands

```text
/setcrate <name>
```

Stand where you want a crate to spawn, then run:

```text
/setcrate Military Base
```

Permission:

```text
reaperlootcrates.setcrate
```

## Config

Main settings:

```xml
<CrateBarricadeId>1374</CrateBarricadeId>
<SpawnIntervalSeconds>3600</SpawnIntervalSeconds>
<SpawnChancePercent>50</SpawnChancePercent>
<SpawnOnLoad>false</SpawnOnLoad>
<AnnouncementFormat>A Tier {tier} Loot Crate has Spawned at {location}</AnnouncementFormat>
```

`CrateBarricadeId` should be a storage barricade item ID.

Loot tiers are configurable in the generated config. Tiers I-V support:

```text
Name
Weight
MinItems
MaxItems
Items
```

Higher `Weight` means that tier is more likely to spawn.
