# LOCAL MRI REPORT(.html) QC

# 🧠 Local MRI QC — A Lightweight fMRIPrep Report Review Tool

A fast, local, installable QC cockpit for reviewing and annotating HTML reports (e.g., fMRIPrep outputs).

Built for high-throughput QC: compare sessions, tag outcomes, take notes, and export structured logs — all **locally**.

---

## TL;DR
- 📂 Load local folders of HTML reports (first-level `.html`, assets supported)
- 🪟 Compare up to 3 reports side-by-side
- 🏷 Tag: Accept / Uncertain / Reject + 📝 notes
- 💾 Persistent memory (autosave via browser storage)
- 📊 Preview decisions as a table; 📤 export CSV anytime
- 🔒 No uploads, no server, no data leaving your machine

---

<details>
  <summary><strong>Why This Exists</strong></summary>

Manual QC is repetitive and cognitively expensive. This tool turns report review into a structured, keyboard-driven workflow with:

- persistent tagging
- searchable notes
- side-by-side comparisons
- exportable QC logs

All running **100% locally** in your browser.
</details>

<details>
  <summary><strong>Core Features</strong></summary>

### 📂 Local Folder Loading
- Select a folder containing HTML reports
- Lists **first-level** `.html` files for clean navigation
- Loads assets recursively so reports render correctly

### 🧭 Fast Navigation
- Keyboard navigation (`↑ ↓`)
- `Enter` to open
- `Shift + Enter` to compare
- Quick tag keys (`1`, `2`, `3`)
- Instant search filtering

### 🪟 Side-by-Side Comparison
- View up to **three** reports simultaneously
- Great for across-session/run comparisons and pipeline/version diffs

### 🏷 Structured Tagging + 📝 Notes
Per report:
- **Accept**
- **Uncertain**
- **Reject**
- Free-text notes (autosaved + searchable)

### 💾 Persistent Memory
Decisions autosave via browser storage:
- survives refresh
- survives closing/reopening
- no manual save step

### 📊 CSV Preview + 📤 Export
- In-app table preview (filter + search + jump-to-report)
- Export CSV with timestamp, filename/path, tag, notes
</details>

<details>
  <summary><strong>Install (Optional, “Feels Like an App”)</strong></summary>

You can run this directly as an HTML file.

For installable “app mode” (recommended):

1. Start a local server in the folder containing `qc_reports.html`:
   ```
   bash python3 -m http.server 8000
   ```

2. Open:

   ```
   http://localhost:8000/qc_reports.html
   ```
3. In Edge/Chrome:

   * `…` → **Apps** → **Install this site as an app**

This creates a standalone desktop launcher.

</details>

<details>
  <summary><strong>Keyboard Shortcuts</strong></summary>

| Key           | Action               |
| ------------- | -------------------- |
| ↑ / ↓         | Navigate reports     |
| Enter         | Open selected report |
| Shift + Enter | Add to comparison    |
| Esc           | Clear comparison     |
| 1             | Accept               |
| 2             | Uncertain            |
| 3             | Reject               |

</details>

<details>
  <summary><strong>Use Cases</strong></summary>

* fMRIPrep QC across subjects
* Multi-session longitudinal studies
* Pre/post intervention review
* Version comparison after pipeline updates
* Manual QC audits with structured logging
* Training new lab members on report review

</details>

<details>
  <summary><strong>Privacy & Data Policy</strong></summary>

* No uploads
* No telemetry
* No cloud sync
* Runs locally (`localhost`) and reads files only after you pick a folder

**Nothing leaves your machine.**

</details>

<details>
  <summary><strong>Technical Notes</strong></summary>

* Pure HTML/CSS/JavaScript (no framework dependencies)
* Uses File System Access API when available
* Falls back to `webkitdirectory` for compatibility
* Uses localStorage for persistence
* Optional PWA support (manifest + service worker) for installable mode

</details>

<details>
  <summary><strong>Limitations</strong></summary>

* Installable mode requires `http://localhost` (not `file://`)
* Does not modify reports
* localStorage is browser-profile specific
* Some exotic asset-linking patterns may need extra rewriting logic

</details>

<details>
  <summary><strong>Future Extensions</strong></summary>

* Subject/session grouping + dashboard summary
* “Jump to next untagged”
* Batch tagging
* Electron/Tauri version for direct on-disk CSV writing
* Multi-user/shared QC logs

</details>

---

> “The first principle is that you must not fool yourself — and you are the easiest person to fool.” — Richard Feynman


