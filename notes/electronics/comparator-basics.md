# Comparator Basics

A comparator answers a simple question:

> Is one voltage higher or lower than another reference voltage?

It is often used when an analog sensor signal needs to be converted into a digital decision.

## Basic idea

A comparator has two inputs:

- non-inverting input `+`
- inverting input `-`

The output changes state depending on which input is higher.

## Why comparators matter

Comparators are useful for:

- threshold detection
- over-voltage / under-voltage detection
- sensor fault detection
- battery monitoring
- fail-safe circuits
- converting analog conditions into logic signals

## Practical points to check

### Hysteresis
Without hysteresis, noise near the threshold can make the output switch rapidly back and forth.

### Output type
A comparator may use:

- push-pull output
- open-drain / open-collector output

These behave differently and affect how multiple signals can be combined.

### Input range
A comparator cannot always accept every voltage between ground and the supply rails. The input common-mode range must be checked in the datasheet.

## Datasheet checklist

When reading a comparator datasheet, check at least:

1. Supply-voltage range
2. Input common-mode range
3. Reference accuracy
4. Propagation delay
5. Output structure
6. Fail-safe behavior

## Next step

Study how comparators are combined with:

- pull-up resistors
- RC delay circuits
- latches
- sensor open/short detection
