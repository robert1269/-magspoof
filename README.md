
# MagSpoof V3 - Credit Card/Magstripe Spoofer

<a href="https://electroniccats.com/producto/magspoof-v3/">
  <p align="center">
  <img src="https://electroniccats.com/wp-content/uploads/badge_store.png" height="104" />
  </p>
</a>

# How does MagSpoof work?

**MagSpoof V3** is a device that can spoof/emulate any magnetic stripe or credit card. It can work "wirelessly", even on **standard magstripe/credit card readers**, by generating a strong electromagnetic field that emulates a traditional magnetic stripe card.

* Allows you to store all of your credit cards and magstripes in one device
* Works on traditional magstripe readers **wirelessly** (no NFC/RFID required)
* Can **disable** Chip-and-PIN (code not included)
* Correctly **predicts** Amex credit card numbers + expirations from previous card number (code not included)
* Supports all three magnetic stripe tracks, and even supports Track 1+2 simultaneously
* Easy to build using Arduino or other common parts

MagSpoof can be used as a traditional credit card and simply store all of your credit cards (and with modification, can technically disable chip requirements) in various impressive and exciting form factors, or can be used for security research in any area that would traditionally require a magstripe, such as readers for credit cards, drivers licenses, hotel room keys, automated parking lot tickets, etc.

**Note:** MagSpoof does **not** enable you to use credit cards that you are not legally authorized to use. The Chip-and-PIN and Amex information is **not** implemented and using MagSpoof requires you to have/own the magstripes that you wish to emulate. Simply having a credit card number and expiration is not enough to perform transactions. MagSpoof **does** allow you to perform research in other areas of magstripes, microcontrollers, and electromagnetism, as well as learn about and create your own devices similar to other existing, commercial technologies such as <a href="http://www.samsung.com/us/support/answer/ANS00043865/997410383/">Samsung MST</a> and <a href="https://onlycoin.com/">Coin</a>.</p>

