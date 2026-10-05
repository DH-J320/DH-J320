# Pull-Up and Pull-Down Resistors

Digital inputs should normally have a defined state.

If an input is disconnected and has no defined path to HIGH or LOW, it may become **floating**.

A floating input can respond unpredictably to noise.

## Pull-Up

A pull-up resistor connects the signal weakly to the supply voltage.

```text
VCC
 |
 R
 |
 +------ Input
 |
Switch
 |
GND
```

- switch open → HIGH
- switch closed → LOW

## Pull-Down

A pull-down resistor connects the signal weakly to ground.

```text
VCC
 |
Switch
 |
 +------ Input
 |
 R
 |
GND
```

- switch open → LOW
- switch closed → HIGH

## Why use a resistor?

The resistor sets the default logic level while limiting current when another device forces the signal to the opposite state.

## Typical uses

- buttons and switches
- microcontroller inputs
- open-drain outputs
- enable pins
- fault signals
- bus lines

## Engineering takeaway

Whenever a digital signal can become disconnected or high-impedance, ask:

> What defines its state when nobody is actively driving it?
