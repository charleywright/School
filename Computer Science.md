## Development methodologies
#### [Iterative Development(https://www.techtarget.com/searchsoftwarequality/definition/iterative-development)
* Break down large problems into smaller parts
* Assign small chunks to individual developers
* Design, Develop, Test, Repeat

#### [Agile methodologies](https://en.wikipedia.org/wiki/Agile_software_development)
1.  Customer satisfaction by early and continuous delivery of valuable software.
2.  Welcome changing requirements, even in late development.
3.  Deliver working software frequently (weeks rather than months).
4.  Close, daily cooperation between business people and developers.
5.  Projects are built around motivated individuals, who should be trusted.
6.  Face-to-face conversation is the best form of communication (co-location).
7.  Working software is the primary measure of progress.
8.  Sustainable development, able to maintain a constant pace.
9.  Continuous attention to technical excellence and good design.
10.  Simplicity—the art of maximizing the amount of work not done—is essential.
11.  Best [architectures](https://en.wikipedia.org/wiki/Agile_Architecture "Agile Architecture"), requirements, and designs emerge from self-organizing teams.
12.  Regularly, the team reflects on how to become more effective, and adjusts accordingly

## [Environmental Impact](https://www.bbc.co.uk/bitesize/guides/zwg987h/revision/2)
#### Heating systems
**Activity Sensors**
* Change temperatures depending on the number of people in a room
* Disable heating if rooms are empty
* Learn patters of activity to preheat rooms

**Smart thermostats**
* Connected to a network
* Manually or automatically controlled using mobile devices
	* Control heating systems without being home

**Benefits**
* Only heating when necessary
* Reduces carbon footprint

#### Traffic control
* Vehicles are considered one of the main contribution sources of greenhouse gas
* Road transport causes 15% of all C02 emissions
* More fuel consumed when starting & stopping such as within a city
* Intelligent systems use software & hardware to improve efficiency
* Cameras, Sensors, Traffic signals are used to try keep traffic moving
* Stellite data can guide away from traffic

#### Car management systems
**Start-stop system**
Turns off and on engine automatically to reduce idling time thus emissions

**Engine control units**
Use sensors to control the air/fuel ratio perfectly

**GPS sensors**
GPS can alert lighting and heating systems to control devices depending on position automatically

## [Computer Structure](https://www.bbc.co.uk/bitesize/guides/zr8kt39/revision/1)
#### Fetch-Execute Cycle

#### System Performance
**No. Cores**
More cores -> More tasks can be run in parallel -> Faster execution
Each core contains an ALU (Arithmetic Unit), control unit and registers
Does not scale linearly, threads need to sync (std::mutex, std::conditional_variable)

**Width of data bus**
Bigger bus -> More data can be sent/received in one trip
32bit to 64bit -> Double the data transferred at one time (4 bytes to 8 bytes)

**Cache memory**
* L1 cache is built into each core (every core has its own cache)
* L2 cache is commonly shared between some/all cores however high end CPUs may have seperate L2 caches for each core (5950X has 512K per core)
* L3 cache depends on the processor and may not exist. It is shared between cores
* If one CPU has more Ln cache than another CPU, it will run faster because it can cache more instructions therefore hits are more likely

**Clock speed**
* How many clock cycles are performed per second
* 3.4gHz -> 3.4 billion cycles per second
* Higher clock speeds produce more heat and require more energy
* Theoretical overclock limits exist: If the clock speed is too high an instruction may not finish executing before the next is called, corrupting memory

## [Data Representation](https://www.bbc.co.uk/bitesize/guides/zsnbr82/revision/1)
#### Two's Complement
**Converting denary to binary**
1. Work out the positive number (for -26 find 26)
2. XOR with a full mask (flip all the bits, 1 becomes 0, 0 becomes 1)
3. Add 1

**Range**
$$-2^{n-1} \le x \le 2^{n-1}-1$$

#### Floating point numbers
* Split into mantissa and exponent
$$123.75 = 1.2375 * 10^{2}, m=1.2375, e=2$$
* Increasing range decreases accuracy (increasing exponent bits)
* Increasing accuracy decreases range (increasing mantissa bits)

**Converting Numbers**
Represent 123.75 in binary

| 64  | 32  | 16  | 8   | 4   | 2   | 1   |     | 1/2 | 1/4 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  1  |  1  |  1  |  1  |  0  |  1  |  1  |     |  1  |  1  |

The decimal point (indicated by the blank column) starts at the second column (32 in the above table). If it is not in this position it's offset needs to be found, which for the above table would be 6 (it is 6 columns to the right) making the exponent 6:
| 4   | 2   | 1   |
| --- | --- | --- |
|  1  |  1  |  0  |

This means the mantissa is 111101111 and the exponent is 110, or $1.11101111*2^{110}$

**Another example**
Represent 225.65625
| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |     | 1/2 | 1/4 | 1/8 | 1/16 | 1/32 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- | ---- |
|  1  | 1   | 1   | 0   | 0   | 0   | 0   | 1   |     | 1   | 0   | 1   | 0    |  1   |

The decimal point has an offset of 7
|  4  |  2  |  1  |
| --- | --- | --- |
|  1  |  1  |  1  |

This means the mantissa is 1110000110101 and the exponent is 111 or $1.110000110101*2^{110}$

#### Unicode

#### Bitmap vs Vector based graphics

## Design
#### Structure Diagram

#### Top level design

## Testing
#### Dry Tuns

#### Trace tables/tools

#### Breakpoints

#### Watchpoints

## Web
#### HTML
* nav
* header
* footer
* section
* main
* form
	* input
		* text
		* number
		* textarea
		* radio
		* submit
	* select
* id attribute

#### CSS
* display (block, inline, none)
* float (left, right)
* clear (both)
* margins/padding
* sizes (height, width)

**Nav bars**
* list-style-type: none
* hover

#### JS
* onmouseover
* onmouseout
* onclick

**Data validation**
* Length
* Presence
* Range