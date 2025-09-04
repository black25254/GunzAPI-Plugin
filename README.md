# GunzAPI - Advanced Weapon System Plugin

A comprehensive weapon system plugin for Minecraft 1.20.4 (If U Want Another Version Create New Issue) that allows custom weapons based on CustomModelData with advanced features. Supports multiple weapons per material using dot notation (e.g., CARROT_ON_A_STICK.1, CARROT_ON_A_STICK.2).

## Features

- **Custom Weapon System**: Define weapons using CustomModelData in `gunz.yml`
- **Multiple Fire Modes**: Auto, Semi-Auto, and Safe modes
- **Scoping System**: Hold Shift to scope with custom model changes and movement slowdown
- **Reload System**: Press Left-Click (swap hands) to reload with configurable reload times
- **Ammo & Magazine System**: Scoreboard-based ammo and magazine tracking
- **Action Bar Display**: Shows weapon name, ammo count, and magazine count
- **Sound Effects**: Configurable fire and reload sounds (supports custom sounds)
- **Visual Effects**: Muzzle flash, bullet trails, and hit effects
- **Recoil System**: Configurable weapon recoil
- **Game Mode Support**: Configure which game modes can use weapons and have infinite ammo

## Installation

1. Download the plugin JAR file
2. Place it in your server's `plugins` folder
3. Start/restart your server
4. Configure weapons in `plugins/GunzAPI/gunz.yml`

## Configuration

### gunz.yml Structure

```yaml
MATERIAL_NAME.ID:
  custom_model_data: 1                    # Normal weapon model
  shift-custom_model_data: 2              # Scoped weapon model
  shift_slow: 1                           # Movement slowdown when scoped (1 = half speed)
  recoil: 0.1                            # Recoil strength
  reload_time: 1                         # Reload time in seconds
  fire: "semi-auto"                      # Fire mode: auto, semi-auto, safe
  fire_sound: "minecraft:entity.trident.throw"  # Fire sound
  fire_effect: "fire"                    # Muzzle flash effect: fire, explosion, smoke
  fire_range: 5                          # Weapon range in blocks
  can_pass_entities: true                # Can bullets pass through entities
  reload_sound: "minecraft:entity.trident.pickup"  # Reload sound
  gamemode_can_use: "creative,survival"  # Game modes that can use this weapon
  gamemode_inf_ammo: "creative"          # Game modes with infinite ammo
```

### Example Weapons

The plugin comes with example weapons using dot notation:
- **CARROT_ON_A_STICK.1** (Pistol): Semi-auto, short range
- **CARROT_ON_A_STICK.2** (Assault Rifle): Full-auto, medium range
- **CARROT_ON_A_STICK.3** (Sniper Rifle): Semi-auto, long range with custom sounds

Multiple weapons can share the same material with different IDs for organization.

## Usage

### For Players

1. **Firing**: Right-click to fire (hold for auto weapons)
2. **Scoping**: Hold Shift to scope (changes weapon model and slows movement)
3. **Reloading**: Press Left-Click to reload (uses magazine and cant shoot)
4. **Running**: Hold Ctrl to run (changes weapon model and cant shoot and reload)
6. **Weapon Info**: Weapon name, ammo, and magazines shown in action bar

### For Admins

- `/gunz reload` - Reload configuration
- `/gunz help` - Show help message
- `/gunz give <player> <material> <id>` - Give weapon by material and ID
  - Example: `/gunz give @s carrot_on_a_stick 1` - Gives CARROT_ON_A_STICK.1 weapon
  - Example: `/gunz give @s carrot_on_a_stick 2` - Gives CARROT_ON_A_STICK.2 weapon

## Custom Sounds

To use custom sounds, set the sound value to `custom:sound_name` in the configuration. You'll need a resource pack with the custom sounds.

## Scoreboard Integration

The plugin uses scoreboards to track:
- `gunz_ammo` - Current ammo count
- `gunz_magazines` - Available magazines

## Support

For issues and feature requests, please create new issue.
