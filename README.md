# Sankey Chart Builder — Excel Add-In
 
An Office Add-in that renders live, interactive Sankey flow charts directly
from your Excel data. Supports unlimited levels, 6 color themes, dollar/
percent formatting, and horizontal or vertical layout.
 
---
 
## Quick Start (GitHub Pages — Recommended)
 
This is the easiest deployment method. No local server needed.
 
### Step 1 — Host the files on GitHub Pages
 
1. Create a new **public** GitHub repository (e.g. `sankey-addin`)
2. Upload all three files into the repo root:
   - `taskpane.html`
   - `commands.html`
   - `manifest.xml`
3. Go to **Settings → Pages → Source → Deploy from branch → main → / (root)**
4. GitHub will give you a URL like:
   `https://YOUR-USERNAME.github.io/sankey-addin/`
5. Open `manifest.xml` and replace every instance of
   `YOUR-GITHUB-USERNAME` with your actual GitHub username.
   Commit and push.
 
### Step 2 — Sideload the add-in into Excel
 
**Mac:**
1. In Excel: **Tools → Excel Add-ins → Manage: Excel Add-ins → Go**
2. Click **Browse** and locate `manifest.xml` on your computer
3. Check the box next to "Sankey Chart Builder" → OK
 
**Windows:**
1. Copy `manifest.xml` to a shared network folder or your Desktop
2. In Excel: **File → Options → Trust Center → Trust Center Settings →
   Trusted Add-in Catalogs**
3. Add the folder path, check "Show in Menu" → OK → restart Excel
4. Insert → My Add-ins → Shared Folder → Sankey Chart Builder
 
Once loaded, click **"Sankey Chart Builder"** in the Home ribbon.
 
---
 
## How to Use
 
### 1. Set up your data table
 
| A (From)   | B (To)       | C (Value)  |
|------------|--------------|------------|
| Medicare   | Pain Mgmt    | 1200000    |
| Medicaid   | Pain Mgmt    | 450000     |
| BCBS       | Ortho        | 875000     |
| Pain Mgmt  | Redefine NJ  | 980000     |
| Ortho      | Mercer Bucks | 740000     |
 
- **From**: source node name
- **To**: target node name  
- **Value**: a positive number (commas and $ signs are stripped automatically)
- Include a header row — it's skipped automatically
- Repeat node names freely to create multi-level flows
 
### 2. Capture your range
 
1. Highlight your table (including the header row) in Excel
2. In the task pane → **① Data tab** → click **📌 Capture**
 
### 3. Style your chart (optional)
 
In the **② Style tab**:
- Set a chart title
- Choose Horizontal or Vertical orientation
- Pick a color theme (Ocean, Sunset, Violet, Emerald, Slate, Coral)
- Set value format: plain number, $dollar, or %percent
- Adjust node thickness and padding
 
### 4. Render
 
Click **⟁ Render Chart** from either the Data or Style tab.  
Switch to the **③ Chart tab** to see your Sankey.  
Click **↻** in the chart toolbar anytime to re-read Excel data and refresh.
 
---
 
## Multi-Level Flows
 
The chart automatically infers node levels from your data. Just chain rows:
 
```
Payer A   → Service Line 1 → Entity 1 → Region
Payer B   → Service Line 1 → Entity 2 → Region
Payer C   → Service Line 2 → Entity 1 → Region
```
 
No configuration needed — Plotly's Sankey engine handles the layout.
 
---
 
## Local Dev (Optional)
 
If you want to run locally instead of GitHub Pages:
 
```bash
npm install -g office-addin-dev-certs http-server
office-addin-dev-certs install
http-server . --ssl --cert ~/.office-addin-dev-certs/localhost.crt --key ~/.office-addin-dev-certs/localhost.key -p 3000
```
 
Then update manifest.xml URLs to `https://localhost:3000/taskpane.html`
and sideload as above.
 
---
 
## Files
 
| File            | Purpose                                      |
|-----------------|----------------------------------------------|
| `taskpane.html` | The full add-in UI and charting logic        |
| `manifest.xml`  | Tells Excel about the add-in                 |
| `commands.html` | Required stub file for the ribbon button     |
| `README.md`     | This file                                    |
 
