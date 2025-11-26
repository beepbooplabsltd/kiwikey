kiwi**key**™ security design
============================

## Overview

The kiwi**key** is a transport adapter device that is designed to convert between the TIA-102.AACD-A KFD protocol and the Tait keyloading protocol.

| OSI model | TIA-102.AACD-A KFD protocol | Tait protocol             | Notes |
|-----------|-----------------------------|---------------------------|-------|
| Layer 1   | Three Wire Interface (TWI)  | USB/UART serial           |
| Layer 1.5 | —                           | Command framing           |
| *Layer 2* | *Exchange session*          | *Exchange session*        | *Passed transparently*
| *Layer 3* | *Key Management Messages*   | *Key Management Messages* | *Passed transparently*

It is **not** a cryptographic device: it does not generate keys, store keys, encrypt or decrypt data, or perform any other function of a cryptographic device.

## Details

| Component                  | Notes |
|----------------------------|-------|
| **Algorithms**             | The kiwi**key** does not implement or use any encryption algorithms in hardware or firmware.
| **Cryptographic boundary** | The kiwi**key** does not have a cryptographic boundary, as it does not perform any cryptographic operations.
| **Development**            | The kiwi**key** is designed and tested in the United States by US nationals.
| **FIPS validation**        | The kiwi**key** is not FIPS validated.
| **Firmware security**      | The kiwi**key** does not include any firmware secure boot features.
| **Keys**                   | The kiwi**key** does not contain any CSPs or keys.
| **Logging**                | The kiwi**key** does not perform any logging.
| **Other attacks**          | The kiwi**key** is not designed to mitigate any specific attacks outside of those listed in this table, including but not limited to power consumption, timing, fault induction, or TEMPEST attacks.
| **Physical security**      | The kiwi**key** does not include any physical anti-tamper features. All components are general-purpose commodity components; no custom components are used.
| **Ports**                  | The kiwi**key** provides two physical ports, both of which are used for data input/output. TWI is used for TIA-102.AACD-A KFD protocol. RJ12 is additionally used for power and Tait keyloading protocol control input and status output.
| **RNG**                    | The kiwi**key** does not implement or use any random number generators in hardware or firmware.
| **Roles**                  | The kiwi**key** supports one role: user.
| **Software**               | The kiwi**key** does not interact with any software.
| **Storage: non-volatile**  | The kiwi**key** does not use any non-volatile memory to store any encryption key material being sent. The executable firmware is stored in non-volatile memory.
| **Storage: volatile**      | The kiwi**key** uses the volatile RAM onboard the ATmega328p microcontroller to buffer and frame encryption key material being sent. The kiwi**key** does not contain any other volatile memory.

## Disclaimer

The above security details apply to a kiwi**key** as manufactured, using original hardware and firmware provided by beep boop labs.

Unauthorized physical or electronic access to the kiwi**key** or radios being keyloaded could result in malicious modifications by a third-party.

⚠️ It is the user's responsibility to maintain physical and electronic control of their kiwi**key** device, radios they connect it to, and their encryption key material, at all times to prevent tampering.
