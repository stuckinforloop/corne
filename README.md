# Corne v3 ZMK Config

This is a ZMK firmware configuration for the Corne v3 split ergonomic keyboard using Seeeduino Xiao BLE controllers.

## Features

- Custom ergonomic key layout with home row mods
- Three layers: Base (ENTHIUM), Navigation, and Symbols
- Optimized for touch typing with modifiers on home row
- Deep sleep support for battery efficiency
- ZMK Studio integration for wireless configuration

## Keymap

### Base Layer (ENTHIUM)
```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│  Z  │  Y  │  U  │  O  │  ;  │  Q  │  L  │  D  │  P  │  X  │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┤
│A(LT)│C(CT)│I(SH)│E(GU)│  ,  │K(GU)│H(SH)│T(CT)│N(AL)│  S  │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┤
│  '  │  -  │  =  │  .  │  /  │  J  │  M  │  G  │  B  │  V  │
└─────┴─────┴─────┼─────┼─────┼─────┴─────┴─────┴─────┴─────┘
                 │ NAV │  R  │ SYM │
                 └─────┴─────┴─────┘
```
- Home row mods: A/C/I/E modifiers (Alt/Ctrl/Shift/GUI) when held, letters when tapped
- Right side mirrored: K/H/T/N modifiers

### Navigation Layer (NAV)
```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│     │     │     │     │     │     │     │     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┤
│◀◀◀  │▶▶▶  │▶‖   │■    │     │ PG↑ │ HOME│  ↑  │ END │     │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │ PG↓ │  ←  │  ↓  │  →  │     │
└─────┴─────┴─────┼─────┼─────┼─────┴─────┴─────┴─────┴─────┘
                 │     │     │     │
                 └─────┴─────┴─────┘
```

### Symbols Layer (SYM)
```
┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
│ F1  │ F2  │ F3  │ F4  │ F5  │ F6  │ F7  │ F8  │ F9  │ F10 │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┤
│  !  │  @  │  #  │  $  │  %  │  ^  │  &  │  *  │  (  │  )  │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┤
│  `  │  [  │  ]  │  (  │  )  │  1  │  2  │  3  │  +  │ F12 │
└─────┴─────┴─────┼─────┼─────┼─────┴─────┴─────┴─────┴─────┘
                 │     │     │     │
                 └─────┴─────┴─────┘
```

## Building

This configuration uses ZMK's automated build system.

### Prerequisites
- Git
- A GitHub account (for building via Actions)

### Build Process
1. Fork this repository
2. Push to your fork or manually trigger the build workflow
3. Download the firmware files from the Actions artifacts

The `build.yaml` defines the build matrix for:
- Left half: `seeeduino_xiao_ble` with `corne_xiao_v2_left` shield
- Right half: `seeeduino_xiao_ble` with `corne_xiao_v2_right` shield
- Settings reset: `seeeduino_xiao_ble` with `settings_reset` shield

### Local Development
For local development and testing:
```bash
# Clone ZMK
git clone https://github.com/zmkfirmware/zmk.git
cd zmk

# Setup west workspace
west init -l app/
west update

# Build the firmware
west build -d build/left -b seeeduino_xiao_ble -- -DSHIELD=corne_xiao_v2_left -DZMK_CONFIG=/path/to/this/config
west build -d build/right -b seeeduino_xiao_ble -- -DSHIELD=corne_xiao_v2_right -DZMK_CONFIG=/path/to/this/config
```

## Flashing

Flash the respective `.uf2` files to each half using your bootloader.

For Xiao BLE, enter bootloader mode by double-tapping the reset button.

## Configuration Details

- **Home Row Mods**: 280ms tapping term, tap-preferred flavor
- **Deep Sleep**: Enabled for power efficiency
- **ZMK Studio**: Enabled for wireless configuration
- **NFC Pins**: Configured as GPIOs

## Dependencies

This config uses ZMK firmware with the following modules:
- ZMK core
- Zephyr RTOS

See `config/west.yml` for module versions.

## Customization

Modify `config/corne.keymap` to change the key layout, or adjust timings in the behaviors section.

Device tree overlays are in `dts/layouts/corne_xiao/` for layout customizations.
