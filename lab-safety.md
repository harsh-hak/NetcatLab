## ⚠️ HID Risks & Lab Safety — Read This Before You Touch Anything

**Short version:** HID payloads (Arduino, Rubber Ducky, etc.) can act like a keyboard and type commands instantly — which means they can also run dangerous stuff without a user noticing. Don’t be clumsy. Don’t be illegal. If you’re not testing on your own equipment or you don’t have explicit written permission, stop now.

### Why HID devices are risky
- HID devices *emulate keyboards* and bypass many endpoint protections by typing commands directly into the OS.  
- A single payload can open a shell, download malware, or change system settings in seconds.  
- These payloads are *extremely powerful* and extremely easy to misuse — which is why we treat them like a scalpel, not a toy.

### Mandatory safety rules (no exceptions)
1. **Get written permission.** If you don’t have explicit written consent from the owner of the device/system, you do not test it. Period.  
2. **Use isolated targets only.** Test only on VMs or hardware that are air-gapped or on a private, non-production network. Use snapshots.  
3. **No Internet on targets.** Disable outbound Internet on your target VM while testing payloads that could call home.  
4. **Use benign payloads first.** Test with harmless scripts (open Calculator, type demo text) before anything else.  
5. **Document everything.** Keep a log of who approved the test, test scope, timestamps, and actions taken.  
6. **Have a rollback plan.** Snapshot targets and verify you can restore them quickly.  
7. **Limit access to tools.** Don’t publish or share aggressive payloads in public repos — keep dangerous scripts out of the wild.  
8. **Responsible disclosure.** If your authorized testing finds a real vulnerability, follow responsible disclosure to the vendor — don’t leak exploits.

### Lab checklist (quick)
- [ ] Target is a VM with a fresh snapshot.  
- [ ] Target network is isolated (no internet).  
- [ ] Written permission is stored (scope + signatures).  
- [ ] Payloads are benign or explicitly approved.  
- [ ] Monitoring/logging is enabled (screen recording or console log).  
- [ ] Rollback snapshot verified.  
- [ ] Test results documented and stored securely.

### Benign payload examples (use these)
- Open Calculator (Windows)  
- Type a multi-line demo message into Notepad  
- Paste a non-malicious status text into an editor

> **Do not** use or share payloads that:
> - download-and-execute remote scripts, or  
> - spawn reverse shells, or  
> - exfiltrate data, or  
> - make persistent changes to the OS.

### If you’re unsure
Stop and ask. Don’t guess. Get permission or run it in a safer sandbox. If you find something sketchy in this repo or someone submits a PR that looks like an exploit, flag it or open an issue — we’ll remove it.

**Bottom line:** HID tech is sick for learning and automation — but it’s also a blunt instrument that can wreck systems and lives if misused. Be smart, be legal, and keep your experiments ethical.
