# Anti-Proxy-Attendance-System
Anti Proxy Attendance System (APAS) — open-source, Raspberry Pi (Raspbian) biometric attendance that prevents proxies using R307 fingerprint verification with faculty-controlled sessions. SIH 2024 winner. Python UART, Adafruit lib, Excel export, easy to fork for classrooms and labs. Contributions welcome!
# Anti Proxy Attendance System (APAS)

Award‑winning, open‑source biometric attendance for classrooms, built on Raspberry Pi with Raspbian/Raspberry Pi OS, using the R307 fingerprint sensor and Python for fast, accurate, proxy‑proof roll calls.

## Highlights
- Biometric accuracy with R307 optical fingerprint verification
- Faculty‑controlled sessions (start/stop + PIN) for integrity
- Portable, low‑cost Raspberry Pi hardware stack
- Instant Excel exports and simple data flows
- SIH 2024 winning solution, now fully open‑sourced

## Why open source?
APAS is released to empower students, educators, and institutions to adopt trustworthy attendance without vendor lock‑in. Open code invites auditability, faster innovation, and community‑driven improvements in usability, security, and scale. Contributions help extend APAS across labs, seminars, and campus events—benefiting real classrooms nationwide.

## Tech stack
- Raspberry Pi 4, Raspbian/Raspberry Pi OS
- R307 fingerprint sensor over UART (57600 baud)
- Python, pyserial, Adafruit Fingerprint library
- Optional: openpyxl/Pandas for Excel exports, reportlab for PDFs

## Core features
- Faculty authentication to open/close sessions
- Student fingerprint enroll, match (fast search), delete
- Per‑subject session handling with teacher verification
- Attendance summary (present/absent) and export
- Image capture utility for sensor diagnostics

## Hardware and wiring
- Raspberry Pi 4
- R307 sensor to Pi UART:
  - R307 TX → Pi RX (GPIO15)
  - R307 RX → Pi TX (GPIO14)
  - VCC → 5V, GND → GND
- Optional 5" display for in‑class UX

## Setup
1) Enable UART on Raspberry Pi OS (disable serial console, keep serial hardware).  
2) Install dependencies:
- Python 3.x
- pip install: serial, adafruit-circuitpython-fingerprint, pillow, openpyxl, pandas, reportlab
3) Connect the R307 and confirm the port (e.g., /dev/ttyS0).  
4) Run the script and follow on‑screen prompts.

## Usage flow
- Enroll students via “e” (two scans per finger for templating)
- Start attendance via “f”, select subject, authenticate faculty fingerprint
- Circulate device; matches log presence and print student details
- End with PIN; export summaries as needed

## Security notes
- Use strong faculty PINs and restricted physical access
- Prefer secure storage for templates/exports
- Follow local data protection and consent policies for biometrics

## Roadmap
- Admin web dashboard and analytics
- LMS integration (via CSV/API)
- Optional face/iris modules
- Encrypted template storage and role‑based access

## Contributing
- Fork, create a feature branch, open a PR
- Add tests where possible and update docs
- Propose issues for bugs and features

## License
- SPDX: MIT. Use it freely for education and research; credit appreciated.

## Acknowledgments
- Community maintainers, educators, and student testers
- Adafruit libraries and Raspberry Pi ecosystem

## Quick start commands
- pip install pyserial adafruit-circuitpython-fingerprint pillow openpyxl pandas reportlab
- python3 apas.py

Build accurate, auditable attendance that scales—together.
