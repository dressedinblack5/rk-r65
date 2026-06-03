# VIA Definition Design for Royal Kludge R65

## Goal
Create a standalone `via-definition.json` file for manual import into the VIA configurator, ensuring full compatibility without modifying the existing `keyboard.json`.

## Architecture
- **Input:** Extract keyboard layout data from existing `keyboard.json`.
- **Output:** Generate `via-definition.json` compliant with VIA schema for manual import.
- **Constraints:** `keyboard.json` MUST NOT be modified.

## Structure (`via-definition.json`)
```json
{
  "name": "Royal Kludge R65 ISO",
  "vendorProductId": "0x342DE480",
  "lighting": "qmk_rgb_matrix",
  "matrix": { "rows": 5, "cols": 15 },
  "layouts": {
    "keymap": [
      // Mappings extracted from keyboard.json:layouts:LAYOUT:layout
    ]
  }
}
```

## Review
- **Consistency:** The matrix size (5x15) and key mappings will be directly mapped from `keyboard.json` to ensure consistency.
- **Scope:** Limited to generating the JSON file. No firmware changes.
