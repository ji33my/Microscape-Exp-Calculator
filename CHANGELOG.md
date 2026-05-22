# Microscape Calculator — Changelog

---

## v1.20 — 2026-05-22

### Time Calculator
- Fix Current Bag Qty: now correctly reduces remaining actions needed (time decreases as expected), with "(X in bag)" shown in result card

---

## v1.19 — 2026-05-22

### Time Calculator
- Added Current Bag Qty field to settings — accounts for items already in your loot bag when calculating bank trips and overlay simulation

---

## v1.18 — 2026-05-21

### Time Calculator
- Fix main page status bar not updating while overlay is open or minimized

---

## v1.17 — 2026-05-20

### Both Calculators
- Replaced single MM:SS input with two separate MM and SS boxes; typing one digit in MM auto-advances to SS
- Old presets load correctly via backward-compatible conversion

---

## v1.16 — 2026-05-20

### Both Calculators
- Fix MM:SS fill order: left-to-right within each pair (tens-of-seconds first), seconds before minutes

---

## v1.15 — 2026-05-19

### Both Calculators
- MM:SS time input reworked: digits fill right-to-left (units of seconds first), template chars stay dim, colon brightens at 3+ digits
- Chill Spot Banking checkbox — switches banking time from 46s to 18s
- Settings checkboxes (Shell, Gilded, Chill Spot) displayed horizontally with individual ⓘ hover tooltips
- Craft Ratio checkbox on all item types — reveals Uses/Makes per action fields
- Resulting items count shown in results when Makes > 1

---

## v1.10 — 2026-05-19

### XP & Item Calculator
- Added **Craft Ratio** checkbox to all item types — reveals "Uses per action" and "Makes per action" fields
- Results card now shows resulting item count when Makes > 1 (e.g. 500 actions → 5,000 Arrow Tips)
- Cost line now multiplies by Uses per action when Uses > 1
- Added version display (v1.01) below subtitle

### Time Calculator
- Added **Craft Ratio** checkbox to all item types — same Uses/Makes fields
- Overlay simulation updated to respect Makes per action
- Result meta shows action count and ratio when Makes > 1
- Seconds per action input changed to **MM:SS** format (e.g. type `116` → `1:16`)
- Hidden **+2 second offset** added to all time calculations to account for action delay
- Added version display (v1.01) below subtitle

### Both Calculators
- Added **Chill Spot Banking** checkbox — switches banking time from 46s to 18s when enabled
- **Backup Presets** button — exports presets as a tagged JSON file
- **Load Presets** button — imports JSON; warns if file is for the wrong calculator
- Preset panel always visible (Backup/Load accessible even with no saved presets)
- `optimizeXP` checkbox state now saved and restored with presets
- Chill Spot banking warning updated to mention abilities that affect acquisition speed
- Overlay window now auto-resizes using ResizeObserver instead of manual calls

---

## v1.0 — Initial Release

### XP & Item Calculator
- XP calculation using verified Microscape XP formula
- Crafting and Gathering modes
- Primary item, Chain item, Secondary items with qty goals
- Qty owned support (deducted from craft count)
- Time estimate with seconds per action (Shell/Gilded Pockets, Double Up Chance)
- Optimize XP Gains — auto-splits level range using best available item per segment
- Skill item tables (Smithing, Cooking, Fletching, Fishing, Mining, Herblaw, Crafting, Woodcutting)
- XP table (levels 1–99)
- Saved presets (localStorage or cookies)
- Level display as `Current → Goal` (e.g. 25 → 90)

### Time Calculator
- Item/quantity/seconds-per-action entry with multiple items
- Bank trip calculation (Shell/Gilded Pockets, Double Up Chance)
- Live overlay timer with Picture-in-Picture support
- Pre-start countdown, progress bar, per-item tracking
- Session persistence (overlay resumes if reopened mid-session)
- Saved presets (localStorage or cookies)
