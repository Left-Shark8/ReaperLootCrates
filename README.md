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
/setcrate <name> [1-5]
/deletecrate <name>
/startcrate
```

Stand where you want a crate to spawn, then run:

```text
/setcrate Military Base 3
```

The final number is optional. Without it, the spawn uses a random weighted tier. For example, `3` saves it as Tier 3.

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
<SpawnChancePercent>100</SpawnChancePercent>
<SpawnOnLoad>false</SpawnOnLoad>
<AnnouncementFormat>A Tier {tier} Loot Crate has Spawned at {location}</AnnouncementFormat>
<CountdownAnnouncementsEnabled>true</CountdownAnnouncementsEnabled>
<CountdownAnnouncementFormat>Loot Crate spawning in {minutes} minutes</CountdownAnnouncementFormat>
```

Default countdown warning minutes are `10`, `5`, and `1`.

`CrateBarricadeId` should be a storage barricade item ID.

`SpawnChancePercent` controls whether the interval actually creates a crate after the countdown. Use `100` if every timer should spawn one.

Loot tiers are configurable in the generated config. Tiers 1-5 support:

```text
Name
Weight
MinItems
MaxItems
Items
```

Higher `Weight` means that tier is more likely to spawn.

## Troubleshooting

If the countdown appears but no crate spawns:

- Set `SpawnChancePercent` to `100`.
- Make sure `CrateBarricadeId` is a valid storage barricade item ID on the server.
- Use `/startcrate`; if spawning fails, the plugin logs the exact reason in console.
