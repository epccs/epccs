# epccs

Hi, I am Ron. I am an electrical engineer who likes a mix of power electronics and microcontrollers. I am in the process of switching gears back to my microcontroller projects; I was not able to do much of that at my last job, but now that I have admin rights on the computer in front of me again... I can make progress. Three and a half years ago I was starting to get the hang of VSCode with IntelliSense for AVR microcontrollers and thought that was amazing, but looking at how AI can get projects started now... it is just nuts, I can't believe how much has changed in such a short time.

## Musings (bimonthly)

I'm switching this section from yearly to every couple months, since I have more to say than once a year apparently.

This round: how STM32CubeMX expects you to work versus how I've actually been using it on my SPY-CNTL02 firmware (on Linux, with Claude doing a lot of the typing). CubeMX wants one `.ioc` file to own one project — you tweak the pinout in the GUI, it regenerates `main.c` between `USER CODE BEGIN/END` markers, and you build it in CubeIDE, which is an Eclipse-based installer that wants admin rights on Windows for itself and the ST-Link USB drivers. I never do any of that. I run the generator once per MCU to get the HAL drivers, linker script, and startup file, then hand-write a `Makefile` and a `Core/` folder for every standalone test project I need, all pointed at that one shared driver tree. No regeneration, no IDE, building with plain `arm-none-eabi-gcc` from `apt`. The `USER CODE BEGIN/END` markers are still in there out of habit even though nothing is ever going to regenerate over them.

It's a roundabout answer to last time's question about admin rights: on Linux the one time you need elevated anything is `sudo apt install gcc-arm-none-eabi binutils-arm-none-eabi libnewlib-arm-none-eabi gdb-multiarch make`, and after that you're a regular user for the rest of the project's life. No IT department keeping an installer alive, no MPLAB silently bricking a PICkit after a Windows update. I don't think I could have put a project together this way without an AI doing the boring scaffolding (Makefiles, linker scripts, the part of CubeMX output nobody enjoys reading) while I focus on the hardware side.

## Thanks for visiting

That is it for now.
