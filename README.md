# Fuel Tracker

A single-file, browser-based fuel log for tracking fill-ups, MPG, fuel cost trends, and vehicle-specific history.

> Mostly vibe coded with [Claude Code](https://claude.ai/code). 🤖⛽

## Live Site

**[🌐 Open on GitHub Pages](https://rickytann14.github.io/fuel-tracker/)**

## What It Does

- Track fill-ups with date, vehicle, odometer, gallons, price per gallon, and total cost.
- Auto-calculate one of `price/gallons/total` when the other two are entered.
- Compute MPG when possible, with an option to skip MPG for first/missed fill-ups.
- Filter by vehicle, year, and month — tap to apply instantly, no "Done" button needed.
- View a Stats area with Summary cards and an interactive Charts tab.
- Bulk-assign a vehicle to selected history records.
- Save/load data using JSON files.
- Export PDF reports.

## Data Storage

- Fill-up data is stored in browser `localStorage` key: `fuelTrackerData`.
- Vehicle list is stored in browser `localStorage` key: `fuelTrackerVehicles`.

## How To Use

1. Open `index.html` in a browser (or visit the live site).
2. Add a vehicle (or select an existing one).
3. Enter fill-up details and submit.
4. Use the header filters to view specific vehicles, years, or months.

## Tabs

### Add Fill-up

- Enter:
	- Vehicle
	- Date
	- Price per Gallon
	- Gallons
	- Total Cost
	- Odometer
- Optional: check `First fill-up or missed a fill-up` to skip MPG calculation.

### Statistics

Statistics are split into subtabs:

- `Summary`
	- Avg MPG
	- Last MPG
	- Best MPG / Worst MPG
	- Avg $/Gallon
	- Last Price Paid
	- Total Spent
	- Total Miles
	- Cost per Mile
- `Charts`
	- MPG Over Time
	- Monthly Spending
	- Cost per Gallon
	- Gallons per Fill-up
	- Total Cost per Fill-up
	- Cost per Mile
	- Miles per Fill-up
	- Year-over-Year MPG (multi-line, one line per year)
	- **Smooth toggle** — collapses per-fill-up charts into monthly averages/sums

### History

- Shows filtered fill-up records.
- Supports per-record `Edit` and `Delete`.
- Supports multi-select with:
	- `Select All`
	- `Assign Vehicle` for selected records
- Includes three data actions:
	- `Save` (export JSON)
	- `Load` (import JSON)
	- `Export to PDF`

## Filters

Tap any filter value to apply it instantly — no confirmation needed.

- Vehicle filter
- Year filter (defaults to most recent year)
- Month filter

## Vehicle Management

- Add vehicles from the Add Fill-up tab.
- Open `Manage Vehicles` to delete vehicles.
- When deleting a vehicle assigned to records, you can remove it from those records as part of deletion.

## Save, Load, and Export

### Save (JSON)

- Exports current vehicles and fill-ups to a `.json` file.

### Load (JSON)

- Loads data from a `.json` file.
- Accepts either:
	- an object with `fillUps` (and optional `vehicles`), or
	- a raw fill-up array.
- Replaces current in-app data after confirmation.

### Export to PDF

- Exports a filtered summary report and recent fill-ups to PDF.

## Notes

- MPG depends on odometer progression and valid previous entries.
- For multi-vehicle datasets, verify odometer continuity per vehicle when reviewing MPG-heavy analysis.
