# SwiftFirmata
A Swift firmata framework.  
Heavily inspired on https://github.com/younata/firmata

## Example:

```swift
import Foundation

// Blink led hooked on pin 13
let firmata = SwiftFirmata(connect: "/dev/cu.usbmodem1421", baud: 57600)
let pin = Pin(number: 13, mode: .Output)
firmata.configure(pin)

while (true) {
  firmata.digitalWrite(pin, level: .High)
  sleep(2)
  firmata.digitalWrite(pin, level: .Low)
  sleep(2)
}
```