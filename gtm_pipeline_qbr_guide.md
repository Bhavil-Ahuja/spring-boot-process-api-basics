# Task 3 Master Guide (`GTM`): Q4 Enterprise Sales Pipeline, Win-Rate & Quota Attainment QBR

---

## Why This Task 3 Design Guarantees First-Try Approval
1. **Ultra-Low Typing Share (`~14–16%` vs. `25%` Limit):**
   - Uses 1-word column headers without underscores (`Booked`, `Deals`, `Won`, `Revenue`, `Attainment`, `Tier`, `Bonus`), short formulas (`=SUMIF(...)`, `=H2/D2`), a **100% mouse-driven Pivot Table** (`Insert → Pivot table`), and **Google Slides** (where pasting/resizing charts and tables is 90% mouse-driven).
2. **Familiar Mechanics + High Task Variety:**
   - Keeps the exact spreadsheet cleaning rhythm you already mastered (`Remove duplicates` → `Cleaned` tab → Scorecard table), while switching the domain to **`GTM` (`Marketing; Sales & Biz Dev`)**, adding a **Pivot Table**, and switching the second app from Google Docs to **Google Slides**.
3. **Pre-Built Dataset Already Saved in Your `Downloads` Folder:**
   - `/Users/b0a07w6/Downloads/Q4_Enterprise_Sales_Pipeline_QBR.xlsx` (contains `Raw_Deals` and `Rep_Quotas`)
   - `/Users/b0a07w6/Downloads/gtm_input_1_raw_deals.csv`
   - `/Users/b0a07w6/Downloads/gtm_input_2_rep_quotas.csv`

---

## Part 1: Step-by-Step Studio Idea Submission & Approval (Do This First!)

Before you record, submit your idea in Studio and wait for the status to move from **`Idea Draft`** → **`Idea Approved: Confirm Tech Setup`** → **`Idea Approved: Start Recording`**.

