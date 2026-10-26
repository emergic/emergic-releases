# Otium

Office AI chat served by your office's own idle Macs. This repository holds release builds only.

## Install

```sh
brew install --cask naklitechie/tap/otium
```

Or download `Otium-macos.zip` from the [latest release](../../releases/latest), unzip it and move `Otium.app` to Applications. Apple Silicon and macOS 14 or later.

Otium is ad-hoc signed and not Apple-notarised. If macOS blocks it, open it once with right-click → Open.

## What it is

One app with three roles, chosen on first launch:

- **Join my office**: chat, and let the office use this Mac's idle time to answer questions.
- **Office server**: run the office hub (machines, users, the office model, the admin console) on an always-on Mac such as a Mac mini.
- **Just chat**: connect to an office or a cloud provider later.

Questions are answered by a model running on the office's own machines. Nothing goes to a cloud service unless the office admin connects one.

## Verify a download

Each release lists the SHA-256 of `Otium-macos.zip` in `SHA256SUMS`:

```sh
shasum -a 256 Otium-macos.zip
```

## License

Otium's desktop app is built on [Jan](https://github.com/janhq/jan) (Apache-2.0, Copyright 2025 Menlo Research) and bundles [llama.cpp](https://github.com/ggml-org/llama.cpp) (MIT). The license texts ship inside the app bundle.
