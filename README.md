# Fuel Tracker

A single-file, browser-based fuel log for tracking fill-ups, MPG, fuel cost trends, and vehicle-specific history.

## Live Site

**[🌐 Open on GitHub Pages](https://rickytann14.github.io/fuel-tracker/)**

## What It Does

- Track fill-ups with date, vehicle, odometer, gallons, price per gallon, and total cost.
- Auto-calculate one of `price/gallons/total` when the other two are entered.
- Compute MPG when possible, with an option to skip MPG for first/missed fill-ups.
- Filter by vehicle, year, and date range.
- View a simplified Stats area with separate Summary and Charts subtabs.
- Bulk-assign a vehicle to selected history records.
- Save/load data using JSON files.
- Export PDF reports.

## Data Storage

- Fill-up data is stored in browser `localStorage` key: `fuelTrackerData`.
- Vehicle list is stored in browser `localStorage` key: `fuelTrackerVehicles`.

## How To Use

1. Open `fuel-tracker-fixed.html` in a browser.
2. Add a vehicle (or select an existing one).
3. Enter fill-up details and submit.
4. Use header filters to view specific vehicles/years/date ranges.

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
	- Avg $/Gallon
	- Last Price Paid
	- Total Spent
	- Total Miles
- `Charts`
	- MPG Over Time
	- Monthly Spending Trends
	- Cost per Gallon Trend

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

### Header Filters

- Vehicle filter
- Year filter

### Advanced Filters

- Start Date
- End Date

## Vehicle Management

- Add vehicles from the Add Fill-up tab.
- Open `Manage Vehicles` to delete vehicles.
- When deleting a vehicle that is assigned to records, you can remove it from those records as part of deletion.

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
