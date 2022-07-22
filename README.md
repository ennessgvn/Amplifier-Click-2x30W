# Amplifier-Click-2x30W
2x30W Amp click is a class-D audio amplifier with a tremendous output power, considering its size and lack of huge heatsinks, usually associated with the audio amplifiers. This is due to the fact that the efficiency of the amplifier IC is quite high (greater than 90%), featuring the efficiency boost mode, which dynamically reduces the current ripple of the external LC filter and current in idle mode. The integrated self-protection circuits include overvoltage, undervoltage, and overtemperature protection, output DC offset detection, as well as the short circuit detection, with the error reporting feature, via the dedicated pin.

With the power efficiency and low power consumption in mind, the 2x30W Amp click is a perfect solution for battery powered active speakers. Due to a low idle current, as low as 25mA, the battery power consumption is greatly reduced, especially when the amplifier is idling. Equipped with all these features, 2x30W Amp is an ideal tool for building various audio applications that require an output amplification with very low noise and distortion (THD), such as wireless Bluetooth speakers, home theater systems, mini and micro audio components, and similar.

## How Does It Work?

The main component of the 2x30W Amp click is TPA3128, 2x30-W class-D amplifier with low idle power dissipation, from Texas Instruments. The most important characteristic of this IC is its output efficiency, which reduces the need for bulky heat sinks, usually associated with the audio amplifiers. This is accomplished by using switching MOSFET outputs, which have very low RDSON, as low as 90 mΩ.
Unlike class A or class AB amplifiers, class D amplifiers are way more efficient, by design. Class D amplifier working principles are based on the switching characteristic of the transistors, rather than the linear characteristic, used for the A/AB class amplifiers. The audio signal is encoded into a PWM signal with the fixed amplitude. An output signal is restored by running it through the LC filter and the speaker itself. Since the basis of this principle is switching of the signal, and the transistors are either fully ON or fully OFF, they spend very little time in the linear region, and dissipate very little power. Using low RDSON MOSFETs becomes possible and desirable so that the efficiency goes up to 90% and over.

2x30W Amp click is designed to work with 2 channels of a single-sided audio source, connected via the 3.5mm stereo audio jack, which is provided on board.

The Click board™ is equipped with a connector for the external power source. By default, the 2x30 Amp click is supplied via the mikroBUS™ 5V rail, which limits the output power. For the full output power, an adequate external power supply should be used. The TPA3128 IC can handle up to 26V. To select operation via the external power supply, the onboard SMD jumper should be switched to the desired position (EXT or 5V). If EXT position is selected, the external power supply should be connected via the 1x2 header on the side of the Click board™, labeled as VEXT.

The connected speaker impedance should not be less than 4Ω. The speakers can be connected via two edge connectors, with clearly labeled input ports: L+ and L- for connecting the left speaker positive and negative terminals; R+ and R- for connecting the right speaker positive and negative terminals. Care should be taken to dimension the speakers according to the maximum output power of the amplifier.

The amplifier has fixed gain of 32dB, determined by two resistors, labeled as R4 and R5 on the provided schematic.

The RST pin of the mikroBUS™ is routed to the SDZ pin of the TPA3128 IC. Setting this pin to a LOW logic level will set the TPA3128 IC in the shutdown mode, with its output stage set to a high impedance (Hi-Z), reducing the idle current to a minimum. It is a good practice to pull the SDZ (RST) pin to a LOW logic level before disconnecting the power from the Click board™ to avoid audible power-off clicks. RST pin is pulled up to a HIGH logic level by the onboard resistor.

Another way to mute the speakers is pulling the MUTE pin to a HIGH logic level. This pin is routed to the CS pin of the mikroBUS™ and it is labeled as the MT. Pulling this pin to a HIGH logic level will also set the output stage to a Hi-Z, but it will perform muting function only, thus muting the IC faster than the complete shutdown with the SDZ pin. This function is useful if used in conjunction with the FAULT pin, allowing power-up in a muted state when there is a problem on the output stage.

FAULTZ pin is routed to the INT pin of the mikroBUS™ and it is labeled as the FLT. It is used to signalize the fault condition (overtemperature, output DC offset detection) to the host MCU. It is active low and can be used to trigger an interrupt request on the host MCU so that the proper action can be taken.

