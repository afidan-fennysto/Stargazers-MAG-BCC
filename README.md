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

The data rows (same as `data/*.csv`) are stored inside the Power Query queries, so the model refreshes in the Power BI web service with no gateway or credentials.

### Open it in the browser (Mac friendly): Fabric Git integration

Needs a work or school Microsoft account (personal Gmail/Outlook accounts can't sign in to Power BI) and a Fabric trial.

1. Sign in at https://app.powerbi.com. Start the free trial: **profile picture (top right) → Start trial** (Fabric trial).
2. **Workspaces → + New workspace**, name it `Stargazers MAG-BCC`. Under **Advanced → License mode**, pick **Trial** (Fabric capacity). Apply.
3. Workspace **Settings → Git integration → GitHub → Add account**. Paste a GitHub personal access token with access to this repo, and the URL `https://github.com/afidan-fennysto/Stargazers-MAG-BCC`. Choose branch `main`, leave the Git folder empty (root). **Connect and sync.**
4. `MH_SmartOffer` (semantic model) and `MH_SmartOffer` (report) appear in the workspace. Open the **semantic model → Refresh now**, wait for it to finish, then open the **report**.

### Open it in Power BI Desktop (Windows)

1. *File → Options and settings → Options → Preview features*: tick **Power BI Project (.pbip) save option**, **Store semantic model using TMDL format** and **Store reports using enhanced metadata format (PBIR)**. Restart.
2. *File → Open* → `MH_SmartOffer.pbip`, then **Home → Refresh**.
3. Optional: *File → Save as* → **Power BI file (*.pbix)**.

### Page layout

1. **Header and slicers:** Route Type, Passenger Type, Profit Scenario (Safe | Normal | Best; Normal Case when nothing is selected)
2. **See the Difference:** Buyers %, Spend per Passenger and CSI, Old Way vs. AI, with the lift
3. **Full-Year Profit:** Extra Sales → Gross Profit (75%) → Year-1 Cost → Year-1 Net Profit
4. **Charts:** spend by passenger type; bundle vs. single add-on (AI group)
5. **Table:** all 8 metrics MAG's data team tracks, per group

KPIs use `AVERAGE` across segments, so they never add up across rows. Profit cards show one scenario at a time.
