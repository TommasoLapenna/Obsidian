Tags: [[Drone Project]]

The Electronic Speed Controller is a electronic control board that varies the motor's speed, it can also act as a dynamic brake. This component also supports the ground pilot in estimating the drone height while it is flying (by calculating the amount of power consumed by all motors and linking it to the drone's altitude).
![[Pasted image 20250118124916.png]]
An ESC follows a speed reference signal and varies the switching rate of  a network of *Field Effect Transistors (FETs)*. By adjusting the duty-cycle or a switching frequency of the transistors, the speed of the motor is changed.
Different types of ESC are required for different types of motors:
- Brushed: a brushed motor can have its speed controlled by varying the voltage on its armature.
- Brushless: the speed of the motor is varied by adjusting the timing of pulses of current delivered to the several windings of the motor. Brushless ESC systems basically create three-phase AC power and are more complex than the brushed counterpart.
The ESC has to take into account the motor rotation in order to deed it the correct phase of current. For this scope, the back EMF from the motor windings is usually used.