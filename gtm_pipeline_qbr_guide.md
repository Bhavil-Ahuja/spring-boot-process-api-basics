# Task 3 Master Guide (`GTM`): SaaS Deal Desk Pricing, Discount & Gross Margin Audit

---

## Why This Task 3 Workflow Is 100% Distinct from Task 2 & AutoQC-Safe
1. **Zero Overlap with Task 2's Operations:**
   - Instead of Task 2's `Remove duplicates` + `FILTER` + `COUNTIFS`, this workflow uses **`VLOOKUP` (cross-table pricing lookup)**, **Gross Margin & Discount math**, **Format → Conditional formatting**, **Insert → Pivot table**, and **Data → Add a slicer** in Google Sheets, paired with **Google Slides** (instead of Google Docs).
2. **Ultra-Low Typing Share (`~12–15%` vs. `25%` Limit):**
   - `Conditional formatting`, `Pivot tables`, `Data slicers`, `Charts`, and arranging slides in **Google Slides** are **90% mouse-driven GUI actions**, keeping your keyboard time well below the `25%` threshold.
3. **Designed for Your 3-Hour Logged Gemini Workflow:**
   - You use the **Gemini Prompt Playbook (Part 3)** during your logged session to design the pricing rules, generate the synthetic CSV/Excel tables with Gemini, and verify formulas—then upload the Gemini-generated `.xlsx` here before recording so we lock in the exact cell/row numbers.

---

## Part 1: Step-by-Step Studio Idea Submission & Approval (Do This First!)

Before you generate data or record, submit your idea in Studio and wait for the status to move from **`Idea Draft`** → **`Idea Approved: Confirm Tech Setup`** → **`Idea Approved: Start Recording`**.

