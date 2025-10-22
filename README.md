# NetcatLab — Ethical HID Device Lab (Educational)

> **NetcatLab** is an educational repository demonstrating how Human Interface Device (HID) payloads can automate keyboard input using microcontrollers (Arduino) and Rubber Ducky–style scripts.  
> **This repo is strictly for learning, research, and authorized testing only.**

---

## ⚠️ TL;DR — Read This Before Doing Anything
- Don’t be dumb: **DO NOT** use these techniques on machines you don’t own or don’t have explicit **written permission** to test.
- This repo contains **benign demo payloads only** (e.g., open Calculator, type demo text). It intentionally **does NOT** include remote shells, download-and-execute code, or code that gives unauthorized control.
- Test inside an **isolated lab** (VMs, snapshots, air-gapped network) and follow the safety checklist in `docs/lab-safety.md`.

---

## Why this repo exists
NetcatLab is for people who want to learn:
- How HID injection devices emulate keyboard entry.
- How Arduino can act like a USB keyboard (HID).
- How Rubber Ducky payload scripts are structured.
- Safe, ethical experimentation and documentation practices for hardware-driven automation.

---

## Repo Structure
NetcatLab/
├─ arduino/ # Example Arduino HID sketches (benign)
├─ rubber_ducky/ # Example Rubber Ducky payloads (benign)
├─ lab-safety.md # Safety checklist & lab setup
├─ README.md # THIS FILE
└─ LICENSE # MIT License

## 🛠️ Lab Setup — Test Safely
- Use virtual machines (VirtualBox / VMware). Snapshot them before any test.
- Isolate the network — use an internal-only network or air-gapped environment. No Internet for the target VMs.
- Never target real users or production systems — only use devices you own or explicitly have consent to test.
- Document scope & permission — always keep written permission and test logs (who, where, when, what).
- Rollback — always have VM snapshots and a rollback plan.
- Monitor & record — keep console/video logs for accountability.

## How to use this repo (quick)
- Clone
```bash
git clone https://github.com/<yourusername>/NetcatLab.git
cd NetcatLab
```
- Read docs/lab-safety.md and follow the checklist.

- Load arduino/*.ino sketches in Arduino IDE (select correct board and USB HID-capable microcontroller like Leonardo, Micro, Pro Micro).

- For Rubber Ducky: compile/upload with DuckEncoder or a supported toolkit, but only with benign payloads and in a lab.

## About the Author

Harsh Kanojia (harsh-hak) — Cyber Security student & hardware-hacking curious.
GitHub: https://github.com/harsh-hak — Hit me up if you want collabs or doc improvements.
