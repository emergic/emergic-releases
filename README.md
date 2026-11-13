# Emergic

Office AI chat served by your office's own idle Macs and Windows PCs. This repository holds release builds only. Emergic was called Otium until version 0.2.0; releases before 0.2.0 keep their Otium file names.

## Install on a Mac

```sh
brew install --cask emergic/tap/emergic
```

Or download `Emergic-macos.zip` from the [latest release](../../releases/latest), unzip it and move `Emergic.app` to Applications. Apple Silicon only.

Emergic is ad-hoc signed and not Apple-notarised. If macOS blocks it, open it once with right-click → Open. When Emergic asks to find devices on your local network, allow it: machines in an office reach each other over the local network.

Emergic updates itself when the office admin approves a release. A Mac that had Otium from Homebrew moves its record once with `brew uninstall --cask --force otium && brew install --cask --adopt emergic/tap/emergic`.

## Install on Windows

1. Download `Emergic-windows-x64-setup.exe` from the [latest release](../../releases/latest). Windows 10 or 11, 64-bit Intel or AMD.
2. Run it. Emergic installs for the signed-in user, without administrator rights.
3. Emergic is not code-signed, so Windows SmartScreen asks once: choose **More info → Run anyway**.
4. If Windows Firewall asks, allow Emergic on **Private** networks, and make sure the office Wi-Fi or Ethernet is set to Private (Settings → Network & internet → the network → Private). Machines in an office cannot reach each other on a Public network.

To upgrade, run the new installer over the old one. For IT installs, `Emergic-windows-x64-setup.exe /S` installs silently.

## What it is

One app with these roles, chosen on first launch:

- **Join my office**: chat, and let the office use this computer's idle time to answer questions.
- **Office server**: run the office (machines, users, the office model, the admin console) on an always-on Mac or PC, such as a Mac mini.
- **Just chat**: connect to an office or a cloud provider later.

Questions are answered by a model running on the office's own machines. Nothing goes to a cloud service unless the office admin connects one. Macs and Windows PCs can join the same office.

## Verify a download

Each release lists the SHA-256 of its downloads in `SHA256SUMS`.

On a Mac:

```sh
shasum -a 256 Emergic-macos.zip
```

On Windows (PowerShell):

```powershell
Get-FileHash Emergic-windows-x64-setup.exe -Algorithm SHA256
```

## License

Emergic's desktop app is built on [Jan](https://github.com/janhq/jan) (Apache-2.0, Copyright 2025 Menlo Research) and bundles [llama.cpp](https://github.com/ggml-org/llama.cpp) (MIT). The license texts ship with the app.
