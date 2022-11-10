# 2D Thingy
`Partly Planned` | `Shelved`

This one doesn't really have a name, but I just wanted to have a go at making a 2-dimensional language anyway, so it didnt get very far.

It was inspired by [Befunge](https://esolangs.org/wiki/Befunge) and [AsciiDots](https://esolangs.org/wiki/AsciiDots).

---

## Basics

There are two types of carriers:

### `*` Entities
Contain NSEW direction, default North (up)<br>
Charge any wire it touches<br>
Deletes if in same place as Wire

### `#` Wires
Contain charge (0, 0-cooldown, 1)<br>
Spread charge to surrounding 0 wires<br>
Deplete charge every tick

### `/\-|` Lines
Reflect/bounce Entities<br>
Carry charge, only input/output in axis

### `^v><` One way arrows
Ensure direction of both Entities and Charge<br>
Carry charge, in side and/or back, out front

### `@` Chargeable inverted xors
| Number of charged inputs | Output |
| - | - |
| 0 | 1 |
| 1 | 0 |
| 2 | 1 |
| 3 | 0 |
| 4 | 1 |

Recommend using arrows so there's no feedback

### `:;` Chargeable Capacitors
Contain energy and essentially breaks a charge flow into pulses
-   If energised, releases Charge when charged
-   If not, will consume it

---

## Example Programs

Here are some example programs written in **2D Thingy**:

### Infinite loop

The great thing about 2D Esolangs, is that loops look like loops.

```
####
#  ^##
#  # *
####
```