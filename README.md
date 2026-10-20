# ConnectOS-demo-CYD

ConnectOS | CYD Port (Alpha)

ConnectOS is the original operating-system-style interface designed for the ESP32-S3 version of the project. It is not a generic embedded dashboard or a single launcher screen, but a compact, touch-first desktop and phone-like environment with its own recognizable identity.

This project adapts ConnectOS to the ESP32-2432S028R (Cheap Yellow Display / CYD), featuring a 2.8-inch, 240×320 touchscreen.

Development Status: ALPHA

The CYD port is currently in the Alpha stage. Core functionality, touchscreen interactions, visual fidelity, performance, and hardware compatibility are still being developed and tested. Features may be incomplete, unstable, or subject to change.

The goal is to preserve the original ConnectOS experience while adapting its interface and functionality to the CYD’s hardware limitations.

Core Features

	•	First-Time Setup : Initial device configuration with saved setup state.
	•	Lock Screen : A slide-to-unlock interaction with touch tracking, unlock thresholds, and cancellation behavior.
	•	Home Screen : Exactly six core applications: Phone, Messages, Cora AI 8.0, Games, Calculator, and ConnectLynx.
	•	More Apps : A separate application directory that keeps the Home screen organized.
	•	System Navigation : Home, Back, Close, Settings, dock controls, notifications, and status elements.
	•	Cora AI 8.0 : A dedicated assistant application with a touchscreen keyboard and honest offline responses when no online AI service is available.
	•	ConnectLynx : A portrait-oriented desktop and workspace environment, not simply another application launcher.
	•	Local Persistence : Saved settings and data, including themes, wallpapers, Connect ID, setup completion, reset state, and application data where supported by the hardware.

These features describe the project’s intended functionality; their implementation and reliability must be verified during Alpha testing.

Original Design, Preserved

ConnectOS should remain recognizable as the same project across hardware platforms. Its branding, visual hierarchy, colors, iconography, typography, proportions, panels, artwork, transitions, and application behavior should stay faithful to the original ESP32-S3 version.

The CYD port may require carefully scaled layouts and simplified rendering, but hardware adaptation should never turn ConnectOS into a different project with a similar name.

CYD Hardware Adaptation

The ESP32-2432S028R introduces several practical constraints:

	•	Display: Adapt the original interface to the 240×320 portrait screen while maintaining correct proportions and full-screen coverage.
	•	Touchscreen: Account for the CYD’s touch controller, coordinate mapping, alignment, and orientation.
	•	Performance: Optimize memory usage, redraw operations, and transitions for the available hardware.
	•	Rendering: Minimize flickering, static, visual noise, and unnecessary full-screen redraws by preserving unchanged screen areas where possible.
	•	Reliable System Information: Never fabricate network connectivity, AI responses, storage capacity, battery levels, sensor readings, or service status. Unsupported features must be identified as offline, unavailable, or local demonstrations.

Lock Screen Interaction

The lock screen is an especially important part of the CYD port. The unlock handle must respond only to a valid touch on the handle, follow the finger smoothly without jumping, and unlock only after reaching the correct threshold.

If the user releases the handle too early, interrupts the touch, or cancels the gesture, the handle must return smoothly to its starting position without accidentally unlocking the device.

Current Project Status

The project targets the ESP32-2432S028R CYD, uses USB power, and contains ConnectOS firmware as an Arduino/C++ project.

Previous deployment evidence indicates successful compilation, firmware upload, and basic boot stability. However, successful deployment alone does not establish full visual fidelity or prove that every touchscreen interaction works correctly on the physical device.

As an Alpha project, the next development stage focuses on:

	1.	Verifying full-screen portrait rendering at 240×320.
	2.	Checking colors, alignment, text, icons, and visual consistency against the original ConnectOS references.
	3.	Testing touch accuracy and major navigation interactions.
	4.	Validating slide-to-unlock behavior, including interrupted and cancelled gestures.
	5.	Checking rendering stability, flickering, memory usage, and responsiveness.
	6.	Comparing the setup flow, Home screen, applications, settings, and ConnectLynx against the original design.

Project Philosophy

One operating system. Multiple hardware targets. One recognizable identity.

The CYD port is an ongoing Alpha adaptation of the original ConnectOS experience for a smaller, more constrained touchscreen device.

It is still under active development, and its functionality, stability, and visual fidelity must continue to be validated on real hardware.

ConnectOS remains ConnectOS, adapted to the hardware, honest about its limitations, and faithful to its original vision.
