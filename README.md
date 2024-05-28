# **Nextion Switch**
![NextionSwitchFront](https://github.com/nollstead/Nextion-Switch/assets/13612518/67bfbe3a-3694-4c33-a39e-566559366220)


A drawback of the Nextion displays is that they only include a single communication port, which is used for both communicating with your microcontroller and uploading new Nextion code using the Nextion Editor.  This means repeatedly swapping the wires between your microcontroller and the Nextion, uploading, swapping back to test - which can be frustrating when in development mode.  Additionally it requires a separate USB-to-Serial adapter - which just adds to the mess of connections to manage.

This handy device solves both of those problems.  Wire this in-line with your Nextion, your PC, your microcontroller and separate power source and it'll automatically switch those wires for you - no need to constantly remove wires.


## Features

- USB-C Connector with Electrostatic Discharge (ESD) protection
- Embedded FTDI USB-to-Serial converter, so no external converter required
- Reverse voltage protection for power pins protects board against accidential reverse wiring of power pins
- 4-wire JST-XH connector for connectng to your Nextion display.  This connector will provide power as well as Tx/Rx signals for both Nextion editor and MCU communication
- RoHS Compliant parts and manufacturing processes


## Setup

### PC USB

The switch includes an on-board FTDI USB-to-Serial connector and requires a virtual COM port driver.  Download and install the VCP driver for your operating system from https://ftdichip.com/drivers/vcp-drivers/.  Once installed and plugged in via the USB port the switch will appear as a virtual COM port, just like any other FTDI adapter.


### Power

At full brightnexx the Nextion display has an average current requirement of approx. 240mA, much more than a typical microcontroller such as an Arduino can support.  Therefore the switch includes a separate Power connector.   Note that there is no onboard voltage regulator on the switch, so be sure that your power supply is 5v and capable of sourcing at least 240mA

### MCU Connection

Connect to your controller using the RX, TX and GND pins.  
  - Connect the TX port on your microcontroller to the RX pin on the switch
  - Connect the RX port on your microcontroller to the TX pin on the switch
  - Connect any GND pin on your microcontroller to the GND pin on the switch.  

### Nextion Connection

Connect a 4-wire 2.54mm Female-to-Female JST-XH wire from the Nextion port on the switch to your Nextion.  

Note that switch is designed to use "straight-through" cables, so if making your own cables you should not swap the TX and RX wires - this is done internally.  The switch has 5V and GND marked to help ensure that the wires are connected correctly, just make sure they line up with the corresponding port ont the Nextion.  Below is an example of what a suitable cable would look like:

![cable](https://github.com/nollstead/Nextion-Switch/assets/13612518/bd77e64a-0e30-43fb-a066-03e7465f0772)

## Operation

In normal operation the Power, MCU and Nextion connections are in place and your microcontroller will communicate with your Nextion through the switch.  Connecting a USB cable will switch the communication to be between your PC and the Nextion - allowing you to upload to your nextion.  Then, simply disconnect the USB (from either your computer or the switch) and communication will switch back to the MCU/Nextion.  

## How to Get one

Included in the repository are the Gerber, BOM and PickandPlace files required to manufacture this board at your favorite PC manufacturer.  

I periodically manufacture these in small quantities for those 

If you're not familiar or comfortable with PCB manufacturing I'm happy to I'm happy to manufacture these in small quantities for the maker community upon request.  The cost of the switch is $35 + +5 shipping (to US), which primarily goes towards manufacturing costs, payable via either PayPal or Venmo.  If you're interested in one email me at nollstead@gmail.com


