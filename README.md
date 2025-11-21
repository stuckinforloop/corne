# ZMK Keyboard Configuration - Typed Split Keyboard

Custom ZMK firmware configuration for a split keyboard with Seeeduino XIAO BLE microcontrollers, featuring the Enthium v11 layout optimized for programmers.

## Keyboard Layout

### Overview
- **Hardware:** Typed Split (seeeduino_xiao_ble)
- **Layout:** QWERTY (standard)
- **Layers:** 4 (BASE, NUM, SYM, FN)
- **Special Features:** Hold Space for numbers, Bluetooth device switching, optimized symbol layer for coding

---

## BASE LAYER (QWERTY)

```
LEFT SIDE                              RIGHT SIDE
┌────┬────┬────┬────┬────┬────┐      ┌────┬────┬────┬────┬────┬────┐
│TAB │ Q  │ W  │ E  │ R  │ T  │      │ Y  │ U  │ I  │ O  │ P  │BSPC│  Row 1
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│CTRL│ A  │ S  │ D  │ F  │ G  │      │ H  │ J  │ K  │ L  │ ;  │ '  │  Row 2
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│SHFT│ Z  │ X  │ C  │ V  │ B  │      │ N  │ M  │ ,  │ .  │ /  │SHFT│  Row 3
└────┴────┴────┴────┴────┴────┘      └────┴────┴────┴────┴────┴────┘
      ┌────┬────┬────┐                ┌────┬────┬────┐
      │ESC │ SYM│SPC*│                │RET │ FN │ CMD│  Thumb row
      └────┴────┴────┘                └────┴────┴────┘

* Hold Space for NUM layer, tap for space bar
```

**Key Features:**
- Standard QWERTY layout for familiarity
- Familiar modifier positions: CTRL on left, SHIFT on both sides
- Backspace on right top corner for easy access
- **Hold Space (thumb) to access numbers on NUM layer**
- Symbols on SYM layer optimized for coding

---

## NUM LAYER (Numbers)

```
LEFT SIDE                              RIGHT SIDE
┌────┬────┬────┬────┬────┬────┐      ┌────┬────┬────┬────┬────┬────┐
│TAB │ 1  │ 2  │ 3  │ 4  │ 5  │      │ 6  │ 7  │ 8  │ 9  │ 0  │BSPC│  Row 1
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│CTRL│    │    │    │    │    │      │    │    │    │    │    │ '  │  Row 2
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│SHFT│    │    │    │    │    │      │    │    │    │    │    │SHFT│  Row 3
└────┴────┴────┴────┴────┴────┘      └────┴────┴────┴────┴────┴────┘
      ┌────┬────┬────┐                ┌────┬────┬────┐
      │ESC │ SYM│SPC │                │RET │ FN │ CMD│  Thumb row
      └────┴────┴────┘                └────┴────┴────┘
```

**Key Features:**
- Access by holding Space from BASE layer
- Numbers 1-0 on QWERTY row (Q-O on first row, plus 0 on P)
- Modifiers (CTRL, SHIFT) still available for combinations like Ctrl+1,2,3,4 for window switching
- Quick access without SYM layer overhead

---

## SYM LAYER (Symbols)

```
LEFT SIDE                              RIGHT SIDE
┌────┬────┬────┬────┬────┬────┐      ┌────┬────┬────┬────┬────┬────┐
│ !  │ @  │ #  │ $  │ %  │ ^  │      │ &  │ *  │ +  │ -  │ =  │ \  │  Row 1
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│ (  │ )  │ [  │ ]  │ {  │ }  │      │ ;  │ :  │ ,  │ .  │ <  │ >  │  Row 2
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│ ~  │ `  │ "  │ '  │ /  │ |  │      │    │    │    │    │    │    │  Row 3
└────┴────┴────┴────┴────┴────┘      └────┴────┴────┴────┴────┴────┘
      ┌────┬────┬────┐                ┌────┬────┬────┐
      │ESC │ SYM│ SPC│                │RET │ FN │ CMD│  Thumb row
      └────┴────┴────┘                └────┴────┴────┘
```

**Key Features (Optimized for Coding):**
- **Row 1:** Logic & math operators: `! @ # $ % ^ & * + - = \`
- **Row 2:** Bracket pairs & punctuation (grouped for muscle memory): `( ) [ ] { } ; : , . < >`
- **Row 3:** Quotes & slashes: `~ ` " ' / |`
- All brackets grouped together for programming efficiency
- Semicolons and colons for statement/label endings
- Common operators always at your fingertips

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

1. **BASE_layer** - Primary QWERTY layout with space as NUM layer access
2. **NUM_layer** - Numbers on QWERTY row (hold Space)
3. **SYM_layer** - Symbols optimized for coding (hold SYM thumb key)
4. **FN_layer** - Functions and navigation (hold FN thumb key)

Each layer is fully commented with ASCII diagrams for easy reference.

---

## Technical Details

### Space Key Behavior
The Space key implements a layer-tap (hold-tap) behavior:
- **Tap:** Types space
- **Hold:** Activates NUM layer for quick number access
- Flavor: `tap-preferred` for natural typing feel

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