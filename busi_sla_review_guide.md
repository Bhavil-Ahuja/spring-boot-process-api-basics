# Task 2 Master Guide (`BUSI`): Q3 Vendor SLA & Incident Performance Audit

---

## Part 1: Step-by-Step Studio Idea Submission & Approval (Do This First!)

Before you build the files or record, you must submit your idea in Studio and wait for the status to move from **`Idea Draft`** → **`Idea Approved: Confirm Tech Setup`** → **`Idea Approved: Start Recording`**.

### How to Fill Out Section `1.0 Create your idea` in Studio
1. Click **Create task** in Studio (make sure you are in `Odin Production Full Workflow`).
2. Scroll to **1.0 Create your idea → Describe your Idea**.
3. **Important:** Type the 5 sections below **in your own words** (never copy-paste directly into Studio's text box). Here are the exact details to include under each of the 5 required headings:

   - **`Domain / Role:`**
     - Write: Business Operations & Vendor Management Lead (`BUSI` — Consulting & Business Operations; Product Management).
   - **`Goal:`** *(Keep a copy of the exact text you type here—once approved, this exact paragraph goes into your Opening Goal Document, TaskRecorder's Task Description box, and `Metadata.rtf`!)*
     - Paraphrase this in your own words:
       *As a Business Operations Lead, I need to conduct a Q3 IT Vendor SLA & Incident Performance Audit for leadership. Using a raw Q3 incident log CSV and a vendor contract fee schedule CSV in Google Sheets, I will clean the log by removing duplicate tickets and excluding cancelled incidents, calculate per-ticket SLA overrun hours and breach flags across P1, P2, and P3 severities, build a vendor scorecard and compliance bar chart to determine each vendor's SLA tier and Q3 financial penalty credit, and compile an executive Q3 Vendor SLA Audit & Remediation Memo in Google Docs exported as a PDF.*
   - **`Starting materials:`**
     - Paraphrase this in your own words:
       *Two synthetic CSV files prepared prior to recording: (1) a 45-row Q3 vendor incident log (`vendor_incidents_q3.csv`) containing ticket IDs, timestamps, vendor names, severity levels, statuses (including duplicate and cancelled tickets), target SLA hours, and actual resolution hours; and (2) a vendor contract schedule (`vendor_contract_terms.csv`) listing monthly retainers, Q3 spend, target SLA compliance thresholds, and warning/breach credit penalty percentages for four vendors.*
   - **`Steps (with the apps for each):`**
     - Paraphrase these 2 app bullets in your own words:
       - *Google Sheets:* Import both CSV datasets into a single workbook, deduplicate the raw incident log using `Remove duplicates`, filter out `CANCELLED` tickets into a clean `Cleaned_Incidents` tab using `FILTER`, calculate `Overrun_Hours` (`MAX`) and `SLA_Status` (`IF`) for all 40 valid resolved incidents, build a vendor scorecard using `COUNTIF`, `COUNTIFS`, and nested `IF` formulas to compute each vendor's compliance rate, SLA tier (`Compliant`, `Warning`, `Breach`), and dollar penalty credit, create a bar chart comparing compliance across vendors, and download the finished workbook as `.xlsx`.
       - *Google Docs:* Create the executive Q3 Vendor SLA Audit & Remediation Memo, embed the linked vendor compliance chart and scorecard summary table from Google Sheets, write the audit findings and 30-day Corrective Action Plan for the breaching vendor, and download the final memo as a `.pdf`.
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
| **0:00 – 0:25** | `25 min` | **1. Ideation & Studio Idea Submission** | Review the `BUSI` guidelines in the Writer Handbook, run **Prompt 1** below with Gemini to design the vendor SLA rules and penalty tiers, and type your 5-part idea into Studio's **Describe your Idea** in your own words. *(Pause timer while waiting for approval if approval isn't immediate.)* |
| **0:25 – 1:05** | `40 min` | **2. Synthetic Data Generation & Math Audit (After Approval)** | Once your idea is approved, run **Prompt 2** and **Prompt 3** with Gemini to generate and refine the 45-row incident log (`input 1.csv`) and contract schedule (`input 2.csv`). Inspect the CSV rows and verify that deduplication (45 → 43 rows) and status filtering (43 → 40 rows) produce exact compliance percentages. |
| **1:05 – 1:45** | `40 min` | **3. Scratch Dry-Run in Google Sheets & Docs** | Practice the exact steps once in a scratch Google Sheet (`Remove duplicates`, `FILTER`, `MAX`, `IF`, `COUNTIFS`, Bar Chart, and copying the chart into Google Docs) so your mouse clicks are smooth and deliberate on camera. |
| **1:45 – 2:00** | `15 min` | **4. Desktop Appearance Change & Pre-Recording Setup** | Change your macOS Wallpaper + Light/Dark mode + Dock size (Task Variety requirement). Open the Goal Document in Window 1, set up Window 2 with Google Sheets (`Raw_Incidents` and `Contract_Terms` imported) and Google Docs, minimize Window 2, and check TaskRecorder + Accessibility Inspector. |
| **2:00 – 2:25** | `25 min` | **5. Actual Video Recording (In TaskRecorder)** | Record the complete 22–24 minute workflow and 3-minute Epilogue in one uninterrupted take using the verbatim What/Where/Why script in Part 5. |
| **2:25 – 3:00** | `35 min` | **6. Verification, `Deliverables.zip`, `Metadata.rtf` & AutoQC** | Spot-check `video.mp4` and the `screenshots/` count, package `Deliverables.zip` (`input 1.csv`, `input 2.csv`, `final output 1.xlsx`, `final output 2.pdf`), fill out `Metadata.rtf`, upload all 4 files to Studio, run AutoQC, and submit. |

---

## Part 3: Professional Gemini Prompt Playbook (Use During Phases 1–2)

Use these prompts in sequence during your prep time. After each response, read through the output, ask follow-up questions to refine edge cases, and test the formulas in a scratch sheet.

### Prompt 1 — Scenario & Business Logic Design (Phase 1)
```text
I am a Business Operations Manager preparing a Q3 Vendor SLA & Incident Performance Audit across four IT/data operations vendors (Apex Cloud Ops, Beacon Data Systems, Crestline Managed IT, and Delta Core Services).
Help me design a realistic SLA contract framework with:
1. Three incident severities (P1-Critical, P2-High, P3-Medium) and their target resolution times in hours (4h, 8h, 24h).
2. Contractual SLA compliance thresholds:
   - >= 90% on-time resolution: Compliant (0% credit penalty)
   - 80% to 89.9% on-time resolution: Warning Tier (5% monthly invoice credit penalty)
   - < 80% on-time resolution: Breach / Remediation Tier (15% monthly invoice credit penalty + mandatory Corrective Action Plan)
3. Show me a summary table of how 40 valid Q3 tickets could be distributed across the 4 vendors so that one vendor lands in Breach (<80%), one lands in Warning (80–89.9%), and two are Compliant (>=90%).
```

### Prompt 2 — Generating the Synthetic Starting Dataset with Data-Quality Traps (Phase 2)
```text
Now generate two clean, synthetic CSV files for this Q3 Vendor SLA Audit:
1. `input 1.csv` (Q3 Incident Log): 45 rows with columns:
   `Ticket_ID,Date_Opened,Vendor,Severity,Category,Status,Target_SLA_Hours,Actual_Resolution_Hours`
   Include these deliberate data-quality issues that I will clean during my workflow:
   - Exactly 2 exact duplicate rows (same Ticket_ID and values) so I can demonstrate Data > Data cleanup > Remove duplicates.
   - Exactly 3 rows with Status = "CANCELLED" (while the remaining 40 unique valid rows have Status = "RESOLVED") so I can filter out cancelled tickets before calculating SLA compliance.
   - Ensure the 40 valid RESOLVED tickets produce these exact SLA compliance rates when comparing Actual_Resolution_Hours <= Target_SLA_Hours:
     * Apex Cloud Ops: 10 resolved tickets, 9 within SLA (90.0% - Compliant)
     * Beacon Data Systems: 10 resolved tickets, 8 within SLA (80.0% - Warning, 5% credit)
     * Crestline Managed IT: 10 resolved tickets, 6 within SLA (60.0% - Breach, 15% credit)
     * Delta Core Services: 10 resolved tickets, 10 within SLA (100.0% - Compliant)
2. `input 2.csv` (Vendor Contract & Monthly Fee Schedule): 4 rows with columns:
   `Vendor,Contract_Owner,Monthly_Retainer_USD,Q3_Total_Spend_USD,Target_Compliance_Pct,Warning_Penalty_Pct,Breach_Penalty_Pct`
```

### Prompt 3 — Formula Verification & Edge-Case Audit (Phase 3)
```text
Verify the exact Google Sheets formulas I should use once the 40 valid RESOLVED rows are in a clean `Cleaned_Incidents` tab (rows 2 to 41):
1. Column I (`Overrun_Hours`): `=MAX(0, H2 - G2)` to calculate hours over the target SLA without negative numbers.
2. Column J (`SLA_Status`): `=IF(H2 <= G2, "Met", "Breached")` to classify each ticket.
3. In a `Vendor_Scorecard` tab listing the 4 vendors in `A2:A5`, give me the exact `COUNTIFS`, `AVERAGEIFS`, and `IF` formulas to compute:
   - Total Resolved Tickets (`B2`)
   - Tickets Breached (`C2`)
   - SLA Compliance % (`D2`)
   - Avg Overrun Hours on Breached Tickets (`E2`)
   - SLA Tier (`F2`: Compliant / Warning / Breach)
   - Q3 Penalty Credit USD (`G2`) based on their Q3 spend.
Double-check all math so I can cross-verify my Pivot Table against these formulas.
```

---

## Part 4: Ready-to-Use Synthetic Input Files (`input 1.csv` & `input 2.csv`)

Here are the exact contents for `input 1.csv` (43 unique rows + 2 exact duplicates = 45 data rows: 40 `RESOLVED` + 3 `CANCELLED` + 2 duplicates) and `input 2.csv`.

### `input 1.csv` (45 rows total -> 43 after Remove Duplicates -> 40 after filtering out `CANCELLED`)
```csv
Ticket_ID,Date_Opened,Vendor,Severity,Category,Status,Target_SLA_Hours,Actual_Resolution_Hours
INC-3001,2026-07-02,Apex Cloud Ops,P1-Critical,Database Failover,RESOLVED,4,3.5
INC-3002,2026-07-04,Apex Cloud Ops,P2-High,API Latency,RESOLVED,8,6.0
INC-3003,2026-07-08,Apex Cloud Ops,P3-Medium,Log Archival,RESOLVED,24,18.0
INC-3004,2026-07-11,Apex Cloud Ops,P2-High,Memory Spike,RESOLVED,8,11.5
INC-3005,2026-07-15,Apex Cloud Ops,P1-Critical,SSL Renewal,RESOLVED,4,2.5
INC-3006,2026-07-19,Apex Cloud Ops,P3-Medium,Backup Sync,RESOLVED,24,20.0
INC-3007,2026-08-03,Apex Cloud Ops,P2-High,Cache Eviction,RESOLVED,8,7.0
INC-3008,2026-08-14,Apex Cloud Ops,P3-Medium,User Provisioning,RESOLVED,24,15.0
INC-3009,2026-09-02,Apex Cloud Ops,P2-High,Load Balancer,RESOLVED,8,5.5
INC-3010,2026-09-18,Apex Cloud Ops,P3-Medium,DNS Propagation,RESOLVED,24,22.0
INC-3004,2026-07-11,Apex Cloud Ops,P2-High,Memory Spike,RESOLVED,8,11.5
INC-3011,2026-07-03,Beacon Data Systems,P1-Critical,ETL Pipeline Stall,RESOLVED,4,5.5
INC-3012,2026-07-09,Beacon Data Systems,P2-High,Warehouse Sync,RESOLVED,8,6.5
INC-3013,2026-07-14,Beacon Data Systems,P3-Medium,Schema Drift,RESOLVED,24,19.0
INC-3014,2026-07-22,Beacon Data Systems,P2-High,ODBC Timeout,RESOLVED,8,12.0
INC-3015,2026-08-01,Beacon Data Systems,P3-Medium,Report Export,RESOLVED,24,16.0
INC-3016,2026-08-11,Beacon Data Systems,P1-Critical,Partition Lock,RESOLVED,4,3.0
INC-3017,2026-08-21,Beacon Data Systems,P2-High,Airflow DAG Retry,RESOLVED,8,7.5
INC-3018,2026-09-05,Beacon Data Systems,P3-Medium,Index Rebuild,RESOLVED,24,21.0
INC-3019,2026-09-12,Beacon Data Systems,P2-High,Connector Auth,RESOLVED,8,6.0
INC-3020,2026-09-25,Beacon Data Systems,P3-Medium,Metadata Refresh,RESOLVED,24,14.0
INC-3021,2026-07-05,Crestline Managed IT,P1-Critical,VPN Gateway Down,RESOLVED,4,7.5
INC-3022,2026-07-10,Crestline Managed IT,P2-High,Firewall RuleLag,RESOLVED,8,14.0
INC-3023,2026-07-17,Crestline Managed IT,P3-Medium,Patch Rollout,RESOLVED,24,20.0
INC-3024,2026-07-26,Crestline Managed IT,P1-Critical,Storage Mount Lost,RESOLVED,4,6.5
INC-3025,2026-08-04,Crestline Managed IT,P2-High,SSO Token Error,RESOLVED,8,7.0
INC-3026,2026-08-13,Crestline Managed IT,P3-Medium,Printer Spooler,RESOLVED,24,31.0
INC-3027,2026-08-24,Crestline Managed IT,P2-High,VLAN Routing,RESOLVED,8,6.5
INC-3028,2026-09-03,Crestline Managed IT,P3-Medium,VM Snapshot,RESOLVED,24,18.5
INC-3029,2026-09-15,Crestline Managed IT,P2-High,Cert Chain Expired,RESOLVED,8,5.0
INC-3030,2026-09-27,Crestline Managed IT,P3-Medium,Audit Log Export,RESOLVED,24,19.5
INC-3021,2026-07-05,Crestline Managed IT,P1-Critical,VPN Gateway Down,RESOLVED,4,7.5
INC-3031,2026-07-06,Delta Core Services,P1-Critical,Auth Cluster Sync,RESOLVED,4,2.0
INC-3032,2026-07-12,Delta Core Services,P2-High,Queue Consumer,RESOLVED,8,5.0
INC-3033,2026-07-20,Delta Core Services,P3-Medium,Key Rotation,RESOLVED,24,12.0
INC-3034,2026-07-28,Delta Core Services,P2-High,Webhook Retry,RESOLVED,8,4.5
INC-3035,2026-08-06,Delta Core Services,P3-Medium,Metrics Scraper,RESOLVED,24,15.5
INC-3036,2026-08-16,Delta Core Services,P1-Critical,Primary Node Switch,RESOLVED,4,3.0
INC-3037,2026-08-27,Delta Core Services,P2-High,Rate Limiter Tune,RESOLVED,8,6.0
INC-3038,2026-09-07,Delta Core Services,P3-Medium,Archive Compression,RESOLVED,24,17.0
INC-3039,2026-09-17,Delta Core Services,P2-High,Session Store Sync,RESOLVED,8,5.5
INC-3040,2026-09-28,Delta Core Services,P3-Medium,Healthcheck Probe,RESOLVED,24,11.0
INC-3041,2026-07-29,Apex Cloud Ops,P3-Medium,Test Alert Drill,CANCELLED,24,0.0
INC-3042,2026-08-19,Beacon Data Systems,P2-High,Sandbox Refresh,CANCELLED,8,0.0
INC-3043,2026-09-09,Crestline Managed IT,P3-Medium,Duplicate Request,CANCELLED,24,0.0
```

### `input 2.csv` (Vendor Contract & Penalty Schedule)
```csv
Vendor,Contract_Owner,Monthly_Retainer_USD,Q3_Total_Spend_USD,Target_Compliance_Pct,Warning_Penalty_Pct,Breach_Penalty_Pct
Apex Cloud Ops,Infrastructure Team,18000,54000,90%,5%,15%
Beacon Data Systems,Data Engineering,15000,45000,90%,5%,15%
Crestline Managed IT,IT Operations,20000,60000,90%,5%,15%
Delta Core Services,Platform Security,16000,48000,90%,5%,15%
```

### Exact Mathematical Results You Will Get in Your Scorecard
| Vendor | Resolved Tickets | Breached | SLA Compliance % | SLA Tier | Q3 Spend (USD) | Penalty % | Q3 Credit Penalty (USD) |
|---|---:|---:|---:|---|---:|---:|---:|
| **Apex Cloud Ops** | 10 | 1 | `90.0%` | `Compliant` | `$54,000` | `0%` | `$0` |
| **Beacon Data Systems** | 10 | 2 | `80.0%` | `Warning` | `$45,000` | `5%` | `$2,250` |
| **Crestline Managed IT** | 10 | 4 | `60.0%` | `Breach` | `$60,000` | `15%` | `$9,000` |
| **Delta Core Services** | 10 | 0 | `100.0%` | `Compliant` | `$48,000` | `0%` | `$0` |
| **Total / Portfolio** | **40** | **7** | **`82.5%`** | — | **`$207,000`** | — | **`$11,250`** |

---

## Part 5: AutoQC-Hardened Minute-by-Minute Recording Script (`20–25 Minutes`)

### Pre-Recording Window Setup (Critical!)
1. **Change Desktop Appearance first:** Change your macOS Wallpaper, toggle Light/Dark mode (or Accent Color), and adjust Dock size slightly so Task 2 is visually distinct from Task 1.
2. **Window 1 (Google Docs — Opening Goal Doc):** Open a browser window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder.
3. **Window 2 (Google Sheets — Main Workspace):** Open a separate Chrome window with two tabs:
   - Tab 1: **Google Sheets** titled `Q3 Vendor SLA Performance Audit` with two sheets already imported: `Raw_Incidents` (from `input 1.csv`) and `Contract_Terms` (from `input 2.csv`).
   - Tab 2: **Google Docs** titled `Q3 Vendor SLA Audit & Remediation Memo` (blank document with title header ready).
   - **Minimize Window 2** using the yellow Minimize button (`-`) in the top-left corner before starting TaskRecorder!

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open Google Sheets from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click the minimized **Google Sheets** window in the Dock on the left side of the screen.

---

### SECTION B: Inspect Raw Data & Remove Duplicate Rows (`00:20 – 04:00`)

1. **Speak, then click:**
   > 🎤 "In the bottom-left sheet tab bar of Google Sheets, we are on the `Raw_Incidents` tab, which contains forty-five rows from row 2 to row 46. I will click cell A1 in the top-left of the data table and press `Command + A` to select the entire table range `A1:H46` so we can remove any duplicate incident records."
2. **Action:** Click cell `A1` and press `Cmd + A`.
3. **Speak, then click:**
   > 🎤 "In the top menu bar of Google Sheets, I will click `Data`, hover over `Data cleanup` in the dropdown menu, and click `Remove duplicates` to strip duplicate ticket entries."
4. **Action:** Click **Data → Data cleanup → Remove duplicates**.
5. **Speak, then click:**
   > 🎤 "Inside the Remove duplicates dialog box in the center of the screen, I will check the `Data has header row` checkbox at the top of the dialog, and then click the green `Remove duplicates` button at the bottom-right of the dialog."
6. **Action:** Check **Data has header row** and click **Remove duplicates**.
7. **Speak, then click:**
   > 🎤 "In the confirmation popup in the center of the screen, Google Sheets reports that two duplicate rows were found and removed, and forty-three unique rows remain. I will click the green `OK` button inside the popup to close it."
8. **Action:** Click **OK**.

---

### SECTION C: Filter Out `CANCELLED` Tickets into `Cleaned_Incidents` (`04:00 – 07:30`)

1. **Speak, then click:**
   > 🎤 "In the bottom-left corner of Google Sheets, I will click the plus icon labeled `Add Sheet` to create a new tab for our cleaned, resolved incidents."
2. **Action:** Click **`+` (Add Sheet)** in the bottom-left bar. Double-click the new tab name, type `Cleaned_Incidents` (5s), and press **Enter**.
3. **Speak, then click:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Raw_Incidents` tab, highlight cells `A1` through `H1` in the top row of the sheet, and press `Command + C` to copy the column headers."
4. **Action:** Copy `A1:H1` from `Raw_Incidents`, switch to `Cleaned_Incidents`, click cell `A1`, and press `Cmd + V`.
5. **Speak, then type the `FILTER` formula in cell `A2` (~15s):**
   > 🎤 "In cell A2 on row 2 of the `Cleaned_Incidents` tab, I will type `=FILTER(Raw_Incidents!A2:H44, Raw_Incidents!F2:F44=\"RESOLVED\")` and press Enter to pull only the forty resolved tickets and exclude the three cancelled tickets."
6. **Action:** In cell `A2`, type:
   ```excel
   =FILTER(Raw_Incidents!A2:H44, Raw_Incidents!F2:F44="RESOLVED")
   ```
   and press **Enter**.
7. **Speak while pointing at row 41:**
   > 🎤 "Scrolling down to row 41 in the center grid of `Cleaned_Incidents`, notice the filtered dataset ends on row 41, giving us forty valid resolved incidents from row 2 to row 41."

---

### SECTION D: Calculate `Overrun_Hours` and `SLA_Status` (`07:30 – 11:00`)

1. **Speak, then type headers in `I1` and `J1` (~8s):**
   > 🎤 "Scrolling back to the top of `Cleaned_Incidents`, I will click cell I1 in row 1, type `Overrun_Hours`, press Tab to move to cell J1, type `SLA_Status`, and press Enter to label our two calculated columns."
2. **Action:** Type `Overrun_Hours` in `I1` and `SLA_Status` in `J1`.
3. **Speak, then type formula in `I2` (~10s):**
   > 🎤 "In cell I2 on row 2 of `Cleaned_Incidents`, I will type `=MAX(0, H2-G2)` and press Enter so that tickets resolved within target show zero overrun hours while late tickets show the exact hours exceeded."
4. **Action:** Type `=MAX(0, H2-G2)` in `I2` and press **Enter** (and accept autofill or double-click the fill handle at the bottom-right corner of cell `I2` to fill down to `I41`).
5. **Speak, then type formula in `J2` (~15s):**
   > 🎤 "In cell J2 on row 2 of `Cleaned_Incidents`, I will type `=IF(H2<=G2, \"Met\", \"Breached\")` and press Enter to classify whether each incident met or breached its target SLA hours."
6. **Action:** Type `=IF(H2<=G2, "Met", "Breached")` in `J2`, press **Enter**, and fill down to `J41`.

---

### SECTION E: Build the `Vendor_Scorecard` Tab & Chart (`11:00 – 16:30`)

1. **Speak, then rename `Contract_Terms` or add scorecard columns in `Contract_Terms`:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Contract_Terms` tab, where cells A2 through G5 hold each vendor's retainer, Q3 spend, and contractual penalty percentages. We will add five scorecard columns in columns H through L of `Contract_Terms`."
2. **Speak, then type headers in `H1:L1` (in two short chunks, ~12s each):**
   > 🎤 "In cell H1 on row 1 of `Contract_Terms`, I will type `Resolved_Tickets`, in cell I1 I will type `Breached_Tickets`, and in cell J1 I will type `SLA_Compliance_Pct`."
   *(Type `H1:J1`, pause, then speak:)*
   > 🎤 "Next, in cell K1 on row 1 of `Contract_Terms`, I will type `SLA_Tier`, and in cell L1 I will type `Q3_Penalty_USD`."
3. **Speak, then type formula in `H2` (~15s):**
   > 🎤 "In cell H2 on row 2 of `Contract_Terms`, I will type `=COUNTIF(Cleaned_Incidents!$C$2:$C$41, A2)` and press Enter to count the total resolved tickets for Apex Cloud Ops, then drag the fill handle down to cell H5."
4. **Speak, then type formula in `I2` (~20s):**
   > 🎤 "In cell I2 on row 2 of `Contract_Terms`, I will type `=COUNTIFS(Cleaned_Incidents!$C$2:$C$41, A2, Cleaned_Incidents!$J$2:$J$41, \"Breached\")` and press Enter to count how many tickets breached SLA for each vendor, then fill down to cell I5."
5. **Speak, then type formula in `J2` (~10s):**
   > 🎤 "In cell J2 on row 2 of `Contract_Terms`, I will type `=(H2-I2)/H2` and press Enter to compute the SLA compliance percentage, fill down to cell J5, and click the `Format as percent (%)` button in the top toolbar of Google Sheets."
6. **Speak, then type formula in `K2` (~22s):**
   > 🎤 "In cell K2 on row 2 of `Contract_Terms`, I will type `=IF(J2>=0.9, \"Compliant\", IF(J2>=0.8, \"Warning\", \"Breach\"))` and press Enter to assign each vendor's SLA tier, then fill down to cell K5."
7. **Speak, then type formula in `L2` (~20s):**
   > 🎤 "In cell L2 on row 2 of `Contract_Terms`, I will type `=IF(K2=\"Breach\", D2*G2, IF(K2=\"Warning\", D2*F2, 0))` and press Enter to calculate the Q3 financial credit penalty in dollars, then fill down to cell L5."
8. **Speak while pointing at rows 2–5:**
   > 🎤 "Looking at columns J, K, and L in the center grid of `Contract_Terms`, Apex Cloud Ops achieved 90% and Delta Core Services achieved 100%, so both are Compliant with zero penalty. Beacon Data Systems is at 80% in the Warning tier with a $2,250 credit penalty, and Crestline Managed IT dropped to 60% in the Breach tier, triggering a 15% credit penalty of $9,000."
9. **Create Bar Chart (Mouse-driven):**
   > 🎤 "In the center grid of `Contract_Terms`, I will hold the Command key and select cells `A1:A5` and `J1:J5`, then click `Insert` in the top menu bar of Google Sheets and select `Chart` to visualize SLA compliance by vendor."
10. **Export `.xlsx` (`final output 1.xlsx`):**
    > 🎤 "In the top menu bar of Google Sheets, I will click `File`, hover over `Download`, and click `Microsoft Excel (.xlsx)` to export our completed workbook as our first final deliverable."

---

### SECTION F: Compile the Executive Audit Memo in Google Docs (`16:30 – 20:30`)

1. **Speak, then switch to the Google Docs tab:**
   > 🎤 "In the top browser tab bar, I will click the `Contract_Terms` chart menu in the top-right corner of the chart and select `Copy chart`. Then I will click the second browser tab titled `Q3 Vendor SLA Audit & Remediation Memo` in Google Docs to assemble our executive report."
2. **Action:** Paste the chart (`Cmd + V` → **Link to spreadsheet**) and paste the scorecard table (`A1:L5` from `Contract_Terms`).
3. **Speak, then type 3 short executive summary bullets (in 3 separate chunks under 25s each):**
   - **Chunk M1 (~20s):**
     > 🎤 "Below the Summary heading in the center page of Google Docs, I will type the first finding bullet summarizing the portfolio SLA compliance rate of 82.5% across 40 valid resolved incidents after removing 2 duplicates and 3 cancelled tickets."
     ```text
     • Portfolio Overview: 40 valid resolved Q3 incidents audited (2 duplicates and 3 cancelled tickets excluded); overall portfolio SLA compliance is 82.5%.
     ```
   - **Chunk M2 (~22s):**
     > 🎤 "On the next line in the center page of Google Docs, I will type the second bullet detailing the $11,250 total Q3 service credit recovery across Crestline Managed IT and Beacon Data Systems."
     ```text
     • Financial Credits Due: $11,250 total Q3 invoice credits ($9,000 from Crestline Managed IT at 60% compliance; $2,250 from Beacon Data Systems at 80% compliance).
     ```
   - **Chunk M3 (~22s):**
     > 🎤 "On the third bullet line in the center page of Google Docs, I will type the mandatory remediation action requiring Crestline Managed IT to submit a Corrective Action Plan for P1 VPN and storage outages."
     ```text
     • Remediation Plan: Place Crestline Managed IT on a 30-day Corrective Action Plan targeting P1 VPN gateway and storage mount response times.
     ```
4. **Export `.pdf` (`final output 2.pdf`):**
   > 🎤 "In the top menu bar of Google Docs, I will click `File`, hover over `Download`, and select `PDF Document (.pdf)` to export our completed executive memo."

---

### SECTION G: 3-Minute Verbal Epilogue (`20:30 – 23:30`)

> 🎤 "Let's wrap up with a summary of our workflow, key methodological decisions, and lessons learned.
>
> First, completion and verification: we completed the Q3 Vendor SLA and Incident Performance Audit by cleaning the raw 45-row incident log in Google Sheets, removing two duplicate ticket entries, filtering out three cancelled tickets so they did not artificially distort vendor resolution rates, and evaluating the forty valid resolved incidents against each severity's target SLA hours. We then built the vendor scorecard and compliance chart and compiled the executive remediation memo in Google Docs, exporting both the Excel workbook and the PDF report.
>
> Second, why this approach was effective: separating raw incident data from the filtered `Cleaned_Incidents` tab preserves an immutable audit trail of the original log while ensuring downstream `COUNTIFS` and compliance formulas only evaluate valid resolved tickets. Linking the Google Sheets scorecard table and chart directly into the Google Docs executive memo ensures the numbers in the stakeholder report match the underlying workbook.
>
> Third, common mistakes that someone less experienced should watch out for in an SLA audit:
> - Number one: failing to deduplicate ticket logs or failing to exclude cancelled and test-drill tickets before calculating compliance percentages, which skews the denominator and produces inaccurate penalty charges.
> - Number two: using simple averages of resolution hours across mixed severities instead of comparing each individual ticket's actual resolution time against its severity-specific target threshold—since a 6-hour resolution meets an 8-hour P2 SLA but breaches a 4-hour P1 SLA.
> - Number three: allowing negative overrun hours when a ticket finishes early; wrapping `H2 - G2` in `MAX(0, ...)` prevents early completions from offsetting late breaches.
>
> All deliverables are saved and ready for packaging. Thank you for watching."

---

## Part 6: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

```text
Deliverables/
├── input 1.csv          <-- Raw 45-row Q3 incident log
├── input 2.csv          <-- Vendor contract & penalty schedule
├── final output 1.xlsx  <-- Exported Google Sheets SLA Audit workbook
└── final output 2.pdf   <-- Exported Google Docs Executive Audit Memo PDF
```

### `Metadata.rtf` Template for This Task
```text
Topology: Google Sheets (MODIFY) -> Google Docs (CREATE)

Request: <Paste the exact Goal text from Studio / TaskRecorder>

Task Description:
1. Import the raw Q3 vendor incident log and contract schedule into Google Sheets and remove duplicate ticket rows.
2. Filter out cancelled tickets into a cleaned incidents sheet and calculate SLA overrun hours and breach status per ticket.
3. Build a vendor scorecard and compliance bar chart in Google Sheets calculating SLA compliance rates, tier classifications, and Q3 penalty credits, and export the workbook as an Excel file.
4. Draft the Q3 Vendor SLA Audit & Remediation Memo in Google Docs with the embedded scorecard table, compliance chart, and corrective action plan, and export the final report as a PDF.
```