The Click board™ uses only GPIO pins, so the usage is extremely simple. However, the Click board™ comes with the library that contains functions for the mikroC, mikroBASIC and mikroPASCAL compilers, which simplify using this Click board™ even more. The provided example application demonstrates their use and it can be used as a reference for a custom design.

## Specifications

![specifications](https://user-images.githubusercontent.com/79998692/180442081-8abfc8b0-4f22-470a-853e-f487210e52be.PNG)

## Used Components

 1)TPA3128D2 (IC) x1 
 
 2)100K Ohm Resistor x2 
 
 3)39K Ohm Resistor x1 
 
 4)1K Ohm Resistor x1 
 
 5)3.24 Ohm Resistor x4 
 
 6)10uH Power Inductor x4 
 
 7)8 Pos. Header x2 
 
 8)2 Pos. Connector x2 
 
 9)LED Green x1 
 
 10)Audio Jack Connector x1 
 
 11)100uF Aluminum Capacitor x2 
 
 12)100nF Capacitor x2 
 
 13)1nF Capacitor x2 
 
 14)1uF Capacitor x6 
 
 15)680nF Capacitor x4 
 
 16)220nF Capacitor x4 
 
 17)10nF Capacitor x4 

### TPA3128D2 Description And Datasheet

The TPA3128D2 and TPA3129D2 have low idle power loss and helps to extend the battery life of Bluetooth/Wireless speakers and other batterypowered audio systems. The high efficiency of the TPA3128D2 device allows it to do 2×30 W without external heat sink on a dual layer PCB. The high efficiency of the TPA3129D2 device allows it to do 2×15 W without external heat sink on a dual layer PCB. This device proposed an efficiency boost Mode, which can dynamically reduced the current ripple of the external LC filter and the idle current.

![TPA Blok](https://user-images.githubusercontent.com/79998692/180445371-8d2d5cbe-8fe6-42df-aae9-ab120c0689bb.PNG)

![datasheet](https://user-images.githubusercontent.com/79998692/180445392-f77fc5ac-4e55-45f4-bb75-693cf245df7c.PNG)

## Shematic Design of Circuit

As seen in the image below, there is a serial RLC filter. The amplified signal enters the LC filter, a low-pass filter, and high-value noise frequencies are eliminated. In this way, we can hear a low-noise audio signal in the speakers.

![1 shematic](https://user-images.githubusercontent.com/79998692/180446351-abc5a6d4-2a7a-48df-b230-3367be0bca8d.PNG)

On the left side of the IC, we can see the audio input and the connections of the communication pins from Mikrobus.

![shematic 2](https://user-images.githubusercontent.com/79998692/180447274-73e863dd-aa6a-4dfb-a2d1-ba98b2efe69b.PNG)

The task of Mikrobus here is to communicate the circuit by an external microcontroller. IC can work with communication protocols such as SPI, I2C, UART.

![shematic 3](https://user-images.githubusercontent.com/79998692/180447663-6b8f1007-dd33-49a4-bcb9-4b59262c917b.PNG)

## PCB Design of Circuit

It was observed that the circuit board had two layers before it was designed. The drawing methods were determined according to the schematic connection. Net thicknesses and clearences were calculated according to the input current. Polygon vias are positioned close to GNDs. These images about view of Top Layer and Bottom Layer nets and pads.

![pcb1](https://user-images.githubusercontent.com/79998692/180454461-797beab0-0e84-47d1-94d7-828d9ce93ba6.PNG)                                                 ![pcb2](https://user-images.githubusercontent.com/79998692/180454479-6ce14948-0db7-4043-976b-416d32283230.PNG)  ![pcb3](https://user-images.githubusercontent.com/79998692/180454492-48cc3c96-c3b7-4309-bf11-5c91863f56db.PNG)

## 3D View of Board

![pcb4](https://user-images.githubusercontent.com/79998692/180454904-7f127ac2-231e-4734-ae6b-8b0cdf0db648.PNG)    ![pcb5](https://user-images.githubusercontent.com/79998692/180454921-e1f37594-4e69-4785-892f-408411238214.PNG)



# THANK YOU FOR CHECKING ON MY PROJECT :)

ENES GUVEN










