# Orbit YouTube Player 1.0

Small static HTTPS wrapper around the official YouTube IFrame Player API.
The Orbit interface, Google account connection and user preferences stay local.
This repository contains no companion software, iCUE exports, credentials or account data.

## Playback

The page uses the official YouTube player, including its normal controls and restrictions.
It does not download, proxy, extract or capture video or audio. Playback is not started automatically.

A standalone test can supply a public video identifier in the URL fragment:
`#video=VIDEO_ID&lang=en`.
Supported languages: English, French, Simplified Chinese, German, Italian, Japanese, Korean, Russian and Spanish.

## Local integration

The embedded page accepts only its exact parent window on the local Orbit HTTP origin
(`127.0.0.1` or `localhost`, port `28943`), with a per-instance random channel identifier.
Commands are limited to playback, pause, volume, seek, status and disposal.
Only public video identifiers and transient player state are exchanged.
Account information, API keys, OAuth tokens, browsing history and preferences must never be sent to this page.

The URL fragment is not part of the HTTP request. GitHub Pages and YouTube still process normal
connection information under their own privacy policies. This page does not claim to provide anonymity.

HTTPS hosting improves the embedded player's source identity. It cannot override YouTube restrictions
or guarantee playback of every video on every device.
