# Push-Pull vs Open-Drain Outputs

These two output structures may represent the same logical HIGH/LOW information, but electrically they behave very differently.

## Push-Pull

A push-pull output actively drives the signal both HIGH and LOW.

### Advantages

- Fast transitions
- Strong HIGH and LOW drive
- Usually no external pull-up resistor required

### Caution

Two push-pull outputs should generally not be directly tied together.

If one tries to drive HIGH while another drives LOW, a large current can flow.

---

## Open-Drain

An open-drain output normally has only the transistor that can pull the output LOW.

When the transistor is OFF, the output becomes electrically high-impedance rather than actively HIGH.

A pull-up resistor is therefore commonly used.

```text
VCC
 |
 R
 |
 +------ signal
 |
open-drain output
 |
GND
```

### Output states

- transistor ON → LOW
- transistor OFF → pulled HIGH by the resistor

## Why open-drain is useful

Multiple open-drain outputs can often share one line.

If any device pulls the line LOW, the shared line becomes LOW.

This is useful for:

- fault signals
- interrupt lines
- wired logic
- buses such as I²C

## Comparison

| Property | Push-Pull | Open-Drain |
|---|---|---|
| Drives HIGH | Yes | No |
| Drives LOW | Yes | Yes |
| Pull-up usually required | No | Yes |
| Multiple outputs can share one line easily | No | Often yes |

## Engineering takeaway

Before interpreting a digital output, ask:

> Is the output actively driven, or is it only capable of pulling the line LOW?

That detail can completely change the circuit logic.