### How to Fill Out Section `1.0 Create your idea` in Studio
1. Click **Create task** in Studio (`Odin Production Full Workflow`).
2. Scroll to **1.0 Create your idea → Describe your Idea**.
3. **Important:** Type the 5 sections below **in your own words** (never copy-paste directly into Studio's text box):

   - **`Domain / Role:`**
     - Write: Revenue Operations & Deal Desk Pricing Lead (`GTM` — Marketing; Sales & Biz Dev).
   - **`Goal:`** *(Keep a copy of the exact text you type here—once approved, this exact paragraph goes into your Opening Goal Document, TaskRecorder's Task Description box, and `Metadata.rtf`!)*
     - Paraphrase this in your own words:
       *As a Deal Desk & Revenue Operations Lead, I need to conduct a Q4 SaaS Enterprise Deal Desk Pricing, Discount, and Gross Margin Audit for executive leadership. Using our Q4 Deal Desk Pricing workbook (`Deal_Orders` and `Product_Catalog` sheets) in Google Sheets, I will pull unit list prices and hosting costs from the product catalog into the order log using `VLOOKUP`, calculate net contract value, gross profit, and gross margin percentage after sales discounts, apply conditional formatting to flag unauthorized over-discounted deals that breach our 65% gross margin floor, build a Pivot Table and interactive Data Slicer to analyze revenue and margin by Product Tier and Sales Region, and compile a 3-slide Executive Deal Desk Pricing & Margin Review deck in Google Slides exported as a PDF.*
   - **`Starting materials:`**
     - Paraphrase this in your own words:
       *Synthetic starting workbook (`Q4_Deal_Desk_Margin_Audit.xlsx`, or its two source CSVs `input 1.csv` and `input 2.csv`) prepared with Gemini prior to recording, containing: (1) `Deal_Orders` (30 enterprise SaaS orders `ORD-301` to `ORD-330` across anonymized customers `Test Client 1`–`30` and 4 sales regions, listing `Product_Code`, `License_Seats`, and `Rep_Discount_Pct`); and (2) `Product_Catalog` (5 SaaS SKU tiers `SKU-101` to `SKU-105` listing `Product_Name`, `Annual_List_Price_Per_Seat`, `Annual_COGS_Per_Seat`, `Max_Approved_Discount_Pct`, and `Target_Gross_Margin_Pct` of `65%`).*
   - **`Steps (with the apps for each):`**
     - Paraphrase these 2 app bullets in your own words:
       - *Google Sheets:* Open the Q4 Deal Desk Pricing workbook (`Deal_Orders` and `Product_Catalog`), use `VLOOKUP` to pull each order's `List_Price` and `Unit_COGS` from `Product_Catalog`, calculate `Gross_ARR`, `Net_ARR` (after discount), `Total_COGS`, `Gross_Margin_Pct`, and `Policy_Status` (`Approved` vs. `Margin_Breach`), apply `Conditional formatting` to highlight margin breaches in red, create a `Pivot Table` and an interactive `Data Slicer` (`Data → Add a slicer`) plus a combo/bar chart comparing Net ARR and Gross Margin across the 5 SaaS SKUs, and export the completed workbook as `.xlsx`.
       - *Google Slides:* Create a 3-slide Q4 Deal Desk Pricing & Margin Review Deck, embed the linked SKU Margin chart and Pivot summary table from Google Sheets, document the Q1 discount approval guardrails for the breaching SKUs, and export the presentation deck as a `.pdf`.
   - **`Deliverable:`**
     - Paraphrase this in your own words:
       *1. The completed multi-tab SaaS Deal Desk Pricing & Margin Audit workbook exported from Google Sheets as an Excel file (`final output 1.xlsx`).*
       *2. The 3-slide Executive Deal Desk Pricing & Margin Review deck exported from Google Slides as a PDF (`final output 2.pdf`).*

4. **Select Apps in Studio's `Used Apps` Dropdown:**
   - Select **`Google Sheets`** and **`Google Slides`**.
5. Click **Submit idea** and wait for approval before moving to Phase 2.

---

## Part 2: Complete 3-Hour (`180-Minute`) End-to-End Time Plan (Includes Gemini + Recording!)

| Time Window | Duration | Phase | What You Actively Do |
|---|---:|---|---|
| **0:00 – 0:25** | `25 min` | **1. Ideation & Studio Idea Submission** | Review the GTM guidelines, run **Prompt 1** below with Gemini to design the SaaS SKU catalog, discount approval rules, and 65% gross margin floor, and type your 5-part idea into Studio's **Describe your Idea** in your own words. *(Pause timer while waiting for approval if approval isn't immediate.)* |
| **0:25 – 1:10** | `45 min` | **2. Interactive Dataset Generation & Math Audit with Gemini (After Approval)** | Once your idea is approved, run **Prompt 2**, **Prompt 3**, and **Prompt 4** with Gemini to generate `Deal_Orders` (30 rows) and `Product_Catalog` (5 rows), save them into `Q4_Deal_Desk_Margin_Audit.xlsx` (using `Test Client 1`–`30` and `Person 1`–`4` to avoid PII), and **upload the `.xlsx` here** so we lock the exact row numbers into Part 5. |
| **1:10 – 1:45** | `35 min` | **3. Scratch Dry-Run in Google Sheets & Slides** | Practice the workflow once in a scratch Google Sheet (`VLOOKUP`, margin math, `Format → Conditional formatting`, `Insert → Pivot table`, `Data → Add a slicer`, Chart, and pasting into Google Slides) so your mouse actions are smooth on camera. |
| **1:45 – 2:00** | `15 min` | **4. Desktop Appearance Change & Pre-Recording Setup** | Change your macOS Wallpaper + toggle Light/Dark mode + change Accent Color + adjust Dock size (Task Variety requirement). Set up Window 1 (Opening Goal Document in Google Docs) and Window 2 (Tab 1: Google Sheets, Tab 2: Google Slides with 3 pre-titled slides), then minimize Window 2. |
| **2:00 – 2:25** | `25 min` | **5. Actual Video Recording (In TaskRecorder)** | Record the complete 21–24 minute workflow and 3-minute Epilogue in one uninterrupted take using the What/Where/Why script in Part 5. |
| **2:25 – 3:00** | `35 min` | **6. Verification, `Deliverables.zip`, `Metadata.rtf` & AutoQC** | Spot-check `video.mp4` and `screenshots/`, package `Deliverables.zip`, fill out `Metadata.rtf`, upload all 4 files to Studio, verify AutoQC passes with 0 required findings, and submit. |

---

## Part 3: Professional Gemini Interaction Strategy & Prompt Playbook (45–60 Mins of Logged Work)

To make your logged time with Gemini thorough and realistic, interact with Gemini in **4 progressive turns** rather than asking for everything in a single prompt:

### Prompt 1 — Designing the SaaS Deal Desk Pricing & Margin Rules (Phase 1 — ~15 mins)
```text
I am a Revenue Operations & Deal Desk Lead designing a Q4 SaaS Enterprise Deal Desk Pricing, Discount & Gross Margin Audit in Google Sheets and Google Slides.
Help me design a realistic B2B SaaS pricing and discounting framework with:
1. A 5-tier SaaS Product Catalog (`SKU-101` to `SKU-105`: e.g., Core Platform, Analytics Pro, Security Suite, AI Copilot, Enterprise Governance) with:
   - Annual List Price per seat ($100 to $500)
   - Annual Hosting/Support COGS per seat ($25 to $120) so baseline gross margins before discounts are around 75%–80%.
   - Maximum Deal Desk Approved Discount % (20%) and a strict Gross Margin Floor of 65.0%.
2. Explain the business logic for why a rep giving a 30%–40% discount on a higher-COGS SKU (like AI Copilot or Security Suite) causes a "Margin Breach" (< 65% gross margin) even when total revenue looks high, and show the exact formulas for Gross ARR, Net ARR, Total COGS, and Gross Margin %.
```

### Prompt 2 — Generating the Anonymized `Product_Catalog` and 30-Row `Deal_Orders` Dataset (Phase 2 — ~15 mins)
```text
Now generate two clean, anonymized CSV tables that I can save as `Product_Catalog` and `Deal_Orders` inside `Q4_Deal_Desk_Margin_Audit.xlsx` (use `Test Client 1` through `Test Client 30` and `Person 1` through `Person 4` as sales reps so there is zero PII):
1. `Product_Catalog` (5 rows, `A2:F6`):
   Columns: `SKU_Code,Product_Name,List_Price_USD,Unit_COGS_USD,Max_Discount_Pct,Margin_Floor_Pct`
   Use clean round numbers for List_Price_USD and Unit_COGS_USD across `SKU-101` to `SKU-105`, with `Max_Discount_Pct = 0.20` and `Margin_Floor_Pct = 0.65`.
2. `Deal_Orders` (30 rows, `A2:G31`):
   Columns: `Order_ID,Order_Date,Client_Name,Sales_Rep,Region,SKU_Code,Seats,Discount_Pct`
   - Distribute the 30 orders (`ORD-301` to `ORD-330`) across `North America`, `EMEA`, `APAC`, and `LATAM` and across `SKU-101` to `SKU-105`.
   - Make sure most orders have compliant discounts (0% to 20%) resulting in Gross Margin >= 65% (`Approved`), while exactly 6 orders have excessive unauthorized discounts (30% to 45%) that push their Gross Margin below 65.0% (`Breach`).
```

### Prompt 3 — Auditing the Exact Row-by-Row Math & Pivot Table Totals (Phase 2 — ~10 mins)
```text
Using the exact 30 rows in `Deal_Orders` and 5 rows in `Product_Catalog` you just generated, calculate and show me a verification table with:
1. Which exact `Order_ID` rows breach the 65% Gross Margin floor (`Margin < 65%`), their exact `Net_ARR`, `COGS`, and `Margin %`.
2. The exact Pivot Table totals by `SKU_Code` (and by `Region`) showing:
   - Total Order Count
   - Total Net ARR (`SUM of Net_ARR`)
   - Average Gross Margin % (`AVERAGE of Margin`)
   - Count of `Breach` orders per SKU/Region
3. Verify the exact Google Sheets formulas for `Deal_Orders` columns `I` through `N` (`Price`, `COGS`, `Net_ARR`, `Total_COGS`, `Margin`, `Status`) using `VLOOKUP`.
```

### Prompt 4 — Executive Slide Deck Narrative & Deal Desk Policy Guardrails (Phase 2 — ~10 mins)
```text
Based on the audit totals above, draft 3 concise 7-word executive bullet points for Slide 3 of my Google Slides Q4 Deal Desk Review deck covering:
1. Total Q4 Net ARR booked across the 30 enterprise orders and portfolio-wide gross margin %.
2. Number of unauthorized discount orders that breached the 65% gross margin floor and their margin erosion impact.
3. The Q1 Deal Desk policy guardrail (requiring VP Finance approval in CRM for any discount > 20% on high-COGS SKUs).
```

---

## Part 4: Google Sheets & Google Slides Architecture (Zero-Typing-Trap Design)

### Columns in `Deal_Orders` (`A1:N31`)
- **Pre-populated Input Columns (`A` to `H`):**
  - `A`: `Order_ID` (`ORD-301` to `ORD-330`)
  - `B`: `Order_Date`
  - `C`: `Client_Name` (`Test Client 1` to `Test Client 30`)
  - `D`: `Sales_Rep` (`Person 1` to `Person 4`)
  - `E`: `Region` (`North America`, `EMEA`, `APAC`, `LATAM`)
  - `F`: `SKU_Code` (`SKU-101` to `SKU-105`)
  - `G`: `Seats`
  - `H`: `Discount_Pct`
- **6 Short Calculated Columns You Add in `Deal_Orders` (`I1:N1` — 1-word headers, short formulas!):**
  - `I1` (`Price`): `=VLOOKUP(F2, Product_Catalog!$A$2:$D$6, 3, FALSE)` *(pulls unit list price)*
  - `J1` (`Unit_Cost`): `=VLOOKUP(F2, Product_Catalog!$A$2:$D$6, 4, FALSE)` *(pulls unit COGS)*
  - `K1` (`Net_ARR`): `=G2*I2*(1-H2)` *(seats × list price × (1 - discount))*
  - `L1` (`COGS`): `=G2*J2` *(seats × unit COGS)*
  - `M1` (`Margin`): `=(K2-L2)/K2` *(formatted as `%`)*
  - `N1` (`Status`): `=IF(M2>=0.65, "Approved", "Breach")`

### 4 Mouse-Driven GUI Features You Use in Google Sheets (Why Typing Stays `< 14%`!)
1. **Conditional Formatting (`Format → Conditional formatting`):**
   - Select `N2:N31`, click **Format → Conditional formatting**, choose **Text is exactly → `Breach`**, pick **Light red fill**, and click **Done** (almost entirely mouse clicks!).
2. **Pivot Table (`Insert → Pivot table`):**
   - Select `A1:N31`, click **Insert → Pivot table → Create**, and in the right sidebar click:
     - **Rows → Add → `SKU_Code`** (or `Region`)
     - **Columns → Add → `Status`**
     - **Values → Add → `Net_ARR`** (`SUM`) and **`Margin`** (`AVERAGE`)
3. **Interactive Data Slicer (`Data → Add a slicer`):**
   - On the Pivot Table sheet, click **Data → Add a slicer**, choose **`Region`** in the right sidebar, and use the mouse dropdown on the slicer to filter the Pivot Table live on camera!
4. **Bar/Column Chart (`Insert → Chart`):**
   - Create a visual chart of Net ARR / Gross Margin by SKU or Region, copy it, and paste it into **Google Slides**.

---

## Part 5: AutoQC-Hardened Recording Script Structure (`21–24 Minutes`, `< 14%` Typing)

*(Once your Studio Idea is approved and you generate `Q4_Deal_Desk_Margin_Audit.xlsx` using the Gemini prompts above, upload the `.xlsx` here and I will plug your exact row numbers and dollar totals into this verbatim script just like we did for Task 2!)*

### Pre-Recording Setup Checklist
1. **Change Your Mac UI First (Mandatory Between Every Task!):**
   - `System Settings → Wallpaper`: Pick a **new wallpaper** (different from macOS default, Task 1, and Task 2).
   - `System Settings → Appearance`: Toggle **Light/Dark mode** and pick a **new Accent Color**.
   - Leave a thin strip of desktop wallpaper visible around your Chrome window.
2. **Window 1 (Google Docs — Opening Goal Doc):**
   - Open a Chrome window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder.
3. **Window 2 (Google Sheets & Google Slides — Main Workspace):**
   - Open a separate Chrome window with two tabs:
     - **Tab 1 (Google Sheets):** `Q4_Deal_Desk_Margin_Audit.xlsx` opened as a Google Sheet (`Deal_Orders` and `Product_Catalog`).
     - **Tab 2 (Google Slides):** `Q4 Deal Desk Pricing & Margin Review` with **3 pre-titled slides** (`Slide 1: Title`, `Slide 2: SKU & Regional Gross Margin Matrix`, `Slide 3: Deal Desk Policy Guardrails & Action Plan`).
   - **Minimize Window 2** using the yellow Minimize button (`-`) in the top-left corner before starting TaskRecorder!

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)
1. Click **Start Recording**, immediately click the **yellow Minimize button (`-`)** on TaskRecorder.
2. Speak (`~10s`):
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open Google Sheets from the Dock."
3. Click the **yellow Minimize button (`-`)** on the Goal document window and open **Google Sheets** from the Dock.

