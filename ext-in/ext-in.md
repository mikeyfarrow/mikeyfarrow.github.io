# Dual External Input Eurorack Module

## Overview

This is a 4hp Eurorack module containing two separate high-gain pre-amps for high impedance sources like electric guitars.

The circuit is heavily inspired by the pre-amp section of the Mutable Instruments module *Ears* (see [the schematic for MI's Ears](https://pichenettes.github.io/mutable-instruments-documentation/modules/ears/downloads/ears_v40.pdf)). There are a couple differences worth noting:

- To fit the circuit on a single PCB with through-hole components, I have jettisoned all the safety diodes:
  - no reverse polarity protection for the power
  - no diode limiters for the input like you see in the *Ears* schematic
- This schematic uses different values for the audio coupling capacitors than *Ears*: 0.1µF instead of 4.7µF.
  - MI's frequency range is unnecessarily wide for our application and it is easier to find capacitors in high quality materials like film if we decrease the capacitance.
  - Our **-3dB frequencies** are **1.5 Hz** on the low end and **??? Hz** on the high end.
  - If you wish to use this module to amplify CVs, you must install jumpers instead of the coupling capacitors.

## Other notes on the circuit:

- A single TL072 is used but obviously this may be substituted
- Each channel has a gain control pot
  - Max gain can be altered by using different resistor values. See schematic for details.
- The switch allows you to select between two different max gain values for channel 1
- When input 2 is unpatched, the signal from input 1 is normalled to input 2
  - This means that by default the unit will operate as an active mult with individual gain controls.

## Files/Resources

- Schematic
- BOM and mouser cart
- Renders of PCB (pop and unpop)
- 