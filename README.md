# Microscape XP & Item Calculator

A browser-based calculator for planning your training in [Microscape](https://www.microscape.com). Enter your current level, goal level, and the items you plan to craft — it tells you exactly how many to make and the total XP contribution of each.

**[Open Calculator](https://ji33my.github.io/Microscape-Exp-Calculator/microscape_calculator.html)**

---

## Features

- **XP calculation** — accurate XP requirements for any level range using the verified Microscape XP formula
- **Primary item** — the main thing you're crafting toward your goal
- **Chain item** — for when your primary item is used as an ingredient in a second craft (e.g. smelt Steel Bars → smith Steel Arrowtips). Supports an optional qty goal if you only need a set number
- **Items with qty goals** — side items you want a fixed quantity of (e.g. Silver Bars), done first before the primary
- **Qty owned** — account for stock you already have; the calculator factors it in and adjusts what's left to craft
- **Material cost** — optional gold cost per craft. Shows total cost and gp/xp across all items
- **Saved presets** — save your current setup by name and switch between them with one click. Persists across sessions
- **XP table** — view cumulative XP and XP-to-next for every level from 1 to 99

## XP Formula

Microscape uses a scaled version of the classic OSRS XP formula:

$$\text{TotalXP}(L) = \left\lfloor \frac{\sum_{n=1}^{L-1} \left\lfloor 10(n + 300 \cdot 2^{n/7}) \right\rfloor}{4} \right\rfloor$$

This gives the cumulative XP required to reach level `L`. XP needed for a given level is `TotalXP(L+1) - TotalXP(L)`.

## Usage

1. Enter your **current level**, **goal level**, and **% through your current level** (shown in-game on the skill panel)
2. Fill in your **primary item** — the item you'll be mass-crafting for XP
3. Optionally add a **chain item** if your primary is consumed as an ingredient in a follow-up craft
4. Optionally add **items with qty goals** for any fixed-quantity crafts you want to do first
5. Hit **Calculate**

Results show exactly how many of each item to craft, XP contributed, and total material cost if prices are entered.