### SECTION B: Inspect `Product_Catalog` & `Deal_Orders` with the Mouse (`00:20 – 03:30`)

1. **Speak, then click `Product_Catalog`:**
   > 🎤 "In the bottom-left sheet tab bar of Google Sheets, I will first click the `Product_Catalog` tab to review our five SaaS SKU tiers from `SKU-101` to `SKU-105`. Looking across columns A through F in the center grid, each SKU lists its annual list price per seat in column C, annual hosting and support COGS per seat in column D, maximum approved rep discount of `20%` in column E, and our company-wide `65%` gross margin floor in column F."
2. **Action:** Click `Product_Catalog` and move your mouse across `A2:F6` (~30s).
3. **Speak, then click `Deal_Orders` and scroll down with the mouse (~45s):**
   > 🎤 "Now in the bottom sheet tab bar, I will click the `Deal_Orders` tab, which contains thirty Q4 enterprise orders from `ORD-301` on row 2 down to `ORD-330` on row 31 across `Test Client 1` through `Test Client 30` and sales reps `Person 1` through `Person 4`. Scrolling down column H (`Discount_Pct`) with the mouse, notice that while most orders stayed within the `20%` discount cap, several orders were given `30%` to `45%` discounts. Let's scroll back up to row 1 so we can pull catalog prices and audit each order's gross margin."
