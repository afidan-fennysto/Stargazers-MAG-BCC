# Stargazers-MAG-BCC

This is our proposed solution for our given study case: **MH SmartOffer**, an AI-driven ancillary offer engine for Malaysia Airlines (MAG Business Case Challenge, Case Study 9).

## MH SmartOffer — Before vs. After Dashboard (Power BI)

A one-page executive dashboard comparing the **Old Way (Static)** offers with **With Our AI System**, and the full-year profit case for Malaysia Airlines.

| Path | What it is |
|---|---|
| `MH_SmartOffer.pbip` | Open this in Power BI Desktop |
| `MH_SmartOffer.SemanticModel/` | Data model in TMDL (tables, Power Query, DAX measures) |
| `MH_SmartOffer.Report/` | Report in PBIR format and the custom theme (`StaticResources/RegisteredResources/MH_SmartOffer_Theme.json`) |
| `data/` | The two source CSVs |

### Open it in Power BI Desktop (Windows)

1. **Enable the project format (one time).** Open Power BI Desktop → *File → Options and settings → Options → Preview features*. Tick **Power BI Project (.pbip) save option**, **Store semantic model using TMDL format** and **Store reports using enhanced metadata format (PBIR)**. Restart Power BI Desktop.
2. **Open and refresh.** Download or clone this repo, then *File → Open* → `MH_SmartOffer.pbip`. Click **Refresh** on the ribbon (Home → Refresh) to load the data.
   - The queries read the CSVs from the `DataFolder` parameter (default `C:\MH_SmartOffer\data`). To use your own copy, go to *Home → Transform data → Edit parameters* and point it at this repo's `data` folder.
   - If the CSVs are not found, each query uses the same data embedded in it, so the report still loads.
3. **Save as .pbix (optional).** *File → Save as* → set *Save as type* to **Power BI file (*.pbix)** → Save. Share or submit the `.pbix`.

### Page layout

1. **Header and slicers:** Route Type, Passenger Type, Profit Scenario (Safe | Normal | Best; Normal Case when nothing is selected)
2. **See the Difference:** Buyers %, Spend per Passenger and CSI, Old Way vs. AI, with the lift
3. **Full-Year Profit:** Extra Sales → Gross Profit (75%) → Year-1 Cost → Year-1 Net Profit
4. **Charts:** spend by passenger type; bundle vs. single add-on (AI group)
5. **Table:** all 8 metrics MAG's data team tracks, per group

KPIs use `AVERAGE` across segments, so they never add up across rows. Profit cards show one scenario at a time.
