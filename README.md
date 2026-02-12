# LOCAL MRI REPORT(.html) QC

# 🧠 Local MRI QC — A Lightweight fMRIPrep Report Review Tool

A fast, local, installable QC cockpit for reviewing and annotating HTML reports (e.g., fMRIPrep outputs).

Designed for researchers who need to move quickly through large batches of reports, compare sessions side-by-side, and keep structured QC records — without spinning up servers or uploading sensitive data.

---

## Why This Exists

Manual QC of neuroimaging reports is repetitive and cognitively expensive.

This tool turns report review into a structured, keyboard-driven workflow with:

* Persistent tagging
* Structured logging
* Side-by-side comparison
* Search and filtering
* Instant CSV export

All running **100% locally in your browser**.

No backend. No uploads. No PHI leaving your machine.

---

## Core Features

### 📂 Local Folder Loading

* Select a folder containing HTML reports.
* Lists first-level `.html` files for clean navigation.
* Loads report assets recursively to ensure correct rendering.

### 🧭 Fast Navigation

* Keyboard navigation (`↑ ↓`)
* `Enter` to open
* `Shift + Enter` to compare
* Quick tag keys (`1`, `2`, `3`)
* Instant search filtering

### 🪟 Side-by-Side Comparison

* View up to three reports simultaneously.
* Ideal for:

  * Across-session comparisons
  * Run-level differences
  * Pre/post contrasts
  * Version comparison

### 🏷 Structured Tagging

Each report can be labeled as:

* **Accept**
* **Uncertain**
* **Reject**

Tags are visually encoded and immediately reflected in:

* Sidebar badges
* Comparison headers
* CSV preview

### 📝 Notes Per Report

* Add detailed free-text notes.
* Notes are autosaved.
* Supports searchable annotations.

### 💾 Persistent Memory (LocalStorage)

Your decisions are automatically saved in browser storage:

* Survive refresh
* Survive closing/reopening
* No manual save required

This creates continuity across QC sessions without needing a database.

### 📊 CSV Preview Panel

* Live preview of structured QC table
* Filter by tag
* Search by filename or notes
* Click a row to jump directly to that report
* Export-ready formatting

### 📤 Structured Logging

Export decisions as CSV including:

* Timestamp
* Relative path
* Filename
* Tag
* Notes

Enables:

* Lab documentation
* QC audit trails
* Pipeline integration
* Downstream tracking

### 🔒 Privacy-Preserving

* No uploads
* No cloud storage
* No data transmission
* Runs entirely on `localhost`

---

## Installation (Optional but Recommended)

You can run it directly as an HTML file.

For a more “app-like” experience:

1. Run a local server:

   ```bash
   python3 -m http.server 8000
   ```
2. Open:

   ```
   http://localhost:8000/qc_reports.html
   ```
3. In Edge or Chrome:

   * `…` → Apps → Install this site as an app

This creates a standalone desktop launcher.

---

## Keyboard Shortcuts

| Key           | Action               |
| ------------- | -------------------- |
| ↑ / ↓         | Navigate reports     |
| Enter         | Open selected report |
| Shift + Enter | Add to comparison    |
| Esc           | Clear comparison     |
| 1             | Accept               |
| 2             | Uncertain            |
| 3             | Reject               |

---

## Use Cases

* fMRIPrep QC across subjects
* Multi-session longitudinal studies
* Pre/post intervention review
* Version comparison (pipeline updates)
* Manual quality audits
* Teaching trainees how to read reports
* Creating structured QC logs for publications

---

## Design Philosophy

This tool embraces three principles:

1. **Speed reduces cognitive fatigue**
2. **Structure reduces ambiguity**
3. **Local tools protect data integrity**

It is intentionally minimal.
It does not attempt to replace your pipeline.
It augments your judgment with structure.

---

## Technical Notes

* Pure HTML/CSS/JavaScript
* No framework dependencies
* Uses File System Access API when available
* Falls back to `webkitdirectory` for compatibility
* Uses localStorage for persistence
* Optional Service Worker for installable PWA behavior

---

## Limitations

* Must be served from `http://localhost` for installable mode.
* Does not modify reports.
* Does not automatically recurse nested HTML unless configured.
* LocalStorage is browser-profile specific.

---

## Future Extensions (Ideas)

* Subject/session grouping
* QC dashboard summary
* “Jump to next untagged”
* Batch tagging
* Auto-detection of motion metrics
* SQLite logging backend (Electron version)
* Multi-user lab version

---

## Why This Matters

Quality control is not glamorous.
But it determines the validity of everything downstream.

This tool turns QC from a scattered activity into a reproducible, logged, inspectable workflow.

As Richard Feynman put it:

> “The first principle is that you must not fool yourself — and you are the easiest person to fool.”

Structured QC is how we reduce that risk.
