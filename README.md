# Powershell-Smuggler
Decrypting a powershell script and executing it using scriptblock smuggling, bypassing AMSI and some telemetry.

# How it works
Powershell-Smuggler is a compact powershell script that works by base64 decoding and XOR decrypting an encrypted powershell command or script. After that it will execute the powershell command using scriptblock smuggling, bypassing AMSI and some powershell logging.

By default Powershell-Smuggler will just execute "Invoke-Mimikatz", a common command used to test the Windows Defender AMSI provider, you can change it by XOR encrypting and then base64 encoding your powershell payload, and replacing "$a" and "$b" in Powershell-Smuggler with a key for XOR decryption and your encoded payload.

# Examples
Bypassing AMSI for the Invoke-Mimikatz command:

<img width="964" height="405" alt="amsibypass" src="https://github.com/user-attachments/assets/95ca0ee5-6e8d-4ae7-a5c0-2a91dc7ebc5f" />

Hiding the real command that will be executed:

<img width="967" height="353" alt="telemetrybypass" src="https://github.com/user-attachments/assets/05699ed5-90b7-4021-9799-fce51ffa8def" />



More information about the scriptblock smuggling technique can be found here:

https://bcsecurity.io/blog/scriptblock_smuggling/
