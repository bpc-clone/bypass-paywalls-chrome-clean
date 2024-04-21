# Add extension (crx) to allowlist

* [Windows](#windows)
* [macOS](#macOS)
* [Linux](#linux)

### Windows

Advance Notice: after adding the allowlist-policy you'll get a message *Your browser is managed by your organisation* on the extensions page (and some settings like Secure DNS are disabled).\
To remove this message you'll have to remove the added policy from the registry again (run regedit and for Chrome check HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Chrome).

If you still want to add the extension to the allowlist:

Run as administrator one of the reg-files in allowlist-folder of extension (unzip).
* for Edge 116+ you may also need to run the *Forcelist* reg-file (also undo reg-file provided) or switch to *Load unpacked* installation.

If you already added extensions to the allowlist than you should change "1" to a new value (also change name of HLM-key for beta/developer versions of browsers).\
To add more extensions to the allowlist you can add more lines.\
Example Chrome-regfile:
```
Windows Registry Editor Version 5.00  
[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Chrome\ExtensionInstallAllowlist]  
"1"="lkbebcjgcmobigpeffafkodonchffocl"
"2"="extension-id2"
```

You can also run the PowerShell script *bypass_paywalls_clean_allowlist.ps1* (as administrator) to add extension to the allowlist (script checks if extension already allowed or adds new registry-key).\
For the parameter browser enter chrome, edge or brave.

### macOS

Run with admin rights one of the .mobileconfig files in allowlist-folder of extension (unzip).\
Finally restart the browser's process (in the Dock: right click on Chrome, 'Quit', reopen).\
This assumes your device is not being managed by MDM software and you don't have any profile related to the 'ExtensionInstallAllowlist' policy already active.\
To add more extensions to the allowlist you can add more lines.
```
<key>ExtensionInstallAllowlist</key>
<array>
<string>lkbebcjgcmobigpeffafkodonchffocl</string>
<string>extension-id2</string>
</array>
```

### Linux

[Chromium-based browsers allow local installations of extensions](https://developer.chrome.com/docs/extensions/mv3/hosting/#hosting), so not necessary :)
