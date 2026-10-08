# Motor Encoder Decoder
This project contains the KiCad files for HPRC's Motor Encoder Decoder board. This PCB was designed for the club's rover payload, which will be flown in the 2027 IREC competition.

## Description
The Motor Encoder Decoder is intended to be used with a [Motoron M2T256 Dual I2C Motor Controller](https://www.pololu.com/product/5065) and powers two 12V DC motors using JST connectors. These connectors will connect to [Pololu rotary encoders](https://www.pololu.com/product/5661) that will be mounted on the gear motors for the rover's wheels. Encoder position is received through these connectors in the form of quadrature square waves and counted with the LS7866C quadrature counter. This data is retrieved off the board using the same i2c bus that controls the motors.

<img width="692" height="566" alt="image" src="https://github.com/user-attachments/assets/c507609f-e1fa-4947-8aaf-63ec7c40fc47" />

## Component Overview
The [LS7866C](https://lsicsi.com/wp-content/uploads/2025/05/LS7866C.pdf) is the primary component of this board, allowing the quadrature encoder data to be connected directly and counted, up to 32 bits. The primary motivation for this was to free up GPIO's and computation time from the Raspberry Pi, as well as being more robust instead of relying on the Pi's OS catching every clock edge.

A board-mount Wago is used for easy connection of the main power, and reliability for the high-current connection. The board was designed with 1.8A peak current per motor in mind, and the Wago is more than capable of handling this. We are supplying 12V to the Wago to power the motors on the rover.

The board is powered using 3.3V to power the LS7866C, and must use 3.3V logic-level I2C.

## PCBWay
A special thank you to our sponsor, [PCBWay](https://www.pcbway.com/), for supporting the manufacturing of this custom PCB! As a competitive high-powered rocketry team, reliable electronics are essential to the success of our projects. PCBWay's high-quality PCB manufacturing services have helped us turn our designs into functional hardware, allowing us to develop and test custom electronics for our rockets and payloads. Their support, attention to detail, and excellent communication throughout the manufacturing process have been greatly appreciated. We are grateful for their contribution to our team's success and highly recommend checking out their services for your next electronics project!

<img width="600" height="221" alt="image" src="https://github.com/user-attachments/assets/36b84c7d-d595-4df8-87c1-90865ea26f46" />
