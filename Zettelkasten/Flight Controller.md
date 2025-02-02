Tags: [[Drone Project]]

Flight controller usage:
- **Telemetry:** the flight controller is connected to a set of sensors, that give informations such as height, orientation and speed. The *Internal Measurement Unit (IMU)* can determine angular speed and acceleration, the barometer can determine the height and the distance sensor can detect obstacles.
- **Controlling:** the drone can accelerate and rotate by controlling the speed differences between the four motors. The flight controller uses the data gathered by the sensors to calculate this speed and then sends the desired speef to the ESC. This process is regulated by an alghoritm, the most common is the PID control.
- **Communicating:** the flight control can comunicate useful information to the pilot.
- **Stabilization:** The flight controller ensures the drone maintains stability in flight by continuously adjusting the motor speeds based on the feedback from onboard sensors.
- **Safety Function**
There are a lot of different flight controller depending on the desired use, for example hobbyists, racing, filing and commercial.
![[flight.jpg]]
### Components
- **Microcontroller**
- **Sensors**
- **I/O Interfaces**
- **Power Source**
