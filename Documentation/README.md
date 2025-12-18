Discrete Class D Audio Amplifier Design
Project Overview
This project involves the design, simulation, and PCB layout of a Class D Audio Amplifier using discrete components. The circuit utilizes an NE555 timer for PWM generation and an LM741 Op-Amp as a comparator to process audio signals.
1. Circuit Design & Logic
The amplifier operates on the principle of Pulse Width Modulation (PWM) to achieve high efficiency.
·	PWM Generation (NE555): The NE555 timer is configured as an astable multivibrator to generate a high-frequency carrier wave. With $R_1=1\text{k}\Omega$, $R_2=3.3\text{k}\Omega$, and $C_1=1\text{nF}$, the switching frequency is approximately 180kHz, well above the human hearing range.
·	Comparator Stage (LM741): The LM741 compares the $1\text{kHz}$ audio input against the high-frequency carrier wave to produce a PWM signal where the pulse width is proportional to the audio amplitude.
·	Low-Pass LC Filter: A second-order filter consisting of a $22\mu\text{H}$ inductor ($L_1$) and a $1\mu\text{F}$ capacitor ($C_3$) is used at the output. It has a cutoff frequency of approximately 34kHz, effectively stripping the high-frequency carrier to recover the original audio signal.
2. Simulation Results
The circuit was verified using the built-in SPICE simulator in KiCad.
·	Audio Recovery: The simulation successfully demonstrates the recovery of a $1\text{kHz}$ sine wave from the PWM signal.
·	Transient Response: A brief startup transient is observed before the signal reaches a clean steady-state output.
3. PCB Specifications
The physical board was designed with manufacturing and reliability in mind.
·	Layers: 2-Layer through-hole design.
·	Netclass & Trace Widths:
·	Power/GND: Assigned a width of 0.8mm to handle current and ensure voltage stability.
·	Signal: Assigned a width of 0.25mm for standard audio and timing connections.
·	Board Dimensions: Approximately 50mm x 50mm with connectors (J1-J3) placed at the edges for easy interfacing.
·	DRC Verification: The board passed the Design Rules Check with 0 Errors and 0 Unconnected Items.
4. Component List (BOM)
Component	Value/Part	Footprint
U1	NE555P	DIP-8_W7.62mm
U2	LM741	DIP-8_W7.62mm
L1	22uH	L_Axial_L9.5mm_D4.0mm_P15.24mm
C3	1uF	C_Disc_D5.0mm_W2.5mm_P5.00mm
J1, J2, J3	2-Pin Conn	PinHeader_1x02_P2.54mm_Vertical


