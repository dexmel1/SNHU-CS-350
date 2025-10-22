# SNHU-CS-350
Emerging Sys Arch &amp; Tech

## Summarize the project and what problem it was solving.
I developed a smart thermostat prototype that measures temperature using an AHT20 sensor over I²C, controls status LEDs with PWM, manages a mode button and set-point buttons via GPIO interrupts, displays data on a 16×2 LCD, and streams telemetry through UART. The goal was to reduce risk in the low-level control and user interface, and to outline a pathway to a Wi-Fi–connected production device.

## What did you do particularly well?
I designed a clear state machine (OFF/HEAT/COOL) with explicit entry/exit actions, which made the behavior predictable and easy to extend. I also kept peripherals loosely coupled behind small driver functions, so swapping hardware or changing timing didn’t cause unnecessary complications.

## Where could you improve?
I could add debounce to button presses to avoid unintentional action triggering and improve error handling to offer better messages explaining what was occurring.

## What tools and/or resources are you adding to your support network?
Vendor SDKs, datasheets, and sample MQTT/TLS stacks for AWS/Azure are now part of my toolkit. I’m also adding a logic analyzer for traces, code linters/formatters, and lightweight CI to maintain high quality.

## What skills from this project will be particularly transferable to other projects and/or course work?
Embedded interfacing and disciplined state-machine design translate well to other hardware projects. Project planning and forward-looking thinking (such as cloud-readiness), along with the ability to justify architecture choices in business terms, are broadly useful.

## How did you make this project maintainable, readable, and adaptable?
I structured the code into dedicated modules (sensor, LEDs, buttons, LCD, telemetry) with consistent naming and clear docstrings. Important parameters are stored in constants, and a central state machine with logging, along with a state diagram/README, facilitates quick onboarding and future Wi-Fi integration.