4. **Action:** Click `Deal_Orders`, scroll down `A2:H31`, and return to row 1.

---

### SECTION C: Pull Catalog Prices via `VLOOKUP` & Compute Gross Margin (`03:30 – 09:30`)

1. **Speak, then type the 6 short 1-word headers in `I1:N1` (~10s):**
   > 🎤 "In row 1 of `Deal_Orders`, starting at cell I1, I will type our six 1-word calculated column headers using Tab: `Price` in I1, `Unit_Cost` in J1, `Net_ARR` in K1, `COGS` in L1, `Margin` in M1, and `Status` in N1."
2. **Action:** Type `Price` (`I1`), `Unit_Cost` (`J1`), `Net_ARR` (`K1`), `COGS` (`L1`), `Margin` (`M1`), and `Status` (`N1`).
3. **Speak, then type `VLOOKUP` for `Price` in `I2` (~15s):**
   > 🎤 "In cell I2 on row 2 of `Deal_Orders`, I will type `=VLOOKUP(F2, Product_Catalog!$A$2:$D$6, 3, FALSE)` and press Enter to look up the annual list price per seat for the SKU in cell F2 from column 3 of `Product_Catalog`, and I will accept the autofill down to row 31."
4. **Action:** Type `=VLOOKUP(F2, Product_Catalog!$A$2:$D$6, 3, FALSE)` in `I2`, press **Enter**, and fill down to `I31`.
5. **Speak, then type `VLOOKUP` for `Unit_Cost` in `J2` (~15s):**
   > 🎤 "In cell J2 on row 2, I will type `=VLOOKUP(F2, Product_Catalog!$A$2:$D$6, 4, FALSE)` and press Enter to pull the unit COGS per seat from column 4 of `Product_Catalog`, then fill down to J31."
