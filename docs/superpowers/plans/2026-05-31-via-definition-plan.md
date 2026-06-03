# VIA Definition Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a standalone `via-definition.json` file for manual import into the VIA configurator, extracted from existing `keyboard.json` data, without modifying `keyboard.json`.

**Architecture:** Use the existing layout data in `keyboard.json` as the source of truth to build a new JSON structure compatible with the VIA "Design" tab schema.

**Tech Stack:** JSON (manual file generation).

---

### Task 1: Extract Layout Data

**Files:**
- Read: `keyboard.json`
- Create: `via-definition.json`

- [ ] **Step 1: Read and analyze `keyboard.json`**
- [ ] **Step 2: Construct the VIA definition JSON structure**
  - Use the following template, filling the `layouts` key with the extracted `layouts:LAYOUT:layout` data from `keyboard.json`.

```json
{
  "name": "Royal Kludge R65 ISO",
  "vendorProductId": "0x342DE480",
  "lighting": "qmk_rgb_matrix",
  "matrix": { "rows": 5, "cols": 15 },
  "layouts": {
    "keymap": [
      // Insert mapped layout data here
    ]
  }
}
```

- [ ] **Step 3: Write to `via-definition.json`**

- [ ] **Step 4: Commit**
```bash
git add via-definition.json
git commit -m "feat: add via-definition.json for manual import"
```
