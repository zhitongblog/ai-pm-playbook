# SoloPDF: six days, two platforms

[English](solopdf.md) · [简体中文](solopdf.zh.md) · [All cases](README.md)

> Website: [solopdf.doaipm.com](https://solopdf.doaipm.com) · Repo: [github.com/zhitongblog/solopdf](https://github.com/zhitongblog/solopdf) (public)
> Numbers below are as stated in the doaipm playbook, as of August 2026.

## What it is

A free, ad-free PDF reader for iOS and macOS where your highlights become your notes. Highlight a passage and a Markdown note file is created next to the PDF: editable, full-text searchable, version-controllable with git, and one click takes you back to the spot in the original. The first commit already said it: "SoloPDF v0.1.0 — free, ad-free PDF reader; your highlights are your notes."

## Timeline

- **2026-07-05:** repo created. 17 commits on day one.
- **2026-07-06:** iOS upload succeeded; the sidebar became an overlay after real iPhone feedback; dual-platform App Store release automation.
- **2026-07-08:** on-device OCR (searchable PDF, Markdown, image to text), v0.2.0 and v0.3.0.
- **2026-07-09 to 07-11:** book reading mode, EPUB and TXT; two App Store rejections fixed.
- **2026-07-11:** iOS 0.4.4 / macOS 1.3.2. **43 commits, 6 days** in total.

## Key decisions

**Lock the positioning in the first commit.** "Your highlights are your notes" defines what to build and what not to: not another PDF reader, but the link between a PDF and your notes. None of the next 42 commits drifted from it.

**Build the store pipeline on day one.** The Mac App Store build pipeline and the iOS project were set up on the first day, release automation on the second. When the rejections came, the fixes were "change one line and run it again".

**Keep the "every client ships a CLI" rule, and pay for it.** OCR was built as a separate `solopdf-ocr` command-line program so scripts and AI agents can call it. That one rule caused three follow-up fixes on a single day: Tauri no longer knew which binary to run, the Mac App Store rejects bare nested executables (validation 90049/90885), and piped output crashed on EPIPE.

## What went wrong

- **Four commits on day one went back and forth on the website address**, because the decision was never written down. The AI did exactly what it was told each time.
- **Failures with no error.** Annotation, form filling and printing all worked in development and all broke inside the packaged `.app`. A config file saved by an external editor with a byte-order mark silently wiped every setting. `--lang ko` silently fell back to the Chinese model.
- **Two App Store rejections under guideline 2.1(a).** The Mac build opened to a white window for the reviewer: the sandbox was missing `com.apple.security.network.client`. Then on iOS, the file picker returned a `file://` URL and every PDF failed to open. The second fix was verified by repeating the reviewer's exact steps in the simulator.

## Where the time went

Counting the 43 commits by type: new features about one third; packaging, store, CI and signing about one third; real-device and detail fixes about a quarter; brand and docs the rest. Features got faster. The rest of shipping a real product didn't.

The last commits were all details: page drift when the font size changes, the panel not closing, reading progress lost when the same book is opened from a different path. None is a feature; missing any of them makes the app feel rough, and an AI doesn't find them because it has never paged through a book on a phone.

---

The full day-by-day trace, with commit hashes, is in the [playbook](https://doaipm.com/en/presale/). Related checklist: [launch self-check](../../templates/launch-checklist.md).