6. **Action:** Type `=VLOOKUP(F2, Product_Catalog!$A$2:$D$6, 4, FALSE)` in `J2`, press **Enter**, and fill down to `J31`.
7. **Speak, then type `Net_ARR` formula in `K2` (~10s):**
   > 🎤 "In cell K2, I will type `=G2*I2*(1-H2)` and press Enter to calculate net annual recurring revenue after multiplying seats in G2 by list price in I2 and subtracting the discount percentage in H2, then fill down to K31."
8. **Action:** Type `=G2*I2*(1-H2)` in `K2`, press **Enter**, and fill down to `K31`.
9. **Speak, then type `COGS` formula in `L2` (~8s):**
   > 🎤 "In cell L2, I will type `=G2*J2` and press Enter to compute total hosting COGS for the order by multiplying seats in G2 by unit cost in J2, then fill down to L31."
10. **Action:** Type `=G2*J2` in `L2`, press **Enter**, and fill down to `L31`.
11. **Speak, then type `Margin` formula in `M2` (~10s):**
    > 🎤 "In cell M2, I will type `=(K2-L2)/K2` and press Enter to calculate the order's gross margin percentage, fill down to M31, and click the `Format as percent (%)` button in the top toolbar."
12. **Action:** Type `=(K2-L2)/K2` in `M2`, fill down to `M31`, and click **`%`** in the top toolbar.
13. **Speak, then type `Status` formula in `N2` (~12s):**
    > 🎤 "In cell N2, I will type `=IF(M2>=0.65, \"Approved\", \"Breach\")` and press Enter to flag whether each order meets our `65%` gross margin floor or falls into `Breach`, then fill down to N31."
