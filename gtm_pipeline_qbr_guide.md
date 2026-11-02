# Task 3 Master Guide (`GTM`): Q4 SaaS Enterprise Deal Desk Pricing, Discount & Gross Margin Audit

---

## Why This Task 3 Workflow Is 100% Distinct from Task 2 & AutoQC-Safe
1. **Zero Overlap with Task 2's Operations:**
   - Instead of Task 2's `Remove duplicates` + `FILTER` + `COUNTIFS`, this workflow uses **`VLOOKUP` (cross-table pricing lookup)**, **Gross Margin & Discount math**, **Format → Conditional formatting**, **Insert → Pivot table**, and **Data → Add a slicer** in Google Sheets, paired with **Google Slides** (instead of Google Docs).
2. **Ultra-Low Typing Share (`~11–13%` vs. `25%` Limit):**
   - Uses whole-column `VLOOKUP` (`Product_Catalog!A:F`—zero `$` signs needed!), 1-word column headers (`Price`, `Unit_COGS`, `Net_ARR`, `COGS`, `Margin`, `Status`), and 90% mouse-driven GUI features (`Conditional formatting`, `Pivot table`, `Data slicer`, `Chart`, and **Google Slides** with three 7-word bullets).
3. **100% Mathematical Validation Completed:**
   - Every single order, margin breach row (`Rows 6, 7, 13, 19, 21, and 23`), SKU total, Region total, and portfolio total (`$18,154,820` Net ARR, `$5,205,350` COGS, `71.33%` weighted / `72.15%` simple avg margin) has been verified and locked into **Part 4** and **Part 5** below.
   - Your starting Excel workbook is also saved locally at [`/Users/b0a07w6/Downloads/Q4_Deal_Desk_Margin_Audit.xlsx`](file:///Users/b0a07w6/Downloads/Q4_Deal_Desk_Margin_Audit.xlsx) (`Deal_Orders` and `Product_Catalog` tabs).

---

## Part 1: Step-by-Step Studio Idea Submission & Approval

### How to Fill Out Section `1.0 Create your idea` in Studio
1. Click **Create task** in Studio (`Odin Production Full Workflow`).
2. Scroll to **1.0 Create your idea → Describe your Idea**.
3. **Important:** Type the 5 sections below **in your own words** (never copy-paste directly into Studio's text box):

   - **`Domain / Role:`**
     - Write: Revenue Operations & Deal Desk Pricing Lead (`GTM` — Marketing; Sales & Biz Dev).
   - **`Goal:`** *(Keep a copy of the exact text you type here—once approved, this exact paragraph goes into your Opening Goal Document, TaskRecorder's Task Description box, and `Metadata.rtf`!)*
     - Paraphrase this in your own words:
       *As a Deal Desk & Revenue Operations Lead, I need to conduct a Q4 SaaS Enterprise Deal Desk Pricing, Discount, and Gross Margin Audit for executive leadership. Using our Q4 Deal Desk Pricing workbook (`Deal_Orders` and `Product_Catalog` sheets) in Google Sheets, I will pull unit list prices and hosting costs from the product catalog into the 30-order log using `VLOOKUP`, calculate net ARR, total hosting COGS, and gross margin percentage after sales discounts, apply conditional formatting to flag unauthorized over-discounted deals that breach our 65% gross margin floor, build a Pivot Table and interactive Region Data Slicer to analyze `$18.15M` in Net ARR and average margin across `SKU-101` through `SKU-105`, and compile a 3-slide Executive Deal Desk Pricing & Margin Review deck in Google Slides exported as a PDF.*
   - **`Starting materials:`**
     - Paraphrase this in your own words:
       *Synthetic starting workbook (`Q4_Deal_Desk_Margin_Audit.xlsx`, or its two source CSVs `input 1.csv` and `input 2.csv`) prepared with Gemini prior to recording, containing: (1) `Deal_Orders` (30 enterprise SaaS orders `ORD-301` to `ORD-330` across anonymized customers `Test Client 1`–`30`, sales reps `Person 1`–`4`, and 4 regions `North America`, `EMEA`, `APAC`, `LATAM`, listing `SKU_Code`, `Seats`, and `Discount_Pct`); and (2) `Product_Catalog` (5 SaaS SKU tiers `SKU-101` to `SKU-105` listing `Product_Name`, `List_Price_USD` from `$100` to `$500`, `Unit_COGS_USD` from `$25` to `$100`, `Max_Discount_Pct` of `20%`, and `Margin_Floor_Pct` of `65%`).*
   - **`Steps (with the apps for each):`**
     - Paraphrase these 2 app bullets in your own words:
       - *Google Sheets:* Open the Q4 Deal Desk Pricing workbook (`Deal_Orders` and `Product_Catalog`), use `VLOOKUP` to pull each order's unit `Price` and `Unit_COGS` from `Product_Catalog`, calculate `Net_ARR`, `COGS`, `Margin` (`%`), and `Status` (`Approved` vs. `Breach` against the `65%` floor), apply `Conditional formatting` to highlight the 6 breaching orders in red, create a mouse-driven `Pivot Table` and an interactive `Data Slicer` (`Data → Add a slicer`) plus a bar chart comparing Net ARR across `SKU-101` to `SKU-105`, and export the completed workbook as `.xlsx`.
       - *Google Slides:* Open the 3-slide Q4 Deal Desk Pricing & Margin Review Deck, embed the linked SKU Net ARR chart and Pivot summary table from Google Sheets on Slide 2, add the 3 executive audit takeaways and Q1 discount guardrails on Slide 3, and export the presentation deck as a `.pdf`.
   - **`Deliverable:`**
     - Paraphrase this in your own words:
       *1. The completed multi-tab SaaS Deal Desk Pricing & Margin Audit workbook exported from Google Sheets as an Excel file (`final output 1.xlsx`).*
       *2. The 3-slide Executive Deal Desk Pricing & Margin Review deck exported from Google Slides as a PDF (`final output 2.pdf`).*

4. **Select Apps in Studio's `Used Apps` Dropdown:**
   - Select **`Google Sheets`** and **`Google Slides`**.
5. Click **Submit idea** and wait for approval before moving to the recording phase.

---

## Part 2: Complete 3-Hour (`180-Minute`) End-to-End Time Plan

| Time Window | Duration | Phase | What You Actively Do |
|---|---:|---|---|
| **0:00 – 0:25** | `25 min` | **1. Ideation & Studio Idea Submission** | Review the GTM guidelines, run **Prompt 1** with Gemini to design the 5-tier SaaS SKU catalog and 65% gross margin floor, and type your 5-part idea into Studio's **Describe your Idea** in your own words. |
| **0:25 – 1:10** | `45 min` | **2. Interactive Dataset Generation & Math Audit with Gemini** | Run **Prompts 2–4** with Gemini to generate `Product_Catalog` (5 rows) and `Deal_Orders` (30 rows), verify the 6 margin breach orders and `$18,154,820` Net ARR Pivot totals, and save `Q4_Deal_Desk_Margin_Audit.xlsx`. |
| **1:10 – 1:45** | `35 min` | **3. Scratch Dry-Run in Google Sheets & Slides** | Practice the workflow once in a scratch Google Sheet (`VLOOKUP`, margin math, `Format → Conditional formatting`, `Insert → Pivot table`, `Data → Add a slicer`, Chart, and pasting into Google Slides) so your mouse actions are smooth on camera. |
| **1:45 – 2:00** | `15 min` | **4. Desktop Appearance Change & Pre-Recording Setup** | Change your macOS Wallpaper + toggle Light/Dark mode + change Accent Color + adjust Dock size (Task Variety requirement). Set up Window 1 (Opening Goal Document in Google Docs) and Window 2 (Tab 1: Google Sheets, Tab 2: Google Slides with 3 pre-titled slides), then minimize Window 2. |
| **2:00 – 2:25** | `25 min` | **5. Actual Video Recording (In TaskRecorder)** | Record the complete 21–24 minute workflow and 3-minute Epilogue in one uninterrupted take using the verbatim What/Where/Why script in Part 5. |
| **2:25 – 3:00** | `35 min` | **6. Verification, `Deliverables.zip`, `Metadata.rtf` & AutoQC** | Spot-check `video.mp4` and `screenshots/`, package `Deliverables.zip`, fill out `Metadata.rtf`, upload all 4 files to Studio, verify AutoQC passes with 0 required findings, and submit. |

---

## Part 3: Exact Validated Data & Mathematical Reference

### 1. `Product_Catalog` (`Rows 2–6`)

| Row | `SKU_Code` (`A`) | `Product_Name` (`B`) | `List_Price_USD` (`C`) | `Unit_COGS_USD` (`D`) | `Max_Discount_Pct` (`E`) | `Margin_Floor_Pct` (`F`) | Baseline Margin | Margin @ 20% Cap |
|---:|---|---|---:|---:|---:|---:|---:|---:|
| **2** | `SKU-101` | Core Platform | `$100` | `$25` | `20%` (`0.20`) | `65%` (`0.65`) | `75.0%` | `68.8%` |
| **3** | `SKU-102` | Analytics Pro | `$200` | `$40` | `20%` (`0.20`) | `65%` (`0.65`) | `80.0%` | `75.0%` |
| **4** | `SKU-103` | Security Suite | `$300` | `$75` | `20%` (`0.20`) | `65%` (`0.65`) | `75.0%` | `68.8%` |
| **5** | `SKU-104` | AI Copilot | `$400` | `$100` | `20%` (`0.20`) | `65%` (`0.65`) | `75.0%` | `68.8%` |
| **6** | `SKU-105` | Enterprise Governance | `$500` | `$100` | `20%` (`0.20`) | `65%` (`0.65`) | `80.0%` | `75.0%` |

### 2. Exact 6 Margin Breach Rows in `Deal_Orders` (`Margin < 65.0%`)

| Sheet Row | `Order_ID` (`A`) | `Client_Name` (`C`) | `Sales_Rep` (`D`) | `Region` (`E`) | `SKU_Code` (`F`) | `Seats` (`G`) | `Discount_Pct` (`H`) | `Net_ARR` (`K`) | `COGS` (`L`) | `Margin` (`M`) | `Status` (`N`) |
|---:|---|---|---|---|---|---:|---:|---:|---:|---:|---|
| **Row 6** | `ORD-305` | `Test Client 5` | `Person 1` | `EMEA` | `SKU-104` | `1,750` | **`31%`** | `$483,000` | `$175,000` | **`63.77%`** | `Breach` |
| **Row 7** | `ORD-306` | `Test Client 6` | `Person 2` | `LATAM` | `SKU-104` | `4,350` | **`39%`** | `$1,061,400` | `$435,000` | **`59.02%`** | `Breach` |
| **Row 13** | `ORD-312` | `Test Client 12` | `Person 2` | `APAC` | `SKU-101` | `2,720` | **`42%`** | `$157,760` | `$68,000` | **`56.90%`** | `Breach` |
| **Row 19** | `ORD-318` | `Test Client 18` | `Person 4` | `EMEA` | `SKU-104` | `3,850` | **`34%`** | `$1,016,400` | `$385,000` | **`62.12%`** | `Breach` |
| **Row 21** | `ORD-320` | `Test Client 20` | `Person 2` | `EMEA` | `SKU-103` | `920` | **`31%`** | `$190,440` | `$69,000` | **`63.77%`** | `Breach` |
| **Row 23** | `ORD-322` | `Test Client 22` | `Person 2` | `EMEA` | `SKU-104` | `4,880` | **`36%`** | `$1,249,280` | `$488,000` | **`60.94%`** | `Breach` |

- **Key Pattern to Narrate:**
  - **4 of the 6 breaches** (`ORD-305`, `ORD-306`, `ORD-318`, `ORD-322` totaling `$3,810,080` in breached Net ARR) occurred on **`SKU-104` (`AI Copilot`, `$100`/seat COGS)** when reps gave `31%–39%` discounts!
  - **4 of the 6 breaches** (`ORD-305`, `ORD-318`, `ORD-320`, `ORD-322`) occurred in **`EMEA`**, and **4 of the 6 breaches** were discounted by **`Person 2`**.

### 3. Exact Pivot Table Totals by `SKU_Code` (and by `Region`)

#### Pivot Table by `SKU_Code` (Rows: `SKU_Code`, Values: `Order_ID` (`COUNTA`), `Net_ARR` (`SUM`), `Margin` (`AVERAGE`))
| `SKU_Code` | Orders (`COUNTA`) | Total `Net_ARR` (`SUM`) | Avg `Margin` (`AVERAGE`) | Breach Count |
|---|---:|---:|---:|---:|
| **`SKU-101`** (Core Platform) | `6` | **`$1,136,640`** | **`70.25%`** | `1` (`ORD-312`) |
| **`SKU-102`** (Analytics Pro) | `8` | **`$3,493,540`** | **`78.02%`** | `0` |
| **`SKU-103`** (Security Suite) | `6` | **`$4,383,660`** | **`70.92%`** | `1` (`ORD-320`) |
| **`SKU-104`** (AI Copilot) | `8` | **`$8,455,480`** | **`66.90%`** | `4` (`ORD-305, 306, 318, 322`) |
| **`SKU-105`** (Enterprise Gov) | `2` | **`$685,500`** | **`79.03%`** | `0` |
| **Grand Total / Portfolio** | **`30`** | **`$18,154,820`** | **`72.15%`** *(simple avg)* / **`71.33%`** *(weighted)* | **`6`** (`$4,158,280` breached Net ARR) |

#### When Filtered by `Region` Using the Data Slicer (`Data → Add a slicer`)
| `Region` | Orders | Total `Net_ARR` | Avg `Margin` | Breaches |
|---|---:|---:|---:|---:|
| **`APAC`** | `4` | `$2,008,730` | `69.64%` | `1` (`ORD-312`) |
| **`EMEA`** | `12` | `$7,266,760` | `70.75%` | `4` (`ORD-305, 318, 320, 322`) |
| **`LATAM`** | `9` | `$5,866,180` | `74.55%` | `1` (`ORD-306`) |
| **`North America`** | `5` | `$3,013,150` | `73.18%` | `0` |

---

## Part 4: AutoQC-Hardened Minute-by-Minute Recording Script (`21–24 Minutes`, `< 13%` Typing)

### Pre-Recording Setup Checklist (Do Not Skip!)
1. **Change Your Mac UI First (Mandatory Between Every Task!):**
   - `System Settings → Wallpaper`: Pick a **new wallpaper** (different from macOS default, Task 1, and Task 2).
   - `System Settings → Appearance`: Toggle **Light/Dark mode** and pick a **new Accent Color**.
   - Leave a thin strip of desktop wallpaper visible around your Chrome window.
2. **Window 1 (Google Docs — Opening Goal Doc):**
   - Open a Chrome window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder.
3. **Window 2 (Google Sheets & Google Slides — Main Workspace):**
   - Open a separate Chrome window with two tabs:
     - **Tab 1 (Google Sheets):** Upload and open `/Users/b0a07w6/Downloads/Q4_Deal_Desk_Margin_Audit.xlsx` as a Google Sheet (`Deal_Orders` and `Product_Catalog`).
     - **Tab 2 (Google Slides):** Create a presentation titled `Q4 Deal Desk Pricing & Margin Review` with **3 pre-titled slides** before recording:
       - **Slide 1 (Title Slide):** Title pre-typed as `Q4 2026 SaaS Deal Desk Pricing & Margin Audit` and Subtitle `Revenue Operations Executive Review`.
       - **Slide 2 (Title Only layout):** Title pre-typed as `SKU Net ARR & Gross Margin Performance`.
       - **Slide 3 (Title and Body layout):** Title pre-typed as `Deal Desk Policy Findings & Q1 Guardrails`.
   - **Minimize Window 2** using the yellow Minimize button (`-`) in the top-left corner before starting TaskRecorder!

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open Google Sheets from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click the minimized **Google Sheets** window in the Dock.

---

### SECTION B: Inspect `Product_Catalog` & `Deal_Orders` with the Mouse (`00:20 – 03:30`)

1. **Speak, then click `Product_Catalog` (~35s of mouse inspection):**
   > 🎤 "In the bottom-left sheet tab bar of Google Sheets, I will first click the `Product_Catalog` tab to review our five SaaS products from `SKU-101` (`Core Platform`) on row 2 through `SKU-105` (`Enterprise Governance`) on row 6. Looking across columns C through F in the center grid, each SKU has a fixed annual list price per seat (`$100` to `$500`), a fixed annual hosting and compute COGS per seat (`$25` to `$100`), a maximum Deal Desk approved discount cap of `20%` (`0.20`) in column E, and a strict `65%` (`0.65`) gross margin floor in column F."
2. **Action:** Click `Product_Catalog` and point across `A2:F6` with your mouse.
3. **Speak, then click `Deal_Orders` and scroll down with the mouse (~45s of mouse inspection):**
   > 🎤 "Now in the bottom sheet tab bar, I will click the `Deal_Orders` tab, which contains thirty Q4 enterprise orders from `ORD-301` on row 2 down to `ORD-330` on row 31 across `Test Client 1` through `Test Client 30` and sales reps `Person 1` through `Person 4`. Scrolling down column H (`Discount_Pct`) with the mouse, notice that while most orders stayed within the `20%` discount cap, several orders—such as `ORD-305` on row 6 (`31%`), `ORD-306` on row 7 (`39%`), `ORD-312` on row 13 (`42%`), `ORD-318` on row 19 (`34%`), `ORD-320` on row 21 (`31%`), and `ORD-322` on row 23 (`36%`)—received deep discounts above `30%`. Let's scroll back up to row 1 to calculate each deal's unit economics."
4. **Action:** Click `Deal_Orders`, scroll down `A2:H31` with the mouse, and scroll back up to row 1.

---

### SECTION C: Pull Catalog Prices via `VLOOKUP` & Compute Gross Margin (`03:30 – 09:30`)

1. **Speak, then type the 6 short 1-word headers in `I1:N1` (~10s):**
   > 🎤 "In row 1 of `Deal_Orders`, starting at cell I1, I will type our six 1-word calculated column headers using Tab: `Price` in I1, `Unit_COGS` in J1, `Net_ARR` in K1, `COGS` in L1, `Margin` in M1, and `Status` in N1."
2. **Action:** Type `Price` (`I1`), `Unit_COGS` (`J1`), `Net_ARR` (`K1`), `COGS` (`L1`), `Margin` (`M1`), and `Status` (`N1`).
3. **Speak, then type `VLOOKUP` for `Price` in `I2` (~14s):**
   > 🎤 "In cell I2 on row 2 of `Deal_Orders`, I will type `=VLOOKUP(F2, Product_Catalog!A:F, 3, FALSE)` and press Enter to pull the annual list price per seat for `SKU-103` (`$300`) from column 3 of `Product_Catalog`, and I will accept the autofill down to row 31."
4. **Action:** Type `=VLOOKUP(F2, Product_Catalog!A:F, 3, FALSE)` in `I2`, press **Enter**, and fill down to `I31`.
5. **Speak, then type `VLOOKUP` for `Unit_COGS` in `J2` (~14s):**
   > 🎤 "In cell J2 on row 2, I will type `=VLOOKUP(F2, Product_Catalog!A:F, 4, FALSE)` and press Enter to pull the fixed unit COGS per seat (`$75` for `SKU-103`) from column 4 of `Product_Catalog`, then fill down to J31."
6. **Action:** Type `=VLOOKUP(F2, Product_Catalog!A:F, 4, FALSE)` in `J2`, press **Enter**, and fill down to `J31`.
7. **Speak, then type `Net_ARR` formula in `K2` (~10s):**
   > 🎤 "In cell K2, I will type `=G2*I2*(1-H2)` and press Enter to calculate net annual recurring revenue after multiplying seats in G2 by list price in I2 and deducting the rep's discount percentage in H2, then fill down to K31."
8. **Action:** Type `=G2*I2*(1-H2)` in `K2`, press **Enter**, and fill down to `K31` (row 2 shows `776,160`).
9. **Speak, then type `COGS` formula in `L2` (~8s):**
   > 🎤 "In cell L2, I will type `=G2*J2` and press Enter to compute total hosting COGS for the order by multiplying seats in G2 by unit COGS in J2, then fill down to L31."
10. **Action:** Type `=G2*J2` in `L2`, press **Enter**, and fill down to `L31` (row 2 shows `220,500`).
11. **Speak, then type `Margin` formula in `M2` (~10s):**
    > 🎤 "In cell M2, I will type `=(K2-L2)/K2` and press Enter to calculate the order's gross margin percentage, fill down to M31, and click the `Format as percent (%)` button in the top toolbar."
12. **Action:** Type `=(K2-L2)/K2` in `M2`, fill down to `M31`, and click **`%`** in the top toolbar (row 2 shows `71.59%`).
13. **Speak, then type `Status` formula in `N2` (~12s):**
    > 🎤 "In cell N2, I will type `=IF(M2<0.65, \"Breach\", \"Approved\")` and press Enter to flag any order whose gross margin falls below our `65%` floor as `Breach`, then fill down to N31."
14. **Action:** Type `=IF(M2<0.65, "Breach", "Approved")` in `N2`, press **Enter**, and fill down to `N31`.

---

### SECTION D: Highlight the 6 Breaches via Conditional Formatting (`09:30 – 12:00`)

*(100% mouse-driven GUI formatting + inspection!)*

1. **Speak, then apply Conditional Formatting to `N2:N31`:**
   > 🎤 "To visually spotlight the margin breaches across the thirty orders, I will select cells `N2` through `N31` with the mouse, click `Format` in the top menu bar of Google Sheets, and click `Conditional formatting` in the dropdown menu."
2. **Action:** Select `N2:N31` and click **Format → Conditional formatting**.
3. **Speak, then configure the rule in the right sidebar:**
   > 🎤 "In the Conditional format rules sidebar on the right side of the screen, under `Format cells if`, I will click the dropdown menu, select `Text is exactly`, type `Breach` in the value box, select the light red fill style, and click the green `Done` button."
4. **Action:** Set **Text is exactly** → `Breach`, choose light red fill, click **Done**, and close the sidebar (`X`).
5. **Speak while scrolling down `Deal_Orders` with the mouse to inspect the 6 red `Breach` rows (~40s):**
   > 🎤 "Scrolling down columns F through N with the mouse, we can verify the six highlighted `Breach` orders:
   > - On **row 6**, `ORD-305` (`Person 1`, `EMEA`, `SKU-104`) has a `31%` discount, dropping margin to `63.77%`.
   > - On **row 7**, `ORD-306` (`Person 2`, `LATAM`, `SKU-104`) has a `39%` discount on `$1,061,400` Net ARR, dropping margin to `59.02%`.
   > - On **row 13**, `ORD-312` (`Person 2`, `APAC`, `SKU-101`) has a `42%` discount, dropping margin to `56.90%`.
   > - And on **rows 19, 21, and 23**, `ORD-318` (`62.12%`), `ORD-320` (`63.77%`), and `ORD-322` (`60.94%`) all breached in `EMEA` due to `31%` to `36%` discounts."

---

### SECTION E: Build Mouse-Driven Pivot Table, Interactive Slicer & Chart (`12:00 – 17:15`)

*(Zero typing in this entire 5-minute section—pure mouse clicks!)*

1. **Speak, then create Pivot Table:**
   > 🎤 "Next, let's build a Pivot Table to aggregate order counts, total Net ARR, and average Gross Margin across `SKU-101` through `SKU-105`. I will click cell A1 in `Deal_Orders`, press `Command + A` to select `A1:N31`, click `Insert` in the top menu bar, and click `Pivot table`, then click `Create` in the center dialog box to place it on a new sheet."
2. **Action:** Select `A1:N31`, click **Insert → Pivot table → Create**.
3. **Speak while configuring the Pivot Table in the right sidebar (100% mouse clicks):**
   > 🎤 "In the Pivot table editor sidebar on the right, next to `Rows`, I will click `Add` and select `SKU_Code`. Next to `Values`, I will click `Add` and select `Order_ID` (summarized by `COUNTA`) to see order volume per SKU. I will click `Add` under `Values` a second time and select `Net_ARR` (summarized by `SUM`) to see total revenue per SKU. Finally, I will click `Add` under `Values` a third time, select `Margin`, and change the `Summarize by` dropdown from `SUM` to `AVERAGE`."
4. **Action:** In the Pivot table editor sidebar:
   - **Rows → Add → `SKU_Code`**
   - **Values → Add → `Order_ID`** (`COUNTA`)
   - **Values → Add → `Net_ARR`** (`SUM`)
   - **Values → Add → `Margin`** (change `SUM` to **`AVERAGE`**)
5. **Speak while pointing at the Pivot Table totals with your mouse (~30s):**
   > 🎤 "Examining our Pivot Table in the center grid across all thirty orders: total Q4 Net ARR is `$18,154,820` with a `72.15%` simple average margin (`71.33%` revenue-weighted margin). Notice `SKU-104` (`AI Copilot`) generated the largest Net ARR at `$8,455,480` across 8 orders, but has the lowest average gross margin at `66.90%` because four of its eight orders were discounted over `30%`. Meanwhile, `SKU-102` (`$3,493,540` at `78.02%`) and `SKU-105` (`$685,500` at `79.03%`) had zero breaches."
6. **Speak, then add an Interactive Data Slicer (`Data → Add a slicer`):**
   > 🎤 "To allow leadership to filter this SKU summary interactively by region, I will click `Data` in the top menu bar and select `Add a slicer`. In the Slicer sidebar on the right, under `Column`, I will select `Region`, drag the floating Slicer widget to the right of our Pivot Table, click the Slicer dropdown with the mouse, and filter to `EMEA`—which accounts for 12 orders and `$7,266,760` in Net ARR (`70.75%` average margin)—before clicking `Select all` and `OK` to restore the full portfolio view."
7. **Action:** Click **Data → Add a slicer**, select **`Region`**, filter to `EMEA` briefly with the mouse, then reset to **Select all → OK**.
8. **Speak, then create the SKU Net ARR Bar Chart (`Insert → Chart`):**
   > 🎤 "Now I will select the SKU and Net ARR cells in our Pivot Table, click `Insert` in the top menu bar, and select `Chart` to generate a bar chart comparing Net ARR across `SKU-101` through `SKU-105`. I will drag the chart below row 9 so it does not overlap the Pivot Table, click the three-dot menu in the top-right corner of the chart, and click `Copy chart`."
9. **Action:** Insert chart, drag it below the Pivot Table, and click **Copy chart**.
10. **Speak, then export `.xlsx` (`final output 1.xlsx`):**
    > 🎤 "In the top menu bar of Google Sheets, I will click `File`, hover over `Download`, and select `Microsoft Excel (.xlsx)` to export our completed Q4 Deal Desk Margin Audit workbook."
11. **Action:** Click **File → Download → Microsoft Excel (`.xlsx`)**.

---

### SECTION F: Assemble 3-Slide Executive Deck in Google Slides (`17:15 – 21:00`)

*(Because Slide 1–3 titles are pre-typed before recording, you only type the three 7-word bullets on Slide 3—taking under 18 seconds of typing total!)*

1. **Speak, then switch to Google Slides:**
   > 🎤 "In the top browser tab bar, I will click the second tab titled `Q4 Deal Desk Pricing & Margin Review` in Google Slides to compile our three-slide executive presentation."
2. **Action:** Click the Google Slides tab.
3. **Speak on Slide 1, then click Slide 2 and paste Chart + Pivot Table:**
   > 🎤 "Slide 1 is our title slide for the `Q4 2026 SaaS Deal Desk Pricing & Margin Audit`. In the left filmstrip, I will click Slide 2 (`SKU Net ARR & Gross Margin Performance`), press `Command + V`, and click `Paste` to embed our linked SKU chart on the left side. Then I will switch back to our Pivot Table tab in Google Sheets, select the Pivot summary cells `A1:D7`, press `Command + C`, return to Slide 2 in Google Slides, and press `Command + V` to place the linked SKU table on the right side of the slide."
4. **Action:** Paste the chart and Pivot Table onto **Slide 2** and resize/align them with the mouse (~30s).
5. **Speak, then click Slide 3 and type your 3 exact 7-word bullets (~6s of typing each):**
   - Click **Slide 3** (`Deal Desk Policy Findings & Q1 Guardrails`) in the left filmstrip:
   - **Bullet 1 (~6s typing):**
     > 🎤 "On Slide 3, in the center text box, I will type our first 7-word takeaway summarizing the `$18.15M` Q4 booked Net ARR and `71.3%` portfolio gross margin."
     ```text
     Q4 booked $18.15M at 71.3% gross margin.
     ```
   - **Bullet 2 (~6s typing):**
     > 🎤 "On the second bullet line, I will type our second 7-word takeaway noting that six unauthorized discount orders breached the `65%` margin floor."
     ```text
     Six unauthorized orders breached 65% margin floors.
     ```
   - **Bullet 3 (~6s typing):**
     > 🎤 "On the third bullet line, I will type our third 7-word takeaway establishing the Q1 Deal Desk policy guardrail for discounts above `20%`."
     ```text
     High-COGS discounts exceeding 20% require VP approval.
     ```
6. **Speak, then export `.pdf` (`final output 2.pdf`):**
   > 🎤 "In the top menu bar of Google Slides, I will click `File`, hover over `Download`, and click `PDF Document (.pdf)` to export our finished Q4 Deal Desk review deck."
7. **Action:** Click **File → Download → PDF Document (`.pdf`)**.

---

### SECTION G: 3-Minute Verbal Epilogue (`21:00 – 24:00`)

*(Slowly click through Slides 1–3 in Google Slides and the `Product_Catalog`, `Deal_Orders`, and `Pivot Table` tabs in Google Sheets with your mouse while speaking—zero typing!)*

> 🎤 "Let's wrap up with a summary of our workflow, key methodological decisions, and lessons learned.
>
> First, completion and verification: we completed the Q4 SaaS Enterprise Deal Desk Pricing, Discount, and Gross Margin Audit across thirty customer orders (`ORD-301` through `ORD-330`) and five SaaS SKUs (`SKU-101` through `SKU-105`). In Google Sheets, we used `VLOOKUP` to pull each SKU's list price and fixed unit COGS from `Product_Catalog` into `Deal_Orders`, calculated `$18,154,820` in total Net ARR against `$5,205,350` in total hosting COGS (`71.33%` weighted gross margin / `72.15%` average order margin), and flagged six unauthorized over-discounted orders (`ORD-305`, `ORD-306`, `ORD-312`, `ORD-318`, `ORD-320`, and `ORD-322`) that fell below our `65.0%` gross margin floor. We then applied conditional formatting to highlight those six breaches in red, built a Pivot Table and interactive Region Data Slicer, and compiled our three-slide executive review deck in Google Slides, exporting both the Excel workbook and the PDF presentation.
>
> Second, why this approach was effective: maintaining unit list prices and unit COGS in a dedicated `Product_Catalog` tab and retrieving them dynamically via `VLOOKUP` prevents manual pricing entry errors across individual orders. Pairing row-level conditional formatting with a SKU Pivot Table and Region Slicer immediately revealed that four of the six margin breaches (`$3.81M` in breached Net ARR) occurred on `SKU-104` (`AI Copilot`, which carries a `$100` per-seat fixed compute cost) when sales reps offered `31%` to `39%` discounts.
>
> Third, common mistakes that someone less experienced should watch out for in a SaaS pricing and gross margin audit:
> - Number one: omitting the `FALSE` exact-match fourth argument in `VLOOKUP`, which can return incorrect tier prices if SKU codes are not sorted.
> - Number two: evaluating enterprise deals solely on top-line Net ARR without deducting fixed seat-level hosting COGS—for example, `ORD-322` (`4,880` seats of `SKU-104` at a `36%` discount) brought in `$1,249,280` in Net ARR, but required `$488,000` in fixed compute COGS, compressing gross margin to `60.94%` below our `65%` profitability floor.
> - Number three: leaving the `Margin` field in a Pivot Table set to `SUM` instead of changing the aggregation dropdown to `AVERAGE`, which produces meaningless percentage sums over `100%`.
>
> All deliverables are exported and ready for packaging. Thank you for watching."

---

## Part 5: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

```text
Deliverables/
├── input 1.xlsx         <-- Starting Q4_Deal_Desk_Margin_Audit.xlsx workbook (or input 1.csv & input 2.csv)
├── final output 1.xlsx  <-- Completed Google Sheets Deal Desk Margin Audit workbook (.xlsx)
└── final output 2.pdf   <-- Exported Google Slides 3-Slide Executive Review Deck (.pdf)
```

### `Metadata.rtf` Template for This Task
```text
Topology: Google Sheets (MODIFY) -> Google Slides (CREATE) -> Google Sheets (LOOKUP) -> Google Slides (MODIFY)

Request: <Paste the exact Goal text from Studio / TaskRecorder>

Task Description:
1. Open the Q4 Deal Desk Pricing workbook in Google Sheets and use VLOOKUP to pull unit list prices and hosting COGS from Product_Catalog into Deal_Orders.
2. Calculate net ARR ($18,154,820 total), total COGS ($5,205,350 total), gross margin percentage, and policy status across all 30 enterprise orders, and apply conditional formatting to flag the 6 orders breaching the 65% gross margin floor.
3. Build a Pivot Table, an interactive Region Data Slicer, and a bar chart summarizing Net ARR and average Gross Margin across SKU-101 through SKU-105, and export the completed workbook as an Excel file.
4. Assemble the 3-slide Q4 Deal Desk Pricing & Margin Review Deck in Google Slides with the embedded SKU chart, Pivot summary table, and Q1 discount guardrails, and export the presentation as a PDF.
```
