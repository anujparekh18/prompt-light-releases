# Prompt Light releases

This repository distributes signed, notarized builds of Prompt Light for
macOS. It intentionally contains no application source code.

[Download the latest stable version](https://github.com/anujparekh18/prompt-light-releases/releases/latest/download/PromptLight.zip)

## Requirements

- macOS 14 Sonoma or later
- Apple silicon or Intel Mac
- Codex for automatic activity updates

## Install

1. Download and extract `PromptLight.zip`.
2. Move `PromptLight.app` to Applications.
3. Open Prompt Light and complete the one-screen onboarding.
4. Connect Codex from Prompt Light settings, then trust the hooks in Codex
   Settings → Hooks.

Prompt Light is signed with a Developer ID certificate and notarized by Apple.

## Verify a download

Download `PromptLight.zip.sha256` from the same release and run:

```sh
shasum -a 256 -c PromptLight.zip.sha256
```

## Privacy

Prompt Light has no account, analytics, advertising, or remote telemetry. It
receives lifecycle signals from Codex through a local receiver bound to your
Mac. Prompt text and responses are not required, collected, or stored. The app
uses GitHub over HTTPS to check for and download cryptographically signed
software updates.

The full privacy summary is available on the
[Prompt Light website](https://prompt-light.vercel.app/#privacy).
