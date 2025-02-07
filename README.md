# Servo Motors

- Rotary / linear actuator
- Controls angular, linear position 
- Velocity - quantified and has direction 
- Acceleration 
- AC or DC
- Position sensor(feedback)
- Gear system(speed and torque)

## Working Principle

- Pulse Width Modulation(PWM) signal
- feedback mechanism through position sensor
- power adjustment(circuit)
- Motor in desired position(angle), at desired speed.


## Types

- Positional - 0-180
- Continuous rotation - 
- Linear 

## Why? 

- Precision -positional servo
- feedback - positional sensor
- torque & speed 


# UART 

- Universal Asynchronous Receiver/Transmitter
- Hardware protocol(serial)
- exchanges data serially

## Working principle

- Two wires (1- transmit 2- receives)
- Frame[start bit | data bits |  parity bits | stop bits]
- Different clock speed devices can comms


# SPI

- Serial Peripheral Interface
- Short distance 
- Data transmitted and received at same time

## Working principle

- Master-Slave configuration
- Data transmission in both directions using Serial clock[SCK],Serial data out[SDO],Serial data in[SDI] pins.


# I2C

- Inter-Integrated Circuit [serial comms protocol ].

## Working principle

- uses SDA & SCL [unique address on each device]
- Master device senda a start condition and slave address
- Slave compares the addresses and if matches it sends ACK bit.
- Master sends the register address it wants to write to. 
- Slave acknowledges again before master sends data.Then it's ends transmission with a STOP condition.
- 