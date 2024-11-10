# Daveys_Deadband


An original design for a parallel wavefolder. It works using Don Buchla's deadband approach to parallel wavefolding.

![Screenshot (166)](https://github.com/user-attachments/assets/f6ca13f9-88ce-4b33-990b-c5e26f4059dd)

[Falstad simulation here](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWEBmAHAJmgdgGzoRmACzICcpkORICkNIJNApgLRhgBQAhjbuKehBZI1MAJCpwSNkjDx4DaOXK14RZaSSz5kbrxwoRQo8iOSw0i+B11k0BFjBl0qB+uUp7joi4fFfOAiiOnoOBkRgBsLUEQbmlto6IJj+qMh+RO7kOMjJ0KkZvt4QcvKhfAguxtSVkvEgMtZJMN7oWK7eGo5Q2AWtHWDoJSE8YSBUdNHjRHT1jaXyDS3+7RkapEu9PgPbGU3w5VGV1ULHc1YLCiwp2+neWaSS1-m7-Rm5l7qjfKhUJ7-Uc6JRYsOx+ZwdB5BBpgt5wyAfEb6ECkPhTVFxKQNC42BpEJTKVRwKENYFwDgAd2R5EERFQdBpUEpyNQ9IYbNZdF0VLGuEkdMmOEk3ORgXCbLFTJ5FUy7LoQWoIrGJFpbJVUuRyHQdAFKG1GrG2v5bKNTIATnLkpBjbZ9XRLhwLbqtTq1VqoPtdE63ar5bL7WVvX6YhKEAYAwcg+Mw5a+R6HVG47rOfHA5aU7rGRHyQAlS2mmZ0U1chjyj1c+wcPO60G0uAwwT2q30EswBBVy2Mwso8Qlmak8s9ds8QZ0mjiJwVcRAz31lgweTpHDKSAIASoUhEBAQbPki2kHBF-tyfvofu7x0ow8oY4n2zHC-769EP53hh-R9X+V8N9jT8HughXMERANZVNIy-CR6zfekSwdKl0T4ACUT4EUpgBSCMLQowsGOZDcMbZkpgmSCSOwmoqmQ2oNSmWJILo8jDGoZDTEVIijDEQRkM4pkABNINYyCzyLEBeKYAAzLgAFcABsABcOH45DhMgnjBDEyTZIUpTr3SLjdKMdSJOk+TFPoyIBOOIzNNMnSdT+ZC6OskztMg6jHL+ZytLMqikOvaivNs0j+18gxAtc5CgOCkSNJcnzrwI0iwPC+LZnrfCrNE4zvLsiQHOvWDkiymyIuvUhBkwzziri3KMUg8rBBShDUGoFT2moPSaJam9BHa982OamI-j6v8iO6tgom6lS0O63luqimbqCivrCsWqDJm6hrzXqiq3y2z9R0kbdBEnAxjvA8kqUOmhdrPI7UOZU6bpO5Ap0IgBzcA7vGa0vrHHAsEbDViDAtcTrDI7e1CcQJvGMDYZnT46BYfEwm3cqtXICwiCwPEvDFOlHjADBUCwXHPmZMGG3HQQWA-SmYb+KK6YGuGniZ+GLJFZmLL62GlR-Cof39SnheoKZiFZiXZQlqHpTC0G+HwcNRbCmMpmVmjDPVkwjAF8J6zGZAhQNPhjckKZza1jqTdornVee5FdX12MjGd9iQ0mIxqJdvAaje02zvEKYqcYqniPPB2sGN5EphdqYE71j2TgTh8HZa+64nt+WJF5sxs-+PPAXpnPQpRKoXfXE4q8YqvEJVq7IEB5Jjyb2kS+sfsX2CZvu+BkC2esZuFsetvB7kXuO723ax-20fm62ifBBHxv+069h9U6kUN-vE7Bm-BvwH35Ffwe1e0vtY-Vseq-oOP0arvvn9vtGi0nqpkHIaB+DwCwcRD3MK4AwACmSfQsCbP2UgIFgS5I9ZcZ0qiRAPD9YUj0IY0EQeg0Ol5wFHUQfAjBwopBlBHOgkBSDgG-URriecsB5CDGEAgY2f9kCvTAIDaEu5dDsM9tTBUepwCeh6IgEA4kAD2Ml+JcAALZiKkgAOwUp9TM4p7QVwNP6Gm5ZLzOl9FeC689GrHjpJIaaj0TFaM-i3WB59rFDyMbAi0fUVLKXPPsS8fVOosQfO4px3U+4eUVL4oQs0-IHwMX4paYFIowOCStdKBV6zZg8ZtCqyF9rBIoSg3+-9frJIAPLgCAdksQMcQGwLES3aYKAGDpBqD0HcNSzwemacgDglS8DVLoAADwAMbsAqkgGAJRf6CKBoBQQuQFxDI9O6ESJZ3RTNgDM2wjTxkoAgEs1cg5TAtJ2bYYRKzkgbHmS0jYWyjnqPWVUC5g42h7JLPc25cFIDnMOYOJwjyPm7Oee0o+gEgkkGhHIBpRU962A4EAA)

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

Note that positive and negative offsets will negate each other once summed together.
The gives us a waveform that has been 'collapsed down', as pictured below. The resultant composite waveform has been overlayed in yellow.

![Screenshot (172)](https://github.com/user-attachments/assets/df1beb70-c474-4439-95be-c61b2aa229eb)


The fold amount is controlled by the amplitude of the input. So, to add voltage control, it just needs a VCA attached to the input.

Buchla would mix in a DC offset to control the asymmetry of the wave. 
To do this, replace the audio's input buffer with a summing amplifier, and add another input for control voltage.

Resistor values were all chosen semi-arbitrarily and there is definitely room for improvement there.

For more info on Buchla's design, and to see how mine compares, check out [Aaron Lanterman's video here](https://www.youtube.com/watch?v=Yd3hxfaPqPA).
