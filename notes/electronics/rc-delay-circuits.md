# RC Delay Circuits

An RC circuit can create a simple time-dependent voltage using a resistor and capacitor.

## Core idea

A capacitor cannot change its voltage instantaneously.

When it charges through a resistor, its voltage changes gradually.

For a simple charging circuit:

`V(t) = V_final × (1 - e^(-t/RC))`

The product

`τ = RC`

is called the **time constant**.

## What the time constant means

After approximately:

- 1τ → 63.2% of the final value
- 2τ → 86.5%
- 3τ → 95.0%
- 5τ → 99.3%

This does **not** mean a digital delay is always exactly `RC`.

The actual switching time depends on the threshold voltage of the next stage.

## RC delay + comparator

A common structure is:

`Input → RC network → Comparator → Digital output`

The RC network generates a gradually changing voltage, while the comparator decides when that voltage crosses a threshold.

This converts an analog charging curve into an approximate digital delay.

## Why a diode may be added

A diode can make charging and discharging behave differently.

For example:

- slow charging through a resistor
- fast discharging through a diode

This is useful when a condition must persist for a certain time before triggering, but the circuit should reset quickly when the condition disappears.

## Limitations

RC delays depend on:

- resistor tolerance
- capacitor tolerance
- temperature
- leakage current
- comparator threshold accuracy

For precise timing, a dedicated timer or digital implementation may be better.

## Engineering takeaway

Do not identify a delay only from `R × C`.

Always check:

1. Initial voltage
2. Charging/discharging path
3. Threshold voltage
4. Component tolerances
5. Reset behavior
