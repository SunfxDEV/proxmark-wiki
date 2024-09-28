## Hardware Testing

Since you probably bought a cheap chinese proxmark instead of the expensive ones, you might wanna test basic functionality.



## Antenna power delivery

```
hw tune
```

### LF Antenna

` 125.00 kHz ........... 25.73 V
[+] 134.83 kHz ........... 17.49 V
[+] 121.21 kHz optimal.... 26.12 V ` 

`[+] Approx. Q factor measurement
[+] Frequency bandwidth... 6.4
[+] Peak voltage.......... 7.6
[+] LF antenna............ ok`

Something between 20-45V would be perfect.

### HF Antenna

`13.56 MHz............. 16.09 V
[+]
[+] Approx. Q factor measurement
[+] Peak voltage.......... 4.7
[+] HF antenna ( ok ) `

I didnt find as much info here, but it seems 6-36V is all good.



### Card Placement

Now test how you should be placing your tags on the readers.

`hf tune` -> Move the card around a bit. Once it drops to 12-13V, thats your optimal placement.



`lf tune` -> Do the same as above and search for the lowest voltage you can get. I dont have any 125khz tags so I dont really know what optimal voltage would be.