14. **Action:** Type `=IF(M2>=0.65, "Approved", "Breach")` in `N2`, press **Enter**, and fill down to `N31`.

---

### SECTION D: Highlight Breaches via Conditional Formatting (`09:30 – 12:00`)

*(100% mouse-driven GUI formatting + inspection!)*

1. **Speak, then apply Conditional Formatting to `N2:N31`:**
   > 🎤 "To visually spotlight the margin breaches, I will select cells `N2` through `N31` with the mouse, click `Format` in the top menu bar of Google Sheets, and click `Conditional formatting` in the dropdown menu."
2. **Action:** Select `N2:N31` and click **Format → Conditional formatting**.
3. **Speak, then configure the rule in the right sidebar:**
   > 🎤 "In the Conditional format rules sidebar on the right side of the screen, under `Format cells if`, I will click the dropdown menu, select `Text is exactly`, type `Breach` in the value box, select the light red fill style under Formatting style, and click the green `Done` button."
4. **Action:** Set **Text is exactly** → `Breach`, choose light red fill, and click **Done**. Close the Conditional format sidebar (`X`).
5. **Speak while scrolling down `Deal_Orders` with the mouse (~35s):**
   > 🎤 "Scrolling down columns H, M, and N in the center grid with the mouse, every order highlighted in red in column N had an excessive discount in column H that pushed its gross margin in column M below our `65.0%` floor."

---

### SECTION E: Build Mouse-Driven Pivot Table, Interactive Slicer & Chart (`12:00 – 17:15`)

