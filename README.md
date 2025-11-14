# OpenSeasame

OpenSeasame is a compact, low-power open-hardware door/lock controller designed for long battery life and simple, tactile interaction. It's built around an STM32L0-series MCU and provides a small OLED display, RGB status LED, piezo speaker, three buttons, and USB-C for data and charging.

Quick highlights
- Low-power STM32L072CBT microcontroller (L0 series)
- 128×64 OLED display (SSD1306)
- RGB status LED for notifications
- Piezoelectric speaker for tones and alerts
- Rechargeable 1000 mAh LiPo battery
- USB-C connector for data and charging
- Three user buttons (menu / action / navigation)
- Small footprint and power-saving firmware

Why this project
OpenSeasame aims to be an open, hackable, battery-friendly building block for door control, access tokens, or other embedded UI projects. The design prioritises low standby power, a simple local UI, and easy firmware development.

Images

![Device front view](https://github.com/user-attachments/assets/be12a38c-e522-4aad-b491-eedd3de9e4ac)

![Device side view](https://github.com/user-attachments/assets/f2dc01b5-bfb4-4dcf-b215-6f4afa0d6af1)

![OLED UI screenshot](https://github.com/user-attachments/assets/010cc4e4-40a0-46a1-823f-5fb57b405ab0)

Getting started

Hardware
- Charge the battery through the USB‑C connector before first use.
- Power on; the OLED will show the boot UI.
- Use the three buttons to navigate: short-press for selection, long-press for alternate actions (e.g., enter configuration). Exact button behaviour is firmware-dependent — see the firmware docs.

Flashing firmware

Recommended: PlatformIO (works well with STM32 and common bootloaders)
1. Install PlatformIO: https://platformio.org
2. Clone this repository:
   git clone https://github.com/Tejaji-0/openseasame.git
3. Open the project in VS Code with the PlatformIO extension or use the CLI.
4. Build and upload:
   pio run -t upload

Project layout (top level)
- firmware/ — MCU firmware source and build files
- hardware/ — schematics, PCB layouts, BOM (if present)
- docs/ — design notes and usage documentation
- LICENSE — project license (CERN‑OHL‑S v2)

Power and low-power considerations
The STM32L0 family is optimised for low-power operation. Firmware uses sleep and peripheral standby modes to maximise battery life. If you add peripherals or change the board, re-measure current draw and adjust wake/sleep behaviour accordingly.

Contributing
Contributions are welcome. Suggested workflow:
1. Open an issue to discuss larger changes or file a bug.
2. Fork the repository and make your changes in a feature branch.
3. Submit a pull request with a clear description and screenshots (for UI or hardware changes).
When contributing hardware revisions, include clear photos, updated schematics (KiCad / Eagle), and an updated BOM.

Code of conduct
Be respectful and constructive. If you want a code of conduct added, I can help draft one.

Troubleshooting
- Device not powering on: confirm battery is charged and cable/connector orientation is correct.
- Firmware won't flash: check that the board's bootloader/jumper settings are correct for your programmer, and that drivers for your programmer are installed.

License
OpenSeasame is distributed under the CERN Open Hardware Licence v2 — Strongly Reciprocal (CERN‑OHL‑S v2). See LICENSE for full terms.

Contact / Support
- Open an issue on this repository for bugs or feature requests.
- Prefer including hardware photos, logs, or serial output when reporting problems.
