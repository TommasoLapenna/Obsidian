Tags: [[Drone Project]]

Flight controller usage:
- **Perception:** the flight controller is connected to a set of sensored, that give informations such as height, orientation and speed. The *Internal Mesurement Unit (IMU)* can determine angular speed and accelleration, the barometer can determine the height and the distance sensor can detect obstacles.
- **Controlling:** the drone ca accellerate and rotate by controlling the speed differences between the four motors. The flight controller uses the data gathered by the sensors to calculate this speed and then sends the desired speef to the ESC. This process is regulated by an alghoritm, the most common is the PID control.
- **Communicating:** the flight control can comunicate useful information to the pilot.