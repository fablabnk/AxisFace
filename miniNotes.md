Axis Fuzz plan

# TODO

- silkscreen to component values where possible
- label pin headers
- PedalLab logo

# README

As our first PedalLab project, we building an Mayer Axis Fuzz. See thread and schematic [here](https://forum.metropoulos.net/viewtopic.php?t=42896&start=15)

Key points are:
- it uses transistors we already have in stock
- We will chain resistors we have in stock to get some values required by the original circuit
	- 2M2 = 2M + 200K
	- 820K = 680K + 150K
- it will be housed in a hand-cream tin
- it has three controls: two pots and one footswitch
- the PCB will mount to the two pots
- there are two pot issues:
	1. our pots are not of same type (one 9mm, one bourns)
	2. we don't have a 2K 'drive' pot, so will use 1K instead
- the footswitch will be wired point-to-point in 'true bypass' form marked terminals on the PCB
	- see [here)](https://stinkfoot.se/archives/2233)
- same goes for the 1/4" audio jacks (it is unclear where we will mount these currently)
- the pedal will be powered a by 9V battery or DC barrel jack
- we will make use of ground and power planes
- we will spice simulate the circuit within KiCad and keep the simulation symbols in when doing the PCB design also

- do all components fit inside the tin?
- does 0.001uF need to be not ceramic? others too?
- how to do DC barrel jack - point to point

FX Return

in the original circuit their is no footswitch, instead we just have guitar input and distorted output
in our version our guitar input will go first to the footswitch, then depending on the footswitch position
	- route the input signal to the output
	- route the output of the distortion circuit to the output
