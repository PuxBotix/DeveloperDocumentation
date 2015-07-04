---
title: Robot Tech
order: 4
section: Sphero Robot Basics
---

Sphero Robots support three programming languages on every Robot that can provide some basic autonomous functions. The easiest to learn and is used by our education program is Macros, followed by OrbBasic, and finally the latest and most powerful, OVAL.  These languages all provide autonomous functionality for fast changing colors or other feedback that would normally be limited to the 12 commands per second limit when communicating with a host device.

## Outputs

### Control System & Motors
Sphero robots have a complex stabilization and control system that provides an easy way to move the robot using 'roll' commands, yet provides direct access to the internal motors by bypassing the control system.

### Lights
Sphero robots have two LEDs, a main RGB Led and a blue tail-light that are independently accessible via the API and SDKs.

## Sensors
Sensor data is available via the sensor streaming API/SDK Commands.  Sensors include a very accurate IMU, Collision Detection algorithm, and Locator.

### IMU
Sphero robots contain a powerful  [Inertial Measurement Unit (IMU)](http://en.wikipedia.org/wiki/Inertial_measurement_unit) used to stabilize the robot during navigation.  The Sphero IMU contains an Accelerometer and Gyrometer which can be used as inputs to sense freefall, jumps, tricks, and human handling of the robot.  

### Collision Detection
Every Sphero robot contains a complex collision detection algorithm.  Since this algorithm needs very high fidelity IMU data to correctly detect collisions and can be slightly different based on the robots mechanical design it has been implemented on the Robot instead of streaming the data back to the host device.

### Locator
Sphero Locator is a feature that provides real-time 2D position and velocity information about the robot.  Much like IMU data, Locator data is available via the Streaming protocol in the [SDKs](/sdk-documentation/getting-started).


### Signal Quality {{>ollie-icon}}
Ollie and our future Bluetooth 4.0 robots give access to Signal Quality which can be used to detect gross proximity to the host device.  Sphero, the robot, does not support Signal Quality.

##Languages
### Macros
The easiest way to develop Macros is via a mobile visual development tool called MacroLab.  MacroLab is available for [Apple](https://itunes.apple.com/us/app/sphero-macrolab/id519917219?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.orbotix.macrolab&hl=en).  Macros excel at fast color changes, fades, and other semi-autonomous functions that would normally be limited by bluetooth bandwidth. For more information see: [Macros](/robot-languages/macros).

### OrbBasic
OrbBasic is a text-based programming language that is easy to experiment with via the OrbBasic App available in the [Apple](https://itunes.apple.com/us/app/orbbasic-for-sphero/id647306205?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.orbotix.orbbasic&hl=en) App Stores.  OrbBasic, like Macros, are a resource that provides for autonomous behavior and provides programmable conditionals that Macros don't support. For more information see: [OrbBasic](/robot-languages/orbbasic).

### Oval {{>ollie-icon}}
Oval is a subset of the computer language C with a few extra features to support streaming and asynchronous communication. It provides 32-bit floating point and signed integer types but does not include pointers, structs, or unions.  Oval gives the developer direct access to sensor data, and control system parameters.  For more information see: [Oval](/robot-languages/oval-language).

##Protocol
### API & SDK Commands
API Commands are a set of commands that are generated on a host (mobile) device and transmitted via Bluetooth to the robot for execution.  By definition there is some latency from the time the command is generated and sent and hence why the onboard robot language interpreters are so important.  Also, due to bandwidth constraints the robot is limited to accepting about 12 commands per second via Bluetooth.  The Objective-C, Swift, and Android SDKs abstract the API Commands into SDK Commands and hide the actual protocol for ease of development.



