# smart-blinds
A blind that open closes at set time. 

![](docs/intro.jpg)

Mechanical Design:
![](docs/stepperdims.jpg)
Figure 1 Dimension of the Smart-Blind System

- make the stepper motor's position adjustable
  - attach the motor to a flexible tube-like arm
- reduce blinds cord slippage
  - by using a vertical holder
  - by cutting out a "circle" of holes, allowing the l-bracket to be mounted at a variey of angles
  

Parts: 
| Tables        | CAD           | Picture  |
| ------------- |:-------------:| -----:|
| Arduino l298n | ![](cad/parts/arduino-l298n-1.snapshot.1/FOTO.JPG)     | ![](cad/parts/arduino-l298n-1.snapshot.1/l298n.png) |
| Arduino uno4     | ![](cad/parts/arduino-uno-4.snapshot.3/ArduinoRender 2.png)     |   ![](ArduinoUnoR3Front.jpg)     |
| Cord Gear | ![](cad/parts/cord gear/imgcord.png)     |    |
| MotherBoard Scew | ![](cad/parts/motherboard-stand-standoff-screw-1.snapshot.1/m_standoff.PNG)     |  ![](cad/parts/motherboard-stand-standoff-screw-1.snapshot.1/m_standoff_size.PNG)   |
| Nema stepper motor mounts| ![](cad/parts/nema-17-nema-23-stepper-motor-mounts-1.snapshot.4/NEMA23MotorMount.PNG) |  |
|nema sepper motor mount| ![](cad/parts/nema-17-stepper-motor-13.snapshot.1/Nema 17 motor.JPG)||


mobile app:
1. Automatically determine opening and closing times based on location
2. Pair with the blind via bluetooth or wifi to set open or close time, and activate open or close action.





# Electric Circuit Design
![ScreenShot](https://raw.github.com/Kamagawa/smart-blinds/master/docs/scans/electrical.jpg)

powering arduino - options:
- barrel jack 7-12V regulated
- vin 7-12V regulated
- usb 5V unregulated

## scenario 1 - ideal, assuming motor is strong enough:
- my current 7.5v adapter with 1A
- motor controller and motor get power from arduino vin
- parts to order: motor, motor bracket, screws

## scenario 2 - 12V motor:
- will need a 12 V adapter with terminal block connector
- cannot use arduino jack and vin to transfer 12V power since too much current
- motor and motor controller will get power directly from source
- parts to order: motor, motor bracket, screws, 12V adapter, protoboard

![ScreenShot](https://raw.github.com/Kamagawa/smart-blinds/master/docs/scans/overlapping-wires.jpg)




# Components List (Cost)
- arduino uno: ~$15
- [sensor shield]: $13
- bluetooth module: $10
- motor controller: $14
- motor: $19
- motor bracket: $10
- 12V adapter: $14
- protoboard: $0.30

- acrylic board
- screws, standoffs, etc.
- motor attachments