**Source code / schematic:** [https://github.com/ElectronicCats/magspoof](https://github.com/ElectronicCats/magspoof)

-----

## Wiki and Getting Started
[Getting Started in our Wiki](https://github.com/ElectronicCats/magspoof/wiki)

-----

# Hardware Versions

## Version DIY


[![MagSpoof](http://samy.pl/magspoof/magspoof.jpg)](http://samy.pl/magspoof/magspoof.jpg)

### [Atmel ATtiny85](http://amzn.to/1S3ha9s) (microcontroller)
An Atmel ATtiny85 is the microcontroller to drive the entire system. It stores all of the magnetic stripe / credit card data. In a thinner, credit-card sized (0.8mm thick!) version, I use an [ATtiny10].

### [L293D H-Bridge](http://amzn.to/1S3h9Ck) (motor driver)
I use an L293D H-bridge to drive the electromagnet. The L293D is a motor driver, but motors are actually driven by the electromagnet(s) and magnets inside of them. Any standard driver should work here. Technically the L293D doesn't work down at 3.7V (voltage of the LiPo battery), but it works surprisingly well. In the credit-card size version, I suggest using a the TI DRV8835 or [TI DRV8833](http://amzn.to/1lu0bTd).

### [24AWG Magnet Wire](http://amzn.to/1lu0ihK) (coil)
I use somewhere around ~24AWG magnet wire to act as the coil to produce the electromagnetic field. This piece of wire incredibly produces an electromagnetic field that makes the card reader believe a card is being swiped. Incredible. By rapidly controlling the polarization of this field, the magstripe reader believes the flipped bits of a real card are being swiped through the reader.

### [100mAh 3.7V LiPo battery](http://amzn.to/1S3h69E) (the powah)
A small 100mAh 3.7V lipo battery powers our contraption. For the credit card size version (not shown here), I use a battery from [PowerStream](http://www.powerstream.com/thin-lithium-ion.htm).

#### [100µF Capacitor](http://amzn.to/1MAONOc)
Keep enough energy in this capacitor to provide the electromagnet with power when we need it, otherwise it will pull too much current and reset the microcontroller. This is the capacitor kit I use as it has all the standard values I'd need.

#### [LED](http://amzn.to/1Hl3y8Z)
To signal to us when we transmit information. I use this LED kit as it has a nice variety of LEDs.

#### [100Ω Resistor](http://amzn.to/1IeCMtP)
Don't burn out the LED.

#### [Momentary Switch](http://amzn.to/1Hl3R3T)
Initiate the electromagnet.

#### [Mini-Protoboard](http://amzn.to/1Hl3VQV)
For soldering everything together.

[![MagSpoof Schematic (DIP version)](https://raw.githubusercontent.com/samyk/magspoof/master/magspoof-schematic-dip.png)](https://raw.githubusercontent.com/samyk/magspoof/master/magspoof-schematic-dip.png)



## Hardware V1

[![MagSpoof](https://electroniccats.com/wp-content/uploads/2018/02/product-600x600.png)](https://electroniccats.com/wp-content/uploads/2018/02/product-600x600.png)

### [Atmel ATtiny85](https://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-2586-AVR-8-bit-Microcontroller-ATtiny25-ATtiny45-ATtiny85_Datasheet.pdf) (microcontroller)
An Atmel ATtiny85 is the microcontroller to drive the entire system. It stores all of the magnetic stripe / credit card data. In a thinner, credit-card sized (0.8mm thick!) version, I use an [ATtiny10].

### [TC4424 H-Bridge](http://ww1.microchip.com/downloads/en/DeviceDoc/21421E.pdf) (motor driver)
I use an TC4424 H-bridge to drive the electromagnet. The TC4424 is a motor driver, but motors are actually driven by the electromagnet(s) and magnets inside of them. Any standard driver should work here. Technically the TC4424 doesn't work down at 3.7V (voltage of the LiPo battery), but it works surprisingly well.

### [24AWG Magnet Wire](http://amzn.to/1lu0ihK) (coil)
I use somewhere around ~24AWG magnet wire to act as the coil to produce the electromagnetic field. This piece of wire incredibly produces an electromagnetic field that makes the card reader believe a card is being swiped. Incredible. By rapidly controlling the polarization of this field, the magstripe reader believes the flipped bits of a real card are being swiped through the reader.

### [100mAh 3.7V LiPo battery](http://amzn.to/1S3h69E) (the powah)
A small 100mAh 3.7V lipo battery powers our contraption. For the credit card size version (not shown here), I use a battery from [PowerStream](http://www.powerstream.com/thin-lithium-ion.htm).

#### [100µF Capacitor](http://amzn.to/1MAONOc)
Keep enough energy in this capacitor to provide the electromagnet with power when we need it, otherwise it will pull too much current and reset the microcontroller. This is the capacitor kit I use as it has all the standard values I'd need.

#### [LED](http://amzn.to/1Hl3y8Z)
To signal to us when we transmit information. I use this LED kit as it has a nice variety of LEDs.

#### [100Ω Resistor](http://amzn.to/1IeCMtP)
Don't burn out the LED.

#### [Momentary Switch](http://amzn.to/1Hl3R3T)
Initiate the electromagnet.


## Hardware V3

[![MagSpoofV3](https://pbs.twimg.com/media/EIFyNhSXYAEjhra?format=jpg&name=large)](https://pbs.twimg.com/media/EIFyNhSXYAEjhra?format=jpg&name=large)

### [Atmel SAMD11]() (microcontroller)
An Atmel SAMD11 is the microcontroller ARM Cortex M0+ of 32bits to drive the entire system. It stores all of the magnetic stripe / credit card data. In a thinner, credit-card sized (0.8mm thick!) version.

### [TC4424 H-Bridge]() (motor driver)
I use an TC4424 H-bridge to drive the electromagnet. The TC4424 is a motor driver, but motors are actually driven by the electromagnet(s) and magnets inside of them. Any standard driver should work here. Technically the TC4424 doesn't work down at 3.7V (voltage of the LiPo battery), but it works surprisingly well.

### [24AWG Magnet Wire](http://amzn.to/1lu0ihK) (coil)
I use somewhere around ~24AWG magnet wire to act as the coil to produce the electromagnetic field. This piece of wire incredibly produces an electromagnetic field that makes the card reader believe a card is being swiped. Incredible. By rapidly controlling the polarization of this field, the magstripe reader believes the flipped bits of a real card are being swiped through the reader.

### [100mAh 3.7V LiPo battery](http://amzn.to/1S3h69E) (the powah)
A small 100mAh 3.7V lipo battery powers our contraption. For the credit card size version (not shown here), I use a battery from [PowerStream](http://www.powerstream.com/thin-lithium-ion.htm).

#### [100µF Capacitor](http://amzn.to/1MAONOc)
Keep enough energy in this capacitor to provide the electromagnet with power when we need it, otherwise it will pull too much current and reset the microcontroller. This is the capacitor kit I use as it has all the standard values I'd need.

#### [LED](http://amzn.to/1Hl3y8Z)
To signal to us when we transmit information. I use this LED kit as it has a nice variety of LEDs.

#### [100Ω Resistor](http://amzn.to/1IeCMtP)
Don't burn out the LED.

#### [Momentary Switch](http://amzn.to/1Hl3R3T)
Initiate the electromagnet.

#### Coil
SWC4242KB120-100 or WMRR138F-0



-----

# Learn how to use the Magspoof with Arduino Firmware

## MagSpoof V1

MagSpoof V1 is compatible with the Arduino framework and can work on traditional Arduinos as well as ATtiny chips of Electronic Cats.

Learn how to use the Magspoof V1 with Arduino in
[Instructables](https://www.instructables.com/id/Getting-Started-With-MagSpoof)


## MagSpoof V3

MagSpoof V3 is compatible with the Arduino framework and can work on traditional Arduinos as well as SAMDLC chips.

Learn how to use the Magspoof V3 with Arduino in
[Electronic Cats Board Index SAMDLC](https://github.com/ElectronicCats/Arduino_Boards_Index)


-----
# Resources

You can learn about magnetic stripes and credit cards from a few places, including:

* [My video on MagSpoof](https://www.youtube.com/watch?v=UHSFf0Lz1qc)
* [ISO/IEC 7810](https://en.wikipedia.org/wiki/ISO/IEC_7810)
* [ISO/IEC 7811](https://en.wikipedia.org/wiki/ISO/IEC_7811)
* [ISO/IEC 7812](https://en.wikipedia.org/wiki/ISO/IEC_7812)
* [ISO/IEC 7813](https://en.wikipedia.org/wiki/ISO/IEC_7813)
* [ISO 8583](https://en.wikipedia.org/wiki/ISO_8583)
* [ISO/IEC 4909](https://en.wikipedia.org/wiki/ISO/IEC_4909)
* [MagTek Magnetic Stripe Standards](http://www.magtek.com/documentation/public/99800004-1.08.pdf) (pdf)
* [Magnetic Stripe Card on Wikipedia](https://en.wikipedia.org/wiki/Magnetic_stripe_card)
* [Amex's Web Services Plural Interface](http://secure.cmax.americanexpress.com/Internet/MSWS/English/PIP-XML_Oct2010.pdf)

-----

# Based in work of SamyKamkar

**Point of Contact:** [@SamyKamkar](https://twitter.com/samykamkar)

You can see more of my projects at <http://samy.pl> or contact me at <code@samy.pl>.


------

------
# License

![OpenSourceLicense](https://github.com/ElectronicCats/AjoloteBoard/raw/master/OpenSourceLicense.png)

Designed by Electronic Cats.

Firmware released under an GNU AGPL v3.0 license. See the LICENSE file for more information.

Hardware released under an CERN Open Hardware Licence v1.2. See the LICENSE_HARDWARE file for more information.

Electronic Cats is a registered trademark, please do not use if you sell these PCBs.

30 Octuber 2019

------
