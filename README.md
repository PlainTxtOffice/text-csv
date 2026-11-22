---
last_updated: 2026-11-22
---

<!-- Authoring guidance: dev-docs/specs/README_SPEC.instructions.md -->
<!-- rumdl-disable MD033 MD041 -->
<p align="center">
  <img src="assets/icons/icon-github-readme.svg" alt="Text CSV app icon" width="128">
</p>

<h1 align="center">Text CSV</h1>

<p align="center">
  A plain-text CSV and TSV editor for anyone who needs to view or change
  delimited files without a full spreadsheet program.
</p>

<p align="center">
  <a href="https://play.google.com/store/apps/details?id=com.plaintxtoffice.textcsv">
    <img src="https://img.shields.io/badge/platform-Android-3DDC84" alt="Platform: Android">
  </a>
  <a href="https://apps.apple.com/app/id6837241235">
    <img src="https://img.shields.io/badge/platform-iOS-555555" alt="Platform: iOS">
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-Proprietary-red" alt="License: Proprietary">
  </a>
</p>
<!-- rumdl-enable MD033 MD041 -->

---

## About

**Development status:** The Android app is available on
[Google Play](https://play.google.com/store/apps/details?id=com.plaintxtoffice.textcsv),
and the iPhone app, version 1.0.0, is available on the
[App Store](https://apps.apple.com/app/id6837241235). The Windows version has no
public download yet.

Spreadsheet programs often change CSV data on the way in, for example by
dropping leading zeroes or turning values into dates and formulas. Text CSV
keeps every cell as the text you typed. Imported files are copied into a local
document library, so the original file never changes, and exports write a clean
UTF-8 CSV wherever you choose. Each platform keeps its own library on the
device.

Text CSV is also useful for recording data when you are away from a computer or
laptop. Log readings, counts, or observations on your phone as they happen,
then export a CSV to use elsewhere.

## Features

- Import CSV, TSV, and plain text files, with commas or tabs detected
  automatically.
- Edit cells as plain text, with no formulas or number conversion.
- Add, insert, and delete rows and columns.
- Save documents in a local library and export UTF-8 CSV copies.
- Recover unsaved edits after an interruption on Windows and iPhone, even when
  the library cannot open.
- Undo and redo changes on Android and iPhone.
- **Paid subscription · Android · Available on Google Play:** without a
  subscription, the app keeps up to three documents and exports
  comma-separated CSV. The optional Text CSV Premium subscription adds
  unlimited documents; find and replace; sorting, filtering, and removing
  duplicate rows; moving rows and columns; splitting and merging columns; and
  export as TSV or a Markdown table with a choice of line endings.
- **Paid subscription · iPhone · Available on the App Store:** the same
  three-document limit and Text CSV Premium features, with the subscription
  billed through the App Store.
- Copy and paste cell ranges, clear cells, edit multiline cells, rename
  documents, and use keyboard shortcuts on Windows.
- Open CSV and TSV files in Text CSV from other apps on iPhone.
- Keep documents on your device; Text CSV does not send them over the network.

## App Screenshot

### Android

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

## Feedback

Send bug reports and feature requests to
[support@plaintxtoffice.com](mailto:support@plaintxtoffice.com) or through the
[contact page](https://plaintxtoffice.com/contact/). You can also send them from
the app. On iPhone, tap the envelope button (**Send Feedback**) next to
**Privacy** in the document list; the email draft holds only the app version,
iOS version, and device model. On Android, choose **Feedback** in the top bar.
