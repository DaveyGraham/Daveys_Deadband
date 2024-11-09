# Daveys_Deadband
An original design for a parallel wavefolder. It works using Don Buchla's deadband approach to parallel wavefolding.
![Screenshot (166)](https://github.com/user-attachments/assets/f6ca13f9-88ce-4b33-990b-c5e26f4059dd)

[Falstad simulation here](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWEBmAHAJmgdgGzoRmACzICcpkORICkNIJNApgLRhgBQAhjbuKehBZI1MAJCpwSNkjDx4DaOXK14RZaSSz5kbrxwoRQo8iOSw0i+B11k0BFjBl0qB+uXIDdh8Rc+ifjiu1vJ6DgZEYAbC1JEG5pbaOiCYvqjI-u7kxCnQaf5+jp4GcqE84TQuxtQIVQkgMiHyUNi+WK6OWQIQMJ2F+cKOTXBhfFR0MSDjElINVqXNLL1tHRbyWA3LAavbDuhiw7rlfFi11UJn9Y0LCiyp2xmdqnDI1Hd5u307qCU6o-FUc4-ahXeY2BreIoCDrPSAQFiQgYDHBJeD-ECkE5GTHxWbXcEsIhKZSwrrSVEjADu+gx4iIqDo5EEumpFVQDIYHPZdBZNNwknpEyCUA4rLGCAiHJRBl5FQQRFiHPl1FlfBIgkFDGQzNFNO1dE1+pFYoM6EgAo5ZskugATpy6Fb7SgzVBhhw7YaXZr1a6bu6nT7NcrfaEPUqFU7pSG0WG6FHNfzoyNY0JhZruUnbU6M5qmZmOAAlJ2OohwFLm10GuhIHktBCFp0IjVlpu+8v0WswetF3N0st52ulho1yv2PRgdD0mjiJx8BDiUEUssweSmTTEOGTs0WAKZrOkHAOodyIeT2t+u0H2xnE-X5luy+HhiA2-PlUPjFPiqvip0C+fuN2WsIcgmtD8rwkMtXwZc9QmpSYcQAjE+F5SZgSQ9DUKMU5BAgnDjXOaYIOmLCaiqCDamtXVJjiJDaNIwxqAg0wVWoowxFwp8OJFAATJCWKQs8UhAHimAAMy4ABXAAbAAXDg+IgoSIO4wRRIkmT5MUp8Mk42wjDU8SpLkhS6KifizkMjSTO0g1AQg2irOMrSkMoujASczTTIovgKKqTybKQoivz4AKXOIoDiNPESjK82yLj0qYgLC7ynxgpD8JS+L0Ig9KsqQ0gJwwjyYus8Kn0QiDCsEFL4NQaghPaahdIIpqUDONqiEBVD6rfIRet-ajerYaJeqEnqahOXrQNa6agLa9KJsgiZeuqkVH0ZIrXzWv9Q3ASdJAQLbkDnIrdrRakJynI7BCuw6UN1WcDBu8ATue8RdAAc32qdD3MA6piwe9eWIID51uiVDo+sJxBGpLJDhxdDlsaB0lQDQsCBjdyA2Ox0goNBPCxtBHA2G5ZVh7Vp0EFhut1cGGkBGbadY6lmaZoC4d5ZnzLarn6b4MA50FiNVRKCNJmIVnzilmXoZNFIwdCiUCIqfBogMlWGPV84BLFhgywqTwqIV43deFBizZo8z9ZeipNX1hMjAdtjFQmIw3P1vBJvenUFYZyYGYYgOjBIgXok8PkjH1yZY+j13zljs59fq+74ht8OJF5swM-gnONZBOmFZ8gxoVV3yqgQqoGLLhCHsuyAgZSY9G41IvgLs0RW76kGREA8xu5m3um5muQm666Xtq27udsemfp5HoDe6HFr2BdFqQYnO9wC3mlN5db8+73ueh3Ste6EWx7d7P3fBsu2-BYBwa7Se6nwHpKH7z9S6sHEP7wFcAYf+X0pDCm9qAyQQ8CJRAPJUcwOBYHAMepDOBEC35ZgsMKNyMDnrVykGUNB-8cFTArEjcmdAliwHgK8TBBB5SoExo4MAYFyYcCFm7CEghgxUwgDcFoiAQBiQAPbST4lwAAtkIySAA7eS31cySj-Hg2Uot0HrSdFTBRSY55NyEqDSQ41Hofzfvo5uPIT5Hl2roocWY2rKSfONJo-o2otWYsnJxdpOr2SfBPbRniBq+RCjKDx-VqAzQiiwmMoTloYWXCEtqa0qpnRCcQohv9BDAKcQAeQASrIhpBI6ZN0EI5uUxmpanlB2PIvoOAlLwGU10AAPAAxuwIqNZqm8LJsJWs9TkD8JHLYe8wNnQoAGZWFAPQemumQBAfpK5BmGFdCM0wYyFkTPQKQZZGytnzNgIsvBIyqh7MgAcjYDoNm43GbBXZ1zfSrIueeVZJyay1J3nGd8JBKlyBaBAGq7yUAcCAA)

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
