# CTF & Offensive Security Practice

**Capture-the-flag writeups and challenge solutions across web, forensics, reverse engineering, cryptography, and binary exploitation.**

Ongoing practice work from CTF competitions and challenge platforms. This repo hosts writeups of challenges I've solved, organized by event, with the goal of documenting both the solutions and the reasoning process behind them.

---

## Why writeups matter

Solving a CTF challenge is worth something. Writing up the solution is worth more. Documenting the reasoning makes patterns memorable, exposes weak spots in my process, and creates a reference I can return to when I see similar techniques in the wild. It's also the format that lets someone else evaluate whether I know what I'm doing beyond just the flag output.

Every writeup here includes:
- The challenge premise as given
- My initial approach and what I tried
- Where I got stuck and how I moved past it
- The final solution with commented code or command sequences
- What I took away from the challenge

---

## Events

### MetaCTF

Multi-category competition covering:
- **Forensics:** artifact recovery from disk images and captured traffic
- **USB HID analysis:** decoding keyboard capture data to reconstruct typed input
- **Cryptography:** RSA common modulus attacks
- **Reverse engineering:** DFA (deterministic finite automaton) reversing
- **Binary exploitation:** format-string vulnerability chained with a stack overflow
- **Web:** cache deception attack

### "Residual" — Multi-stage Ransomware Forensics

A layered forensics challenge simulating post-ransomware IR:
- **MFT (Master File Table) analysis** for timeline reconstruction
- **Timestamp stomping detection** using cross-artifact correlation
- **Cryptanalysis of keystream reuse** across three encrypted files, recovering plaintext via XOR relationships between ciphertexts

### SkillBit CTF

Broad-category session covering:
- **EXIF forensics** for image-based metadata challenges
- **HID keyboard capture decoding** from raw USB traffic
- **TOCTOU race condition** exploitation
- **Bytecode VM reverse engineering** for a custom stack-based virtual machine
- **`pwntools`-based format-string / ROP exploit** for binary exploitation

### Additional challenge work

Miscellaneous challenges outside formal events:
- **Custom Python ELF emulator** for stepping through unfamiliar assembly instruction by instruction
- **XOR key recovery via known-plaintext attack** when partial plaintext structure was inferable
- **TCP SYN scanning** and network reconnaissance challenges
- **Burp Suite web exploitation** including session cookie manipulation and endpoint enumeration
- **Disk forensics** on ext4 images with deleted-file recovery

---

## Categories covered

| Category | Sub-areas |
|----------|-----------|
| **Web** | Authentication bypass, cache deception, session manipulation, source analysis |
| **Forensics** | Disk imaging, MFT parsing, timestamp analysis, EXIF, HID capture decoding |
| **Reverse Engineering** | Binary RE, custom VMs, assembly emulation, DFA reversing |
| **Cryptography** | RSA attacks, XOR analysis, keystream reuse, known-plaintext attacks |
| **Binary Exploitation** | Format strings, stack overflows, ROP chains, `pwntools` workflows |
| **OSINT** | Metadata extraction, infrastructure enumeration |

---

## Toolkit

The tools I reach for most across challenge categories:

- **Kali Linux** as the working environment (running in UTM on M-series MacBook)
- **Burp Suite** for web challenge proxying, repeater, and intruder work
- **Ghidra** for binary reverse engineering
- **`pwntools`** for exploit development
- **`nmap`** and **Wireshark** for network reconnaissance and traffic analysis
- **Python** for custom tooling: emulators, decoders, one-off cryptanalysis scripts

---

## Approach

A few patterns I've settled into after enough challenges:

**Read the problem twice before touching anything.** Half the challenges hide the actual task in the framing. Rereading before executing saves time on false starts.

**Build the tool if the tool doesn't exist.** Writing a custom Python emulator or decoder is often faster than trying to make a general-purpose tool fit a specific challenge shape. This is where scripting skill compounds.

**Document as you go, not after.** Trying to reconstruct a solution path after the fact loses the decision points that made it work. The notes I take during the solve become the writeup with minor editing.

**Fail visibly.** When something isn't working, print aggressive debug output rather than trying to reason about it silently. This is especially true for exploit development, where you cannot afford to guess at what a payload is doing.

---

## Writeups

*Individual writeups to be added as separate markdown files in this repo. Prioritized by educational value.*

Planned first writeups:
1. Residual ransomware forensics: keystream reuse cryptanalysis (walks through the XOR math and shows the recovery)
2. Custom Python ELF emulator for assembly reversing (demonstrates how to bootstrap when standard tools don't fit)
3. Web cache deception attack from MetaCTF (a class of vulnerability that shows up in real-world bug bounty scope)

---

*Ongoing personal practice. Not affiliated with any employer.*