1. **Speak, then create Pivot Table:**
   > 🎤 "Next, let's build a Pivot Table to aggregate Net ARR, average Gross Margin, and breach counts across our five SaaS SKUs. I will click cell A1 in `Deal_Orders`, press `Command + A` to select `A1:N31`, click `Insert` in the top menu bar, and click `Pivot table`, then click `Create` in the center dialog box to place it on a new sheet."
2. **Action:** Select `A1:N31`, click **Insert → Pivot table → Create**.
3. **Speak while configuring the Pivot Table in the right sidebar (100% mouse clicks):**
   > 🎤 "In the Pivot table editor sidebar on the right, next to `Rows`, I will click `Add` and select `SKU_Code`. Next to `Columns`, I will click `Add` and select `Status` so `Approved` and `Breach` orders appear side by side. Next to `Values`, I will click `Add` and select `Net_ARR` (summarized by `SUM`), and I will click `Add` under `Values` a second time, select `Margin`, and change the `Summarize by` dropdown from `SUM` to `AVERAGE`."
4. **Action:** Configure Rows (`SKU_Code`), Columns (`Status`), and Values (`Net_ARR` as `SUM`, `Margin` as `AVERAGE`).
5. **Speak, then add an Interactive Data Slicer (`Data → Add a slicer`):**
   > 🎤 "To allow leadership to filter this SKU summary interactively by sales region, I will click `Data` in the top menu bar and select `Add a slicer`. In the Slicer sidebar on the right, under `Column`, I will choose `Region`, drag the floating Slicer widget above our Pivot Table, click the Slicer dropdown with the mouse, and demonstrate filtering by individual regions before selecting `Select all` and clicking `OK`."
6. **Action:** Click **Data → Add a slicer**, choose **`Region`**, test filtering with the mouse, then reset to **Select all → OK**.
7. **Speak, then create the SKU Margin & Revenue Chart (`Insert → Chart`):**
   > 🎤 "Now I will select the SKU summary range in our Pivot Table, click `Insert` in the top menu bar, and select `Chart` to generate a visual comparison across `SKU-101` through `SKU-105`. I will drag the chart below the table, click the three-dot menu in the top-right corner of the chart, and click `Copy chart`."
8. **Action:** Insert chart, position it cleanly, and copy it.
9. **Speak, then export `.xlsx` (`final output 1.xlsx`):**
   > 🎤 "In the top menu bar of Google Sheets, I will click `File`, hover over `Download`, and select `Microsoft Excel (.xlsx)` to export our completed Deal Desk Margin Audit workbook."
10. **Action:** Click **File → Download → Microsoft Excel (`.xlsx`)**.

---

### SECTION F: Assemble 3-Slide Executive Deck in Google Slides (`17:15 – 21:00`)

1. **Speak, then switch to Google Slides:**
   > 🎤 "In the top browser tab bar, I will click the second tab titled `Q4 Deal Desk Pricing & Margin Review` in Google Slides to compile our three-slide executive presentation."
2. **Action:** Click the Google Slides tab.
3. **Speak on Slide 1, then click Slide 2 and paste Chart + Pivot Table:**
   > 🎤 "Slide 1 is our title slide for the `Q4 Deal Desk Pricing & Margin Review`. In the left filmstrip, I will click Slide 2 (`SKU & Regional Gross Margin Matrix`), press `Command + V`, and click `Paste` to embed our linked SKU chart on the left side. Then I will switch back to Google Sheets, copy our Pivot Table summary cells with `Command + C`, return to Slide 2 in Google Slides, and press `Command + V` to place the linked summary table on the right side of the slide."
