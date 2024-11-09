# Daveys-Deadband
My original design for a parallel wavefolder. It works using Don Buchla's deadband approach to parallel wavefolding.

The input wave is sliced horizontally into separate voltage bands. Alternating bands are then inverted, and all the bands are mixed back together.
At low amplitude, the input will occupy just one band and will pass through unchanged.
As the gain is increased, the peaks of the wave spill over into the neighbouring inverted bands.
Increasing the wave further will push the wave back into a non-inverted band, and so on.

Where Buchla used op-amps to separate the bands, I'm using diodes to clamp the signal between reference voltages derived from a resistor ladder.
This results in a simpler circuit that's a little easier to parse.

The fold amount is controlled by the amplitude of the input. So, to add voltage control, it just needs a VCA attached to the input.
Buchla mixed in a DC offset to control the asymmetry of the wave. 
To do this, replace the audio's input buffer with a simple op-amp mixer, and add another input for control voltage.

