# Complete ZMK Layout Plan for Typed Split Keyboard

## Overview
- **Keyboard:** Typed Split (seeeduino_xiao_ble)
- **Layout Base:** Enthium v11 (programmer-optimized)
- **Layers:** BASE (Enthium), SYM (Numbers/Symbols), FN (Functions/Navigation)
- **Special:** Mod-tap shift on Z, Bluetooth device switching

---

## BASE LAYER (Enthium v11)

```
LEFT SIDE                              RIGHT SIDE
┌────┬────┬────┬────┬────┬────┐      ┌────┬────┬────┬────┬────┬────┐
│ESC │ SFT│ Y  │ O  │ U  │ =  │      │ Q  │ L  │ D  │ P  │ X  │DEL │  Row 1
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│ W  │ C  │ I  │ A  │ E  │ ;  │      │ K  │ H  │ T  │ N  │ S  │ F  │  Row 2
├────┼────┼────┼────┼────┼────┤      ├────┼────┼────┼────┼────┼────┤
│CTRL│ '  │ -  │ ,  │ .  │ /  │      │ J  │ M  │ G  │ B  │ V  │ALT │  Row 3
└────┴────┴────┴────┴────┴────┘      └────┴────┴────┴────┴────┴────┘
      ┌────┬────┬────┐                ┌────┬────┬────┐
      │ CMD│ SYM│ SPC│                │ R  │ FN │ ENT│  Thumb row
      └────┴────┴────┘                └────┴────┴────┘

SFT = homerow_mod LSHIFT Z (hold for shift, tap for Z)
```

### Base Layer Bindings

**Row 1:**
- Left: `&kp ESC, &homerow_mod LSHIFT Z, &kp Y, &kp O, &kp U, &kp EQUAL`
- Right: `&kp Q, &kp L, &kp D, &kp P, &kp X, &kp DEL`

**Row 2:**
- Left: `&kp W, &kp C, &kp I, &kp A, &kp E, &kp SEMI`
- Right: `&kp K, &kp H, &kp T, &kp N, &kp S, &kp F`

**Row 3:**
- Left: `&kp LCTRL, &kp SQT, &kp MINUS, &kp COMMA, &kp DOT, &kp FSLH`
- Right: `&kp J, &kp M, &kp G, &kp B, &kp V, &kp LALT`

**Thumb Cluster:**
- Left: `&kp LGUI, &mo SYM, &kp SPACE`
- Right: `&kp R, &mo FN, &kp RET`

---

## SYM LAYER (Numbers & Symbols for Coding)

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

× = trans (pass-through to base)
```

### SYM Layer Bindings

**Row 1:**
- Left: `&kp N1, &kp N2, &kp N3, &kp N4, &kp N5, &kp N6`
- Right: `&kp N7, &kp N8, &kp N9, &kp N0, &kp MINUS, &kp EQUAL`

**Row 2:**
- Left: `&kp LPAR, &kp LBKT, &kp LBRC, &kp LT, &kp QUESTION, &trans`
- Right: `&kp GRAVE, &kp GT, &kp RBRC, &kp RBKT, &kp RPAR, &kp DQT`

**Row 3:**
- Left: `&kp EXCL, &kp AT, &kp HASH, &kp DLLR, &kp PRCNT, &kp CARET`
- Right: `&kp AMPS, &kp KP_MULTIPLY, &kp PLUS, &kp FSLH, &kp PIPE, &kp BSLH`

**Thumb Cluster:**
- Left: `&kp LGUI, &mo SYM, &kp SPACE`
- Right: `&kp COLON, &mo FN, &kp RET`

---

## FN LAYER (Functions, Navigation & System)

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

× = trans (pass-through to base)
BOOT = &bootloader
BT1/BT2/BT3 = &bt BT_SEL 0/1/2
H/J/K/L = vim navigation keys
```

### FN Layer Bindings

**Row 1:**
- Left: `&kp F1, &kp F2, &kp F3, &kp F4, &kp F5, &kp F6`
- Right: `&kp F7, &kp F8, &kp F9, &kp F10, &kp F11, &kp F12`

**Row 2:**
- Left: `&kp H, &kp J, &kp K, &kp L, &trans, &trans`
- Right: `&kp HOME, &kp UP, &kp END, &kp PG_UP, &trans, &trans`

**Row 3:**
- Left: `&bootloader, &bt BT_SEL 0, &bt BT_SEL 1, &bt BT_SEL 2, &trans, &trans`
- Right: `&kp LEFT, &kp DOWN, &kp RIGHT, &kp PG_DN, &trans, &kp DEL`

**Thumb Cluster:**
- Left: `&kp LGUI, &mo SYM, &kp SPACE`
- Right: `&kp R, &mo FN, &kp RET`

---

## Notes & Implementation

- **Shift Behavior:** Z key uses `homerow_mod LSHIFT Z` (balanced flavor, 150ms idle requirement)
- **Layer Taps:** Already defined in behaviors: `lt_sym_spc`, `lt_fn_bspc` (for future use)
- **Bluetooth:** 3 device slots (BT1, BT2, BT3) on FN layer for quick switching
- **Bootloader:** Accessible via FN+BOOT for easy firmware flashing
- **Navigation:** vim keys (hjkl) on FN layer, plus arrow keys on right side
