---
last_updated: 2026-11-24
version: 6.0.0
product_versions:
  windows: "1.0.0"
  ios: "1.0.0"
  android: "0.3.0"
generated_from: "dev-docs/specs/USER_MANUAL_SPEC.instructions.md"
---

# User Manual

## Overview

Text CSV edits CSV and TSV documents as plain text in a local document library.
It is for anyone who needs to view or change delimited text files without a
full spreadsheet program. Text CSV is available for iPhone and Android, which
have touch interfaces. A Windows desktop version is in development and has no
download yet. All three support import, cell editing, row and column
operations, saving, and export. Windows and iPhone also recover unsaved edits.
Android and iPhone offer an optional Text CSV Premium subscription.
<!-- Verified from: app registry dev-docs/APPS.md [Published Apps, Store Status]; GitHub releases (none) -->

Text CSV is also useful for recording data when you are away from a computer or
laptop. Log readings, counts, or observations on your phone as they happen,
then export a CSV to use elsewhere.

Each platform's library is independent. Export and import CSV files to move
documents between them.
<!-- Verified from: platform/windows/text_csv/application/documents.py; platform/windows/text_csv/ui/gui/app.py; platform/ios/text_csv/Library/DocumentListView.swift; platform/ios/text_csv/Editor/CSVEditorView.swift -->

## Installation and Setup

### Install the app

The Windows version is in development. It has no download or installer yet,
so it cannot be installed. The Windows sections of this manual describe how it
works.
<!-- Verified from: app registry dev-docs/APPS.md [Published Apps: Windows Code]; GitHub releases (none) -->

#### Install on iPhone