4. **Action:** Paste the chart and Pivot Table onto **Slide 2** and resize/align them with the mouse (~30s).
5. **Speak, then click Slide 3 and type 3 ultra-short 7-word bullets (~6s of typing each):**
   - Click **Slide 3** (`Deal Desk Policy Guardrails & Action Plan`) in the left filmstrip:
   - **Bullet 1 (~6s typing):**
     > 🎤 "On Slide 3, in the center text box, I will type our first bullet summarizing the 30 audited orders and portfolio gross margin."
     ```text
     Audited 30 Q4 enterprise orders across 5 SaaS SKUs (65% margin floor).
     ```
   - **Bullet 2 (~6s typing):**
     > 🎤 "On the second bullet line, I will type the finding on unauthorized discounts above 20% causing margin breaches."
     ```text
     Discounts above 20% triggered all gross margin breaches below 65%.
     ```
   - **Bullet 3 (~6s typing):**
     > 🎤 "On the third bullet line, I will type the Q1 Deal Desk policy guardrail requiring VP Finance sign-off."
     ```text
     Q1 Policy: Enforce 20% discount cap; require VP Finance approval above 20%.
     ```
6. **Speak, then export `.pdf` (`final output 2.pdf`):**
   > 🎤 "In the top menu bar of Google Slides, I will click `File`, hover over `Download`, and click `PDF Document (.pdf)` to export our finished Q4 Deal Desk review deck."
7. **Action:** Click **File → Download → PDF Document (`.pdf`)**.

---

### SECTION G: 3-Minute Verbal Epilogue (`21:00 – 24:00`)

*(Slowly click through Slides 1–3 in Google Slides and the `Product_Catalog`, `Deal_Orders`, and `Pivot Table` tabs in Google Sheets with your mouse while speaking—zero typing!)*

> 🎤 "Let's wrap up with a summary of our workflow, key methodological decisions, and lessons learned.
>
> First, completion and verification: we completed the Q4 SaaS Enterprise Deal Desk Pricing, Discount, and Gross Margin Audit across thirty customer orders (`ORD-301` through `ORD-330`) and five SaaS SKUs (`SKU-101` through `SKU-105`). In Google Sheets, we used `VLOOKUP` to pull each SKU's list price and unit COGS from `Product_Catalog` into `Deal_Orders`, computed net ARR after rep discounts, total hosting COGS, and gross margin percentage per order, and classified every order against our `65%` gross margin floor. We then applied conditional formatting to highlight breaching orders in red, constructed a Pivot Table and interactive Region Data Slicer to inspect revenue and margin across SKUs and regions, and compiled our three-slide executive review deck in Google Slides, exporting both the Excel workbook and the PDF presentation.
>
> Second, why this approach was effective: maintaining unit list prices and unit COGS in a normalized `Product_Catalog` table and retrieving them via `VLOOKUP` eliminates manual pricing entry errors across individual orders. Pairing row-level conditional formatting with a Pivot Table and Region Slicer allows Deal Desk leadership to spot both individual rep discount exceptions and systemic SKU-level margin compression at a glance.
>
> Third, common mistakes that someone less experienced should watch out for in a SaaS pricing and gross margin audit:
> - Number one: omitting the `FALSE` exact-match fourth argument in `VLOOKUP` or forgetting absolute dollar signs (`$A$2:$D$6`) on the catalog lookup range, which causes lookup references to shift when filled down.
> - Number two: evaluating sales orders solely on top-line Net ARR without deducting seat-level hosting COGS—since a large enterprise order with a `35%` to `40%` discount can generate high top-line revenue while eroding gross margin well below the `65%` profitability threshold.
> - Number three: summing margin percentages in a Pivot Table instead of changing the aggregation function from `SUM` to `AVERAGE`, which produces meaningless percentage totals above `100%`.
>
> All deliverables are exported and ready for packaging. Thank you for watching."

---

## Part 6: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

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
2. Calculate net ARR, total COGS, gross margin percentage, and policy status across all 30 enterprise orders, and apply conditional formatting to flag orders breaching the 65% gross margin floor.
3. Build a Pivot Table, an interactive Region Data Slicer, and a margin comparison chart summarizing Net ARR and Gross Margin by SKU and Region, and export the completed workbook as an Excel file.
4. Assemble the 3-slide Q4 Deal Desk Pricing & Margin Review Deck in Google Slides with the embedded margin chart, summary table, and Q1 discount guardrails, and export the presentation as a PDF.
```
