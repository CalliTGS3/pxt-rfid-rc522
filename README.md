 MakeCode Package for the Joy-IT SBC-RFID-RC522 RFID module and AZ-Delivery RFID Kit RC522 (MFRC522).

This library provides a Microsoft Makecode package for the Joy-IT SBC-RFID-RC522 RFID module and RFID Kit RC522 (MFRC522) modules.
See https://joy-it.net/products/SBC-RFID-RC522 or https://www.az-delivery.de/products/rfid-set for more details.

## Connection

The display needs to be connected with six pins to the Micro:bit:

| RFID module   | Calliope mini |
| ------------- |:-------------:|
| VCC           | 3V            |
| GND           | GND           |
| MOSI          | C9            |
| MISO          | C8            |
| SCK           | C7            |
| SDA           | P0            |

## Initialize module

The RFID module needs to be initialized before it is ready to use. All necessary commands will be transfered via SPI here.

```typescript
// Initialize RIFD module
MFRC522.Init(DigitalPin.C9,DigitalPin.C8,DigitalPin.C7,DigitalPin.P0)
```

## Read ID from card
This function reads the cards unique ID and returns it.

```typescript
// Read unique ID
basic.forever(function () {
  let id = MFRC522.getID().toString()
})
```

## Test if card available and read ID
This function tests if card is available and reads the cards unique ID and returns it.

```typescript
// Test and read unique ID
basic.forever(function () {
  let id = MFRC522.testID().toString()
})
```

## Read data from card
Data stored on the card can be retrieved with this function.

```typescript
// Read data
let data = MFRC522.read()
```

## Write data to card
Write data, formatted as string, to the card.

```typescript
// Write data
MFRC522.write("1234")
```

## Turn off antenna
After use, the antenna can be turned off.

```typescript
// Turn antenna off
MFRC522.AntennaOff()
```

## Supported targets

* for PXT/Calliope

## License

MIT
