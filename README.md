# Emergic

Office AI answered by your office's own idle Macs and PCs: chat, documents, meetings in English and Hindi, follow-ups, mail and a phone app. This repository holds release builds only. Source: [emergic/emergic](https://github.com/emergic/emergic) and [emergic/emergic-app](https://github.com/emergic/emergic-app). Docs: [emergic.com/docs](https://emergic.com/docs/).

## Install on a Mac

```sh
brew install --cask emergic/tap/emergic
```

Or download `Emergic.dmg` from the [latest release](../../releases/latest), open it and drag `Emergic.app` onto the Applications folder beside it. Apple Silicon, macOS 13 or later. `Emergic-macos.zip` holds the same app, for Homebrew and older links: unzip it and move `Emergic.app` to Applications.

Emergic is signed but not yet Apple-notarised. If macOS blocks it, open it once with right-click → Open. When Emergic asks to find devices on your local network, allow it: machines in an office reach each other over the local network.

## Install on Windows

1. Download `Emergic-windows-x64-setup.exe` from the [latest release](../../releases/latest). Windows 10 or 11, 64-bit Intel or AMD.
2. Run it. Emergic installs for the signed-in user, without administrator rights.
3. The installer is not yet code-signed, so Windows SmartScreen asks once: choose **More info → Run anyway**.
4. If Windows Firewall asks, allow Emergic on **Private** networks, and set the office Wi-Fi or Ethernet to Private (Settings → Network & internet → the network → Private). Machines in an office cannot reach each other on a Public network.

To upgrade by hand, run the new installer over the old one. For IT installs, `Emergic-windows-x64-setup.exe /S` installs silently.

## Install on Android

Download [Emergic-android.apk](https://github.com/emergic/emergic-releases/releases/latest/download/Emergic-android.apk) on the phone (this link always serves the latest release) and allow the install when Android asks. Pair the phone with your office by its QR code, or join with a join code.

## Join an office

On the computer that stays on, choose **Set this computer up as the office server** and add people in its admin console. Everyone else chooses **Join my office** and types the join code the admin gives them. With the office relay on, the code works from home or on mobile data too.

## Updates

Computers in an office update from the office server, never straight from the internet. The office server checks this repository's signed update feed and installs a new release when the admin's policy says so: automatically at a quiet moment, or after the admin approves it. Every package is signed, and a package must name its own release.

## Verify a download

Each release lists the SHA-256 of its downloads in `SHA256SUMS`.

```sh
shasum -a 256 Emergic.dmg                                         # Mac disk image
shasum -a 256 Emergic-macos.zip                                   # Mac zip
```

```powershell
Get-FileHash Emergic-windows-x64-setup.exe -Algorithm SHA256       # Windows
```

## Earlier names

Emergic was called Otium until version 0.2.0; releases before 0.2.0 keep their Otium file names. A Mac that had Otium from Homebrew moves once with `brew uninstall --cask --force otium && brew install --cask --adopt emergic/tap/emergic`.

## License

Emergic is Apache-2.0. The desktop app is built on [Jan](https://github.com/janhq/jan) (Apache-2.0, Menlo Research) and bundles [llama.cpp](https://github.com/ggml-org/llama.cpp) (MIT). Models the app downloads, including Koyal Hindi (CC-BY-4.0, Adalat AI) and EmbeddingGemma (Gemma Terms of Use), are listed with their licences in the app's third-party notices.
