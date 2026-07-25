# jfm-firmware

Public **firmware binaries** (`.bin`) for JFM / RFM ESP32-S3 OTA updates.

This repository hosts **compiled images only**.  
Application source code and internal firmware projects remain **private**.

## Purpose

Devices download firmware over HTTPS using a URL supplied by the mobile app (from a remote manifest).  
Release assets in this repository provide those downloadable `.bin` files.

## Layout

Firmware images are published as **GitHub Release assets**, for example:

- Tag: `v1.0.1`
- Asset: `JFM_1_v1.0.1.bin`
- URL shape:  
  `https://github.com/Muhammad-1991/jfm-firmware/releases/download/v1.0.1/JFM_1_v1.0.1.bin`

Prefer Release download URLs over branch/`main` raw links so each published version stays immutable.

## Naming

Typical artifact name:

`JFM_<n>_v<MAJOR>.<MINOR>.<PATCH>.bin`

Example: `JFM_1_v1.0.1.bin`

## Integrity

Each published image should be listed in the OTA manifest with:

- `version`
- `url`
- `size` (bytes)
- `sha256` (lowercase hex of the exact uploaded file)

Do not replace an already-published Release asset. Publish a new version instead.

## What not to put here

- C/C++ / Arduino source
- Private keys, tokens, Wi-Fi credentials
- Internal design documents

## Notes

- Factory / lab baseline firmware may be flashed over USB.
- Field updates use Wi-Fi HTTPS OTA coordinated by the app over BLE.
- Binary publication does not include source; reverse engineering of binaries is not authorized.
