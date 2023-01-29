## Development methodologies
#### [Iterative Development](https://www.techtarget.com/searchsoftwarequality/definition/iterative-development)
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
11.  Best architectures, requirements, and designs emerge from self-organizing teams.
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
**Reading**
1. MAR (Memory Address Register) sets up the address bus with the relevant memory location to be read from
2.  The control unit read line is activated
3.  The contents of the address held on the address bus are placed on the data bus
4.  The data bus transfers the data from memory to the MDR (Memory Data Register)

**Writing**
1.  MAR (Memory Address Register) sets up the address bus with the relevant memory location to be written to
2.  MDR (Memory Data Register) passes the data to be written to the data bus
3.  The control unit write line is activated
4.  Data bus transfers the data to the memory location specified on the address bus

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
* Original ASCII used 7 bits. The 8th bit has had plenty of use but there is not one cohesive standard. In extended ASCII it is used to represent more characters however it can also be used for parity checking. ASCII and extended ASCII are both limited in the number of characters they can represent, making them unable to store other languages or less popular symbols therefore Unicode was created
* Unicode can use 8, 16, or 32 bit encoding depending on the number of characters needed, and aims to represent every character needed to write in any language. The tradeoff is of course unicode takes more memory to store the same characters

#### Bitmap vs Vector based graphics
**Bitmaps**
* Bitmaps store each pixel of an image individually
* An image has a bit depth, which is how many bits are used per pixel (8 bit color -> 256 colors, 24 bit color -> 16+ million colors). 16bit is known as "true color"
* They do not scale well, becoming blurry or blocky as they are resolution dependant
* They are stored using a 2D array structure
* JPEG, PNG, GIF are commonly used alongside compression
* Ignoring compression, adding/removing detail will not change the file size

**Vector Graphics**
* Vector graphics are a set of instructions detailing how to draw an image
* They scale infinitely, small or large
* Layering does not lose data underneath as layers are simply drawn on top of eachother (in the file, not necessarily the implementation)
* Adding/removing detail will change the file size
* Very difficult to store a highly detailed image such as a photo and will produce very large files
* SVG is the most common format

## [Design](https://www.bbc.co.uk/bitesize/guides/z3yc9j6/revision/1)
#### Structure Diagram

#### Top level design

#### Pseudocode

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

## [Security](https://www.bbc.co.uk/bitesize/guides/z9fbr82/revision/1)
#### Computer Misuse Act 1990
The Computer Misuse Act (1990) recognises the following as offences:
1.  Unauthorised access to computer material
2.  Unauthorised access with intent to commit or facilitate a crime
3.  Unauthorised modification of computer material.
4.  Making, supplying or obtaining anything which can be used in computer misuse offences.

#### Risks
**Tracking cookies**
Most often used for sessions & storing state, however can be used to exfiltrate data (Does XSS come into this?)

**DOS Attacks**
Multiple forms:
* Fill bandwidth so other requests cannot get through
* Use all available resources e.g disk or CPU

Can be motivated by
* Financial gain e.g ransom
* Political opposition (hitting a government site in protest)
* Personal e.g a grudge, revenge, disproval etc

Costs:
* Overtime for employees fixing the problem
* Lost purchases/deals in the time offline
* Customers going elsewhere
* Business deals falling through e.g a contractor not being able to complete work
* Critical infrastructure failing

#### Encryption/signatures
**PKE (Public key encryption)**
Normally communication goes something like this (having implemented it a few times over TCP)
1. Open a socket, server sends its public key
2. Client encrypts its public key using the server key and sends it back
3. Server decrypts the client's key using it's private key
4. Server generates a shared secret, encrypts using the client key and sends it
5. Client decrypts the shared key, from now on communication uses a block cipher such as AES CTR

Of course this is not needed to know for the exam, only the following:
* Public key encrypts a message to be sent
* Private key decrypts a received message
* Encryption schemes (Ciphers) are very complicated with lots of maths allowing only the private key to decrpy a message. Brute forcing is near impossible (Sidenote: See [the factoring problem](https://en.wikipedia.org/wiki/Integer_factorization) and [Shor's Algorithm](https://en.wikipedia.org/wiki/Shor%27s_algorithm) for more detail)
* The public key cannot work out the private key (Sidenote: Private keys can normally work out the public key, used by RSA fairly often)

**Digital Certificates e.g SSL**
* Used to validate the sender is who they claim to be
* Can only be issued by certified authorities e.g Google, Comodo
* Used for SSL, the padlock indicates secure transport. (Sidenote: HTTPS is not always secure: [Weak cipher suites exist and shouldn't ever be used](https://owasp.org/www-project-web-security-testing-guide/v41/4-Web_Application_Security_Testing/09-Testing_for_Weak_Cryptography/01-Testing_for_Weak_SSL_TLS_Ciphers_Insufficient_Transport_Layer_Protection)

**Digital signatures e.g HMAC**
* Ensure a message or document is authentic
* Created using a private key (opposite of PKE)
* The public key is sent with the signature to validate it