# epccs

Hi, I am Ron. I am an electrical engineer that enjoys work on [embededed systems].

[embededed systems]: ./embedded_systems.md

[experience](./experience.md)

[past_projects](./past_projects.md)

## Overview

I'm competent with the AVR toolchain; I plan to gain competency with the ARM and RISC-V toolchain as time permits.

## Status

Working on circuit boards and software for my projects (MacGyver, Gravimetric, and others).

## How I work

I mostly lean away from cutting-edge technology to take advantage of abundant, well-understood, and cheap.

I can do Python and C. To be clear, I am not doing UX software. I would describe the software I do as daemon-like, and it tends to be debugged with a command-line interface (e.g., a terminal). IoT is not my thing; placing networking services on bare metal adds nightmarish complexity resulting in security footprints fraught with an intolerable scale. The flip side of IoT is establishing a networking machine (e.g., Raspberry Pi) next to one or more bare metal devices and using that as the cloud server, but it is connected by hard link(s) with bare-metal devices. Networking options like Starlink should make this option more desirable.

## Need help with a project

I spent over 15 years as a test engineer on an SMD line that produced power conversion products for telecom. I got to see a lot go wrong during that time. Don't ICT unless you lay out the board for ICT (but AOI is an excellent way to go). I am a fan of functional and self-testing (with constraints that prevent damage). I develop the test early on my projects and then change it if I need to change things during evaluation. I have done a fair number of prototype boards and have confidence that I can do that for others, but it is still done by hand placing parts, so SMD should mostly be 0805 with a few 0603.
