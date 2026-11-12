---
last_updated: 2026-11-11
---

<!-- Authoring guidance: dev-docs/specs/README_SPEC.instructions.md -->
<!-- rumdl-disable MD033 MD041 -->
<p align="center">
  <img src="assets/icons/text_csv.svg" alt="Text CSV app icon" width="128">
</p>

<h1 align="center">Text CSV</h1>

<p align="center">
  A plain-text CSV and TSV editor for Windows and iPhone, for anyone who needs
  to view or change delimited files without a full spreadsheet program.
</p>

<p align="center">
  <a href="docs/USER_MANUAL.md#install-on-windows">
    <img src="https://img.shields.io/badge/Windows-1.0.0-0078D4" alt="Windows version 1.0.0">
  </a>
  <a href="docs/USER_MANUAL.md#install-on-iphone">
    <img src="https://img.shields.io/badge/iOS-1.0.0-555555" alt="iOS version 1.0.0">
  </a>
  <a href="docs/USER_MANUAL.md#android-preview">
    <img src="https://img.shields.io/badge/Android_preview-0.2.2-3DDC84" alt="Android preview version 0.2.2">
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-Proprietary-red" alt="License: Proprietary">
  </a>
</p>
<!-- rumdl-enable MD033 MD041 -->

---

## About

Spreadsheet programs often change CSV data on the way in, for example by
dropping leading zeroes or turning values into dates and formulas. Text CSV
keeps every cell as the text you typed. Imported files are copied into a local
document library, so the original file never changes, and exports write a clean
UTF-8 CSV wherever you choose. Text CSV runs on Windows and iPhone; each keeps
its own library on the device.

## Features

- Import CSV, TSV, and plain text files, with commas or tabs detected
  automatically.
- Edit cells as plain text, with no formulas or number conversion.
- Add, insert, and delete rows and columns.
- Save documents in a local library and export UTF-8 CSV copies.
- Recover unsaved edits after an interruption, even when the library cannot
  open.
- Copy and paste cell ranges, clear cells, edit multiline cells, rename
  documents, and use keyboard shortcuts on Windows.
- Open CSV and TSV files in Text CSV from other apps on iPhone.
- Keep documents on your device; Text CSV does not send them over the network.

## App Screenshot

### Android preview

The editor keeps leading zeroes intact, and the document library keeps saved
files together. Click a screenshot to view it at full size.

<!-- rumdl-disable MD033 -->
<p align="center">
  <a href="platform/android/assets/screenshots/editor.png">
    <img src="platform/android/assets/screenshots/editor.png"
         alt="Android CSV editor showing inventory codes with leading zeroes"
         width="280">
  </a>
  <a href="platform/android/assets/screenshots/library.png">
    <img src="platform/android/assets/screenshots/library.png"
         alt="Android document library with Price list, Contacts, and Inventory"
         width="280">
  </a>
</p>
<!-- rumdl-enable MD033 -->

## User Manual

See the [User Manual](docs/USER_MANUAL.md) for installation, setup, usage, and
troubleshooting.
