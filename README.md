# epccs

Hi, I am Ron. I am an electrical engineer that enjoys working with microcontrolers and the systems that use them.

## The problem

Programable devices are nearly ubiquitous. Most do simple tasks (e.g., timing the cooking of my oatmeal); once the firmware is done and verified, it may never need to change. I want the stovetop to work even if the electricity is out (which it does). Still, I also want the stove to notify a host computer (e.g., Raspberry Pi) to follow an event schedule, which it does not. When I stop the timer beeping, I want it to send that to a host computer; when I push start, it needs to upload the time for the next event in the schedule from the host (or load a default.) Maybe the microwave, toaster, coffee maker, and dishwasher also need an interface for automation. However, they don't need computers embedded that become obsolete in a few years.

## Current solutions and why they suck

The high-end kitchen stove has a touch screen computer and wi-fi. By the time it reaches a showroom, some exploits have been discovered that will allow it to be added to someone's botnet or do other nefarious things. The problem is a metaphor for complexity; the better solution is to keep things less complicated. Wireless may sound like a good option, but it adds complexity and a vast exploitable footprint. Maybe USB could be used to interface with a computer, but that would mean the host needs to be within two meters.

The industry standard for equipment automation is RS-485; though the cable is expensive, only UART hardware is needed on the microcontroller and a transceiver to interface with the cable. Firmware updates over RS-485 require a bootloader on the device and an uploader on the host; unfortunately, even when done perfectly, the system can get locked, thus blocking updates.

## My solution

RS-485 transceivers have a few flavors; for example, some have a built-in fail-safe. Also, they can be configured as full-duplex rather than half-duplex, which makes locking the interface between the host and device impossible (this is the incident that launches the story, it may need more flesh added). RS-485 transceivers work fine over CAT5 cable, which has pairs for full-duplex (and more). Once graduating to full-duplex, bootloaders are a dime a dozen, almost all are done full full-duplex, and there are a bunch of them. I have started using UPDI, which is the new programming/debugging interface on Microchip's AVR. UPDI can also be done over the multi-drop full-duplex lines, which removes the bootloader entirely; the host just needs to run Microchip's upload tool (which works on Win/Lin/Mac).

## Why my solution is better

Who has worked on equipment where the updates were not getting through (e.g., something locking the programming interface).  Maybe NASA is the primary caretaker of ensuring a robust upload method. The old-school Arduino Uno is robust; in other words, no matter how messed up my program was, I could still overwrite it with a new one; newer models seem more fragile. The newer AVR's with UPDI allows setting flags that can lock the microcontroller, so they have to be erased first.

## More traction

I want the stove I use to stay as simple as possible, with no radio, Wi-Fi, or networking. But I do want a way to interface it with things that can do those. I would also like to update the firmware on the stoves microcontroller that connects with a multi-drop to the cluster of devices in my kitchen that my host (R-Pi) uses. This would allow updating/replacing the host independent of the equipment and get the computer security problems out of the equipment.

## Resolution of story

It is essential to minimize the security footprint and maximize simplicity. The question is how to bring desirable capabilities without ditching the essentials. Some software developers don't seem to believe in computer security or updates, even after their system gets owned. Outfits like Tesla know how important software updates are. I have not disassembled a Tesla, but I suspect updates are done over wires (no radios). A radio may get a verifiable package into the host that orchestrates all the update steps. Still, the updates don't happen until the package is verified, and they are done over wires, probably CAN bus (that is not a trivial bootloader). All programable things should be done like this; it is the only extensible and potentially secure way. There are many options for a host at the network edge, I like an R-Pi, but the important thing is that this is where the **network ends**.

### Note to self

<https://startuppitch.substack.com/p/nail-your-startup-pitch-use-pixars>