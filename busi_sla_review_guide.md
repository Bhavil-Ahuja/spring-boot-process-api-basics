# Task 2 Master Guide (`BUSI`): Q3 Vendor SLA & Incident Performance Audit

---

## Part 1: Step-by-Step Studio Idea Submission & Approval (Do This First!)

Before you record, submit your idea in Studio and wait for the status to move from **`Idea Draft`** → **`Idea Approved: Confirm Tech Setup`** → **`Idea Approved: Start Recording`**.

### How to Fill Out Section `1.0 Create your idea` in Studio
1. Click **Create task** in Studio (`Odin Production Full Workflow`).
2. Scroll to **1.0 Create your idea → Describe your Idea**.
3. **Important:** Type the 5 sections below **in your own words** (never copy-paste directly into Studio's text box):

   - **`Domain / Role:`**
     - Write: Business Operations & Vendor Management Lead (`BUSI` — Consulting & Business Operations; Product Management).
   - **`Goal:`** *(Keep a copy of the exact text you type here—once approved, this exact paragraph goes into your Opening Goal Document, TaskRecorder's Task Description box, and `Metadata.rtf`!)*
     - Paraphrase this in your own words:
       *As a Business Operations Lead, I need to conduct a Q3 IT Vendor SLA & Incident Performance Audit for leadership. Using our Q3 Vendor SLA Performance Audit workbook (`Raw_Incidents` and `Contract_Terms` sheets) in Google Sheets, I will clean the raw incident log by removing duplicate tickets and excluding cancelled incidents, calculate per-ticket SLA overrun hours and breach flags across P1, P2, and P3 severities, build a vendor scorecard and compliance bar chart across Test Company 1 through Test Company 4 to determine each vendor's SLA tier and Q3 financial penalty credit, and compile an executive Q3 Vendor SLA Audit & Remediation Memo in Google Docs exported as a PDF.*
   - **`Starting materials:`**
     - Paraphrase this in your own words:
       *Synthetic starting workbook (`Q3 Vendor SLA Performance Audit.xlsx`, or its two source CSVs `input 1.csv` and `input 2.csv`) prepared prior to recording, containing: (1) `Raw_Incidents` (45 rows of Q3 vendor tickets `TKT-1001` to `TKT-1043` across Test Company 1–4, including 2 exact duplicate rows and 3 `CANCELLED` rows); and (2) `Contract_Terms` (4 rows listing `Person 1`–`Person 4`, monthly retainers, Q3 spend totaling `$195,000`, target SLA compliance of `90%`, warning penalty of `5%`, and breach penalty of `15%`).*
   - **`Steps (with the apps for each):`**
     - Paraphrase these 2 app bullets in your own words:
       - *Google Sheets:* Open the Q3 Vendor SLA Performance Audit workbook (`Raw_Incidents` and `Contract_Terms`), deduplicate the 45-row incident log using `Remove duplicates` (leaving 43 unique rows), filter out the 3 `CANCELLED` tickets into a `Cleaned_Incidents` tab using `FILTER` (leaving 40 valid `RESOLVED` rows), calculate `Overrun_Hours` (`MAX`) and `SLA_Status` (`IF`) per ticket, build the vendor scorecard in `Contract_Terms` using `COUNTIF`, `COUNTIFS`, and nested `IF` formulas to compute each vendor's compliance rate, SLA tier (`Compliant`, `Warning`, `Breach`), and dollar penalty credit, create a bar chart comparing compliance across vendors, and download the finished workbook as `.xlsx`.
       - *Google Docs:* Create the executive Q3 Vendor SLA Audit & Remediation Memo, embed the linked vendor compliance chart and scorecard summary table from Google Sheets, write the audit findings and 30-day Corrective Action Plan for the breaching vendor (`Test Company 3`), and download the final memo as a `.pdf`.
   - **`Deliverable:`**
     - Paraphrase this in your own words:
       *1. The completed multi-tab SLA audit workbook exported from Google Sheets as an Excel file (`final output 1.xlsx`).*
       *2. The formatted Q3 Vendor SLA Audit & Remediation Memo exported from Google Docs as a PDF (`final output 2.pdf`).*

4. **Select Apps in Studio's `Used Apps` Dropdown:**
   - Select **`Google Sheets`** and **`Google Docs`**.
5. Click **Submit idea** and wait for approval before moving to the recording phase.

---

## Part 2: Complete 3-Hour (`180-Minute`) End-to-End Time Plan (Includes Recording!)

All work—including your Gemini interactions, idea submission, synthetic data creation, scratch practice, the **actual 23-minute video recording**, and packaging/AutoQC—fits cleanly inside **3 hours (180 minutes)**:

| Time Window | Duration | Phase | What You Actively Do |
|---|---:|---|---|
| **0:00 – 0:25** | `25 min` | **1. Ideation & Studio Idea Submission** | Review the guidelines in the Writer Handbook, run **Prompt 1** below with Gemini to design the vendor SLA rules and penalty tiers, and type your 5-part idea into Studio's **Describe your Idea** in your own words. *(Pause timer while waiting for approval if approval isn't immediate.)* |
| **0:25 – 1:05** | `40 min` | **2. Synthetic Data Generation & Math Audit (After Approval)** | Once your idea is approved, run **Prompt 2** and **Prompt 3** with Gemini to generate and verify the 45-row incident log (`Raw_Incidents`) and contract schedule (`Contract_Terms`) in `Q3 Vendor SLA Performance Audit.xlsx`. Inspect the rows and verify that deduplication (45 → 43 rows) and status filtering (43 → 40 rows) produce the exact compliance percentages below. |
| **1:05 – 1:45** | `40 min` | **3. Scratch Dry-Run in Google Sheets & Docs** | Practice the exact steps once in a scratch Google Sheet (`Remove duplicates`, `FILTER`, `MAX`, `IF`, `COUNTIFS`, Bar Chart, and copying the chart into Google Docs) so your mouse clicks are smooth and deliberate on camera. |
| **1:45 – 2:00** | `15 min` | **4. Desktop Appearance Change & Pre-Recording Setup** | Change your macOS Wallpaper + Light/Dark mode + Accent Color + Dock size (Task Variety requirement). Open the Goal Document in Window 1, set up Window 2 with Google Sheets (`Q3 Vendor SLA Performance Audit` with `Raw_Incidents` and `Contract_Terms`) and Google Docs, minimize Window 2, and check TaskRecorder + Accessibility Inspector. |
| **2:00 – 2:25** | `25 min` | **5. Actual Video Recording (In TaskRecorder)** | Record the complete 22–24 minute workflow and 3-minute Epilogue in one uninterrupted take using the verbatim What/Where/Why script in Part 5. |
| **2:25 – 3:00** | `35 min` | **6. Verification, `Deliverables.zip`, `Metadata.rtf` & AutoQC** | Spot-check `video.mp4` and the `screenshots/` count, package `Deliverables.zip`, fill out `Metadata.rtf`, upload all 4 files to Studio, run AutoQC, and submit. |

---

## Part 3: Professional Gemini Prompt Playbook (Use During Phases 1–2)

### Prompt 1 — Scenario & Business Logic Design (Phase 1)
```text
I am a Business Operations Manager preparing a Q3 Vendor SLA & Incident Performance Audit across four anonymized IT operations vendors (Test Company 1, Test Company 2, Test Company 3, and Test Company 4) managed by Person 1 through Person 4.
Help me design a realistic SLA contract framework with:
1. Three incident severities (P1 - Critical, P2 - High, P3 - Medium) and their target resolution times in hours (4h, 8h, 24h).
2. Contractual SLA compliance thresholds:
   - >= 90% on-time resolution: Compliant (0% credit penalty)
   - 80% to 89.9% on-time resolution: Warning Tier (5% Q3 invoice credit penalty)
   - < 80% on-time resolution: Breach / Remediation Tier (15% Q3 invoice credit penalty + mandatory Corrective Action Plan)
3. Show me a summary table of how 40 valid Q3 tickets (TKT-1001 to TKT-1040) can be distributed across Test Company 1–4 so that one vendor lands in Breach (60%), one lands in Warning (80%), and two are Compliant (90% and 100%).
```

### Prompt 2 — Generating the Anonymized Synthetic Dataset with Data-Quality Traps (Phase 2)
```text
Now generate two clean, anonymized synthetic tables for `Q3 Vendor SLA Performance Audit.xlsx`:
1. `Raw_Incidents` (45 rows): columns `Ticket_ID,Date_Opened,Vendor,Severity,Category,Status,Target_SLA_Hours,Actual_Resolution_Hours`
   Include these deliberate data-quality issues that I will clean during my workflow:
   - Exactly 2 exact duplicate rows (`TKT-1006` for Test Company 1 and `TKT-1026` for Test Company 3) so I can demonstrate Data > Data cleanup > Remove duplicates.
   - Exactly 3 rows with Status = "CANCELLED" (`TKT-1041`, `TKT-1042`, `TKT-1043`) while the remaining 40 unique valid rows have Status = "RESOLVED".
   - Ensure the 40 valid RESOLVED tickets produce these exact SLA compliance rates when comparing Actual_Resolution_Hours <= Target_SLA_Hours:
     * Test Company 1: 10 resolved tickets, 9 within SLA, 1 breached (`TKT-1010`) -> 90.0% (Compliant)
     * Test Company 2: 10 resolved tickets, 8 within SLA, 2 breached (`TKT-1019`, `TKT-1020`) -> 80.0% (Warning, 5% credit)
     * Test Company 3: 10 resolved tickets, 6 within SLA, 4 breached (`TKT-1027`, `TKT-1028`, `TKT-1029`, `TKT-1030`) -> 60.0% (Breach, 15% credit)
     * Test Company 4: 10 resolved tickets, 10 within SLA, 0 breached -> 100.0% (Compliant)
2. `Contract_Terms` (4 rows): columns `Vendor,Contract_Owner,Monthly_Retainer_USD,Q3_Total_Spend_USD,Target_Compliance_Pct,Warning_Penalty_Pct,Breach_Penalty_Pct` for Test Company 1–4 and Person 1–4.
```

### Prompt 3 — Formula Verification & Edge-Case Audit (Phase 2)
```text
Verify the exact Google Sheets formulas I should use once the 40 valid RESOLVED rows are in a clean `Cleaned_Incidents` tab (rows 2 to 41):
1. Column I (`Overrun_Hours`): `=MAX(0, H2 - G2)` to calculate hours over the target SLA without negative numbers.
2. Column J (`SLA_Status`): `=IF(H2 <= G2, "Met", "Breached")` to classify each ticket.
3. In the `Contract_Terms` tab listing Test Company 1 to Test Company 4 in `A2:A5`, verify the `COUNTIF`, `COUNTIFS`, and `IF` formulas in columns `H` through `L` (`Resolved_Tickets`, `Breached_Tickets`, `SLA_Compliance_Pct`, `SLA_Tier`, and `Q3_Penalty_USD`).
```

---

## Part 4: Exact Data & Mathematical Reference (Matches Your Uploaded `.xlsx`)

### What Happens at Each Cleaning Step in `Raw_Incidents`:
- **Initial `Raw_Incidents` rows:** `45` data rows (`A2:H46`, plus header row `A1:H1`).
- **After `Data → Data cleanup → Remove duplicates`:**
  - Removes `2` exact duplicate rows (`TKT-1006` and `TKT-1026`).
  - **`43` unique rows remain** (`A2:H44`).
- **After `=FILTER(Raw_Incidents!A2:H44, Raw_Incidents!F2:F44="RESOLVED")` in `Cleaned_Incidents`:**
  - Excludes `3` `CANCELLED` tickets (`TKT-1041`, `TKT-1042`, `TKT-1043`).
  - **`40` valid `RESOLVED` rows remain** (`A2:H41` in `Cleaned_Incidents`).

### Exact Scorecard Results in `Contract_Terms` (`Rows 2–5`)

| Vendor (`A`) | Owner (`B`) | Monthly Retainer (`C`) | Q3 Total Spend (`D`) | Resolved Tickets (`H`) | Breached Tickets (`I`) | SLA Compliance % (`J`) | SLA Tier (`K`) | Q3 Penalty USD (`L`) | Breached Ticket IDs & Categories |
|---|---|---:|---:|---:|---:|---:|---|---:|---|
| **Test Company 1** | `Person 1` | `$15,000` | `$45,000` | `10` | `1` | **`90.0%`** | `Compliant` | **`$0`** | `TKT-1010` (P1 Database: 11h vs 4h) |
| **Test Company 2** | `Person 2` | `$12,000` | `$36,000` | `10` | `2` | **`80.0%`** | `Warning` | **`$1,800`** | `TKT-1020` (P1 Storage: 9h vs 4h), `TKT-1019` (P2 Network: 12h vs 8h) |
| **Test Company 3** | `Person 3` | `$18,000` | `$54,000` | `10` | `4` | **`60.0%`** | `Breach` | **`$8,100`** | `TKT-1028` (P1 Auth: 11h vs 4h), `TKT-1029` (P1 Database: 14h vs 4h), `TKT-1027` (P2 Network: 12h vs 8h), `TKT-1030` (P2 Database: 16h vs 8h) |
| **Test Company 4** | `Person 4` | `$20,000` | `$60,000` | `10` | `0` | **`100.0%`** | `Compliant` | **`$0`** | *(None — all 10 met SLA)* |
| **Total / Portfolio** | — | **`$65,000`** | **`$195,000`** | **`40`** | **`7`** | **`82.5%`** | — | **`$9,900`** | — |

---

## Part 5: AutoQC-Hardened Minute-by-Minute Recording Script (`20–25 Minutes`)

### Pre-Recording Window Setup (Critical!)
1. **Change Desktop Appearance first (Fixes Reviewer Theo's UI Setup Note):**
   - Change your macOS **Wallpaper** (`System Settings → Wallpaper`, pick a non-default wallpaper).
   - Toggle **Light/Dark mode** and change **Accent Color** (`System Settings → Appearance`, e.g., Purple or Orange).
   - Slightly adjust **Dock size** (`System Settings → Desktop & Dock`) and leave a small border around your Chrome window so the new wallpaper is visible.
2. **Window 1 (Google Docs — Opening Goal Doc):** Open a browser window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder.
3. **Window 2 (Google Sheets & Google Docs — Main Workspace):** Open a separate Chrome window with two tabs:
   - Tab 1: **Google Sheets** with `Q3 Vendor SLA Performance Audit.xlsx` opened as a Google Sheet (containing the `Raw_Incidents` and `Contract_Terms` tabs).
   - Tab 2: **Google Docs** titled `Q3 Vendor SLA Audit & Remediation Memo` (blank document with title header ready).
   - **Minimize Window 2** using the yellow Minimize button (`-`) in the top-left corner before starting TaskRecorder!

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open Google Sheets from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click the minimized **Google Sheets** window in the Dock on the left side of the screen.

---

### SECTION B: Inspect Raw Data & Remove Duplicate Rows (`00:20 – 04:30`)

1. **Speak while slowly scrolling down `Raw_Incidents` with your mouse (~35s of mouse-driven inspection to boost mouse time):**
   > 🎤 "In the bottom-left sheet tab bar of Google Sheets, we are on the `Raw_Incidents` tab, which contains forty-five incident rows from row 2 to row 46 across Test Company 1 through Test Company 4. Before we run any formulas, let's scroll down the table in the center grid to inspect the data quality. Notice on rows 6 and 7 we have a duplicate entry for `TKT-1006`, further down we have a duplicate entry for `TKT-1026`, and at the bottom on rows 44 through 46 we have three tickets—`TKT-1041`, `TKT-1042`, and `TKT-1043`—with a status of `CANCELLED` in column F. Let's scroll back up to row 1."
2. **Speak, then click:**
   > 🎤 "I will click cell A1 in the top-left corner of the sheet and press `Command + A` to select the entire table range `A1:H46` so we can remove the duplicate ticket records."
3. **Action:** Click cell `A1` and press `Cmd + A`.
4. **Speak, then click:**
   > 🎤 "In the top menu bar of Google Sheets, I will click `Data`, hover over `Data cleanup` in the dropdown menu, and click `Remove duplicates` to strip duplicate ticket entries."
5. **Action:** Click **Data → Data cleanup → Remove duplicates**.
6. **Speak, then click:**
   > 🎤 "Inside the Remove duplicates dialog box in the center of the screen, I will check the `Data has header row` checkbox at the top of the dialog, and then click the green `Remove duplicates` button at the bottom-right of the dialog."
7. **Action:** Check **Data has header row** and click **Remove duplicates**.
8. **Speak, then click:**
   > 🎤 "In the confirmation popup in the center of the screen, Google Sheets reports that two duplicate rows—`TKT-1006` and `TKT-1026`—were found and removed, and forty-three unique rows remain. I will click the green `OK` button inside the popup to close it."
9. **Action:** Click **OK**.

---

### SECTION C: Filter Out `CANCELLED` Tickets into `Cleaned` (`04:30 – 08:00`)

1. **Speak, then click:**
   > 🎤 "In the bottom-left corner of Google Sheets, I will click the plus icon labeled `Add Sheet` to create a new tab for our cleaned, resolved incidents."
2. **Action:** Click **`+` (Add Sheet)** in the bottom-left bar.
3. **Speak, then rename the new tab (~4s):**
   > 🎤 "In the bottom sheet tab bar of Google Sheets, I will double-click `Sheet1`, type `Cleaned`, and press Enter to name our filtered tab."
4. **Action:** Rename tab to `Cleaned`.
5. **Speak, then copy headers from `Raw_Incidents`:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Raw_Incidents` tab, select cells `A1` through `H1` in row 1 of the center grid, and press `Command + C` to copy the eight column headers."
6. **Action:** Copy `A1:H1` from `Raw_Incidents`.
7. **Speak, then paste headers into `Cleaned`:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Cleaned` tab, click cell A1 in the top-left corner of the grid, and press `Command + V` to paste the headers."
8. **Action:** Switch to `Cleaned`, click `A1`, and press `Cmd + V`.
9. **Speak, then type the `FILTER` formula in cell `A2` (~15s):**
   > 🎤 "In cell A2 on row 2 of the `Cleaned` tab, I will type `=FILTER(Raw_Incidents!A2:H44, Raw_Incidents!F2:F44=\"RESOLVED\")` and press Enter to pull only the forty resolved tickets and exclude the three cancelled tickets `TKT-1041`, `TKT-1042`, and `TKT-1043`."
10. **Action:** In cell `A2`, type:
    ```excel
    =FILTER(Raw_Incidents!A2:H44, Raw_Incidents!F2:F44="RESOLVED")
    ```
    and press **Enter**.
11. **Speak while scrolling down to row 41 with the mouse:**
    > 🎤 "Scrolling down to row 41 in the center grid of `Cleaned`, notice the filtered dataset ends on row 41, giving us forty valid resolved incidents from row 2 to row 41 with all cancelled tickets excluded."

---

### SECTION D: Calculate `Overrun` and `SLA` (`08:00 – 11:45`)

1. **Speak, then type short 1-word headers in `I1` and `J1` (~4s):**
   > 🎤 "Scrolling back to row 1 of `Cleaned`, I will click cell I1, type `Overrun`, press Tab to move to cell J1, type `SLA`, and press Enter to label our two calculated SLA columns."
2. **Action:** Type `Overrun` in `I1` and `SLA` in `J1`.
3. **Speak, then type formula in `I2` (~10s):**
   > 🎤 "In cell I2 on row 2 of `Cleaned`, I will type `=MAX(0, H2-G2)` and press Enter so that tickets resolved within target show zero overrun hours while breached tickets show the exact hours exceeded, and I will click the checkmark in the Suggested autofill popup to fill down to row 41."
4. **Action:** Type `=MAX(0, H2-G2)` in `I2`, press **Enter**, and accept autofill (or double-click the bottom-right fill handle of `I2` down to `I41`).
5. **Speak, then type formula in `J2` (~15s):**
   > 🎤 "In cell J2 on row 2 of `Cleaned`, I will type `=IF(H2<=G2, \"Met\", \"Breached\")` and press Enter to classify whether each incident met or breached its target SLA hours, then fill the formula down to cell J41."
6. **Action:** Type `=IF(H2<=G2, "Met", "Breached")` in `J2`, press **Enter**, and fill down to `J41`.
7. **Speak while slowly scrolling down columns `I` and `J` with the mouse (~30s of mouse inspection):**
   > 🎤 "Let's scroll down columns I and J in the center grid of `Cleaned` using the mouse to verify our row-level results. On row 11, `TKT-1010` for Test Company 1 took 11 hours against a 4-hour P1 SLA, showing 7 overrun hours and `Breached`. Scrolling further down to rows 20 and 21, Test Company 2 has two breached tickets (`TKT-1019` and `TKT-1020`). And on rows 28 through 31, Test Company 3 has four consecutive breached tickets (`TKT-1027` through `TKT-1030`), whereas Test Company 4 at the bottom has zero breaches across all ten of its tickets."

---

### SECTION E: Build the Vendor Scorecard & Chart in `Contract_Terms` (`11:45 – 17:15`)

1. **Speak, then click `Contract_Terms`:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Contract_Terms` tab, where cells A2 through G5 hold the contract owners `Person 1` through `Person 4`, monthly retainers, Q3 spend, and penalty percentages for `Test Company 1` through `Test Company 4`."
2. **Action:** Click the `Contract_Terms` tab.
3. **Speak, then type short 1-word headers in `H1:J1` (~6s):**
   > 🎤 "In cell H1 on row 1 of `Contract_Terms`, I will type `Resolved`, press Tab to cell I1 and type `Breached`, and press Tab to cell J1 and type `Compliance`."
4. **Action:** Type `Resolved` in `H1`, `Breached` in `I1`, and `Compliance` in `J1`.
5. **Speak, then type short 1-word headers in `K1:L1` (~4s):**
   > 🎤 "In cell K1 on row 1 of `Contract_Terms`, I will type `Tier`, press Tab to cell L1, type `Penalty`, and press Enter."
6. **Action:** Type `Tier` in `K1` and `Penalty` in `L1`.
7. **Speak, then type formula in `H2` (~10s):**
   > 🎤 "In cell H2 on row 2 of `Contract_Terms`, I will type `=COUNTIF(Cleaned!$C$2:$C$41, A2)` and press Enter to count the resolved tickets for Test Company 1, then fill down from H2 to H5."
8. **Action:** Type `=COUNTIF(Cleaned!$C$2:$C$41, A2)` in `H2` and fill down to `H5` (all 4 show `10`).
9. **Speak, then type formula in `I2` (~15s):**
   > 🎤 "In cell I2 on row 2 of `Contract_Terms`, I will type `=COUNTIFS(Cleaned!$C$2:$C$41, A2, Cleaned!$J$2:$J$41, \"Breached\")` and press Enter to count the breached tickets for each vendor, then fill down from I2 to I5."
10. **Action:** Type `=COUNTIFS(Cleaned!$C$2:$C$41, A2, Cleaned!$J$2:$J$41, "Breached")` in `I2` and fill down to `I5` (shows `1`, `2`, `4`, `0`).
11. **Speak, then type formula in `J2` (~10s):**
    > 🎤 "In cell J2 on row 2 of `Contract_Terms`, I will type `=(H2-I2)/H2` and press Enter to calculate the SLA compliance rate, fill down from J2 to J5, and click the `Format as percent (%)` button in the top toolbar of Google Sheets."
12. **Action:** Type `=(H2-I2)/H2` in `J2`, fill down to `J5`, and click **`%`** in the top toolbar (shows `90.0%`, `80.0%`, `60.0%`, `100.0%`).
13. **Speak, then type formula in `K2` (~20s):**
    > 🎤 "In cell K2 on row 2 of `Contract_Terms`, I will type `=IF(J2>=E2, \"Compliant\", IF(J2>=0.8, \"Warning\", \"Breach\"))` and press Enter to classify each vendor's SLA tier against the 90% target in column E, then fill down from K2 to K5."
14. **Action:** Type `=IF(J2>=E2, "Compliant", IF(J2>=0.8, "Warning", "Breach"))` in `K2` and fill down to `K5` (shows `Compliant`, `Warning`, `Breach`, `Compliant`).
15. **Speak, then type formula in `L2` (~20s):**
    > 🎤 "In cell L2 on row 2 of `Contract_Terms`, I will type `=IF(K2=\"Breach\", D2*G2, IF(K2=\"Warning\", D2*F2, 0))` and press Enter to compute the Q3 financial penalty credit in dollars, then fill down from L2 to L5."
16. **Action:** Type `=IF(K2="Breach", D2*G2, IF(K2="Warning", D2*F2, 0))` in `L2` and fill down to `L5` (shows `$0`, `$1,800`, `$8,100`, `$0`).
17. **Speak while pointing at rows 2–5 in `Contract_Terms` (~30s):**
    > 🎤 "Reviewing columns J, K, and L in the center grid of `Contract_Terms`: Test Company 1 is at 90% and Test Company 4 is at 100%, so both are Compliant with zero penalty. Test Company 2 is at 80% in the Warning tier, resulting in a 5% credit of $1,800 on its $36,000 Q3 spend. Test Company 3 dropped to 60% in the Breach tier with four breached tickets, triggering a 15% penalty credit of $8,100 on its $54,000 Q3 spend, for a total recovery of $9,900."
18. **Create Bar Chart (Mouse-driven):**
    > 🎤 "In the center grid of `Contract_Terms`, I will select cells `A1:A5`, hold down the Command key, and select cells `J1:J5`. Then in the top menu bar of Google Sheets, I will click `Insert` and select `Chart` to generate a bar chart comparing SLA compliance across Test Company 1 through Test Company 4."
19. **Action:** Create the chart, drag it below row 7 so it doesn't cover the table, and click the three-dot menu in the top-right corner of the chart → **Copy chart**.
20. **Export `.xlsx` (`final output 1.xlsx`):**
    > 🎤 "In the top menu bar of Google Sheets, I will click `File`, hover over `Download`, and click `Microsoft Excel (.xlsx)` to export our completed SLA audit workbook."

---

### SECTION F: Compile the Executive Audit Memo in Google Docs (`17:15 – 21:00`)

*(Note: Keep the 3 typed bullets here ultra-concise (8 words each) as written below, and spend ~20 seconds pointing with your mouse at the pasted chart and table between bullets—this easily cuts ~40 seconds of typing and drops you well below 25%!)*

1. **Speak, then click the Google Docs tab:**
   > 🎤 "In the top browser tab bar, I will click the second tab titled `Q3 Vendor SLA Audit & Remediation Memo` in Google Docs to draft the executive summary report."
2. **Action:** Click the Google Docs tab.
3. **Speak, then paste the chart:**
   > 🎤 "In the center page of Google Docs, below the first section heading, I will press `Command + V` and click `Paste` in the Link to spreadsheet dialog to embed our SLA compliance chart. Looking at the pasted chart in the center of the document, we can clearly see Test Company 4 at 100%, Test Company 1 at 90%, Test Company 2 at 80%, and Test Company 3 at 60%."
4. **Action:** Switch back to the Google Sheets tab briefly to copy `A1:L5` (`Cmd + C`), return to the Google Docs tab, and press `Cmd + V` below the second section heading to paste the linked scorecard summary table. Point with your mouse across the pasted table rows for ~15 seconds while narrating the columns.
5. **Speak, then type 3 ultra-concise executive summary bullets (~6s of typing each, with mouse pointing in between):**
   - **Bullet 1 (~6s typing):**
     > 🎤 "Below the Key Audit Findings heading in the center page of Google Docs, I will type our first bullet summarizing the 40 audited tickets and 82.5% portfolio compliance."
     ```text
     • 40 resolved tickets audited; 82.5% portfolio SLA compliance.
     ```
   - **Bullet 2 (~6s typing):**
     > 🎤 "On the second bullet line in the center page of Google Docs, I will type the $9,900 Q3 service credit recovery across Test Company 3 and Test Company 2."
     ```text
     • $9,900 total penalty ($8,100 Company 3; $1,800 Company 2).
     ```
   - **Bullet 3 (~6s typing):**
     > 🎤 "On the third bullet line in the center page of Google Docs, I will type the 30-day Corrective Action Plan requirement for Person 3 at Test Company 3."
     ```text
     • 30-day Corrective Action Plan required from Person 3.
     ```
6. **Export `.pdf` (`final output 2.pdf`):**
   > 🎤 "In the top menu bar of Google Docs, I will click `File`, hover over `Download`, and select `PDF Document (.pdf)` to export our completed executive audit memo."

---

### SECTION G: 3-Minute Verbal Epilogue (`21:00 – 24:00`)

*(Move your mouse slowly across the Google Doc and Google Sheet while delivering this summary—zero typing during these 3 minutes lowers your overall typing % even further!)*

> 🎤 "Let's wrap up with a summary of our workflow, key methodological decisions, and lessons learned.
>
> First, completion and verification: we completed the Q3 Vendor SLA and Incident Performance Audit across Test Company 1 through Test Company 4 by cleaning the raw 45-row incident log in Google Sheets, removing two duplicate ticket entries (`TKT-1006` and `TKT-1026`), filtering out three cancelled tickets (`TKT-1041`, `TKT-1042`, and `TKT-1043`) so they did not distort vendor resolution rates, and evaluating the forty valid resolved incidents against each severity's target SLA hours. We then built the vendor scorecard and compliance chart in `Contract_Terms` and compiled the executive remediation memo in Google Docs, exporting both the Excel workbook and the PDF report.
>
> Second, why this approach was effective: separating raw incident data from the filtered `Cleaned_Incidents` tab preserves an immutable audit trail of the original log while ensuring downstream `COUNTIF` and `COUNTIFS` scorecard formulas only evaluate valid resolved tickets. Linking the Google Sheets scorecard table and chart directly into the Google Docs executive memo ensures the $9,900 total penalty calculation ($8,100 from Test Company 3 and $1,800 from Test Company 2) stays synchronized with the underlying workbook.
>
> Third, common mistakes that someone less experienced should watch out for in an SLA audit:
> - Number one: failing to deduplicate ticket logs or failing to exclude cancelled tickets before calculating compliance percentages, which inflates total ticket counts and produces inaccurate penalty charges.
> - Number two: using simple averages of resolution hours across mixed severities instead of comparing each individual ticket's actual resolution time against its severity-specific target threshold—since a 6-hour resolution meets an 8-hour P2 SLA (`TKT-1002`) but breaches a 4-hour P1 SLA.
> - Number three: allowing negative overrun hours when a ticket finishes early; wrapping `H2 - G2` in `MAX(0, ...)` prevents early completions from offsetting late breaches.
>
> All deliverables are saved and ready for packaging. Thank you for watching."

---

## Part 6: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

```text
Deliverables/
├── input 1.csv          <-- Raw 45-row Q3 incident log (Test Company 1–4)
├── input 2.csv          <-- Contract_Terms schedule (Test Company 1–4, Person 1–4)
├── final output 1.xlsx  <-- Completed Google Sheets SLA Audit workbook (.xlsx)
└── final output 2.pdf   <-- Exported Google Docs Executive Audit Memo (.pdf)
```
*(Or if you used the single starting `.xlsx` workbook as your input instead of the two CSVs, name the starting `.xlsx` `input 1.xlsx`.)*

### `Metadata.rtf` Template for This Task
```text
Topology: Google Sheets (MODIFY) -> Google Docs (CREATE) -> Google Sheets (LOOKUP) -> Google Docs (MODIFY)

Request: <Paste the exact Goal text from Studio / TaskRecorder>

Task Description:
1. Open the Q3 Vendor SLA Performance Audit workbook in Google Sheets and remove duplicate ticket rows from the Raw_Incidents sheet.
2. Filter out cancelled tickets into a Cleaned_Incidents sheet and calculate SLA overrun hours and breach status per ticket across Test Company 1 through Test Company 4.
3. Build the vendor scorecard and compliance bar chart in the Contract_Terms sheet calculating SLA compliance rates, tier classifications, and Q3 penalty credits ($9,900 total), and export the workbook as an Excel file.
4. Draft the Q3 Vendor SLA Audit & Remediation Memo in Google Docs with the embedded scorecard table, compliance chart, and corrective action plan for Test Company 3, and export the final report as a PDF.
```
