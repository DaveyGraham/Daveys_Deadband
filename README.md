# Daveys_Deadband


An original design for a parallel wavefolder. It works using Don Buchla's deadband approach to parallel wavefolding.

![Screenshot (166)](https://github.com/user-attachments/assets/f6ca13f9-88ce-4b33-990b-c5e26f4059dd)

[Falstad simulation here](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWEBmAHAJmgdgGzoRmACzICcpkORICkNIJNApgLRhgBQAhjbuKehBZI1MAJCpwSNkjDx4DaOXK14RZaSSz5kbrxwoRQo8iOSw0i+B11k0BFjBl0qB+uUG7D4i+9FfwljW8noOBkRgBsLUEQbmlto6IJg+qMh+7uRBKf6ujrl+gnIhPGE0LsbUCBXxIDLB8lDYPlh5FvIQMPkBqd4GxfChfFR00SAjElJ1VgMKLF0tbZmkVHULBd1txA1wQ1HVlUIHtfWzcHU5Lun5y0TSl0s9ZEFnexKrY6irJzM2dV6OZx5ZYIagsAG9TYOSDIHa6Up8Uh8MZIuJTU5-FhEJTKVRwEF1RKDADu+hA5EERFQdApUA4pLKqGpDGZTLougZyJwkipo25dM5BhwCHCzOFBg5ZNBMWZ0oFZJIlOZivlZWQ6DovJQGtVfA1POZ+rpACcWXQjVr1eydhxTZadVqVXRZrazQx1W65c6QnbZUQZXRxVAbb7AyK3bhJN7BqGhPytWzgy7Y4mtbTo7sAEpui3nI3Woh0JDWmAIDjZrXgynnKtJ5JF4Ps+zlt20ws08QFugsYuN5s8MDoKk0cROPgIcQ-IkKGDyZDIIg4LC5QdL-3ICVw10rc2F6x7ofW5PknC2A5yPfpQQZ3SmncMVYXzWrG-b09kp9k1939-c8wiQMmSTH0TzoalvT3cDgJJQ5UVA8k+ElT5VnvL5qCQowsAOe8sOvelDgme8JgwqoKnvaoo3wsZYngmiSMMah71MdCqKMMRBHvdi6QAE3g5j4MPZIQG4pgADMuAAVwAGwAFw4Xj70EzjxEEETxOkuSFPfK8+KMVSxMk2T5NoyI+IOfT1KMrTn0Y98aIswzNPgijaNWByNOM8jEXfFz3Ks+DCJ8vVhIMjzrPGICiIPELLKcnDsN-IC-Li98oPiwRks81KUNSvMYscrKaUHeC0KEtSCvCuD71IYrMtJVpqEEhqUAOJDUGoHTmsXFj6vah9qGaso2rBUzmsE4ayWav95SmoDmqgiaoOamq8J-IqigA8liu-cAh0kBBirHAwDuvG1SUHYcTt2y7EPwo6aEO5Bx07DgAHNrskU9zD28YsFOyViCAicihFfaXtKcQ2CFICocmKwMSSbF2EHNIsGQQd8CIPgkfYdUqX9Sh0Faf8QgZSGPWBuoX3wymWFWaa6Z6iLJEZ5npglfCGdGvrYclMowHHPhiCZ-n-UOYWZrYsWxi4vm9SBvVwzlgx8CiPSldYxrwzGfjlYYc41X5PWN0kHWjc1lB+Wo0y9ausotT1rVqOZeinaMFy9bwKpnrwwUR0EMZKfoymxmImnkQ3SajD1sZY+ji244G1rw7iG64htlOJFGswM-qnO1eoUq9a8gwBEov2y9gip6MrlFbvOyA-uSPc5Cb7r5U-dvW8pamG73abu7ZgHG8EAeR-6jvNpW6wm+n4fZ8O8fpuHy9z0HM9ffAdeWqKbehruvehc2-e+7A852B1BaD8v8-D458674+r9XXuynAbB06XXOrBxC+8BXCFJASi70LD8i9lIMBQF2R3RwCsco5hYGAPLhA-aFRQEfxNCg+B4BEHYOdHieEWC-6RDgX-KccJuyzngOqFw7UFzpGFALdAsIby6AFgGf4gg5QeggLMJoiAQCiQAPZSV4lwAAtkIiSAA7OS700yimdNXVUYsiydkwfaVsm4Bh3XHoJd+zdoHnSpBggx41dEHhbnovct4hB9SUu+caDRXTNR0kxVqzjTRdRyjZaCtjBreSLIhTxdjqDTSIlAkJ81zioXOBmFxfVp7VW2iEkhSDwA-1HkAvxHAADy-9wzENIJHP+0ChHN3GB1d0oJ6AwE6CgCpu4UAcHKXgSpwYAAeqBkZcKaLwjJQlAyCBYbAXsHpzTBg9CMyAYz6mnXRg02cYzrTzNsPw3s6BSDBlOpsxZoztlRkGckSQ0yNlBAmeaIIpzgJbOuc6Uw2ykwPLuS0regZ0LVNEE2CAGU3nNKAA)


**How it works**

The input wave is sliced horizontally into separate voltage bands.
The upper and lower limits of these bands are determined by the reference voltages coming from the op-amps on the left hand column.
Alternating bands are then inverted, then all the bands are mixed back together.
At low amplitude, the input will occupy just one band and will pass through unchanged.
As the gain is increased, the peaks of the wave spill over into the neighbouring inverted bands.
Increasing the wave further will push the wave back into a non-inverted band, and so on.

Where Buchla used op-amps to separate the bands, I'm using diodes to clamp the signal between reference voltages derived from a resistor ladder.
This results in a simpler circuit that is - to my eyes - a little easier to parse.


Below: The seperated bands, measured at the 10k resistors after the diode chain.

![Screenshot (170)](https://github.com/user-attachments/assets/910cda5a-5d79-4871-9270-1e015568426b)


Below: The same bands with alternating bands inverted.

![Screenshot (171)](https://github.com/user-attachments/assets/7c63b4b7-cee6-4831-8ee4-62eae532ef7b)

Each of these voltage bands will have it's own offset voltage. These positive and negative offsets will negate each other once summed together.
The gives us a waveform that has been 'collapsed down', as pictured below. The resultant composite waveform has been overlayed in yellow. (Note, this isn't a terribly scientific graph, I've just manually lined up the input bands with the output waves)

![Screenshot (172)](https://github.com/user-attachments/assets/df1beb70-c474-4439-95be-c61b2aa229eb)

**Voltage control**

The fold amount is controlled by the amplitude of the input. So, to add voltage control, it just needs a VCA attached to the input. Fihdi has developed a great version of this with a VCA included, enabling CV control. You can find that here: [Wavefolder with VCA](https://github.com/Fihdi/Eurorack/tree/main/Fold2).

**Symmetry control**

Buchla would mix in a DC offset to control the asymmetry of the wave. 
To do this, replace the audio's input buffer with a summing amplifier, and add another input for control voltage.

**Component selection**

Resistor values were all chosen semi-arbitrarily and there is definitely room for improvement there.

I'd advise using diodes with a low forward voltage drop, e.g. Schottky diodes for the clipping chain. 
I've had a lot of success with using 1N5817 diodes, as these give a very clean reflection. 1N4148 diodes on the other hand will clip for a while before reflecting, which may be more apt for distortion effects.

**Increasing number of folds**

Without using additional op amps, an extra stage can be tapped at the bottom and top of the diode ladder using only 2 extra diodes, and six extra resistors, as pictured below. The gain/feedback resistor should be modified to compensate for this, as all the bands will now have a smaller width.

![Screenshot (180)](https://github.com/user-attachments/assets/61605926-f0b2-4385-ade6-72f411a5605c)

More additional bands can be added between the +/-5v reference voltages using op-amps to increase the amount of folds. More bands seemingly can't be added indefinitely, and this might only work to a certain extent before too much voltage is lost from the diodes' forward voltages. 

![Screenshot (182)](https://github.com/user-attachments/assets/70435ce6-d7d4-48cc-a4c0-ba0ba8d58219)

**Working with different input amplitudes**

To ensure that the input signal is distibuted across as many of the available bands as are available, the reference voltages at either end of the resistor voltage divider (+/-5v in my example) should be changed according to your input signal's amplitude.

If the input signal's amplitude is unknown, then some form of peak detection could be used to set the upper and lower limits of the bands.
Below is a very primative example of how peak detection could be used for this (untested IRL, and does not reset when presented with a signal smaller than a previous one, thought the capacitors will steadily leak until it reaches this newer value). 

A more sophisticated implementation could digitally sample and average the signal over time, and generate a voltage accordingly.  

![Screenshot (183)](https://github.com/user-attachments/assets/1f3c168e-4d3a-4948-91a3-eacf3f885714)


For more info on Buchla's design, and to see how mine compares, check out [Aaron Lanterman's video here](https://www.youtube.com/watch?v=Yd3hxfaPqPA).
