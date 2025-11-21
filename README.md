# ZMK Keyboard Configuration - Typed Split Keyboard

Custom ZMK firmware configuration for a split keyboard with Seeeduino XIAO BLE microcontrollers, featuring the Enthium v11 layout optimized for programmers.

## Keyboard Layout

### Overview
- **Hardware:** Typed Split (seeeduino_xiao_ble)
- **Layout:** QWERTY (standard)
- **Layers:** 3 (BASE, SYM, FN)
- **Special Features:** Bluetooth device switching, number & symbol access on SYM layer

---

## BASE LAYER (QWERTY)

```
LEFT SIDE                              RIGHT SIDE
┌────┬────┬────┬────┬────┬────┐      ┌────┬────┬────┬────┬────┬────┐
│TAB │ Q  │ W  │ E  │ R  │ T  │      │ Y  │ U  │ I  │ O  │ P  │BSPC│  Row 1
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│CTRL│ A  │ S  │ D  │ F  │ G  │      │ H  │ J  │ K  │ L  │ ;  │ '  │  Row 2
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│SPC │ Z  │ X  │ C  │ V  │ B  │      │ N  │ M  │ ,  │ .  │ /  │SHFT│  Row 3
└────┴────┴────┴────┴────┴────┘      └────┴────┴────┴────┴────┴────┘
      ┌────┬────┬────┐                ┌────┬────┬────┐
      │ESC │ SYM│ CMD│                │RET │ FN │ OPT│  Thumb row
      └────┴────┴────┘                └────┴────┴────┘
```

**Key Features:**
- Standard QWERTY layout for familiarity
- Familiar modifier positions: CTRL on left, SHIFT on both sides
- Backspace on right top corner, Delete on right thumb for easy access
- Numbers & symbols on SYM layer (no need for number row)

---

## SYM LAYER (Numbers & Symbols)

```
LEFT SIDE                              RIGHT SIDE
┌────┬────┬────┬────┬────┬────┐      ┌────┬────┬────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │ 5  │ 6  │      │ 7  │ 8  │ 9  │ 0  │ -  │ =  │  Row 1
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│ (  │ [  │ {  │ <  │ ?  │ ×  │      │ `  │ >  │ }  │ ]  │ )  │ "  │  Row 2
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│ !  │ @  │ #  │ $  │ %  │ ^  │      │ &  │ *  │ +  │ /  │ |  │ \  │  Row 3
└────┴────┴────┴────┴────┴────┘      └────┴────┴────┴────┴────┴────┘
      ┌────┬────┬────┐                ┌────┬────┬────┐
      │ CMD│ SYM│ SPC│                │ :  │ FN │ ENT│  Thumb row
      └────┴────┴────┘                └────┴────┴────┘

× = trans (pass-through to base layer)
```

**Key Features:**
- Numbers 1-9, 0 on row 1 for quick number access
- All bracket types: (), [], {}, <> for coding needs
- Question mark for ternary operators (condition ? true : false)
- Backtick for shell commands and template literals
- Colon on right thumb for vim commands (:wq, :q, :set, etc.)
- Complete operator symbols: !, @, #, $, %, ^, &, *, +, /, |, \
- Pre-shifted symbols (no shift needed on this layer)

---

## FN LAYER (Functions & Navigation)

```
LEFT SIDE                              RIGHT SIDE
┌────┬────┬────┬────┬────┬────┐      ┌────┬────┬────┬────┬────┬────┐
│ F1 │ F2 │ F3 │ F4 │ F5 │ F6 │      │ F7 │ F8 │ F9 │F10 │F11 │F12 │  Row 1
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│ H  │ J  │ K  │ L  │ ×  │ ×  │      │HOME│ ↑  │END │PGUP│ ×  │ ×  │  Row 2
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│BOOT│ BT1│ BT2│ BT3│ ×  │ ×  │      │ ←  │ ↓  │ →  │PGDN│ ×  │DEL │  Row 3
└────┴────┴────┴────┴────┴────┘      └────┴────┴────┴────┴────┴────┘
      ┌────┬────┬────┐                ┌────┬────┬────┐
      │ CMD│ SYM│ SPC│                │ R  │ FN │ ENT│  Thumb row
      └────┴────┴────┘                └────┴────┴────┘

× = trans (pass-through to base layer)
```

**Key Features:**
- F1-F12 function keys for system shortcuts and applications
- vim navigation keys (hjkl) for alternative movement on left side
- Arrow keys (↑, ↓, ←, →) on right side
- Navigation keys: Home, End, Page Up, Page Down
- Bootloader key for easy firmware flashing without hardware reset
- 3 Bluetooth device slots (BT1, BT2, BT3) for quick switching between paired devices
- Delete key on right bottom corner for quick access

---

## Building & Flashing

### GitHub Actions
This repository uses **GitHub Actions** for automated firmware builds. Firmware artifacts are generated for both left and right keyboard halves on each push.

---

## Configuration Files

- **`config/typed.keymap`** - Keymap definitions for all three layers
- **`config/typed.conf`** - Keyboard configuration settings and features
- **`config/west.yml`** - ZMK module manifest for dependencies
- **`boards/shields/typed/`** - Hardware definitions, overlays, and device tree files

---

## Customization

To modify the keyboard layout, edit `config/typed.keymap`:

1. **BASE_layer** - Primary Enthium v11 layout (default)
2. **SYM_layer** - Numbers and symbol access (hold SYM thumb key)
3. **FN_layer** - Functions and navigation (hold FN thumb key)

Each layer is fully commented with ASCII diagrams for easy reference.

---

## Technical Details

### Shift Behavior
The Z key implements a mod-tap with the `balanced` flavor:
- **Hold:** Activates SHIFT modifier
- **Tap:** Types Z
- **Idle requirement:** 150ms to prevent accidental modifiers during fast typing

### Bluetooth
Quick device switching with 3 pre-defined BT slots on FN layer (BT1, BT2, BT3).

### Hardware
- **Board:** Seeeduino XIAO BLE (ARM Cortex-M4)
- **Display:** SSD1306 128x32 OLED (shows current layer)
- **Connectivity:** Bluetooth 5.2 wireless
- **Power:** Li-po battery support

---

## References

- [Enthium Layout](https://github.com/sunaku/enthium) - Optimized keyboard layout
- [ZMK Documentation](https://zmk.dev) - ZMK firmware documentation
- [Seeeduino XIAO BLE](https://wiki.seeedstudio.com/XIAO_BLE/) - Hardware documentation