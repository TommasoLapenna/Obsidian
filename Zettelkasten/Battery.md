Tags: [[Drone Project]]

# LiPo Batteries
A lithium polymer batteries are the source powers for drones, their exceptional power-to-weight ratio make them an ideal choice.
![[Pasted image 20250123181108.png]]
LiPo batteries consist of individual cells, each with a nominal voltage of 3.7 V, the number of cell and total voltage is indicated on the label. 
A LiPo battery cell is to be chared and dischareged within a specific voltage: 4.2V (fully charged) - 3.0V (fully dischareged). Staying between these limits is important in order to respectively fires or irreversible performance damage.
# Naming
Example:
- **3s 2000 mAH 20c**
	- 3s: is how may cells are wired in series and parallel
	- 2000 mAH: is the capacity of the battery, it means how much electricity it can supply before it dies. By dividing this number by 1000 multiplying it by the c rating the maximum number of amps the battery can supply before damage is obtained.
	- 20c: is the c rating, it represents the maximum amount of amps that the battery can supply. The burst c rating can be calculated from this
- **BEC**: is the Battery Eliminator Circuit
So, to get the nominal voltage of a battery pack: s rating\*3.7V.
There is also a more rare type of rating, which is the p rating (parallel).
Battery voltage directly affects motor speed, so using a higher cell-count battery can increase the drone's power, however the increase of cost and weight are to be considered.
## Also
- if two batteries connected (for example): 4S 1000 mAh and 2S 1000 mAh
	- in parallel: 2S 2000 mAh
	- in series: 4S 1000 mAh
