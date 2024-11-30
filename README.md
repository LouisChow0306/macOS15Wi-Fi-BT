First of all thank for Win10Q,and I translate it to English 
You need is OCLP to path WIFI:https://github.com/laobamac/OCLP-Mod
Add the following kexts to the kexts folder in the specified order:

IOSkywalkFamily.kext
IO80211FamilyLegacy.kext
AirportItlwm.kext
Please make sure to delete the existing Itlwm.kext first.
In the example.plist, copy the contents of Kernel/Block and paste them into the corresponding location in your existing config.

Under Misc/Security, ensure that SecureBootModel is set to Disabled.

In the NVRAM tab, select the entry that starts with 7C. Then:

Copy the boot-args from example.config and append them to the current boot-args.

Change csr-active-config to 03080000 (you can copy this value from example.plist).

Make sure the Delete section includes the 7C entry with both boot-args and csr-active-config.

Restart your computer, then open OCLP (OpenCore Legacy Patcher).

Click Post-Install Root Patch and then Start Root Patching.

After the root patching is complete, restart your computer again. At this point, Wi-Fi should work directly without needing HeliPort.

In addition, Bluetooth is not working properly on my computer. I have also uploaded the Bluetooth drivers.
Only put them in plist flie and rebot your computer.
