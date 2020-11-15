# Embedded Systems

I believe the rise of mobile Internet connections (e.g., Starlink) will usher in new advances in autonomous mobility (robotics) that will require low-level firmware and embedded engineering skills. Embedded software is written differently than application software, but it commonly needs to interact with enterprise systems. The ability to update the embedded devices within these machines is critical, and some programming interfaces seem better suited than others. 

An embedded system (a.k.a., target) is a computer integrated with a mechanical or electrical system. The target performs pre-defined tasks with specific requirements (often related to timing.) Embedded systems can be microprocessors, an integrated version of a computer’s central processing unit (CPU). They can also be microcontrollers (MCU), which will usually have a simple CPU core that includes memory and peripherals, a system on a chip (SoC). In either case, there is a system of integrated circuit(s) at the heart of the product designed to carry out computation for real-time operations.


# Examples

One thing is for sure; everyone has their idea of what an embedded system is. I consider general-purpose computers are not, but phones are often in the embedded system group. Industrial Programmable Logic Controllers (PLC) are general purpose, but once programed and wired into their specific function, they are embedded systems. Advanced Telecom Computing Architecture (ATCA) are general-purpose; many could run as cloud servers, but for some reason, they are also grouped in with embedded systems. What I am trying to get at is this is fuzzy. The easy ones are microwaves, coffee machines, fridges, air conditioning, remote controls, traffic lights, airbags, and anti-lock brakes. 


# Embedded Engineer

Embedded engineers typically have control over both hardware and software design. Typically this requires an in-depth knowledge of embedded architectures (e.g., AVR, ARM, RISC-V). I am from an Electrical Engineering background. I have command of the AVR architecture, including the toolchain, peripherals, and board layout for EMI (power-distribution, [crystal]). The programming language I most commonly use is C (e.g., Linux and round-robins); C++ gets more attention than it deserves. C programming is the bedrock of embedded engineering. The toolchain is implemented to run on a general-purpose Operating System (OS): so embedded developers usually need experience in programming in the supported OS. Additionally, the OS itself may be embedded, which means the embedded engineer needs command of the OS. Sadly in the past, when I claimed to have command of Linux, then the IT headhunters would start calling (don't waste your time).

[crystal]: ./crystal.md


# Yet more

 - Board Layout, I like to do the board layout and find it therapeutic.

 - Self Test, software that scans through the integrated hardware and gives a pass-fail result. 

 - Debug with oscilloscopes, logic analyzers, multimeters, software debugers (gdb), and hardware layout interfaces that experience has proven useful.

 - Microprocessor interrupt processing for: I2C, UART, Timers, ADC.

 - Microprocessor register control for: PWM, DAC, DMA, I2C, SPI, UART, Timers, ADC.

 - Python for programs that I need to run on a host (e.g., not the embedded target)

 - I am experimenting with WSGI as an interface to a hard-link that browsers can access (e.g., JS in DOM using JSON data returned from WSGI).

