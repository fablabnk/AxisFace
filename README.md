https://www.home-wrecker.com/sili-face2.html

Pavlos' version is here: https://github.com/Sysex89/fuzzface

# Components / BOM

2 transistors, 4 resistors, 3 caps and 2 pots

# Description of the circuit

I tried to summarise the key points of the deep-dive into the fuzz-face found [here](https://www.electrosmash.com/fuzz-face).

`The circuit is a simple 2 stage amplifier with a feedback network path. It can be broken down into three parts: Input Stage, Output Stage and Feedback Network. The last block (the Feedback Network) will affect the rest of the analysis because it will influence the most important parameters: voltage gain, input impedance, output impedance and frequency response.`

## Input Stage:

- Input jack
- 2.2uF capacitor:  blocks any DC level, removing hum and protecting the pedal/guitar against dangerous DC levels
- AC128 transistor:
- 33K resistor: sets the main input stage parameters like the voltage gain, bias points, and maximum collector current

## Output Stage:

PNP Common Emitter Amplifier
variable emitter degeneration resistor (RFUZZ=1KΩ)


The output stage of the Fuzz Face circuit boosts the signal to drive the amplifier and enhances harmonic content, resulting in a distinctive, saturated fuzz effect.

Input Capacitor (C2): Blocks DC voltage while allowing AC signal to pass through.
Emitter Resistor (RE): Sets the bias point and stabilizes the transistor.
Emitter Bypass Capacitor (CE): Increases gain and frequency response.
Output Capacitor (C3): Blocks DC voltage while allowing AC signal to pass through, shaping the output frequency response.
Volume Potentiometer (RV1): Adjusts the level of the output signal

## Feedback Network:

- When the fuzz control (1KΩ pot) is set to minimum, a big amount of signal is sent back to the input, creating a big feedback loop and reducing the total pedal gain (left image below).

When the fuzz control increases the attack, the 20uF C2 cap will gradually shunt the negative feedback to the ground, thus letting the circuit operate with more gain (right image below).


# Expected behaviour of the circuit

# Transistor types

Is is important to decide first if we will use NPN or PNP transisors in our design, as this affects the overall topology of the schematic. I decided to use the 2N3906 PNP transistor, as we have a transistor kit similar to [this](https://www.amazon.com/BOJACK-General-Purpose-Transistors-Assortment/dp/B07T61SY9Y/ref=sr_1_2_sspa?crid=3CZ8I2M8Y477&dib=eyJ2IjoiMSJ9.K72wwbAF5iW2kf8H6Fox1LnOYMAHnPOKU5US_5vlfMn8DHxB5zyEE168C56UF1AWR4pkUgDK8s8D_Qz6BV7tvaUW_ADToqoFVJ2cdKOUBkSo3u3PCN5OYQ6I2IzFou0xQqVvCv1qnfxc-Z7mjKhpS5aYe4Fm7NDoV1I8iaLPPa_7kdqWA5mqpBDd1apUEIc43sA2lfgUod4YT-uKydM7tf_C24xex0AyWmWGq5bC2kc.DDjJLIM_iIoefxprtJl_gLEOM4SSovt4RaqQyJyAWJw&dib_tag=se&keywords=transistor+kit&qid=1716450756&sprefix=transistor+ki%2Caps%2C179&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1) in our lab. We should be able to easily switch them out later if we don't like the sound.



- BC108 NPN Silicon transistor (Pavlos' version)
- AC128 PNP Geranium transistor (simulatable version, see below)

In an NPN transistor, the layers are arranged as N-type semiconductor sandwiched between two layers of P-type semiconductor.
In a PNP transistor, the layers are arranged as P-type semiconductor sandwiched between two layers of N-type semiconductor.
This difference leads to opposite polarities of voltage and current flow between the emitter, base, and collector terminals for NPN and PNP transistors.

There is also a lot of mythology around geranium transistors - which are favored in guitar pedals for their warm, vintage tone, soft clipping distortion, dynamic response, and historical significance. ideal for us would be to use silicon transistors we have in our lab, 

# Simulation

https://forum.kicad.info/t/fuzz-face-tone-bender-projects-updated-05-22-23/41450

PNP

## Simulating Potentiometers

The 

I would 

Q: Is there a way to plot multiple potentiometer values side by side?

## Another approach: tuning

# Potentiometer values

We don't have 100


# Footswitch

- A range of footswitch wiring methods are described [here](https://stinkfoot.se/archives/2233)
- We will use the "better true bypass" method, as we want to make ususe the DPDT footswitches we already have in stock
- We will try to include the bypass wiring as part of the wiring of our main PCB, but if the layout doesn't make sense, we could design a mini bypass PCB
- In future we prefer to use a 3PDT, so as to also have an LED that shows when the fuzz is on or off

# Power

9V Battery

# Audio Ins/Outs

Q: How do they mount?

# PCB Layout

Q: What case will we use?
A: A recycled metal tin

# JLCPCB Plugin

# Misc

Lots of other circuit resources: https://electronotes.netfirms.com/free.htm