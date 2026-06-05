$e$ is elementary charge constant, which is defined as electrical charge energy that is carried by single proton (positive charge) or electron (negative charge) which is equal to $+-1.602 * 10^{-19}\ C$

Coulomb = unit of charge per second, is equal to $e^{-1}$

Coulomb = unit of charge, - electron per



Current (Ampere) = 1 coulomb per second. No current, no electricity flow. 
Relation with coulomb I = Q / t, where Q is unit of charge and t is time.
Current flows in negative direction (from negative to positive)




Volt = potential difference.
Resistance = Limitation of current. Resistors convert energy to heat

Resistivity
Conductivity
Wattage
Joule = measure of energy

Type of element can be determined by numbers of atoms (number of atoms is always the same for same element). Neutrons and protons are bound together into nucleus, and around  them is electron field

# $I^2C$

i2c is inter integrated circuit protocol (short distance) for communication, with multiple masters / slaves, but only one master can communicate at time

***Master (controller)*** - device/owner of bus line (MCU, SBC) that wants to communicate with targets
***Slave (target)*** - devices that by itself don't communicate, only by request master

> [!info] 
> Each target must have unique address, addresses can be set by jumpers (predetermined by target makers) [List of addresses](https://learn.adafruit.com/i2c-addresses/the-list)

Typical speeds:
1. Standard - 100KHz
2. Fast - 400KHz
3. Fast plus = 1MHz
4. Ultra fast = 4MHz (uncommon, unidirectional, only write)
Bigger speeds reduce range.

i2c communication flow:
1. Send start signal on SDA, start clock signal on SCL
2. Send 7bit target address on SDA
3. Send R/W bit on SDA
4. Receive ACK from target (SDA)
5. Receive data from target, where after each byte master must send ACK or NACK on SDA bus
6. End signal, stop sending clock signal in SCL
SDA - data channel
SCL - i2c clock signal, that determines speed of device

> [!info] 
> Both SDA and SCL must have pull up resistor because targets by themselves are not capable to send huge current. Also it's more efficient and easier to pull current from master.

***Repeated start*** - some devices require to send another start before end, for example they require that you write some operation byte and then immediately read response, otherwise it will throw away result

It's hard to determine whatever device is sending signal or just it takes too long, ***Clock stretching*** strategy is used, where target device takes control of clock and keeps clock low to signal that is computing.
