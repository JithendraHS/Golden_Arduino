﻿<a name="br1"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**Golden Arduino**

**Objecꢀve:**

A board like Arduino Uno was designed with a focus on modular separaꢀon and enhanced debugging

capabiliꢀes, featuring addiꢀonal test points to simplify the debugging process during development and

tesꢀng phases. Industry best pracꢀces were implemented, including the integraꢀon of a separate

ground plane, essenꢀal decoupling, and low-pass ﬁlter capacitors, and minimizing cross-under. Rouꢀng

for Tx and Rx traces was opꢀmized by treaꢀng them as diﬀerenꢀal pairs, thereby improving signal

integrity, and reducing electromagneꢀc interference such as cross talk. Strategic component

placement was employed during board bring-up to enhance performance, miꢀgate ground bounce,

and minimize electromagneꢀc noise.

**Plan of record:**

•

•

•

•

•

•

•

•

•

•

•

•

•

5V power input raꢀng from either power jack or USB-mini.

LDO to regulate voltage to 3.3V.

Sense resistor to measure inrush current.

12MHz oscillator for USB data transmission.

16MHz oscillator for system clock.

USB to UART communicaꢀons to upload sketches.

Circuit for microcontroller reset.

Ferrite beads to reduce noise on AVCC.

Bypass capacitors to compensate for the current surge in power rail.

Low pass ﬁlters.

LED indicators

Circuit to avoid switch debouncing.

Jump start circuit for oscillators.

**Risk reducꢀon:**

•

•

•

•

Added LEDs to indicate power supply is working ﬁne.

ESD protecꢀon to USB mini port.

Proper labelling for each input and outputs.

Added test points to each module to read measurements and verify the funcꢀonality of

module.

**What does it mean to work:**

•

•

•

•

•

•

•

•

•

•

Obtaining a 5V power supply from the power jack and USB mini.

Measuring the 3.3V output from the LDO regulator.

Uꢀlizing a 12MHz frequency oscillator for the USB data transmission.

Uꢀlizing a 16MHz oscillator frequency for the system clock.

Data transmission via D+ and D- pins.

Data transmission via Tx and Rx.

Implemenꢀng proper microcontroller reset without debouncing.

Ensuring that LED indicators are working ﬁne.

Achieving reduced ground bounce compared to a commercial board.

Achieving reduced power rail noise compared to a commercial board.

1



<a name="br2"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**Component lisꢀng:**

•

•

•

•

•

•

•

•

•

•

Microcontroller: Atmega328p

USB to TTL converter: CH340g

Crystal oscillator: 12MHz, 16MHz

Capacitor: 22pF, 1uF, 10uF, 22uF

Resistor: 500m, 1K, 10K, 1M

Inductor: 10uH

Headers

LEDs: Red

Switch: push buꢁon

Power jack and USB mini

**Schemaꢀc:**

*Circuit involved in Golden Arduino board.*

2



<a name="br3"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**Layout:**

**Board:**

Figure 1.1 Assembled board with LEDs lit up.

3



<a name="br4"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**Scope output:**

**1. 5V and 3.3V power supply:**

Measured and verified that 5V DC voltage is coming from the power jack and USB mini, which

is then converted to 3.3V by the LDO.

**2. Oscillators:**

Observed a clock signal of frequency 12MHz generated by the oscillator used for USB data

transmission and 16MHz generated by the oscillator used for the system clock.

**3. USB mini output:**

Seen keepalive signal received from D+ and D- of the USB port every 1ms.

4



<a name="br5"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**4. UART output:**

Captured the state of the Tx channel when data was sent out of the Arduino board and

confirmed that UART is working fine.

**5. Steady and In-rush current**

Measured a voltage drop of 162.50mV across 0.5Ω, indicating a steady-state current draw of

about 325mA. Noted a voltage drop of 851mV upon plugging in the power supply, indicating

an inrush current draw of around 1.7A.

With the help of the noise shield provided below, we evaluated the performance of the

Golden Arduino compared to a Commercial Arduino.

5



<a name="br6"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**6. Quiet Low output observed with a greater number of switching digital pins acꢀng as**

**aggressors:**

From the commercial board, observed ground bounce noise of about 385.93mV and 1.47V

on the quiet low digital pin.

From the Golden Arduino board, observed ground bounce noise of about 289.45mV and

996\.98mV on the quiet low digital pin.

6



<a name="br7"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**7. Quiet Low output observed with just one digital pin acꢀng as an aggressor:**

From the commercial board, observed ground bounce noise of about 217mV and 184mV on

the quiet low digital pin.

From the Golden Arduino board, observed ground bounce noise of about 104.52mV and

88\.44mV on the quiet low digital pin.

**8. Quiet High output observed with the IC acꢀng as an aggressor:**

7



<a name="br8"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

