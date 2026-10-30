# Phlox

**Private conversations. Quiet flame.**

A messenger for Android. No phone number, no email: you sign in with one signature from a free wallet app. Every message, photo and call is end-to-end encrypted, so only the people in a conversation can read it.

Website: https://phlox.im

This repository holds only release files. It contains no source code.

## Download

Get the APK from [Releases](../../releases/latest).

- Android 8.0 or newer, 64-bit phone.
- No iPhone or desktop app yet.

## Install

1. If your browser warns about the file, keep it. Android says this about every app from outside Google Play.
2. Open the file and allow installs from your browser.
3. Tap Install.

Lose your wallet, and nobody can restore your account.

## Check the file

Every release lists two fingerprints. Both must match.

In the commands below, use the name of the file you downloaded instead of `Phlox-VERSION.apk`.

**1. SHA-256 of the file** — shows the download is complete and unchanged.

Windows (PowerShell):

```
Get-FileHash Phlox-VERSION.apk -Algorithm SHA256
```

macOS / Linux:

```
shasum -a 256 Phlox-VERSION.apk
```

**2. Signing key fingerprint** — shows the app is signed with the Phlox key. It is the same for every release:

```
5F:92:F1:DC:B7:63:BD:4E:C2:A2:34:51:81:AD:2E:FB:02:25:E1:B6:66:D6:13:8D:92:F7:55:E6:CB:E1:64:DE
```

Check it with `apksigner` from the Android SDK build tools:

```
apksigner verify --print-certs Phlox-VERSION.apk
```

The line `Signer #1 certificate SHA-256 digest` must show the same value (without colons, in lower case).

## In short

- **Sign-up:** no phone number, email or name. You sign one text in a free wallet app. It isn't a payment; the wallet can stay empty.
- **Messages:** carried by the XMTP network and end-to-end encrypted with MLS. Phlox servers never carry or see them.
- **Media:** photos, files and voice notes are encrypted on the phone before upload and erased from storage after 30 days.
- **Calls:** WebRTC, straight between the two phones, encrypted with DTLS-SRTP.
- **Tor:** built in, one switch, off by default.
- **Backup:** optional, off until you turn it on. The key comes from your wallet signature and never reaches the server.