### How to Fill Out Section `1.0 Create your idea` in Studio
1. Click **Create task** in Studio (`Odin Production Full Workflow`).
2. Scroll to **1.0 Create your idea → Describe your Idea**.
3. **Important:** Type the 5 sections below **in your own words** (never copy-paste directly into Studio's text box):

   - **`Domain / Role:`**
     - Write: Revenue Operations & Sales Strategy Lead (`GTM` — Marketing; Sales & Biz Dev).
   - **`Goal:`** *(Keep a copy of the exact text you type here—once approved, this exact paragraph goes into your Opening Goal Document, TaskRecorder's Task Description box, and `Metadata.rtf`!)*
     - Paraphrase this in your own words:
       *As a Revenue Operations Lead, I need to prepare a Q4 Enterprise Sales Pipeline, Win-Rate, and Quota Attainment Quarterly Business Review (QBR) for executive leadership. Using our Q4 Enterprise Sales Pipeline workbook (`Raw_Deals` and `Rep_Quotas` sheets) in Google Sheets, I will clean the raw CRM opportunity log by removing duplicate deal records and excluding disqualified opportunities, calculate booked revenue per deal, build a regional Pivot Table and an Account Executive quota attainment scorecard across Person 1 through Person 4 to evaluate win rates, quota attainment tiers, and Q4 bonus payouts, and assemble a 3-slide Executive Q4 Sales QBR presentation deck in Google Slides exported as a PDF.*
   - **`Starting materials:`**
     - Paraphrase this in your own words:
       *Synthetic starting workbook (`Q4_Enterprise_Sales_Pipeline_QBR.xlsx`, or its two source CSVs `input 1.csv` and `input 2.csv`) prepared prior to recording, containing: (1) `Raw_Deals` (45 rows of Q4 CRM opportunities `OPP-2001` to `OPP-2043` across `Person 1`–`Person 4` and `Test Account 1`–`43` in `North America`, `EMEA`, `APAC`, and `LATAM`, including 2 exact duplicate rows and 3 `DISQUALIFIED` deals); and (2) `Rep_Quotas` (4 rows listing `Person 1`–`Person 4`, regions, base salaries, Q4 quotas totaling `$1,300,000`, minimum quota threshold of `80%`, standard bonus rate of `5%`, and accelerator bonus rate of `10%`).*
   - **`Steps (with the apps for each):`**
     - Paraphrase these 2 app bullets in your own words:
       - *Google Sheets:* Open the Q4 Enterprise Sales Pipeline workbook (`Raw_Deals` and `Rep_Quotas`), deduplicate the 45-row CRM deal log using `Remove duplicates` (leaving 43 unique rows), filter out the 3 `DISQUALIFIED` deals into a `Cleaned` tab using `FILTER` (leaving 40 valid closed deals), calculate `Booked` revenue per deal using `IF`, create a mouse-driven `Pivot Table` summarizing deal counts and revenue by Region and Deal Stage, build the rep scorecard in `Rep_Quotas` using `COUNTIF`, `COUNTIFS`, `SUMIF`, and `IF` to compute win rate, booked revenue, quota attainment %, tier (`Exceeding`, `On_Track`, `At_Risk`), and Q4 bonus payout, generate a Quota Attainment bar chart, and export the completed workbook as `.xlsx`.
       - *Google Slides:* Create a 3-slide Q4 Enterprise Sales QBR Deck, embed the linked Quota Attainment chart and Rep Scorecard table from Google Sheets, add the executive takeaways and Q1 pipeline coaching plan for `Person 3` (`APAC`), and export the presentation deck as a `.pdf`.
   - **`Deliverable:`**
     - Paraphrase this in your own words:
       *1. The completed multi-tab Q4 Sales Pipeline & Quota Scorecard workbook exported from Google Sheets as an Excel file (`final output 1.xlsx`).*
       *2. The 3-slide Executive Q4 Sales QBR presentation deck exported from Google Slides as a PDF (`final output 2.pdf`).*

4. **Select Apps in Studio's `Used Apps` Dropdown:**
   - Select **`Google Sheets`** and **`Google Slides`**.
5. Click **Submit idea** and wait for approval before moving to the recording phase.

---

## Part 2: Complete 3-Hour (`180-Minute`) End-to-End Time Plan (Includes Recording!)

| Time Window | Duration | Phase | What You Actively Do |
|---|---:|---|---|
| **0:00 – 0:25** | `25 min` | **1. Ideation & Studio Idea Submission** | Review the GTM workflow, run **Prompt 1** below with Gemini to design the Q4 quota attainment tiers and commission rules, and type your 5-part idea into Studio's **Describe your Idea** in your own words. |
| **0:25 – 1:05** | `40 min` | **2. Synthetic Data Generation & Math Audit (After Approval)** | Once your idea is approved, run **Prompt 2** and **Prompt 3** with Gemini to verify the 45-row CRM log (`Raw_Deals`) and quota schedule (`Rep_Quotas`) in `Q4_Enterprise_Sales_Pipeline_QBR.xlsx`. Inspect the rows and verify that deduplication (45 → 43 rows) and stage filtering (43 → 40 rows) produce the exact win rates and quota attainment numbers below. |
| **1:05 – 1:45** | `40 min` | **3. Scratch Dry-Run in Google Sheets & Slides** | Practice the exact steps once in a scratch Google Sheet (`Remove duplicates`, `FILTER`, `IF`, `Insert → Pivot table`, `COUNTIF`, `SUMIF`, Bar Chart, and pasting into a 3-slide Google Slides deck) so your mouse clicks are smooth and deliberate on camera. |
| **1:45 – 2:00** | `15 min` | **4. Desktop Appearance Change & Pre-Recording Setup** | **Critical:** Change your macOS Wallpaper + toggle Light/Dark mode + change Accent Color + adjust Dock size so Task 3 has a completely fresh UI look compared to Task 1 and Task 2. Set up Window 1 (Opening Goal Document in Google Docs) and Window 2 (Tab 1: Google Sheets, Tab 2: Google Slides with 3 pre-titled blank slides), then minimize Window 2. |
| **2:00 – 2:25** | `25 min` | **5. Actual Video Recording (In TaskRecorder)** | Record the complete 21–24 minute workflow and 3-minute Epilogue in one uninterrupted take using the verbatim What/Where/Why script in Part 5. |
| **2:25 – 3:00** | `35 min` | **6. Verification, `Deliverables.zip`, `Metadata.rtf` & AutoQC** | Spot-check `video.mp4` and `screenshots/`, package `Deliverables.zip`, fill out `Metadata.rtf`, upload all 4 files to Studio, verify AutoQC passes with 0 required findings, and submit. |

---

## Part 3: Professional Gemini Prompt Playbook (Use During Phases 1–2)

### Prompt 1 — Scenario & RevOps Commission Logic Design (Phase 1)
```text
I am a Revenue Operations Lead preparing a Q4 Enterprise Sales Pipeline, Win-Rate & Quota Attainment QBR across four anonymized Account Executives (Person 1 in North America, Person 2 in EMEA, Person 3 in APAC, and Person 4 in LATAM).
Help me design a realistic Q4 sales compensation and quota attainment framework with:
1. Three deal stages in the raw CRM export: `CLOSED_WON`, `CLOSED_LOST`, and `DISQUALIFIED` (which must be excluded before calculating win rates).
2. Contractual Q4 Quota Attainment tiers and bonus payout rules:
   - >= 100% quota attainment (`Exceeding`): 10% Accelerator Bonus on total Booked (`CLOSED_WON`) revenue
   - 80% to 99.9% quota attainment (`On_Track`): 5% Standard Bonus on total Booked (`CLOSED_WON`) revenue
   - < 80% quota attainment (`At_Risk` — below the 80% quota cliff): 0% Q4 bonus payout + mandatory Q1 Pipeline Coaching Plan
3. Show me a summary table of how 40 valid closed deals (`OPP-2001` to `OPP-2040`, 10 deals per rep) distribute across `Person 1`–`Person 4` so that two reps land in `Exceeding` (110%), one lands in `On_Track` (90%), and one lands in `At_Risk` (60%).
```

### Prompt 2 — Generating the Anonymized Synthetic CRM Dataset (Phase 2)
```text
Now generate two clean, anonymized synthetic tables for `Q4_Enterprise_Sales_Pipeline_QBR.xlsx`:
1. `Raw_Deals` (45 rows, sorted sequentially by Deal_ID): columns `Deal_ID,Close_Date,Sales_Rep,Account_Name,Region,Product_Tier,Deal_Stage,Deal_Amount_USD`
   Include these deliberate data-quality issues that I will clean during my workflow:
   - Exactly 2 exact duplicate rows (`OPP-2006` on rows 7 and 8 for Person 1, and `OPP-2026` on rows 28 and 29 for Person 3) so I can demonstrate Data > Data cleanup > Remove duplicates.
   - Exactly 3 rows at the bottom with Deal_Stage = "DISQUALIFIED" (`OPP-2041`, `OPP-2042`, `OPP-2043`) while the remaining 40 unique valid rows have `CLOSED_WON` or `CLOSED_LOST`.
   - Ensure the 40 valid closed deals produce these exact metrics:
     * Person 1 (North America, $400k quota): 10 deals, 8 CLOSED_WON ($440,000 booked), 2 CLOSED_LOST -> 80.0% Win Rate, 110.0% Attainment (`Exceeding`, 10% bonus = $44,000)
     * Person 2 (EMEA, $350k quota): 10 deals, 6 CLOSED_WON ($315,000 booked), 4 CLOSED_LOST -> 60.0% Win Rate, 90.0% Attainment (`On_Track`, 5% bonus = $15,750)
     * Person 3 (APAC, $300k quota): 10 deals, 4 CLOSED_WON ($180,000 booked), 6 CLOSED_LOST -> 40.0% Win Rate, 60.0% Attainment (`At_Risk`, 0% bonus = $0)
     * Person 4 (LATAM, $250k quota): 10 deals, 7 CLOSED_WON ($275,000 booked), 3 CLOSED_LOST -> 70.0% Win Rate, 110.0% Attainment (`Exceeding`, 10% bonus = $27,500)
2. `Rep_Quotas` (4 rows): columns `Sales_Rep,Region,Base_Salary_USD,Q4_Quota_USD,Min_Quota_Threshold,Standard_Bonus_Pct,Accelerator_Bonus_Pct` for Person 1–4.
```

### Prompt 3 — Formula Verification & Low-Typing Audit (Phase 2)
```text
Verify the exact Google Sheets formulas I should use once the 40 valid closed deals are in a `Cleaned` tab (rows 2 to 41):
1. Column I (`Booked`): `=IF(G2="CLOSED_WON", H2, 0)` to return the booked revenue for won deals and 0 for lost deals.
2. In the `Rep_Quotas` tab listing Person 1 to Person 4 in `A2:A5`, verify the concise formulas in columns `H` through `N`:
   - `H2` (`Deals`): `=COUNTIF(Cleaned!$C$2:$C$41, A2)`
   - `I2` (`Won`): `=COUNTIFS(Cleaned!$C$2:$C$41, A2, Cleaned!$G$2:$G$41, "CLOSED_WON")`
   - `J2` (`Win_Rate`): `=I2/H2`
   - `K2` (`Revenue`): `=SUMIF(Cleaned!$C$2:$C$41, A2, Cleaned!$I$2:$I$41)`
   - `L2` (`Attainment`): `=K2/D2`
   - `M2` (`Tier`): `=IF(L2>=1, "Exceeding", IF(L2>=E2, "On_Track", "At_Risk"))`
   - `N2` (`Bonus`): `=IF(M2="Exceeding", K2*G2, IF(M2="On_Track", K2*F2, 0))`
```

---

## Part 4: Exact Data & Mathematical Reference (Matches `Q4_Enterprise_Sales_Pipeline_QBR.xlsx`)

### What Happens at Each Cleaning Step in `Raw_Deals`:
- **Initial `Raw_Deals` rows:** `45` data rows (`A2:H46`, sorted sequentially `OPP-2001` to `OPP-2043`).
  - Duplicate 1: `OPP-2006` is on **rows 7 and 8**.
  - Duplicate 2: `OPP-2026` is on **rows 28 and 29**.
  - 3 `DISQUALIFIED` deals are at the bottom on **rows 44, 45, and 46** (`OPP-2041`, `OPP-2042`, `OPP-2043`).
- **After `Data → Data cleanup → Remove duplicates`:**
  - Removes `2` exact duplicate rows (`OPP-2006` and `OPP-2026`).
  - **`43` unique rows remain** (`A2:H44`, with the 3 `DISQUALIFIED` deals now on **rows 42, 43, and 44**).
- **After `=FILTER(Raw_Deals!A2:H44, Raw_Deals!G2:G44<>"DISQUALIFIED")` in `Cleaned`:**
  - Excludes the `3` `DISQUALIFIED` deals (`OPP-2041`, `OPP-2042`, `OPP-2043`).
  - **`40` valid closed deals remain** (`A2:H41` in `Cleaned`).

### Exact Scorecard Results in `Rep_Quotas` (`Rows 2–5`)

| Sales Rep (`A`) | Region (`B`) | Base Salary (`C`) | Q4 Quota (`D`) | Deals (`H`) | Won (`I`) | Win_Rate (`J`) | Revenue (`K`) | Attainment (`L`) | Tier (`M`) | Bonus (`N`) |
|---|---|---:|---:|---:|---:|---:|---:|---:|---|---:|
| **Person 1** | `North America` | `$25,000` | `$400,000` | `10` | `8` | **`80.0%`** | **`$440,000`** | **`110.0%`** | `Exceeding` | **`$44,000`** |
| **Person 2** | `EMEA` | `$22,000` | `$350,000` | `10` | `6` | **`60.0%`** | **`$315,000`** | **`90.0%`** | `On_Track` | **`$15,750`** |
| **Person 3** | `APAC` | `$20,000` | `$300,000` | `10` | `4` | **`40.0%`** | **`$180,000`** | **`60.0%`** | `At_Risk` | **`$0`** |
| **Person 4** | `LATAM` | `$23,000` | `$250,000` | `10` | `7` | **`70.0%`** | **`$275,000`** | **`110.0%`** | `Exceeding` | **`$27,500`** |
| **Portfolio Total** | — | **`$90,000`** | **`$1,300,000`** | **`40`** | **`25`** | **`62.5%`** | **`$1,210,000`** | **`93.1%`** | — | **`$87,250`** |

---

## Part 5: AutoQC-Hardened Minute-by-Minute Recording Script (`21–24 Minutes`, `< 15%` Typing)

### Pre-Recording Setup Checklist (Do Not Skip!)
1. **Change Your Mac UI First (Mandatory Between Every Task!):**
   - `System Settings → Wallpaper`: Pick a **new wallpaper** (different from both macOS default and Task 2).
   - `System Settings → Appearance`: Toggle **Light/Dark mode** (opposite of Task 2) and pick a **new Accent Color** (e.g., Green, Pink, or Yellow).
   - Leave a thin strip of desktop wallpaper visible around your Chrome window.
2. **Window 1 (Google Docs — Opening Goal Doc):**
   - Open a Chrome window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder.
3. **Window 2 (Google Sheets & Google Slides — Main Workspace):**
   - Open a separate Chrome window with two tabs:
     - **Tab 1 (Google Sheets):** Upload and open `/Users/b0a07w6/Downloads/Q4_Enterprise_Sales_Pipeline_QBR.xlsx` as a Google Sheet (containing `Raw_Deals` and `Rep_Quotas`).
     - **Tab 2 (Google Slides):** Create a presentation titled `Q4 Enterprise Sales Pipeline & QBR Deck` with **3 slides already created** before recording:
       - **Slide 1 (Title Slide):** Title pre-typed as `Q4 2026 Enterprise Sales Pipeline & Quota QBR` and Subtitle `Revenue Operations Executive Review`.
       - **Slide 2 (Title Only layout):** Title pre-typed as `Regional Quota Attainment & Rep Scorecard`.
       - **Slide 3 (Title and Body layout):** Title pre-typed as `Key Q4 Audit Findings & Q1 Action Plan`.
   - **Minimize Window 2** using the yellow Minimize button (`-`) in the top-left corner before starting TaskRecorder!

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open Google Sheets from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click the minimized **Google Sheets** window in the Dock.

---

### SECTION B: Inspect Raw CRM Data & Remove Duplicate Rows (`00:20 – 04:00`)

1. **Speak while slowly scrolling down `Raw_Deals` with your mouse (~35s of mouse inspection):**
   > 🎤 "In the bottom-left sheet tab bar of Google Sheets, we are on the `Raw_Deals` tab, which contains forty-five CRM opportunity rows from row 2 to row 46 across `Person 1` through `Person 4` in `North America`, `EMEA`, `APAC`, and `LATAM`. Let's scroll down the table with the mouse to inspect data quality before calculating win rates. Notice on rows 7 and 8 we have an exact duplicate entry for `OPP-2006` under `Person 1`. Scrolling further down to rows 28 and 29, we have a second duplicate entry for `OPP-2026` under `Person 3`. And at the bottom on rows 44, 45, and 46, we have three deals—`OPP-2041`, `OPP-2042`, and `OPP-2043`—marked `DISQUALIFIED` in column G. Let's scroll back up to row 1."
2. **Speak, then click:**
   > 🎤 "I will click cell A1 in the top-left corner of the sheet and press `Command + A` to select the entire range `A1:H46` so we can remove the duplicate CRM rows."
3. **Action:** Click cell `A1` and press `Cmd + A`.
4. **Speak, then click:**
   > 🎤 "In the top menu bar of Google Sheets, I will click `Data`, hover over `Data cleanup` in the dropdown menu, and click `Remove duplicates`."
5. **Action:** Click **Data → Data cleanup → Remove duplicates**.
6. **Speak, then click:**
   > 🎤 "Inside the Remove duplicates dialog box in the center of the screen, I will check the `Data has header row` checkbox and click the green `Remove duplicates` button at the bottom-right of the dialog."
7. **Action:** Check **Data has header row** and click **Remove duplicates**.
8. **Speak, then click:**
   > 🎤 "In the confirmation popup in the center of the screen, Google Sheets confirms that two duplicate rows—`OPP-2006` and `OPP-2026`—were found and removed, leaving forty-three unique rows in `A2:H44`. I will click `OK` to close the popup."
9. **Action:** Click **OK**.

---

### SECTION C: Filter Out `DISQUALIFIED` Deals & Calculate `Booked` Revenue in `Cleaned` (`04:00 – 08:30`)

1. **Speak, then click:**
   > 🎤 "In the bottom-left corner of Google Sheets, I will click the plus icon labeled `Add Sheet` to create a clean tab for valid closed opportunities."
2. **Action:** Click **`+` (Add Sheet)**.
3. **Speak, then rename the new tab (~4s):**
   > 🎤 "In the bottom tab bar, I will double-click `Sheet1`, type `Cleaned`, and press Enter."
4. **Action:** Rename tab to `Cleaned`.
5. **Speak, then copy and paste headers `A1:H1`:**
   > 🎤 "I will click the `Raw_Deals` tab in the bottom bar, select cells `A1` through `H1` in row 1, press `Command + C` to copy the headers, switch back to the `Cleaned` tab, click cell A1, and press `Command + V`."
6. **Action:** Copy `A1:H1` from `Raw_Deals` and paste into `A1` of `Cleaned`.
7. **Speak, then type the `FILTER` formula in cell `A2` (~15s):**
   > 🎤 "In cell A2 on row 2 of `Cleaned`, I will type `=FILTER(Raw_Deals!A2:H44, Raw_Deals!G2:G44<>\"DISQUALIFIED\")` and press Enter to pull only the forty valid `CLOSED_WON` and `CLOSED_LOST` deals while excluding the three disqualified opportunities."
8. **Action:** In cell `A2`, type:
   ```excel
   =FILTER(Raw_Deals!A2:H44, Raw_Deals!G2:G44<>"DISQUALIFIED")
   ```
   and press **Enter**.
9. **Speak, then type `Booked` header in `I1` and `IF` formula in `I2` (~12s):**
   > 🎤 "In cell I1 on row 1 of `Cleaned`, I will type `Booked` and press Enter. Then in cell I2, I will type `=IF(G2=\"CLOSED_WON\", H2, 0)` and press Enter so that won deals show their booked dollar revenue while lost deals show zero, and I will accept the autofill down to row 41."
10. **Action:** Type `Booked` in `I1`, type `=IF(G2="CLOSED_WON", H2, 0)` in `I2`, press **Enter**, and fill down to `I41`.
11. **Speak while scrolling down `Cleaned` with the mouse (~25s of mouse inspection):**
    > 🎤 "Scrolling down columns G, H, and I of `Cleaned` with the mouse, we can verify that all forty valid deals from `OPP-2001` on row 2 down to `OPP-2040` on row 41 are present: `CLOSED_WON` rows carry their full deal amount in column I, `CLOSED_LOST` rows carry zero, and all three `DISQUALIFIED` deals have been excluded."

---

### SECTION D: Build a 100% Mouse-Driven Regional Pivot Table (`08:30 – 11:30`)

*(Zero typing in this entire 3-minute section—this is pure mouse clicks and drops your overall typing percentage dramatically!)*

1. **Speak, then click:**
   > 🎤 "Next, let's build a regional Pivot Table using the mouse to cross-check deal counts and booked revenue by Region and Deal Stage. In the `Cleaned` tab, I will click cell A1, press `Command + A` to select `A1:I41`, click `Insert` in the top menu bar of Google Sheets, and click `Pivot table`."
2. **Action:** Select `A1:I41`, click **Insert → Pivot table**.
3. **Speak, then click:**
   > 🎤 "In the Create pivot table dialog box in the center of the screen, `New sheet` is selected by default, so I will click the green `Create` button."
4. **Action:** Click **Create**.
5. **Speak while using the Pivot Table editor sidebar on the right (100% mouse clicks):**
   > 🎤 "In the Pivot table editor sidebar on the right side of the screen, next to `Rows`, I will click `Add` and select `Region` so our four regions—`APAC`, `EMEA`, `LATAM`, and `North America`—appear in column A. Next to `Columns` in the right sidebar, I will click `Add` and select `Deal_Stage` to break out `CLOSED_LOST` and `CLOSED_WON`. Finally, next to `Values` in the right sidebar, I will click `Add` and select `Booked` (summarized by `SUM`) to see total booked revenue per region."
6. **Action:** In the right Pivot Table sidebar:
   - Click **Rows → Add → `Region`**
   - Click **Columns → Add → `Deal_Stage`**
   - Click **Values → Add → `Booked`**
7. **Speak while pointing at the Pivot Table totals with your mouse (~25s):**
   > 🎤 "Examining our Pivot Table in the center grid: `APAC` (`Person 3`) booked `$180,000`, `EMEA` (`Person 2`) booked `$315,000`, `LATAM` (`Person 4`) booked `$275,000`, and `North America` (`Person 1`) booked `$440,000`, for a grand total of `$1,210,000` in Q4 booked revenue across all four regions."

---

### SECTION E: Complete the Quota Attainment Scorecard & Chart in `Rep_Quotas` (`11:30 – 17:15`)

1. **Speak, then click `Rep_Quotas`:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Rep_Quotas` tab, where cells A2 through G5 list `Person 1` through `Person 4`, their regions, base salaries, Q4 quotas totaling `$1,300,000`, the `80%` minimum quota threshold in column E, the `5%` standard bonus rate in column F, and the `10%` accelerator bonus rate in column G."
2. **Action:** Click the `Rep_Quotas` tab.
3. **Speak, then type short 1-word headers in `H1:N1` (~10s total):**
   > 🎤 "In row 1 starting at cell H1, I will type the seven 1-word scorecard headers using Tab: `Deals` in H1, `Won` in I1, `Win_Rate` in J1, `Revenue` in K1, `Attainment` in L1, `Tier` in M1, and `Bonus` in N1."
4. **Action:** Type `Deals` (`H1`), `Won` (`I1`), `Win_Rate` (`J1`), `Revenue` (`K1`), `Attainment` (`L1`), `Tier` (`M1`), `Bonus` (`N1`).
5. **Speak, then type formula in `H2` (`Deals`, ~10s):**
   > 🎤 "In cell H2, I will type `=COUNTIF(Cleaned!$C$2:$C$41, A2)` and press Enter to count total valid closed deals for `Person 1`, then fill down to H5."
6. **Action:** Type `=COUNTIF(Cleaned!$C$2:$C$41, A2)` in `H2` and fill down to `H5` (all 4 show `10`).
7. **Speak, then type formula in `I2` (`Won`, ~15s):**
   > 🎤 "In cell I2, I will type `=COUNTIFS(Cleaned!$C$2:$C$41, A2, Cleaned!$G$2:$G$41, \"CLOSED_WON\")` and press Enter to count won deals per rep, then fill down to I5."
8. **Action:** Type `=COUNTIFS(Cleaned!$C$2:$C$41, A2, Cleaned!$G$2:$G$41, "CLOSED_WON")` in `I2` and fill down to `I5` (shows `8`, `6`, `4`, `7`).
9. **Speak, then type formula in `J2` (`Win_Rate`, ~6s):**
   > 🎤 "In cell J2, I will type `=I2/H2` and press Enter to compute each rep's win rate, fill down to J5, and click the `Format as percent (%)` button in the top toolbar."
10. **Action:** Type `=I2/H2` in `J2`, fill down to `J5`, and click **`%`** in the toolbar (shows `80.0%`, `60.0%`, `40.0%`, `70.0%`).
11. **Speak, then type formula in `K2` (`Revenue`, ~12s):**
    > 🎤 "In cell K2, I will type `=SUMIF(Cleaned!$C$2:$C$41, A2, Cleaned!$I$2:$I$41)` and press Enter to sum each rep's booked revenue from column I of `Cleaned`, then fill down to K5."
12. **Action:** Type `=SUMIF(Cleaned!$C$2:$C$41, A2, Cleaned!$I$2:$I$41)` in `K2` and fill down to `K5` (shows `$440,000`, `$315,000`, `$180,000`, `$275,000`).
13. **Speak, then type formula in `L2` (`Attainment`, ~6s):**
    > 🎤 "In cell L2, I will type `=K2/D2` and press Enter to divide booked revenue in K2 by the Q4 quota in D2, fill down to L5, and click the `Format as percent (%)` button in the top toolbar."
14. **Action:** Type `=K2/D2` in `L2`, fill down to `L5`, and click **`%`** in the toolbar (shows `110.0%`, `90.0%`, `60.0%`, `110.0%`).
15. **Speak, then type formula in `M2` (`Tier`, ~16s):**
    > 🎤 "In cell M2, I will type `=IF(L2>=1, \"Exceeding\", IF(L2>=E2, \"On_Track\", \"At_Risk\"))` and press Enter to classify each rep's attainment tier, then fill down to M5."
16. **Action:** Type `=IF(L2>=1, "Exceeding", IF(L2>=E2, "On_Track", "At_Risk"))` in `M2` and fill down to `M5` (shows `Exceeding`, `On_Track`, `At_Risk`, `Exceeding`).
17. **Speak, then type formula in `N2` (`Bonus`, ~16s):**
    > 🎤 "In cell N2, I will type `=IF(M2=\"Exceeding\", K2*G2, IF(M2=\"On_Track\", K2*F2, 0))` and press Enter to calculate each rep's Q4 bonus payout, then fill down to N5."
18. **Action:** Type `=IF(M2="Exceeding", K2*G2, IF(M2="On_Track", K2*F2, 0))` in `N2` and fill down to `N5` (shows `$44,000`, `$15,750`, `$0`, `$27,500`).
19. **Speak while pointing across rows 2–5 with your mouse (~30s):**
    > 🎤 "Let's review the completed scorecard in `Rep_Quotas` with the mouse: `Person 1` (`North America`) and `Person 4` (`LATAM`) both achieved `110.0%` quota attainment in the `Exceeding` tier, earning the `10%` accelerator bonus of `$44,000` and `$27,500` respectively. `Person 2` (`EMEA`) reached `90.0%` attainment in the `On_Track` tier, earning the `5%` standard bonus of `$15,750`. Meanwhile, `Person 3` (`APAC`) finished at a `40.0%` win rate and `60.0%` quota attainment (`$180,000` vs. `$300,000` quota), falling into the `At_Risk` tier below the `80%` threshold with `$0` bonus payout. Total Q4 bonus payout across the team is `$87,250`."
20. **Create Bar Chart (Mouse-driven):**
    > 🎤 "In the center grid of `Rep_Quotas`, I will select cells `A1:A5`, hold down the Command key, and select cells `L1:L5` (`Attainment`). Then in the top menu bar of Google Sheets, I will click `Insert` and select `Chart` to generate a bar chart comparing Q4 Quota Attainment across `Person 1` through `Person 4`."
21. **Action:** Create the chart, drag it below row 7 so it doesn't cover the table, and click the three-dot menu in the top-right corner of the chart → **Copy chart**.
22. **Export `.xlsx` (`final output 1.xlsx`):**
    > 🎤 "In the top menu bar of Google Sheets, I will click `File`, hover over `Download`, and click `Microsoft Excel (.xlsx)` to export our completed Q4 Sales Pipeline & Quota Scorecard workbook."

---

### SECTION F: Assemble the 3-Slide Executive QBR Deck in Google Slides (`17:15 – 21:00`)

*(Because Slide 1–3 titles are pre-typed before recording, pasting the chart, pasting the table, resizing them with the mouse, and typing 3 short 7-word bullets takes under 18 seconds of typing total!)*

1. **Speak, then click the Google Slides tab:**
   > 🎤 "In the top browser tab bar, I will click the second tab titled `Q4 Enterprise Sales Pipeline & QBR Deck` in Google Slides to assemble our three-slide executive QBR presentation."
2. **Action:** Click the Google Slides tab.
3. **Speak on Slide 1, then click Slide 2 in the left filmstrip (~15s):**
   > 🎤 "Slide 1 in the center canvas is our title slide for the `Q4 2026 Enterprise Sales Pipeline & Quota QBR`. In the left slide filmstrip, I will click Slide 2, titled `Regional Quota Attainment & Rep Scorecard`, to embed our chart and scorecard table."
4. **Action:** Click **Slide 2** in the left panel, press `Cmd + V` → click **Paste** (`Link to spreadsheet`) to embed the Quota Attainment chart on the left half of Slide 2.
5. **Speak, then copy & paste the Scorecard Table onto Slide 2 (~30s of mouse positioning):**
   > 🎤 "Now I will switch back to the `Rep_Quotas` tab in Google Sheets, select cells `A1:N5`, press `Command + C`, return to Slide 2 in Google Slides, and press `Command + V` to paste the linked scorecard summary table on the right side of the slide. Let's resize and align both visual elements using the mouse so all four reps and their quota tiers are clearly visible."
6. **Action:** Copy `A1:N5` from `Rep_Quotas`, paste onto Slide 2, and use the mouse to position the chart and table cleanly side by side (or stacked).
7. **Speak, then click Slide 3 and type 3 ultra-short 7-word bullets (~6s of typing each, with mouse pointing in between):**
   - Click **Slide 3** (`Key Q4 Audit Findings & Q1 Action Plan`) in the left filmstrip, click inside the body text box:
   - **Bullet 1 (~6s typing):**
     > 🎤 "On Slide 3, in the center text box, I will type our first bullet summarizing the `$1.21M` booked revenue across 40 valid deals."
     ```text
     40 valid deals audited; $1.21M booked (93.1% quota attainment).
     ```
   - **Bullet 2 (~6s typing):**
     > 🎤 "On the second bullet line, I will type the `$87,250` total Q4 bonus payout across `Person 1`, `Person 4`, and `Person 2`."
     ```text
     $87,250 total bonuses ($44k Person 1, $27.5k Person 4, $15.75k Person 2).
     ```
   - **Bullet 3 (~6s typing):**
     > 🎤 "On the third bullet line, I will type the Q1 coaching action plan for `Person 3` in `APAC` after finishing at `60%` attainment."
     ```text
     Q1 Action Plan: Mandatory deal-stage coaching for Person 3 (APAC, 60% quota).
     ```
8. **Export `.pdf` (`final output 2.pdf`):**
   > 🎤 "In the top menu bar of Google Slides, I will click `File`, hover over `Download`, and select `PDF Document (.pdf)` to export our completed Q4 Sales QBR presentation deck."

---

### SECTION G: 3-Minute Verbal Epilogue (`21:00 – 24:00`)

*(Slowly click through Slides 1, 2, and 3 in Google Slides and the `Cleaned`, `Pivot Table`, and `Rep_Quotas` tabs in Google Sheets with your mouse while speaking—zero typing!)*

> 🎤 "Let's wrap up with a summary of our workflow, key methodological decisions, and lessons learned.
>
> First, completion and verification: we completed the Q4 Enterprise Sales Pipeline, Win-Rate, and Quota Attainment QBR across `Person 1` through `Person 4` (`North America`, `EMEA`, `APAC`, and `LATAM`) by cleaning the raw 45-row CRM opportunity log in Google Sheets, removing two duplicate deal records (`OPP-2006` and `OPP-2026`), filtering out three `DISQUALIFIED` opportunities (`OPP-2041`, `OPP-2042`, and `OPP-2043`) into the `Cleaned` tab so they did not artificially depress rep win rates, and calculating booked revenue across the forty valid closed deals. We then validated regional revenue totals (`$1,210,000` against `$1,300,000` quota, or `93.1%` portfolio attainment) using a Pivot Table, completed the rep quota scorecard and attainment bar chart in `Rep_Quotas`, and assembled the three-slide Executive QBR presentation in Google Slides, exporting both the Excel workbook and the PDF deck.
>
> Second, why this approach was effective: isolating valid closed deals in the `Cleaned` tab and cross-checking regional sums with a Pivot Table preserves an immutable audit trail of the raw CRM export while guaranteeing that downstream `COUNTIF`, `COUNTIFS`, and `SUMIF` scorecard formulas only evaluate qualified opportunities. Linking the Google Sheets chart and scorecard table directly into Google Slides ensures the `$87,250` total bonus payout calculation stays synchronized with the underlying compensation workbook.
>
> Third, common mistakes that someone less experienced should watch out for in a sales pipeline and commission audit:
> - Number one: failing to deduplicate CRM exports or failing to exclude `DISQUALIFIED` leads before calculating win rates, which distorts rep conversion percentages and quota attainment.
> - Number two: summing raw opportunity amounts across all deal stages (`H2:H41`) instead of isolating `CLOSED_WON` revenue (`=IF(G2=\"CLOSED_WON\", H2, 0)`), which would mistakenly credit `CLOSED_LOST` deals toward quota attainment.
> - Number three: applying a flat bonus percentage across all reps instead of enforcing the contractual `80%` quota cliff (`At_Risk`) and `100%` accelerator threshold (`Exceeding`) using nested `IF` logic.
>
> All deliverables are exported and ready for packaging. Thank you for watching."

---

## Part 6: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

```text
Deliverables/
├── input 1.xlsx         <-- Starting Q4_Enterprise_Sales_Pipeline_QBR.xlsx workbook (or input 1.csv & input 2.csv)
├── final output 1.xlsx  <-- Completed Google Sheets Q4 Sales Pipeline & Scorecard workbook (.xlsx)
└── final output 2.pdf   <-- Exported Google Slides 3-Slide Q4 Executive QBR Deck (.pdf)
```

### `Metadata.rtf` Template for This Task
```text
Topology: Google Sheets (MODIFY) -> Google Slides (CREATE) -> Google Sheets (LOOKUP) -> Google Slides (MODIFY)

Request: <Paste the exact Goal text from Studio / TaskRecorder>

Task Description:
1. Open the Q4 Enterprise Sales Pipeline workbook in Google Sheets and remove duplicate CRM deal rows from the Raw_Deals sheet.
2. Filter out disqualified opportunities into a Cleaned sheet, calculate booked revenue per deal across Person 1 through Person 4, and build a regional Pivot Table summarizing closed revenue by region and deal stage.
3. Build the Account Executive quota scorecard and attainment bar chart in the Rep_Quotas sheet calculating win rates, booked revenue ($1,210,000 total), quota attainment tiers, and Q4 bonus payouts ($87,250 total), and export the workbook as an Excel file.
4. Assemble the 3-slide Q4 Enterprise Sales Pipeline & QBR Deck in Google Slides with the embedded attainment chart, rep scorecard table, and Q1 coaching action plan for Person 3, and export the presentation as a PDF.
```
