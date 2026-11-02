# Otium

Office AI chat served by your office's own idle Macs and Windows PCs. This repository holds release builds only.

## Install on a Mac

```sh
brew install --cask naklitechie/tap/otium
```

Or download `Otium-macos.zip` from the [latest release](../../releases/latest), unzip it and move `Otium.app` to Applications. Apple Silicon only.

Otium is ad-hoc signed and not Apple-notarised. If macOS blocks it, open it once with right-click → Open. When Otium asks to find devices on your local network, allow it: machines in an office reach each other over the local network.

Upgrade with `brew upgrade --cask otium`.

## Install on Windows

1. Download `Otium-windows-x64-setup.exe` from the [latest release](../../releases/latest). Windows 10 or 11, 64-bit Intel or AMD.
2. Run it. Otium installs for the signed-in user, without administrator rights.
3. Otium is not code-signed, so Windows SmartScreen asks once: choose **More info → Run anyway**.
4. If Windows Firewall asks, allow Otium on **Private** networks, and make sure the office Wi-Fi or Ethernet is set to Private (Settings → Network & internet → the network → Private). Machines in an office cannot reach each other on a Public network.

To upgrade, run the new installer over the old one. For IT installs, `Otium-windows-x64-setup.exe /S` installs silently.

## What it is

One app with three roles, chosen on first launch:

- **Join my office**: chat, and let the office use this computer's idle time to answer questions.
- **Office server**: run the office hub (machines, users, the office model, the admin console) on an always-on Mac or PC, such as a Mac mini.
- **Just chat**: connect to an office or a cloud provider later.

Questions are answered by a model running on the office's own machines. Nothing goes to a cloud service unless the office admin connects one. Macs and Windows PCs can join the same office.

## Verify a download

Each release lists the SHA-256 of both downloads in `SHA256SUMS`.

On a Mac:

```sh
shasum -a 256 Otium-macos.zip
```

On Windows (PowerShell):

```powershell
Get-FileHash Otium-windows-x64-setup.exe -Algorithm SHA256
```

## License

Otium's desktop app is built on [Jan](https://github.com/janhq/jan) (Apache-2.0, Copyright 2025 Menlo Research) and bundles [llama.cpp](https://github.com/ggml-org/llama.cpp) (MIT). The license texts ship with the app.