From the commercial board, observed power rail noise of about 627mV and 731.66mV on

the quiet high digital pin.

From the Golden Arduino board, observed power rail noise of about 385.93mV and

578\.89mV on the quiet high digital pin.

**9. Quiet High output observed with the enꢀre board acꢀng as an aggressor:**

From the commercial board, observed power rail noise of about 482.41mV and 321.6mV on

the quiet high digital pin.

8



<a name="br9"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

From the Golden Arduino board, observed power rail noise of about 410mV and 337.69mV

on the quiet high digital pin.

**10. Near field emissions:**

From the Commercial Arduino board, observed around 264.8mV and 555.8mV of NFE (near

field emission).

From the Golden Arduino, observed around 27.6mV and 29.3mV of NFE (near field

emission). Moreover the maximum noise is produced from switching digital pin.

**11. Digital pin output:**

9



<a name="br10"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

In the commercial board, a rise time of 4ns and fall time of 5ns were observed when digital

pin 13 was triggered to output a signal of 5Hz.

The rise time of 4.2ns and fall time of 4.8ns were noted when digital pin 13 is triggered to

output a signal of 5Hz on the Golden Arduino board. This signifies that there is not much

difference in signal timing characteristics between the Golden Arduino and the commercial

board. Otherwise, it could lead to jitter in high-frequency communication signal

transmission.

12\. **Reset pin:**

Observed a rise time of 1.78ms at the commercial board to reach logic high once the reset

button is pressed. Similarly, a rise time of 201.93ms was observed at the Golden Arduino

board, demonstrating better control over switch debouncing. Both boards maintain the

reset pin low for more than 10 microseconds as required by the microcontroller.

10



<a name="br11"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

**13. Thevenin resistance and voltage at digital pin 12:**

The Thevenin voltage measured about 5.23V. After adding a 33ohm resistor as a load, the

calculated load voltage is about 2.57V. Therefore, the Thevenin resistance (internal

resistance of the voltage source, here microcontroller) is **34.15 ohms.**

**14. Noise summary of Commercial Board and Golden Arduino:**

Parameter

Trigger Commercial Golden Change

edge

board

Arduino in noise

(%)

Current through 50ohm resistor

Quiet Low with multiple aggressors

Quiet Low with single aggressors

rise

37mA

35mA

fall

rise

34mA

386mV

35mA

290mV 25

fall

rise

fall

1\.47V

217mV

105mV

627mV

997mV 32

185mV 14

88 mV

386mV 38

579mV 20

410mV 15

338mV

28mV 89.5

29mV 95

15

Quiet High with micro controller as

aggressor

rise

fall

732mV

Quiet High with whole board as aggressor rise

fall

482mV

322mV

265mV

556mV

4

Near Field emission

rise

fall

**15. What All worked**

characteristics

Result Remarks

Obtaining a 5V power supply from the power jack Worked

and USB mini.

Measuring the 3.3V output from the LDO Worked

regulator.

Uꢀlizing a 12MHz frequency oscillator for the USB Worked

data transmission.

11



<a name="br12"></a> 

JITHENDRA H S

PCB REPORT – BOARD 3

Uꢀlizing a 16MHz frequency oscillator for the Worked

system clock.

Data transmission via D+ and D- pins.

Worked

Worked

Data transmission via Tx and Rx.

Implemenꢀng proper microcontroller reset Worked

without debouncing.

Ensuring that LED indicators are working ﬁne.

Worked

Reduced ground bounce compared to commercial Worked

board.

Achieving reduced ground bounce compared to a Worked

commercial board.

Achieving reduced power rail noise compared to a Worked

commercial board.

**16. Mistakes**

Missed labelling the reset switch.

•

•

Placed components too close to each other, which made soldering the components

difficult.

•

Forgot to add independent ICSP pins.

**17. Key learnings**

•

•

•

Prototype Design: Practicing the entire design flow to gain hands-on experience.

Datasheet Reading: Extracting useful information while navigating ambiguity.

Feature Incorporation: Adding extra features to enhance functionality and evaluation

options.

•

•

•

•

•

•

•

Prototype Elements: Including test points, LEDs, and isolation switches for testing and

debugging.

Initial Design Phase: Beginning with POR, sourcing non-commodity parts, and

prototyping on breadboards.

Signal Routing: Employing best practices to minimize cross talk and power rail noise

by avoiding cross under.

Board Improvements: Identifying areas for enhancement in commercial boards to

optimize performance.

Inrush Current Measurement: Understanding and measuring inrush current to

prevent damage to components and ensure proper functioning of the circuit.

Importance of Differential Pairs: Recognizing the significance of using differential pairs

to minimize noise and improve signal integrity in high-speed communication lines.

Microcontroller Boot loading: Learning the process of boot loading a microcontroller

to load firmware onto it, enabling it to execute specific tasks upon startup.

12
