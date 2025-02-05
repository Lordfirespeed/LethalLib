# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## LethalLib [0.12.0]

> [!WARNING]
> Includes potentially breaking changes!

### Added
- Ability to pass rarity dictionaries for registering scrap items.

### Changed
- Cleaned up git repo slightly.  
- Internal changes to the way scrap items are added to levels.  
- When registering the same scrap item multiple times it will be merged with the previous ones.  

## LethalLib [0.11.2]

### Fixed

- (to verify) Issue with Terminal, where when a mod was disabling a shop item,
  all the shop items after it would mess up their orders.

## LethalLib [0.11.1]

### Changed

- RegisterNetworkPrefab now checks prefabs to avoid registering duplicates

## LethalLib [0.11.0]

### Added

- Module: PrefabUtils
  - Method: ClonePrefab()
  - Method: CreatePrefab()
- Method: NetworkPrefabs.CreateNetworkPrefab()
  - Creates a network prefab programmatically and registers it with the network manager.
- Method: NetworkPrefabs.CloneNetworkPrefab()
  - Clones a network prefab programmatically and registers it with the network manager.

### Changed

- Behaviour for Items module
  - When a scrap item is registered as a shop item, the LethalLib
    will now automatically create a copy and switch the IsScrap value.
  - When a shop item is registered as a scrap, the LethalLib will now
    automatically create a copy, assign sell values, set IsScrap to true, and add a scan node.

## LethalLib [0.10.4]

### Added

- Additional error logging and prevented an exception when
  a custom dungeon RandomMapObject had an invalid prefab assigned.

### Removed

- LethalExpansion soft dependency as it caused more issues than it was worth.

## LethalLib [0.10.3]

### Added

- Soft dependency to LethalExpansion which might help compatibility(?)

### Fixed

- Fixed custom dungeon generation breaking because of Lethal Company update.

## LethalLib [0.10.1]

### Fixed

- Fixed issue with Ragdolls system where ragdolls got registered multiple times.

## LethalLib [0.10.0]

> [!WARNING]
> Includes potentially breaking changes!

### Added

- Save system patch which attempts to keep the items array in the same order,
  so that items don't change when you load an old save after mods have updated.
  - This will likely break all existing saves.
- Intellisense comments to all API functions.
- Method: Enemies.RemoveEnemyFromLevels()
- Method: Items.RemoveScrapFromLevels()
- Method: Items.RemoveShopItem()
- Method: Items.UpdateShopItemPrice()
- Method: Unlockables.DisableUnlockable()
- Method: Unlockables.UpdateUnlockablePrice()
- Method: Weathers.RemoveWeather()
- Method: MapObjects.RemoveMapObject()
- Method: MapObjects.RemoveOutsideObject()
- Added Module: ContentLoader
  - This acts as an alternative way to register content, abstracting
    some extra stuff away such as network registry and asset loading.
- Added Module: Player
  - Method: RegisterPlayerRagdoll()
  - Method: GetRagdollIndex()
  - Method: GetRagdoll()
