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

# PROJECTS
 001
# CONTROLLING A STEPPER MOTOR WITH ARDUINO

## Introduction

- A stepper motor is a type of a brushless DC motor that divides a full rotation in equal steps.
- Both the stepper motor and arduino controll the speed and direction .

## coomponents required

- 28BYJ- 48 Stepper motor
- ULN2003 motor Driver
- Arduino board (uno,mega )
- Jumper wires
- Power supply 5v DC
-

## Wiring Diagram

 ULN2003                 Arduino pins
 IN1                     PIN8
 IN2                     PIN9
 IN3                     PIN10
 IN4                     PIN11
 VCC                     5V
 GND                     GND

- The 28BYJ-48 stepper motor is connected to ULN2003 motor driver via an onboard white 5-pin connector.

## ARDUINO CODE

# include <Stepper.h>
`
# define STEPS 2048 // Steps per revolution for 28BYJ-48

Stepper myStepper(STEPS, 8, 10, 9, 11);

void setup() {
    myStepper.setSpeed(10); // Speed in RPM
    Serial.begin(9600);
}

void loop() {
    Serial.println("Rotating clockwise");
    myStepper.step(STEPS); // Full rotation
    delay(1000);

    Serial.println("Rotating counterclockwise");
    myStepper.step(-STEPS); // Full rotation in opposite direction
    delay(1000);
}

## Breakdown

- The Stepper library is included to handle stepper motor movement.
- The Stepper object is initialized with the number of steps per revolution and the control pins.
- The setSpeed() function sets the rotation speed in RPM.
- The step() function is used to move the motor forward and backward in steps.

## Root Cause Analysis

- If the motor vibrates but does not rotate, check the wiring.
- Ensure the correct sequence of motor driver inputs.
- Adjust the speed settings if the motor does not move smoothly.
- Make sure the motor is receiving sufficient power.

## Conclusion

- Using an Arduino with a ULN2003 driver makes it simple to control a stepper motor for precise movements.                                                                                - This setup is ideal for robotics, automation, and CNC applications.
 
002
 # 12V and 5V Regulated Power supply

 ## Introduction:
 - -A regulated power supply  provides a stable voltage regardless of variations in input voltage or load conditions.
                                                                                                                                          .
## Components Required

- Step-down transformer 
- Bridge Rectifier - Four diodes (1N4007) 
- Capacitors - 1000µF/25V, 470µF/25V, 0.1µF
- Voltage Regulators - 7805  and 7812 
- Resistors - 1kΩ 
- LEDs
- PCB or Perfboard 
- Heat Sinks 
- Wires and Connectors
-  
## Circuit Design 

- Step-down Transformer: Converts 230V AC to 15V AC.
- Bridge Rectifier: Converts AC voltage to pulsating DC voltage.
- Filtering Capacitor: Smoothens the rectified DC voltage.
- Voltage Regulators: The 7812 voltage regulator outputs 12V DC, and the 7805 voltage regulator provides a stable 5V DC.
- Output Filtering: Additional capacitors (0.1µF) are used to remove high-frequency noise.


## Working Principle

- The transformer steps down the high-voltage AC to 15V AC.
- The bridge rectifier (four diodes arranged in a bridge configuration) converts AC to DC.
- A filter capacitor smoothens the DC signal by reducing ripples.
- The 7812 and 7805 voltage regulators regulate the voltage to 12V and 5V, respectively.
- The final output is a stable 5V and 12V DC supply.
 
## Applications

- Microcontrollers (Arduino, Raspberry Pi, etc.)
- Sensors and actuators
- Embedded systems
- DC motors and relays
  
# Note:
Ensure proper heat dissipation using heat sinks for voltage regulators to prevent overheating and potential failure.
