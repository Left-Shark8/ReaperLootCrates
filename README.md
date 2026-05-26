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
/setcrate <name> <1-5>
/deletecrate <name>
/startcrate
```

Stand where you want a crate to spawn, then run:

```text
/setcrate Military Base 3
```

The final number sets the crate tier for that spawn. For example, `3` saves it as Tier III.

Permission:

```text
reaperlootcrates.setcrate
reaperlootcrates.deletecrate
reaperlootcrates.startcrate
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