Text CSV requires an iPhone with iOS 26.2 or later. Install version 1.0.0 from
the [App Store](https://apps.apple.com/app/id6837241235). No account or initial
configuration is required.
<!-- Verified from: platform/ios/text_csv.xcodeproj/project.pbxproj [IPHONEOS_DEPLOYMENT_TARGET, TARGETED_DEVICE_FAMILY] -->

#### Install on Android

Text CSV requires Android 8.0 or newer. Install it from
[Google Play](https://play.google.com/store/apps/details?id=com.plaintxtoffice.textcsv).
No account or initial configuration is required.

#### Use Text CSV on Android

On Android, choose **New document** to create a three-by-three table or
**Import** to select a UTF-8 CSV/TSV file. Tap a document to open it, then tap
a cell to edit its text. **Save** in the cell dialog applies the edit and saves
the local library copy. The editor toolbar offers **Save**, **Undo**, **Redo**,
**Find**, **Sort**, **Filter**, **Duplicates**, **Add row**, **Add column**,
**Rename**, and **Export**; the row numbers and column letters open insert,
delete, move, split, merge, and sort commands. **Export** writes a separate
copy through the system file picker. Deletion requires confirmation. Tools
marked with a small lock need Text CSV Premium.

**Undo** and **Redo** work without a subscription. They cover cell edits, row
and column changes, sorts, and replacements made since the document was
opened. Up to twenty recent states are kept in memory.

If a library save fails, edits remain in memory: choose **Retry Save** or
**Export** before leaving the app. Returning to **Documents** retries
unsaved changes before closing. Saved documents remain on this device;
unconfirmed dialog text and failed saves have no recovery draft after process
termination. Android does not yet support range clipboard editing or opening
documents directly from other apps.

Input reads are limited to 5 MB. Saved library documents are limited to 1 MB
of serialized CSV text, 200,000 cells, and 500 columns. Imports make library
copies and never change source files. Your documents are not sent anywhere. The
app includes Google's billing library for Text CSV Premium, which has internet
access and may send diagnostic information about purchases to Google. Automatic
Android backup is disabled. Removing the app removes its library.

**Feedback** in the top bar opens a form for a bug report or feature request.
**Email feedback** opens your email app with a draft to
<feedback@plaintxtoffice.com> containing your note, the app version, the Android
version, and the device model; if no email app is installed, you choose another
app to receive the message. Nothing is sent until you send it.
**Open contact page** opens the Plain Text Office contact page. Your documents
are never included. **Privacy** in the top bar explains what the app stores and
links to the full privacy policy.
<!-- Verified from: platform/android/app/build.gradle.kts; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/main/; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/feedback/FeedbackScreen.kt; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/privacy/PrivacyScreen.kt; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/data/; platform/android/app/src/main/AndroidManifest.xml -->

#### Text CSV Premium on Android

Text CSV Premium is a subscription billed through Google Play, with a monthly
plan and, where Google Play offers it, a yearly plan. The **Premium** screen
shows each plan's price in your local currency and how much the yearly plan
saves; pick a plan, then choose **Subscribe**. The subscription renews each
month or year until you cancel it in Google Play subscriptions;
**Manage subscription** on the Premium screen opens that page.
**What's new in Premium** on the same screen lists what each release added, and
a dot on the Premium icon marks notes you have not opened yet. Without a
subscription, the document list shows how many of the three library documents
are in use, and choosing a Premium feature shows a prompt. Nothing changes
until you subscribe.

Premium unlocks:

- **Unlimited documents.** Without Premium, the library keeps up to three
  documents. When a subscription ends, existing documents stay and remain
  editable; you cannot add a fourth until you subscribe again.
- **Find & replace.** Type text to count matching cells, choose **Match
  case**, **Edit next match** to open each match, or **Replace all**. Searches
  are plain text unless you check **Regular expression**; then the replacement
  can use `$1` for the first group.
- **Sort rows.** Choose **Sort** in the toolbar, or tap a column letter and
  choose **Sort rows**. Pick up to three columns, each **A to Z** or **Z to
  A**; later columns order rows that match on the earlier ones. Leave **First
  row is a header** checked to keep the first row in place. Sorting compares
  text, so **10** comes before **9**.
- **Filter rows.** Choose **Filter**, pick one column or **Any column**, and
  type the text rows must contain. The grid shows only matching rows and says
  how many; **Clear filter** shows them all again. Filtering never changes the
  document, and export always writes every row. A filter on one column ends
  when columns are added, removed, moved, split, or merged.
- **Remove duplicate rows.** Choose **Duplicates** to see how many rows
  exactly repeat an earlier row, then **Remove**. The first copy of each stays.
- **Row and column tools.** Tap a row number for **Move up** and **Move
  down**, or a column letter for **Move left**, **Move right**, **Split
  column…**, and **Merge with next column…**. Splitting cuts each cell at a
  separator you type and puts the extra parts in new columns to the right.
  Merging joins two columns with your separator, leaving it out when either
  cell is empty.
- **Export…** options. Choose a comma (CSV) or tab (TSV) separator or a
  **Markdown table**, and Windows (CRLF) or Unix (LF) line endings, before
  picking a destination. A Markdown table uses the first row as its header and
  writes line breaks inside cells as `<br>`. The default CSV export does not
  need Premium.

**Have an access code?** on the Premium screen unlocks Premium on this device
for someone who was given a code, such as an app reviewer. It is not needed to
subscribe.

If Google Play is unavailable or a purchase is pending, the Premium screen
says so. Choose **Restore purchases** after signing in to Google Play or
completing a pending payment.
<!-- Verified from: platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/domain/Premium.kt; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/billing/PlayBilling.kt; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/main/MainScreenViewModel.kt; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/premium/PremiumScreen.kt; platform/android/app/src/main/res/values/strings.xml -->

#### Text CSV Premium on iPhone

Text CSV Premium is an App Store subscription with a monthly plan and a yearly
plan. Tap **Premium**, the star button at the top of the document list, or any
locked tool to open **Text CSV Premium**. The screen shows each plan's price in
your local currency. Pick a plan and tap **Subscribe**, then confirm with the
App Store. The subscription renews until you cancel it in your App Store
subscriptions. **Restore Subscription** checks the App Store for a subscription
bought with the same Apple Account. When Premium is active, the screen shows
**Premium is active** and **Manage Subscription**, which opens your App Store
subscription settings.

Without a subscription, the library keeps up to three documents. The document
list shows how many are in use, with a **Get Premium** button that opens the
Premium screen. At the limit, **New**, **Import**, and opening a file from
another app show the Premium screen instead. When a subscription ends,
existing documents stay and remain editable, and an active filter is cleared.

Premium adds unlimited documents, find and replace, sorting, filtering,
duplicate removal, moving rows and columns, splitting and merging columns, and
export options. Locked tools show a lock and open the Premium screen. **Undo**,
**Redo**, and the standard CSV export do not need Premium. See
[Use Premium tools on iPhone](#use-premium-tools-on-iphone).

If the App Store cannot be reached, the Premium screen shows **Subscription
Unavailable**. Premium that is already active keeps working offline.
<!-- Verified from: platform/ios/text_csv/Premium/Premium.swift; platform/ios/text_csv/Premium/PremiumStore.swift; platform/ios/text_csv/Premium/PremiumView.swift; platform/ios/text_csv/Library/DocumentListView.swift; platform/ios/text_csv/Editor/CSVEditorView.swift -->

The step-by-step instructions in the sections that follow describe Windows and
iPhone. The Android steps are above; the reference sections note where Android
differs.

## Starting the Program

### Launch and close the app

#### Start on Windows (in development)

The Windows version has no download yet. When it starts, the window opens with
the status **Opening library…**, then shows
**Create a document or import a CSV/TSV file.** A file named on the command line
is imported as a library copy. Without arguments, an interactive terminal offers
**1. Desktop GUI (--gui)** or **q. Quit**. A launch without a terminal, such as
from a shortcut, must include `--gui` or a file.

To quit, close the window or choose **File > Exit**. Pending edits are saved
first; if the save fails, the window stays open.
<!-- Verified from: platform/windows/text_csv/ui/cli/app.py; platform/windows/text_csv/ui/gui/app.py [run]; platform/windows/text_csv/ui/gui/views/window.py; platform/windows/text_csv/ui/gui/events/editor.py [close] -->

#### Start on iPhone

Open Text CSV. The **CSV Editor** document list appears. When the library is
empty, it shows **No Documents** with **New Document** and **Import File**
buttons.

You can also open a CSV or TSV file in Text CSV from another app, such as Files.
Text CSV imports a copy and opens it in the editor.

Returning to **Documents** saves pending changes; if the save fails, you stay in
the editor. The app also saves when it moves to the background.
<!-- Verified from: platform/ios/text_csv/App/text_csvApp.swift; platform/ios/text_csv/Info.plist [CFBundleDocumentTypes]; platform/ios/text_csv/Library/DocumentListView.swift; platform/ios/text_csv/Editor/CSVEditorView.swift -->

## Getting Around

### Navigate the interface

#### Navigate on Windows (in development)

- The left sidebar lists each document with its size and last-opened time. Type
  in **Filter documents** to narrow the list. Double-click a document, or select
  it and press **Enter**, to open it.
- The right side is the grid. Drag column boundaries to change widths and drag
  the divider to resize the sidebar.
- The window title shows the document name and size. A leading `*` means the
  document has unsaved changes.
- The **File**, **Edit**, and **Grid** menus hold all commands. The toolbar
  repeats **New**, **Import**, **Save**, **Export CSV**, **Add row**, and **Add
  column**. Right-click a cell for grid commands.
- The status bar at the bottom reports save and recovery results.
- **Help > Privacy** explains local storage and shows the library location.
<!-- Verified from: platform/windows/text_csv/ui/gui/views/window.py; platform/windows/text_csv/ui/gui/app.py [build_window]; platform/windows/text_csv/ui/gui/events/library.py [refresh]; platform/windows/text_csv/ui/gui/events/editor.py [title] -->

#### Navigate on iPhone

- The document list shows each document with its size and last-opened time.
  **Privacy** at the top left opens the privacy information, and **Premium**,
  the star button, opens Text CSV Premium. Without a subscription, a row at the
  top of the list shows how many of the three library documents are in use.
- Tap a document to open it. Scroll the grid horizontally or vertically.
- Tap a column letter or row number for insert and delete commands, and for
  the Premium move, split, merge, and sort commands.
- **Tools** at the top of the editor holds the Premium tools. Save status
  appears above the grid, with the filter summary when a filter is on.
  **Undo**, **Redo**, the grid size, **Add Row**, and **Add Column** appear
  below the grid.
- While typing, the keyboard toolbar shows **Tab**, which moves to the next
  cell, and **Done**, which stops editing.
- The envelope button next to **Privacy** opens **Send Feedback**. Tap
  **Report a bug** or **Request a feature** to open your email app with a draft
  to <feedback@plaintxtoffice.com> (<support@plaintxtoffice.com> in version
  1.0.0) that holds only the app version, the iOS version, and the device model.
  Write your message and send it. Tap **Open contact form** to use the contact
  page in your browser instead, and **Done** to close the screen. Your CSV files
  are never included, and nothing is sent until you send it.
<!-- Verified from: platform/ios/text_csv/Library/DocumentListView.swift; platform/ios/text_csv/Support/PrivacyPolicyView.swift; platform/ios/text_csv/Editor/CSVGridView.swift; platform/ios/text_csv/Editor/CSVEditorView.swift -->
<!-- Verified from: platform/ios/text_csv/Support/Feedback.swift [Feedback, FeedbackView] -->

## Everyday Tasks

### Create and edit a document

1. Choose **New**. On iPhone, you can also tap **New Document** in an empty
   library.
1. Enter a document name and confirm. An empty name becomes **Untitled**.
1. A blank three-by-three grid opens.
1. Enter text in a cell. On Windows, double-click the cell or select it and
   start typing. On iPhone, tap the cell.
1. Choose **Save** to save edits in the app library. On iPhone, **Save** is the
   checkmark button.

Cells contain text. Leading zeroes and numeric-looking values stay as typed;
there are no formulas or automatic number conversions.
<!-- Verified from: platform/windows/text_csv/ui/gui/events/library.py [create]; platform/windows/text_csv/adapters/library.py [create]; platform/windows/text_csv/domains/document/codec.py [normalize]; platform/ios/text_csv/Library/DocumentListView.swift [createDocument]; platform/ios/text_csv/Editor/CSVEditorViewModel.swift; platform/ios/text_csv/Editor/CSVEditorView.swift -->

### Change rows and columns

- **Windows (in development):** use **Add row** or **Add column** to append. To
  insert above, below, before, or after the selected cell, or to delete its row
  or column, right-click the cell or use the **Grid** menu.
- **iPhone:** tap **Add Row** or **Add Column** to append. Tap a row number for
  **Insert Row Above**, **Insert Row Below**, and **Delete Row**. Tap a column
  letter for **Insert Column Before**, **Insert Column After**, and **Delete
  Column**. With Text CSV Premium, the same menus also move, split, and merge;
  see [Use Premium tools on iPhone](#use-premium-tools-on-iphone).

At least one row and one column always remain. Deleting a row or column takes
effect immediately.
<!-- Verified from: platform/windows/text_csv/ui/gui/app.py [build_window]; platform/windows/text_csv/ui/gui/events/grid.py; platform/windows/text_csv/domains/document/models.py; platform/ios/text_csv/Editor/CSVGridView.swift; platform/ios/text_csv/Editor/CSVEditorView.swift -->

### Undo and redo changes

On iPhone and Android, **Undo** and **Redo** work without a subscription. On
iPhone they are at the bottom left of the editor, and with a hardware keyboard
**Cmd+Z** undoes and **Shift+Cmd+Z** redoes. Windows has no undo history.

- Up to 20 recent steps are kept while the document is open, including after
  saving.
- On iPhone, typing in one cell is one step; moving to another cell starts the
  next. Each row or column change and each Premium tool is one step.
- A new change after undoing clears **Redo**.
- On iPhone, **Reload Saved Copy** clears the history.
<!-- Verified from: platform/ios/text_csv/Editor/CSVEditorViewModel.swift [undo, redo, registerUndo, reloadSavedCopy]; platform/ios/text_csv/Editor/CSVEditorView.swift; platform/ios/text_csv/Editor/CSVGridView.swift -->

### Use Premium tools on iPhone

These tools need Text CSV Premium on iPhone. Open them from **Tools** at the
top of the editor, or from the row and column menus.

- **Find & Replace…:** type in **Find** to count matching cells. Turn on
  **Match case** or **Regular expression** as needed; with a regular
  expression, `$1` in **Replace with** inserts the first group. **Edit Next
  Match** closes the sheet and selects the next matching cell, and choosing it
  again continues from there. **Replace All** changes every match, including
  in the first row.
- **Sort Rows…:** choose a column under **Sort by** and **A to Z** or **Z to
  A**. Add up to two **Then by** levels to order rows that match on the
  earlier columns. Leave **First row is a header** on to keep the first row in
  place, then tap **Sort**. Sorting compares text, so **10** comes before
  **9**. **Sort Rows…** in a column letter's menu starts with that column.
- **Filter Rows…:** choose **Any column** or one column under **Look in**, type
  in **Rows containing**, and tap **Apply**. The editor shows **Showing X of Y
  rows** with **Clear Filter**. Filtering only hides rows; saving and export
  include every row. Typing in a cell does not hide its row. The filter is
  checked again after row or column changes, tools, undo, and redo, and a
  filter on one column ends when columns are added, removed, moved, split, or
  merged.
- **Remove Duplicates…:** shows how many rows exactly repeat an earlier row.
  Tap **Remove** to delete them. The first copy of each stays, and capital
  letters count as different.
- **Row and column tools:** tap a row number for **Move Up** and **Move
  Down**, or a column letter for **Move Left**, **Move Right**, **Split
  Column…**, and **Merge with Next Column…**. Splitting cuts each cell at the
  separator you type, a comma by default, and puts the extra parts in new
  columns to the right; spaces count. Merging joins the column with the next
  one using your separator, a space by default, and leaves it out when either
  cell is empty.
- **Export Options…:** see [Export a CSV copy](#export-a-csv-copy).

If a tool cannot run, for example because a regular expression is not valid or
a split would make more than 500 columns or 200,000 cells, **Could Not Change
the Document** explains why. The document is unchanged.
<!-- Verified from: platform/ios/text_csv/Editor/CSVEditorView.swift [toolsMenu]; platform/ios/text_csv/Editor/EditorToolSheets.swift; platform/ios/text_csv/Editor/CSVGridView.swift; platform/ios/text_csv/Editor/CSVEditorViewModel.swift; platform/ios/text_csv/Model/CSVTools.swift -->

### Use desktop editing tools

These commands are available only on Windows, which is in development.

1. Select a rectangle of cells and press **Ctrl+C** to copy it as tab-separated
   text.
1. Select the destination cell and press **Ctrl+V** to paste CSV or TSV text.
   The grid grows when needed.
1. Press **Delete** to clear the selected cells without removing rows or
   columns.
1. Choose **Edit > Edit multiline cell** or press **Ctrl+Enter** to edit a cell
   that contains line breaks.
1. Choose **File > Rename** or press **F2** to rename the current document, then
   save.

Changes have no undo history. **File > Reload saved copy** discards all edits
since the last save after you confirm.
<!-- Verified from: platform/windows/text_csv/ui/gui/events/grid.py; platform/windows/text_csv/ui/gui/events/library.py [rename]; platform/windows/text_csv/ui/gui/events/editor.py [reload] -->

### Remove a document

- **Windows (in development):** select the document in the sidebar, choose
  **File > Delete document**, and confirm.
- **iPhone:** swipe left on the document in the list and tap **Delete**. iPhone
  deletes immediately without asking for confirmation.

The library copy and its recovery draft are removed. Original imported files and
exported copies are not affected.
<!-- Verified from: platform/windows/text_csv/ui/gui/events/library.py [remove]; platform/windows/text_csv/application/documents.py [remove]; platform/ios/text_csv/Library/DocumentListView.swift [deleteDocuments] -->

### Recover unsaved edits

Reopening a document restores a readable recovery draft, and the status shows
**Recovered unsaved edits**. Save or export the recovered edits.

If the saved library copy changed elsewhere, the status reports that the saved
copy changed. Export your edits first, then choose **Reload saved copy** (on
iPhone, **Reload Saved Copy**) and confirm to discard them. The app does not
overwrite a conflicting saved copy.

On Windows, a recovery draft is written about half a second after a cell edit is
committed. If the app is forced to close before then, the latest change can be
lost. **File > Export recovery draft** works even when the library cannot open,
and **File > Retry opening library** tries to open it again.

On iPhone, if the library cannot open, a **Library Unavailable** screen offers
**Retry Opening Library** and an export button for each readable recovery draft.
<!-- Verified from: platform/windows/text_csv/application/documents.py [open_document]; platform/windows/text_csv/ui/gui/events/editor.py [checkpoint, reload]; platform/windows/text_csv/ui/gui/events/recovery.py; platform/ios/text_csv/Editor/CSVEditorViewModel.swift; platform/ios/text_csv/Editor/CSVEditorView.swift; platform/ios/text_csv/Library/CSVLibraryUnavailableView.swift -->

## Settings and Preferences

Text CSV has no user-editable settings on any platform. On Windows, sidebar and
column widths can be adjusted while the app is open; they reset when it
restarts.
<!-- Verified from: platform/windows/text_csv/ui/gui/views/window.py; platform/windows/text_csv/ui/gui/app.py; platform/ios/text_csv/App/ContentView.swift; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/main/ -->

## Importing and Exporting

### Import a document

1. Choose **Import**. On iPhone, you can also tap **Import File** in an empty
   library, or open the file in Text CSV from another app.
1. Select a UTF-8 CSV, TSV, or plain text file.
1. Edit the new library copy. Importing the same file again creates another
   copy. The original file is never changed.

Text CSV chooses commas or tabs by counting separators outside quotes in the
first record. Quoted separators, escaped quotes, and line breaks inside quoted
cells are supported. Shorter rows are padded with empty cells. On Windows, a
UTF-8 byte order mark is accepted. No column names are required. For example:

```csv
Name,Notes
Example,"Text with a comma, preserved"
```
<!-- Verified from: platform/windows/text_csv/domains/document/codec.py; platform/windows/text_csv/adapters/files.py [read_text]; platform/windows/text_csv/application/documents.py [import_file]; platform/ios/text_csv/Model/CSVParser.swift; platform/ios/text_csv/Editor/CSVEditorViewModel.swift; platform/ios/text_csv/Library/DocumentListView.swift -->

### Export a CSV copy

1. Choose **Export CSV** on Windows or **Export** on iPhone and Android.
1. Select a destination and filename. Confirm replacement if asked about an
   existing file.
1. Wait for the export result. Canceling leaves the document unchanged.

Exports use UTF-8, commas between fields, and CRLF line endings. On Android,
Text CSV Premium can instead export tab-separated text or a Markdown table,
with CRLF or LF line endings; see
[Text CSV Premium on Android](#text-csv-premium-on-android). On iPhone, with
Text CSV Premium, **Export** first opens **Export Options**: choose
**Comma-separated (CSV)**, **Tab-separated (TSV)**, or **Markdown table**, and
**Windows (CRLF)** or **Unix (LF)**, then tap **Export**. These files end every
line, including the last, and use the `.csv`, `.tsv`, or `.md` extension. A
Markdown table uses the first row as its header, escapes `|`, and writes line
breaks inside cells as `<br>`. An export includes
current edits but does not save them in the app library; choose **Save**
separately. On Windows, the status shows **CSV exported. Library save state is
unchanged.** On Android, it shows **File exported.**, or **File exported.
Library edits are still unsaved.** when edits are not yet saved.
<!-- Verified from: platform/windows/text_csv/domains/document/codec.py [serialize]; platform/windows/text_csv/adapters/files.py; platform/windows/text_csv/ui/gui/events/library.py [export]; platform/ios/text_csv/Model/CSVExportSnapshot.swift; platform/ios/text_csv/Model/CSVExportFormat.swift; platform/ios/text_csv/Editor/EditorToolSheets.swift [ExportOptionsSheet]; platform/ios/text_csv/Editor/CSVEditorView.swift; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/domain/DelimitedText.kt [ExportFormat, serialize]; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/data/DocumentFiles.kt; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/main/MainScreenViewModel.kt [export]; platform/android/app/src/main/res/values/strings.xml [status_exported, status_exported_unsaved] -->

## Commands and Shortcuts

### Windows keyboard shortcuts (in development)

| Shortcut | Menu command | What it does |
| --- | --- | --- |
| Ctrl+N | File > New | Create a document |
| Ctrl+O | File > Import | Import a file |
| Ctrl+S | File > Save | Save in the app library |
| Ctrl+Shift+S | File > Export CSV | Export a CSV copy |
| F2 | File > Rename | Rename the current document |
| Alt+F4 | File > Exit | Close, saving pending edits first |
| Ctrl+C | Edit > Copy | Copy selected cells |
| Ctrl+V | Edit > Paste | Paste CSV or TSV text |
| Delete | Edit > Clear cells | Clear selected cells |
| Ctrl+Enter | Edit > Edit multiline cell | Edit a cell with line breaks |

The remaining **File** and **Grid** commands have no shortcuts.
<!-- Verified from: platform/windows/text_csv/ui/gui/app.py [build_window] -->

### Windows terminal options (in development)

The Windows app accepts these command-line options.

| Command or option | Accepted values | What it does |
| --- | --- | --- |
| `FILE` | Path to a UTF-8 CSV or TSV file | Import the file and open the desktop app |
| `--gui` | None | Open the desktop app without the startup menu |
| `-h`, `--help` | None | Show usage and exit |

There is no separate command-line editing mode.
<!-- Verified from: platform/windows/text_csv/ui/cli/app.py; platform/windows/text_csv/main.py; platform/windows/pyproject.toml [project.scripts] -->

### iPhone controls

iPhone uses touch controls. While editing, the keyboard toolbar **Tab** button
moves to the next cell and stops editing at the last cell without adding a row.
With a hardware keyboard, **Cmd+Z** undoes and **Shift+Cmd+Z** redoes.
<!-- Verified from: platform/ios/text_csv/Editor/CSVGridView.swift; platform/ios/text_csv/Editor/CSVEditorViewModel.swift [nextCell]; platform/ios/text_csv/Editor/CSVEditorView.swift [keyboardShortcut] -->

## Your Data Files

| Platform | Files and locations |
| --- | --- |
| Windows (in development) | `library.sqlite3` and `recovery/*.json` in the `data` folder under `%LOCALAPPDATA%/text-csv/`; a portable build keeps them under a `text-csv-data` folder beside the program. **Help > Privacy** shows the location. |
| iPhone | Private app library and recovery storage on the device, plus a record of whether Text CSV Premium is active |
| Android | Private app library on the device; there are no recovery drafts |
| All | Imported originals and exported files stay where you chose |

Do not edit library or recovery files by hand. Export a CSV to get an editable
copy. The Windows app does not send documents over the network. Deleting the
iPhone or Android app removes its library.
<!-- Verified from: platform/windows/text_csv/config/path_handler.py [resolve_storage, DATA_DIR]; platform/windows/text_csv/main.py; platform/windows/text_csv/application/documents.py; platform/windows/text_csv/ui/gui/app.py [Privacy]; platform/ios/text_csv/Storage/CSVRecoveryStore.swift; platform/ios/text_csv/Storage/CSVLibraryStorage.swift; platform/ios/text_csv/Support/PrivacyPolicyView.swift; platform/ios/text_csv/Premium/PremiumStore.swift [cacheKey]; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/data/DocumentLibrary.kt; platform/android/app/src/main/res/values/strings.xml [privacy_removal_body] -->

## Troubleshooting

| Symptom | Likely Cause | Resolution |
| --- | --- | --- |
| Library cannot open | Storage is unavailable, full, or not permitted | Make space or fix permissions, then choose **Retry opening library**. Export readable recovery drafts if needed. |
| **Could not complete operation** (Windows) or **Could Not Save** (iPhone) | The save or file operation failed | Keep the document open, fix storage access, and retry Save, or export your edits. |
| Status says the saved copy changed | The library copy changed after you opened it | Export your edits, then reload the saved copy. |
| **Could not read file** or import fails | The file is not readable UTF-8 text | Save the file as UTF-8 CSV or TSV and import again. |
| **Recovery unavailable** in the status | Recovery drafts cannot be written | Keep the document open until Save or Export succeeds. On iPhone, tap **Retry Recovery**. |
| Premium screen shows **Subscription Unavailable** (iPhone) | The App Store cannot be reached, or the subscription is not offered in your country or region | Check your connection and App Store sign-in, then open the Premium screen again. |
| **Could Not Change the Document** (iPhone) | A Premium tool could not run, for example because of an invalid regular expression or a split that is too large | Correct the input and try again. The document is unchanged. |
<!-- Verified from: platform/windows/text_csv/ui/gui/events/editor.py; platform/windows/text_csv/application/documents.py; platform/ios/text_csv/Editor/CSVEditorView.swift; platform/ios/text_csv/Library/DocumentListView.swift [handleIncomingFile]; platform/ios/text_csv/Library/CSVLibraryUnavailableView.swift; platform/ios/text_csv/Premium/PremiumView.swift; platform/ios/text_csv/Editor/CSVEditorView.swift [toolError] -->

## FAQ

**Does Save change the file I imported?** No. Save updates the library copy.
Export writes a new file where you choose.
<!-- Verified from: platform/windows/text_csv/application/documents.py; platform/ios/text_csv/Library/DocumentListView.swift -->

**Do Windows, iPhone, and Android synchronize?** No. Move documents by
exporting a CSV on one and importing it on another.
<!-- Verified from: platform/windows/text_csv/adapters/library.py; platform/ios/text_csv/Storage/CSVLibraryStorage.swift; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/data/DocumentLibrary.kt -->

**Does exporting save my changes?** No. Choose **Save** separately.
<!-- Verified from: platform/windows/text_csv/ui/gui/events/library.py [export]; platform/ios/text_csv/Editor/CSVEditorViewModel.swift -->

**Can I undo a change?** On Android and iPhone, yes: **Undo** and **Redo** work
without a subscription and cover changes made since the document was opened.
Windows has no undo history. On Windows, **File > Reload saved copy** discards
all edits since the last save.
<!-- Verified from: platform/windows/text_csv/ui/gui/app.py; platform/windows/text_csv/ui/gui/events/editor.py [reload]; platform/ios/text_csv/Editor/CSVEditorView.swift; platform/ios/text_csv/Editor/CSVEditorViewModel.swift [undo, redo] -->

## Feedback

Send bug reports and feature requests by email to
<feedback@plaintxtoffice.com> or through the contact page at
<https://plaintxtoffice.com/contact/>. Each platform also has a feedback
screen that prepares the email for you:

| Platform | How to open feedback |
| --- | --- |
| iPhone | Tap the envelope button, **Send Feedback**, next to **Privacy** in the document list. |
| Android | Choose **Feedback** in the top bar. |
| Windows (in development) | Choose **Help > Send Feedback...**. |

The screen offers a bug report, a feature request, or the contact page. Your
documents are never included, and nothing is sent until you send it. The
details each draft holds are described in
[Navigate on iPhone](#navigate-on-iphone) and
[Use Text CSV on Android](#use-text-csv-on-android).
<!-- Verified from: platform/ios/text_csv/Library/DocumentListView.swift; platform/ios/text_csv/Support/Feedback.swift; platform/android/app/src/main/kotlin/com/plaintxtoffice/textcsv/ui/feedback/FeedbackScreen.kt; platform/android/app/src/main/res/values/strings.xml [feedback]; platform/windows/text_csv/ui/gui/app.py; platform/windows/text_csv/ui/gui/feedback.py [add_feedback_action] -->

## Glossary

- **Library:** the app's collection of saved documents.
- **Recovery draft:** a local copy of unsaved edits, kept separately from the
  saved document.
- **CSV / TSV:** plain text tables with values separated by commas or tabs.
- **Saved-copy conflict:** the library copy changed after the editor opened it.
- **Text CSV Premium:** an optional subscription on Android and iPhone that
  adds unlimited documents and extra editing and export tools.
