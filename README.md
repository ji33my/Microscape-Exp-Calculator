# Microscape Calculators

Browser-based tools for planning your training in [Microscape](https://microscape.cc/play/).

**[Open Exp/Time Calculator](https://ji33my.github.io/Microscape-Exp-Calculator/microscape_calculator.html)** — XP planning, item quantities, crafting/gathering modes, and time estimates.

**[Open Basic Time Calculator](https://ji33my.github.io/Microscape-Exp-Calculator/microscape_time_calculator.html)** — Enter items, quantities, and seconds per action to get a time estimate. Includes a live overlay timer.

---

## Free to Use

This project is completely open — use it, save it, fork it, modify it, do whatever you want with it. No credit required. If you want to host your own version, customize it for a different game, or strip it down for something else entirely, go for it. The whole thing is a single self-contained HTML file with no dependencies beyond a Google Fonts import, so it works offline too — just save the page and open it in any browser.

---

## Usage

1. Select **Crafting** or **Gathering** mode
2. Enter your **current level**, **goal level**, and **% to next level** (shown in-game on the skill panel)
3. Fill in your primary item and any additional items
4. Optionally enable **time estimate** and enter seconds per action
5. Hit **Calculate**

Results show how many of each item to craft or gather, XP contributed per item, and estimated time if enabled.

---

## Features

### General
- **XP calculation** — accurate XP requirements for any level range using the verified Microscape XP formula
- **Collapsible panels** — Items and Results panels collapse automatically after calculating to keep things clean
- **Saved presets** — save your current setup by name and switch between them with one click. Persists across sessions (localStorage or cookies). Use **Backup** to export presets as a JSON file and **Load** to import them back — handy for transferring between devices or browsers
- **XP table** — view cumulative XP and XP-to-next for every level from 1 to 99
- **Skill item tables** — browse XP and sell price data for Smithing, Cooking, Fletching, Fishing, Mining, Herblaw, Crafting, and Woodcutting. Filter by name

### Crafting Mode
- **Primary item** — the main thing you're crafting toward your goal
- **Chain item** — for when your primary item is used as an ingredient in a second craft (e.g. smelt Steel Bars → smith Steel Arrowtips). Supports an optional qty goal
- **Items with qty goals** — side items you want a fixed quantity of (e.g. Silver Bars), calculated first before the primary
- **Qty owned** — account for stock you already have; the calculator factors it in and adjusts what's left to craft
- **Material cost** — optional gold cost per craft. Shows total cost and gp/xp across all items

### Gathering Mode
- **Gathering item** — the main resource you're collecting (e.g. Willow Logs)
- **Additional gathering items** — add extra resources with an optional qty goal
- **Optimize XP Gains** — type a gathering item name and the calculator automatically looks it up in the skill tables, then splits your level range into segments using the best available item at each level (e.g. Oak Logs from 25→30, Willow Logs from 30→45)

### Time Estimate
- Enable time tracking to see how long your grind will take
- Input **seconds between items** for your activity
- **Shell Pockets** (+2 slots) and **Gilded Pockets** (+3 slots) checkboxes adjust loot bag size (base 25) for more accurate banking trip calculations
- **Chill Spot Banking** reduces banking time from 46s to 18s per trip
- **Current Bag Qty** — enter how many items are already in your loot bag; adjusts the bank trip count to reflect your actual starting state
- Time displays in seconds, minutes, hours, days, or years as appropriate
- Each result card shows the estimated time for that specific portion of XP
- Note: does not account for some abilities that would speed up item acquisition and exp gains

### Live Overlay Timer (Basic Time Calculator only)
After calculating, click **Open Live Overlay** to launch a floating timer window you can keep visible while playing.

- **Always-on-top** — uses the browser's Picture-in-Picture API (Chrome 116+) so the overlay floats above all other windows, including when the main browser is minimized. Falls back to a regular popup on unsupported browsers
- **Pre-start countdown** — a 10-second idle countdown before the activity timer begins, with a prompt to start your activity at zero. Can be skipped with the Skip Countdown toggle
- **Live item tracking** — shows each item's quantity, estimated done count, and remaining, updated every second
- **Simulated double-up** — if a double-up chance is set, the session is pre-simulated so the done count realistically jumps by 1 or 2 per action rather than using a smooth average. Bank trips are also simulated
- **Progress bar** — visual fill with percentage complete shown below the table
- **Collapse** — shrink the overlay to just the timer with the − button; expand back with +
- **Reset** — returns the overlay to the idle state without closing it
- **Session persistence** — if you close the overlay mid-session (e.g. via Back to Tab) and reopen it, the timer resumes from where it left off including real elapsed time. State clears automatically on page refresh, new calculation, or browser close

---

## XP Formula

Microscape uses a scaled version of the classic OSRS XP formula:

$$\text{TotalXP}(L) = \left\lfloor \frac{\sum_{n=1}^{L-1} \left\lfloor 10(n + 300 \cdot 2^{n/7}) \right\rfloor}{4} \right\rfloor$$

This gives the cumulative XP required to reach level `L`. XP needed for a given level is `TotalXP(L+1) - TotalXP(L)`.
