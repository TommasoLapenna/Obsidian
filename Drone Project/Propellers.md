Tags: [[Drone Project]]

A Propeller is a device with a rotating hub and radiating blades that are set at a pitch to set a helical spiral which, when rotated exerts linear thrust upon a working fluid such as water or air. the blades are shaped so that their rotational motion through the fluid causes a pressure difference between the two surfaces of the blade by Bernoulli's principle which exerts force on the fluid. So in other words the airfoil shaped blades create a pressure difference (lower pressure above and higher pressure below), propelling the drone upward or forward.![[prop.jpg]]
The front edge of the blade is called leading edge, which cuts into the air first. It splits the airflow, directing some over the curved surface (generating low pressure) and some under the flatter side (higher pressure). The rear edge of the blade is called Trailing Edge, where the airflow recombines. The combined pressure difference across the blade surfaces generates lift. The spin direction is the one where the leading edge points to.

In a quadcopter, two motor spin clockwise (CW) and the other two spin counter-clockwise (CCW). The reason behind this setup is that two propeller generate CW torque, the other two generate CCW torque that cancel the previous, eliminating the rotational forces
# Specifications and Naming
The three main dimension of a drone's propeller are size, pitch and blade count (5x4x3 or 5040x3)
### Size
The first number in the specification is the *size* of a propeller. This number refers to the diameter of the propeller (inches), which is the circular area the propeller creates while spinning. 
Bigger and smaller sizes have their own advantages and disadvantages: the former generates more thrust due to its larger surface area, but requires a stronger motor, whereas the latter produces less thrust but are easier on the motor and the RPM can be change faster (and makes the drone more responsive and agile).
### Pitch
The second number represents the *pitch*. This refers to how far the propeller would theoretically move forward in one rotation (inches) if there were no air resistance (similar to a screw)
![[pithc.png]]
As the size mention before, higher and lower pitch have their advantages and disadvantages:
- Low pitch
	- Easier to spin through the air, enabling quicker RPM changes
	- Provides, provides more responsive control and generates less propwash vibration (da vedere)
	- Requires less motor torque and draw less current
	- Lower thrust and top speed, due to the less moved air
- High pitch props
	- Creates greater thrust and top speeds, due to the more moved air
	- Requires more torque to change RPM, which reduces responsiveness
	- Less efficient
### Blades
The third number is the number of *blades*. 
- 2 blade: efficiency and low drag, ideal for longer flights
- 3 blades: Balance of thrust, agility and efficiency (most popular choice)
- 4 blades: More thrust and stability, but less efficiency, ideal for heavier payloads 
### Mounting Methods
- **Prop Nuts:** The propeller is plance onto the motors shaft with a M5 thread and secured with a self-locking nylon nut
- **T-Mounts:** The propeller is secured to the motor bell using two small M2 screws (used on smaller drones)
- **Press Fit:** The propeller is pushed onto the motor shaft using friction to hold it in place (ultralight drones)