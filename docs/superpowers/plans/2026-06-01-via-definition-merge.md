# Via Definition Merge Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Merge functional definitions (`keycodes`, `menus`, `customKeycodes`) from the reference file into the verified `via-definition.json` while preserving its existing matrix/layout structure.

**Architecture:** Manually construct the JSON object, taking functional metadata from the reference file and structural layout data from the original file.

**Tech Stack:** JSON.

---

### Task 1: Merge Definitions and Verify

**Files:**
- Modify: `/home/dressedinblack/Projects/rk-r65/via-definition.json`

- [ ] **Step 1: Construct the merged JSON object**

Create the following JSON structure:

```json
{
  "name": "Royal Kludge R65 ISO",
  "vendorId": "0x342D",
  "productId": "0xE480",
  "lighting": "qmk_rgb_matrix",
  "keycodes": ["qmk_lighting"],
  "menus": [
    {
      "label": "Lighting",
      "content": [
        {
          "label": "Backlight",
          "content": [
            {
              "label": "Brightness",
              "type": "range",
              "options": [0, 255],
              "content": ["id_qmk_rgb_matrix_brightness", 3, 1]
            },
            {
              "label": "Effect",
              "type": "dropdown",
              "content": ["id_qmk_rgb_matrix_effect", 3, 2],
              "options": [
                ["All Off", 0],
                ["Solid Color", 1],
                ["Alphas Mods", 2],
                ["Gradient Up Down", 3],
                ["Gradient Left Right", 4],
                ["Breathing", 5],
                ["Band Sat", 6],
                ["Band Val", 7],
                ["Band Pinwheel Sat", 8],
                ["Band Pinwheel Val", 9],
                ["Band Spiral Sat", 10],
                ["Band Spiral Val", 11],
                ["Cycle All", 12],
                ["Cycle Left Right", 13],
                ["Cycle Up Down", 14],
                ["Rainbow Moving Chevron", 15],
                ["Cycle Out In", 16],
                ["Cycle Out In Dual", 17],
                ["Cycle Pinwheel", 18],
                ["Cycle Spiral", 19],
                ["Dual Beacon", 20],
                ["Rainbow Beacon", 21],
                ["Rainbow Pinwheels", 22],
                ["Raindrops", 23],
                ["Jellybean Raindrops", 24],
                ["Hue Breathing", 25],
                ["Hue Pendulum", 26],
                ["Hue Wave", 27],
                ["Pixel Rain", 28],
                ["Pixel Flow", 29],
                ["Pixel Fractal", 30],
                ["Typing Heatmap", 31],
                ["Digital Rain", 32],
                ["Solid Reactive Simple", 33],
                ["Solid Reactive", 34],
                ["Solid Reactive Wide", 35],
                ["Solid Reactive Multiwide", 36],
                ["Solid Reactive Cross", 37],
                ["Solid Reactive Multicross", 38],
                ["Solid Reactive Nexus", 39],
                ["Solid Reactive Multinexus", 40],
                ["Splash", 41],
                ["Multisplash", 42],
                ["Solid Splash", 43],
                ["Solid Multisplash", 44],
                ["Close All", 45]
              ]
            },
            {
              "showIf": "{id_qmk_rgb_matrix_effect} != 0",
              "label": "Effect Speed",
              "type": "range",
              "options": [0, 255],
              "content": ["id_qmk_rgb_matrix_effect_speed", 3, 3]
            },
            {
              "showIf": "{id_qmk_rgb_matrix_effect} != 0 && {id_qmk_rgb_matrix_effect} != 24 && {id_qmk_rgb_matrix_effect} != 28 && {id_qmk_rgb_matrix_effect} != 29 && {id_qmk_rgb_matrix_effect} != 32",
              "label": "Color",
              "type": "color",
              "content": ["id_qmk_rgb_matrix_color", 3, 4]
            }
          ]
        }
      ]
    }
  ],
  "matrix": {
    "rows": 5,
    "cols": 15
  },
  "customKeycodes": [
    {"name": "BT DEV1","title": "BT Device 1","shortName": "DEV1"},
    {"name": "BT DEV2","title": "BT Device 2","shortName": "DEV2"},
    {"name": "BT DEV3","title": "BT Device 3","shortName": "DEV3"},
    {"name": "BT DEV4","title": "BT Device 4","shortName": "DEV4"},
    {"name": "BT DEV5","title": "BT Device 5","shortName": "DEV5"},
    {"name": "2.4G","title": "2.4G","shortName": "DEV 2.4G"},
    {"name": "USB","title": "USB","shortName": "DEV USB"}
  ],
  "layouts": {
    "keymap": [
      {"matrix": [0, 0], "x": 0, "y": 0},
      {"matrix": [0, 1], "x": 1, "y": 0},
      {"matrix": [0, 2], "x": 2, "y": 0},
      {"matrix": [0, 3], "x": 3, "y": 0},
      {"matrix": [0, 4], "x": 4, "y": 0},
      {"matrix": [0, 5], "x": 5, "y": 0},
      {"matrix": [0, 6], "x": 6, "y": 0},
      {"matrix": [0, 7], "x": 7, "y": 0},
      {"matrix": [0, 8], "x": 8, "y": 0},
      {"matrix": [0, 9], "x": 9, "y": 0},
      {"matrix": [0, 10], "x": 10, "y": 0},
      {"matrix": [0, 11], "x": 11, "y": 0},
      {"matrix": [0, 12], "x": 12, "y": 0},
      {"matrix": [0, 13], "x": 13, "y": 0, "w": 2.25},
      {"matrix": [0, 14], "x": 15.25, "y": 0},
      {"matrix": [1, 0], "x": 0, "y": 1, "w": 1.5},
      {"matrix": [1, 1], "x": 1.5, "y": 1},
      {"matrix": [1, 2], "x": 2.5, "y": 1},
      {"matrix": [1, 3], "x": 3.5, "y": 1},
      {"matrix": [1, 4], "x": 4.5, "y": 1},
      {"matrix": [1, 5], "x": 5.5, "y": 1},
      {"matrix": [1, 6], "x": 6.5, "y": 1},
      {"matrix": [1, 7], "x": 7.5, "y": 1},
      {"matrix": [1, 8], "x": 8.5, "y": 1},
      {"matrix": [1, 9], "x": 9.5, "y": 1},
      {"matrix": [1, 10], "x": 10.5, "y": 1},
      {"matrix": [1, 11], "x": 11.5, "y": 1},
      {"matrix": [1, 12], "x": 12.5, "y": 1},
      {"matrix": [2, 13], "x": 14, "y": 1, "w": 1.25, "h": 2},
      {"matrix": [1, 14], "x": 15.25, "y": 1},
      {"matrix": [2, 0], "x": 0, "y": 2, "w": 1.75},
      {"matrix": [2, 1], "x": 1.75, "y": 2},
      {"matrix": [2, 2], "x": 2.75, "y": 2},
      {"matrix": [2, 3], "x": 3.75, "y": 2},
      {"matrix": [2, 4], "x": 4.75, "y": 2},
      {"matrix": [2, 5], "x": 5.75, "y": 2},
      {"matrix": [2, 6], "x": 6.75, "y": 2},
      {"matrix": [2, 7], "x": 7.75, "y": 2},
      {"matrix": [2, 8], "x": 8.75, "y": 2},
      {"matrix": [2, 9], "x": 9.75, "y": 2},
      {"matrix": [2, 10], "x": 10.75, "y": 2},
      {"matrix": [2, 11], "x": 11.75, "y": 2},
      {"matrix": [2, 12], "x": 12.75, "y": 2, "w": 1.25},
      {"matrix": [2, 14], "x": 15.25, "y": 2},
      {"matrix": [3, 0], "x": 0, "y": 3, "w": 1.25},
      {"matrix": [3, 1], "x": 1.25, "y": 3},
      {"matrix": [3, 2], "x": 2.25, "y": 3},
      {"matrix": [3, 3], "x": 3.25, "y": 3},
      {"matrix": [3, 4], "x": 4.25, "y": 3},
      {"matrix": [3, 5], "x": 5.25, "y": 3},
      {"matrix": [3, 6], "x": 6.25, "y": 3},
      {"matrix": [3, 7], "x": 7.25, "y": 3},
      {"matrix": [3, 8], "x": 8.25, "y": 3},
      {"matrix": [3, 9], "x": 9.25, "y": 3},
      {"matrix": [3, 10], "x": 10.25, "y": 3},
      {"matrix": [3, 11], "x": 11.25, "y": 3},
      {"matrix": [3, 12], "x": 12.25, "y": 3, "w": 2},
      {"matrix": [3, 13], "x": 14.25, "y": 3},
      {"matrix": [3, 14], "x": 15.25, "y": 3},
      {"matrix": [4, 0], "x": 0, "y": 4, "w": 1.25},
      {"matrix": [4, 1], "x": 1.25, "y": 4, "w": 1.25},
      {"matrix": [4, 2], "x": 2.5, "y": 4, "w": 1.25},
      {"matrix": [4, 5], "x": 3.75, "y": 4, "w": 6.5},
      {"matrix": [4, 8], "x": 10.25, "y": 4, "w": 1.25},
      {"matrix": [4, 9], "x": 11.5, "y": 4, "w": 1.25},
      {"matrix": [4, 11], "x": 13.25, "y": 4},
      {"matrix": [4, 13], "x": 14.25, "y": 4},
      {"matrix": [4, 14], "x": 15.25, "y": 4}
    ]
  }
}
```

- [ ] **Step 2: Write merged JSON to `via-definition.json`**

```bash
# Verify it's valid JSON
echo '...' | jq . > /dev/null
# Write
echo '...' > /home/dressedinblack/Projects/rk-r65/via-definition.json
```

- [ ] **Step 3: Commit**

```bash
git add /home/dressedinblack/Projects/rk-r65/via-definition.json
git commit -m "chore: update via-definition.json with functional definitions"
```
