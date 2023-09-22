<a href="https://www.microchip.com" rel="nofollow"><img src="images/microchip.png" alt="MCHP" width="300"/></a>

# Numerically Controlled Oscillator (NCO) — Tone Generator Using the PIC16F18446 Microcontroller

In this project, the NCO peripheral generates a square-wave with variable frequency in the audible spectrum.
The POT1 potentiometer on the Curiosity Board adjusts the frequency. The potentiometer is read using the Analog-to-Digital Converter (ADC) peripheral.

## Related Documentation
- [PIC16F18446 Product Family Page](https://www.microchip.com/design-centers/8-bit/pic-mcus/device-selection/pic16f18446)
- [PIC16F18446 Data Sheet](http://ww1.microchip.com/downloads/en/DeviceDoc/40001985B.pdf)

## Software Used

- [MPLAB® X IDE](http://www.microchip.com/mplab/mplab-x-ide) v6.15 or newer
- [MPLAB® XC8](http://www.microchip.com/mplab/compilers) v2.45 or newer
- [PIC16F1xxxx_DFP](https://packs.download.microchip.com/) v1.21.368

## Hardware Used

- [Curiosity Development Board](https://www.microchip.com/Developmenttools/ProductDetails/DM164137)
  <br><img src="images/curiosity-lpc.PNG" width="800">

- [PIC16F18446 PDIP20](https://www.microchip.com/en-us/product/PIC16F18446)
  <br><img src="images/pic16f18446pdip.PNG" width="400">

- [BUZZ CLICK board™](https://www.mikroe.com/buzz-click) (mikroBUS™ socket 1):
  <br><img src="images/buzz-click-board.jpg" height="400">
<br>

## Operation

To program the microcontroller with this MPLAB X project, follow the steps provided in the [How to Program the Microcontroller](#how-to-program-the-microcontroller) chapter.<br><br>

## Setup

The following configurations must be made for this project:

- Clock Control:
  - Clock Source: HFINTOSC
  - HF Internal Clock: 32 MHz
  - Clock Divider: 4

  <br><img src="images/clock_control.PNG" width="600">

- Configuration bits:
  - WDT operating mode: WDT disabled

  <br><img src="images/config_bits.PNG" width="600">

- NCO1:
  - Enable NCO: Yes
  - NCO Mode: FDC mode
  - Output polarity: Active high
  - Clock Source: F<sub>OSC</sub>
  - Requested NCO Output Frequency: 1000 Hz

  <br><img src="images/nco1.PNG" width="600">

- ADCC:
  - Enable ADC: Yes
  - Operating Mode: Basic mode
  - Result Alignment: Right
  - Positive Input Channel: ANC0
  - Positive Reference: V<sub>DD</sub>
  - Negative Reference: V<sub>SS</sub>
  - Auto-conversion Trigger: Disabled
  - Acquisition Count: 1
  - Clock Source: F<sub>OSC</sub>
  - Clock Divider: F<sub>OSC</sub>/32

  <br><img src="images/adc.PNG" width="600">

| Pin | Configuration  |        Description        |
| :-: | :------------: | :-----------------------: |
| RC0 |  Analog input  |        Potentiometer      |
| RC5 | Digital output |           Buzzer          |

<br><img src="images/pin_grid_3.PNG" width="600">
<br><img src="images/pins_3.PNG" width="600">

## Demo

Board setup:

<br><img src="images/demo.jpg" width="600">

## Summary

This code example shows how to make a tone generator using the NCO and ADC peripherals.

## How to Program the Microcontroller

This chapter demonstrates how to use the MPLAB X IDE to program a PIC® device with an `Example_Project.X`. This applies to other projects.

1.  Connect the Curiosity Development board to the PC.

2.  Open the `Example_Project.X` project in MPLAB X IDE.

3.  Set the `Example_Project.X` project as main project.
    <br>Right click the project in the **Projects** tab and then Set as Main Project.
    <br><img src="images/Program_Set_as_Main_Project.PNG" width="600">

4.  Clean and build the `Example_Project.X` project.
    <br>Right click the `Example_Project.X` project and select Clean and Build.
    <br><img src="images/Program_Clean_and_Build.PNG" width="600">

5.  Select Starter Kits (PKOB) in the Connected Hardware Tool section of the project settings:
    <br>Right click the project and **Properties**.
    <br>Click the arrow under the Connected Hardware Tool, and from the dropdown, select Starter Kits (PKOB) by clicking the SN.
    <br>Click **Apply** and then **OK**.
    <br><img src="images/Program_Tool_Selection.PNG" width="600">

6.  Program the project to the microcontroller.
    <br>Right click the project and then Make and Program Device.
    <br><img src="images/Program_Make_and_Program_Device.PNG" width="600">

<br>

- [Back to Top](#numerically-controlled-oscillator-nco--tone-generator-using-the-pic16f18446-microcontroller)
- [Back to Setup](#setup)
- [Back to Demo](#demo)
- [Back to Summary](#summary)