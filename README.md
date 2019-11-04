# pwnagotchi-18650
A pwnagotchi case with space for an 18650

* Full credit to Evil Socket for this awesome project: https://github.com/evilsocket/pwnagotchi

## Why?
Because sometimes you want to blow fat clouds, sometimes you want to pwn wifi. I had a few 18650s sitting around and wanted to learn 3D modeling, so I created this. It isn't pretty, or properly designed.

## Warning
This is not properly designed, and things likely won't work.

## Parts
This case is designed with the following parts in mind:

| Name                                               | Quantity | Supplier     | Supplier ID   |
|----------------------------------------------------|----------|--------------|----------------|
|RasPi Zero W                                        | 1        | Adafruit     | 3400           |
|Headers for RasPi (or just by the pi with headers)  | 1        | Adafruit     | 2822           |
|LiPo Zero Hat                                       | 1        | Digi-Key     | PIM185         |
|2-Pin JST connector (optional, see below)           | 1        | Digi-Key     | ASR00015-100   |
|Battery Holder (18650)                              | 1        | Digi-Key     | 1042           |
|18650 Battery                                       | 1        | batteryspace | FB-18650P-34PA |

### Digikey shared cart
https://www.digikey.com/short/p07hfn

### NOTES ON BATTERY:
The listed battery above is technically wrong size for the holder. Ideally you want a battery without tabs, however that seller only sells this model with tabs. It does fit in the holder, however it is very snug and difficult to get out. If you have existing 18650s then try them before buying any more.

## Make This Notes
* When 3d printing the case, print upright (battery holder facing upward) as that opening is more critical than the front opening.
  * Printed on an ultimaker 2+ with heated bottom, 2mm layer height.
* On the LiPo power hat, you have to desolder and remove the 2-Pin JST (Female) connector as it interferes with the screen.
  * If you want this to be disassemble in the future, solder wires from the hat to the JST (female) connector you just removed. Then solder the 2-pin JST (male) connector to the battery holder. Note the holder has polarity marked on it. You'll also want to drill a 3/8 hole between the battery holder and the interior of the case.
  * If you are ok with cutting wires to remove the PI from the case, solder wires to connect the battery holder directly to the power board, and you don't need the 2-PIN JST outlined above.
* The battery holder only goes in one way, negative terminal to the right when looking at the front of the case with battery-opening facing upward.
  * I found the mounting tabs provide enough of a press-fit but if you want you can glue down the holder.
  
## Issues
### Case design
I learned 3D modeling building this case, so v1 has a lot of issues. The holes intended to mount the Ras Pi don't line up, and the cutout intended for the bottom of the headers is on the wrong side. Eventually it might be fixed, but until then it does press-fit into the opening. The cutout to the side was intended for a different power board (adafruit powerboost 500) but there were issues with removing the support material. So for printability I moved to a power hat and used the space for tucking wires into.

### Brown-out voltage
Another issue with this design is the brownout voltage of the voltage booster is 3.0v, however the battery's minimum voltage is 2.5v. So there is still charge left in the battery when the circuit cuts off. I do not know a lot about batteries (or electronics) so maybe this is ok, but you won't get the listed output of the battery.

## Future Work
Ideally, I want to change the following sometime in the future:
### The Case
By folding the tabs on the battery holder down, it is possible to shrink the overall length of the case ~0.5in. I also want to fix the mounts for the RasPi to the case for screws.

### Power
The power hat has a low-battery indication on GPIO #4 (pin 7), so it would be great to integrate this with the pwnagotchi UI.
