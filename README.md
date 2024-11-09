# Daveys-Deadband
My original design for a parallel wavefolder. It works using Don Buchla's deadband approach to parallel wavefolding.
![Screenshot (166)](https://github.com/user-attachments/assets/f6ca13f9-88ce-4b33-990b-c5e26f4059dd)

The input wave is sliced horizontally into separate voltage bands. Alternating bands are then inverted, and all the bands are mixed back together.
At low amplitude, the input will occupy just one band and will pass through unchanged.
As the gain is increased, the peaks of the wave spill over into the neighbouring inverted bands.
Increasing the wave further will push the wave back into a non-inverted band, and so on.

Where Buchla used op-amps to separate the bands, I'm using diodes to clamp the signal between reference voltages derived from a resistor ladder.
This results in a simpler circuit that's a little easier to parse.

![Screenshot (170)](https://github.com/user-attachments/assets/910cda5a-5d79-4871-9270-1e015568426b)

The seperated bands, measured at the 10k resistors after the diode chain.

![Screenshot (171)](https://github.com/user-attachments/assets/7c63b4b7-cee6-4831-8ee4-62eae532ef7b)

The same bands, with every other band inverted. Note that positive and negative offsets will cancel each other out,
and that the final waveform is a version that has been 'collapsed down'.

The fold amount is controlled by the amplitude of the input. So, to add voltage control, it just needs a VCA attached to the input.

Buchla would mix in a DC offset to control the asymmetry of the wave. 
To do this, replace the audio's input buffer with a summing amplifier, and add another input for control voltage.

Resistor values were all chosen semi-arbitrarily and there is definitely room for improvement there.
