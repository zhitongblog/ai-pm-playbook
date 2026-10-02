# Launch self-check

[English](launch-checklist.md) · [简体中文](launch-checklist.zh.md)

Go through this before you call anything done, deploy it, or submit it to a store. It is condensed from the launch chapter of the [doaipm playbook](https://doaipm.com/en/presale/), which comes from shipping four products and getting rejected by the App Store three times.

The principle behind every item: **success has to be read back from the outside world. You can't declare it yourself.** AI agents handle error paths well. What they don't catch are failures that throw no error: a packaged app where three features silently stopped working, a config file with a byte-order mark that silently wiped all settings, a `--lang ko` flag that silently fell back to Chinese. Unit tests were green in all three.

## 1. Self-check before declaring done

Run the real flow, not just the tests. For each feature:

- [ ] **Data round trip.** Create a fixture, drive the feature, read the result back and assert. Only what should change changed.
- [ ] **UI path.** Drive the real UI with the app actually running, and verify with screenshots.
- [ ] **Unit tests** for whichever layers were touched.
- [ ] **Clean, minimal diff.** Glance at `git diff`. Reformatted files, unrelated indentation changes and deleted "unused" code show up immediately.
- [ ] **CLI / MCP smoke test**, if your product exposes them: new capabilities appear there too.
- [ ] **Localization.** New strings are in the primary language; the other languages have placeholders.
- [ ] **High-fidelity check.** Real content, all four states (loading / empty / error / success), real interactions, critical path end to end, narrow screen, odd input. See [Phase 5 · Validate](../method/05-validate.md).

**Red line: not done until the self-test passes.** If something truly can't be automated, fall back to a lower level (for example, state-level assertions plus screenshots) and write the fallback down. Downgrading is allowed. Skipping is not.

## 2. Before trusting any "success"

- [ ] **Who decided it succeeded?** If the code judged its own success, read it back from the real target instead.
- [ ] **Could this step hit the wrong thing?** Locating by text, position or index, followed by a write or a click that can't be undone: a person takes over. (`Publish` matching `Published` is a real example.)
- [ ] **Can the agent see the result?** Packaged builds, real devices, store review, external services: a person checks once.
- [ ] **Any process you'll run repeatedly has a pre-run checkup**, including one real action (for example, one real click) to prove the tooling works before the real run.

## 3. Web launch

- [ ] Deploy is one push (for example, Cloudflare Pages building from the main branch).
- [ ] **Wait for a real 200 before announcing.** Edge nodes don't update at the same moment. In one measured deploy, pages started returning 200 about 60 seconds after the push, and one locale kept returning 404 for about another minute.

```bash
until [ "$(curl -s -o /dev/null -w '%{http_code}' https://your-domain/path)" = "200" ]; do
  sleep 15
done
echo LIVE
```

## 4. App Store submission

The three rejections, turned into a checklist. Two came from metadata and configuration, not from feature code; the third was the reviewer's plainest path failing at the file picker.

| Check | Why |
|---|---|
| [ ] No price words ("free", etc.) in the subtitle, keywords, promotional text, description, **or the text on screenshots** | Guideline **2.3.7** (accurate metadata). FreeID Photo was rejected with "Truly free" as the first screenshot's headline |
| [ ] Camera, face, health or location data? The privacy page and review notes answer Apple's questions directly | Guideline **2.1**. FreeID Photo uses Vision face detection; the fix was a "Face data" section: processed on device, not stored, not shared, not retained |
| [ ] **Launch the signed release build once in a clean environment** | Guideline **2.1(a)**. SoloPDF's Mac build opened to a blank white window for the reviewer: the sandbox was missing `com.apple.security.network.client`. It worked in development, which doesn't use the sandbox |
| [ ] **Walk the plainest user path**: open the app, pick a file, use it | Guideline **2.1(a)**. SoloPDF on iOS: the file picker returned a `file://` URL and every PDF failed to open |
| [ ] No bare nested executables in the Mac App Store bundle | Validation errors **90049 / 90885** (SoloPDF embedded a CLI helper) |
| [ ] Extended attributes cleared (`xattr -cr`) | Validation error **91109** |
| [ ] Hardened runtime **off** for the Mac App Store build | It conflicts with the sandbox; the submission is rejected |
| [ ] Review notes include the root cause of any fix, a sample file, and the support page | Saves a round trip |

Three habits that pay back on the next app:

- **Make submission one command.** Bump version, test, archive, upload, wait for processing, apply metadata, submit. Keep all metadata in one file. Two of the three rejections were "change metadata, resubmit the same build"; with a script, that's one edited line.
- **Your tooling must accept a rejected version as editable.** After a rejection, the version state changes, and a script that doesn't expect that state can't resubmit.
- **Reproduce the reviewer's exact path before resubmitting.** SoloPDF's fix was verified by repeating the reviewer's steps in the iPad simulator, then end to end on the iPhone simulator.

## 5. After launch

- [ ] Look at each channel with your own eyes on a schedule: real views, comments, account status. A script that reports "posted" every day can hide a channel that has been dead for a month.
- [ ] If two or more people work on the product, write down who owns which directories.

---

Want the full story behind each item, commit by commit? It's in the [playbook](https://doaipm.com/en/presale/). The case summaries are in [`cases/official/`](../cases/official/README.md).
