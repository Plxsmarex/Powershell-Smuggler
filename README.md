# Powershell-Smuggler
Decrypting a powershell script and executing it using scriptblock smuggling, bypassing AMSI and some telemetry.

# How it works
Powershell-Smuggler is a compact, tiny powershell script that works by base64 decoding and XOR decrypting an encrypted powershell command or script. After that, it will execute the powershell command using scriptblock smuggling, bypassing AMSI and some powershell logging. Its small size makes it easy to evade static signature detection.

By default, Powershell-Smuggler will just execute `Invoke-Mimikatz`, a common command used to test the Windows Defender AMSI provider, you can change it by XOR encrypting and then base64 encoding your powershell payload, and replacing `0xEB,0xC1,0x89,0xB4` and `oq//24CkpPmCrODfirXz` in Powershell-Smuggler with a key for XOR decryption and your encoded payload.

# Examples
Bypassing AMSI for the Invoke-Mimikatz command:
<img width="974" height="420" alt="AMSI_bypass" src="https://github.com/user-attachments/assets/aac9982a-ed78-4db2-8092-700e896d63ab" />

Hiding the real command that will be executed:
<img width="975" height="372" alt="Hiding_real_command" src="https://github.com/user-attachments/assets/fa91b731-01c0-4dcc-ba3b-877fb5895730" />

More information about the scriptblock smuggling technique can be found here:

https://bcsecurity.io/blog/scriptblock_smuggling/
