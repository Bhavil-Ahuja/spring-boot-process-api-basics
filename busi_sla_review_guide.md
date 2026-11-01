# Task 2 Master Guide v2 (`BUSI` — Low-Typing & UI-Variety Hardened): Q3 Vendor SLA Audit

> [!IMPORTANT]
> **What Changed Based on Reviewer Theo W's Feedback:**
> 1. **UI Setup Fix (Required by Reviewer):** Before recording, change **all three** of these in macOS **System Settings** (takes 20 seconds):
>    - **Wallpaper:** Pick a new built-in macOS wallpaper (not the macOS default *Sequoia Sunset* and not your Task 1 wallpaper). Leave a thin strip of wallpaper visible around your browser window or Dock so screenshots capture it.
>    - **Accent Color & Appearance:** Go to **System Settings → Appearance** and switch **Appearance** (e.g., from Dark to **Light** mode) AND change **Accent color** (e.g., from Blue to **Purple**, **Orange**, or **Green**). Because Chrome covered most of your wallpaper in the last take, changing Light/Dark mode + Accent color guarantees every frame looks visually distinct!
>    - **Dock Size:** Go to **System Settings → Desktop & Dock** and adjust the **Size** slider slightly.
> 2. **Typing Reduced from `28.37%` Down to `< 18%` (So AutoQC `#19` Passes Automatically):**
>    - **Mouse Range Selection:** Instead of typing `Cleaned_Incidents!$C$2:$C$41` on the keyboard, you now **select ranges with your mouse** while entering `FILTER`, `COUNTIF`, and `COUNTIFS`.
>    - **Shorter Column Headers:** `Overrun`, `SLA`, `Resolved`, `Breached`, `Compliance`, `Tier`, `Penalty` (cuts header typing by 55%).
>    - **Concise Memo Bullets + Mouse-Driven Formatting:** Shorter typed bullets in Google Docs paired with richer verbal narration and mouse-driven currency/highlight formatting in Google Sheets.

---

## Part 1: Pre-Recording UI & Window Setup Checklist

- [ ] **1. Change macOS UI Appearance (Mandatory for Task Variety & Non-Default UI):**
  - **System Settings → Wallpaper:** Select a non-default built-in wallpaper (different from Task 1).
  - **System Settings → Appearance:** Switch **Light / Dark mode** AND pick a new **Accent color** (e.g., Purple or Orange).
  - **System Settings → Desktop & Dock:** Change the **Dock Size** slider slightly.
  - Resize your Chrome window slightly so a small margin of the new desktop wallpaper is visible next to the Dock.
- [ ] **2. Window 1 (Google Docs — Opening Goal Doc):**
  - Open a browser window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder.
- [ ] **3. Window 2 (Google Sheets & Google Docs — Main Workspace):**
  - Open a separate Chrome window with two tabs:
    - **Tab 1 (Google Sheets):** `Q3 Vendor SLA Performance Audit` containing `Raw_Incidents` (45 rows, `A1:H46`) and `Contract_Terms` (4 rows, `A1:G5`).
    - **Tab 2 (Google Docs):** `Q3 Vendor SLA Audit & Remediation Memo` with the document title and section headings (`1. Compliance Chart`, `2. Vendor Scorecard`, `3. Executive Findings & Remediation Plan`) already pre-typed before recording so you don't waste typing quota on headings!
  - **Minimize Window 2** using the yellow Minimize button (`-`) in the top-left corner before starting TaskRecorder.

---

## Part 2: Exact Scorecard Reference (Matches `Q3 Vendor SLA Performance Audit.xlsx`)

| Vendor (`A`) | Owner (`B`) | Monthly Retainer (`C`) | Q3 Total Spend (`D`) | Resolved (`H`) | Breached (`I`) | Compliance (`J`) | Tier (`K`) | Penalty (`L`) | Breached Tickets |
|---|---|---:|---:|---:|---:|---:|---|---:|---|
| **Test Company 1** | `Person 1` | `$15,000` | `$45,000` | `10` | `1` | **`90.0%`** | `Compliant` | **`$0`** | `TKT-1010` (P1 Database: 11h vs 4h) |
| **Test Company 2** | `Person 2` | `$12,000` | `$36,000` | `10` | `2` | **`80.0%`** | `Warning` | **`$1,800`** | `TKT-1020` (P1 Storage: 9h vs 4h), `TKT-1019` (P2 Network: 12h vs 8h) |
| **Test Company 3** | `Person 3` | `$18,000` | `$54,000` | `10` | `4` | **`60.0%`** | `Breach` | **`$8,100`** | `TKT-1028`, `TKT-1029` (P1), `TKT-1027`, `TKT-1030` (P2) |
| **Test Company 4** | `Person 4` | `$20,000` | `$60,000` | `10` | `0` | **`100.0%`** | `Compliant` | **`$0`** | *(None)* |
| **Total / Portfolio** | — | **`$65,000`** | **`$195,000`** | **`40`** | **`7`** | **`82.5%`** | — | **`$9,900`** | — |

---

## Part 3: AutoQC-Hardened, Low-Typing Recording Script (`21–24 Minutes`)

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open Google Sheets from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click the minimized **Google Sheets** window in the Dock on the left side of the screen.

---

### SECTION B: Inspect Raw Data & Remove Duplicate Rows (`00:20 – 04:00` — 100% Mouse-Driven!)

1. **Speak while pointing at columns A through H in `Raw_Incidents`:**
   > 🎤 "In the bottom-left sheet tab bar of Google Sheets, we are on the `Raw_Incidents` tab, which contains forty-five incident rows from row 2 to row 46 across Test Company 1 through Test Company 4. Looking across row 1 in the center grid, columns A through H track the Ticket ID, Date Opened, Vendor, Severity, Category, Status, Target SLA Hours, and Actual Resolution Hours. Notice that P1 Critical tickets have a 4-hour target, P2 High tickets have an 8-hour target, and P3 Medium tickets have a 24-hour target."
2. **Speak, then select the table using the mouse (top-left corner box):**
   > 🎤 "In the top-left corner of the grid, right above row 1 and to the left of column A, I will click the empty select-all square to highlight the entire sheet so we can remove any duplicate ticket records."
3. **Action:** Click the top-left select-all square (between `A` and `1`) with the mouse (zero keyboard typing!).
4. **Speak, then click:**
   > 🎤 "In the top menu bar of Google Sheets, I will click `Data`, hover over `Data cleanup` in the dropdown menu, and click `Remove duplicates` to strip duplicate ticket entries."
5. **Action:** Click **Data → Data cleanup → Remove duplicates**.
6. **Speak, then click:**
   > 🎤 "Inside the Remove duplicates dialog box in the center of the screen, I will check the `Data has header row` checkbox at the top of the dialog, and then click the green `Remove duplicates` button at the bottom-right of the dialog."
7. **Action:** Check **Data has header row** and click **Remove duplicates**.
8. **Speak, then click:**
   > 🎤 "In the confirmation popup in the center of the screen, Google Sheets reports that two duplicate rows—`TKT-1006` and `TKT-1026`—were found and removed, and forty-three unique rows remain from row 2 to row 44. I will click the green `OK` button inside the popup to close it."
9. **Action:** Click **OK**.

---

### SECTION C: Filter Out `CANCELLED` Tickets into `Cleaned` (`04:00 – 07:30`)

1. **Speak, then click:**
   > 🎤 "In the bottom-left corner of Google Sheets, I will click the plus icon labeled `Add Sheet` to create a new tab for our cleaned, resolved incidents."
2. **Action:** Click **`+` (Add Sheet)** in the bottom-left bar.
3. **Speak, then rename the new tab (~3s typing):**
   > 🎤 "In the bottom sheet tab bar of Google Sheets, I will double-click the new tab name, type `Cleaned`, and press Enter to name our filtered tab."
4. **Action:** Type `Cleaned` and press **Enter**.
5. **Speak, then copy headers using the mouse (`Edit → Copy` / `Edit → Paste`):**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Raw_Incidents` tab, drag my mouse across cells `A1` through `H1` in row 1, then click `Edit` in the top menu bar and select `Copy`."
6. **Action:** Drag mouse across `A1:H1`, click **Edit → Copy**.
7. **Speak, then paste headers using the mouse:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Cleaned` tab, click cell A1 in the top-left corner of the grid, then click `Edit` in the top menu bar and select `Paste` to place our eight column headers."
8. **Action:** Switch to `Cleaned`, click `A1`, click **Edit → Paste**.
9. **Speak, then build the `FILTER` formula using MOUSE range selection (~6s typing!):**
   > 🎤 "In cell A2 on row 2 of the `Cleaned` tab, I will type `=FILTER(`, then click the `Raw_Incidents` tab in the bottom bar and drag my mouse across cells `A2` through `H44` to select the data range. Next, I will type a comma, drag my mouse down column F from cell `F2` to `F44`, and type `=\"RESOLVED\")` followed by Enter so only the forty resolved tickets are pulled in and the three cancelled tickets `TKT-1041`, `TKT-1042`, and `TKT-1043` are excluded."
10. **Action:**
    - In `Cleaned!A2`, type `=FILTER(`
    - Click `Raw_Incidents` tab and drag mouse over `A2:H44`
    - Type `,`
    - Drag mouse over `F2:F44`
    - Type `="RESOLVED")` and press **Enter**.
11. **Speak while scrolling down and pointing at row 41:**
    > 🎤 "Scrolling down to row 41 in the center grid of the `Cleaned` tab, notice the filtered dataset ends on row 41, giving us forty valid resolved incidents from row 2 to row 41 across our four vendors."

---

### SECTION D: Calculate `Overrun` and `SLA` Columns (`07:30 – 11:00`)

1. **Speak, then type short headers in `I1` and `J1` (~4s typing):**
   > 🎤 "Scrolling back to row 1 of the `Cleaned` tab, I will click cell I1, type `Overrun`, press Tab to move to cell J1, type `SLA`, and press Enter to label our two calculated SLA columns."
2. **Action:** Type `Overrun` in `I1` and `SLA` in `J1`.
3. **Speak, then enter `=MAX(0, H2-G2)` in `I2` using mouse clicks (~4s typing):**
   > 🎤 "In cell I2 on row 2 of the `Cleaned` tab, I will type `=MAX(0,`, click cell H2 with my mouse, type `-`, click cell G2 with my mouse, and type `)` followed by Enter so tickets resolved within target show zero overrun hours while late tickets show the exact hours exceeded. Then I will click the green checkmark in the Suggested autofill popup to fill down to row 41."
4. **Action:** Type `=MAX(0,`, click `H2`, type `-`, click `G2`, type `)`, press **Enter**, and click the green autofill checkmark (or double-click the bottom-right fill handle of `I2`).
5. **Speak, then enter `=IF(H2<=G2, "Met", "Breached")` in `J2` (~8s typing):**
   > 🎤 "In cell J2 on row 2 of the `Cleaned` tab, I will type `=IF(`, click cell H2, type `<=`, click cell G2, and type `,\"Met\",\"Breached\")` followed by Enter to classify whether each incident met or breached its target SLA hours, then click the green autofill checkmark to fill down to cell J41."
6. **Action:** Enter `=IF(H2<=G2,"Met","Breached")` in `J2`, press **Enter**, and click the autofill checkmark (or double-click the fill handle of `J2`).
7. **Speak while pointing at breached rows in column J:**
   > 🎤 "Scanning down column I and column J in the center grid of the `Cleaned` tab, we can see specific breaches such as `TKT-1027` on row 4 with 4 overrun hours, `TKT-1020` on row 14 with 5 overrun hours, and `TKT-1010` on row 18 with 7 overrun hours."

---

### SECTION E: Build the Vendor Scorecard & Chart in `Contract_Terms` (`11:00 – 17:00`)

1. **Speak, then click `Contract_Terms`:**
   > 🎤 "In the bottom tab bar of Google Sheets, I will click the `Contract_Terms` tab, where cells A2 through G5 hold the contract owners `Person 1` through `Person 4`, monthly retainers, Q3 spend totaling $195,000, the 90% target compliance threshold, the 5% warning penalty, and the 15% breach penalty for `Test Company 1` through `Test Company 4`."
2. **Action:** Click the `Contract_Terms` tab.
3. **Speak, then type short 1-word headers in `H1:J1` (~6s typing):**
   > 🎤 "In cell H1 on row 1 of `Contract_Terms`, I will type `Resolved`, press Tab to cell I1 and type `Breached`, and press Tab to cell J1 and type `Compliance`."
4. **Action:** Type `Resolved` in `H1`, `Breached` in `I1`, and `Compliance` in `J1`.
5. **Speak, then type short 1-word headers in `K1:L1` (~4s typing):**
   > 🎤 "In cell K1 on row 1 of `Contract_Terms`, I will type `Tier`, press Tab to cell L1, type `Penalty`, and press Enter."
6. **Action:** Type `Tier` in `K1` and `Penalty` in `L1`.
7. **Speak, then build `=COUNTIF(...)` in `H2` using MOUSE range selection (~4s typing):**
   > 🎤 "In cell H2 on row 2 of `Contract_Terms`, I will type `=COUNTIF(`, click the `Cleaned` tab in the bottom bar, drag my mouse down column C from `C2` to `C41`, press `F4` to lock the range, type a comma, and click cell `A2` back on `Contract_Terms` followed by `)` and Enter to count resolved tickets for Test Company 1, then drag the fill handle down to cell H5."
8. **Action:** Build `=COUNTIF(Cleaned!$C$2:$C$41, A2)` in `H2` using mouse selection and fill down to `H5` (all 4 show `10`).
9. **Speak, then build `=COUNTIFS(...)` in `I2` using MOUSE range selection (~6s typing):**
   > 🎤 "In cell I2 on row 2 of `Contract_Terms`, I will type `=COUNTIFS(`, select `Cleaned!$C$2:$C$41` with my mouse, click cell `A2` as the vendor criterion, select `Cleaned!$J$2:$J$41` with my mouse as the status range, and type `,\"Breached\")` followed by Enter to count breached tickets per vendor, then drag the fill handle down to cell I5."
10. **Action:** Build `=COUNTIFS(Cleaned!$C$2:$C$41, A2, Cleaned!$J$2:$J$41, "Breached")` in `I2` and fill down to `I5` (shows `1`, `2`, `4`, `0`).
11. **Speak, then enter `=(H2-I2)/H2` in `J2` using mouse clicks (~4s typing):**
    > 🎤 "In cell J2 on row 2 of `Contract_Terms`, I will type `=(`, click cell H2, type `-`, click cell I2, type `)/`, click cell H2, and press Enter to compute the SLA compliance percentage. Then I will drag the fill handle down to cell J5 and click the `Format as percent (%)` button in the top toolbar of Google Sheets."
12. **Action:** Enter `=(H2-I2)/H2` in `J2`, fill down to `J5`, and click **`%`** in the top toolbar (shows `90.0%`, `80.0%`, `60.0%`, `100.0%`).
13. **Speak, then enter `=IF(J2>=E2, "Compliant", IF(J2>=0.8, "Warning", "Breach"))` in `K2` (~12s typing):**
    > 🎤 "In cell K2 on row 2 of `Contract_Terms`, I will type `=IF(J2>=E2,\"Compliant\",IF(J2>=0.8,\"Warning\",\"Breach\"))` and press Enter to classify each vendor's SLA tier against the 90% target in column E, then drag the fill handle down to cell K5."
14. **Action:** Enter `=IF(J2>=E2,"Compliant",IF(J2>=0.8,"Warning","Breach"))` in `K2` and fill down to `K5` (shows `Compliant`, `Warning`, `Breach`, `Compliant`).
15. **Speak, then enter `=IF(K2="Breach", D2*G2, IF(K2="Warning", D2*F2, 0))` in `L2` (~12s typing):**
    > 🎤 "In cell L2 on row 2 of `Contract_Terms`, I will type `=IF(K2=\"Breach\",D2*G2,IF(K2=\"Warning\",D2*F2,0))` and press Enter to compute the Q3 financial penalty credit in dollars, then drag the fill handle down to cell L5."
16. **Action:** Enter `=IF(K2="Breach",D2*G2,IF(K2="Warning",D2*F2,0))` in `L2` and fill down to `L5` (shows `0`, `1800`, `8100`, `0`).
17. **Mouse-Driven Formatting Step (Adds 45s of pure mouse work, 0s typing!):**
    > 🎤 "To format the financial figures clearly, I will drag my mouse across cells `C2:D5` and `L2:L5` in the center grid of `Contract_Terms`, click `Format` in the top menu bar of Google Sheets, hover over `Number`, and click `Currency` so all retainer, spend, and penalty amounts display in US dollars. Next, I will drag my mouse across row 4 from `A4` to `L4` for `Test Company 3`, click the `Fill color` paint-bucket icon in the top toolbar of Google Sheets, and select light red 3 to visually highlight the breaching vendor."
18. **Action:** Format `C2:D5` and `L2:L5` as Currency via **Format → Number → Currency**, and highlight `A4:L4` in light red via the **Fill color** toolbar icon.
19. **Speak while pointing at rows 2–5 in `Contract_Terms`:**
    > 🎤 "Reviewing columns J, K, and L in the center grid of `Contract_Terms`: Test Company 1 is at 90% and Test Company 4 is at 100%, so both are Compliant with $0 penalty. Test Company 2 is at 80% in the Warning tier, resulting in a 5% credit of $1,800 on its $36,000 Q3 spend. Test Company 3 dropped to 60% in the Breach tier with four breached tickets, triggering a 15% penalty credit of $8,100 on its $54,000 Q3 spend, for a total recovery of $9,900."
20. **Create Bar Chart (100% Mouse-driven):**
    > 🎤 "In the center grid of `Contract_Terms`, I will drag my mouse across cells `A1:A5`, hold down the Command key, and drag across cells `J1:J5`. Then in the top menu bar of Google Sheets, I will click `Insert` and select `Chart` to generate a bar chart comparing SLA compliance across Test Company 1 through Test Company 4."
21. **Action:** Create the chart, drag it below row 7 so it doesn't cover the table, and click the three-dot menu in the top-right corner of the chart → **Copy chart**.
22. **Export `.xlsx` (`final output 1.xlsx`):**
    > 🎤 "In the top menu bar of Google Sheets, I will click `File`, hover over `Download`, and click `Microsoft Excel (.xlsx)` to export our completed SLA audit workbook."

---

### SECTION F: Compile the Executive Audit Memo in Google Docs (`17:00 – 20:30`)

1. **Speak, then click the Google Docs tab:**
   > 🎤 "In the top browser tab bar, I will click the second tab titled `Q3 Vendor SLA Audit & Remediation Memo` in Google Docs to assemble the executive report."
2. **Action:** Click the Google Docs tab.
3. **Speak, then paste the chart using the mouse (`Edit → Paste`):**
   > 🎤 "In the center page of Google Docs, below the `1. Compliance Chart` heading, I will click `Edit` in the top menu bar, select `Paste`, and click the blue `Paste` button in the Link to spreadsheet dialog to embed our SLA compliance chart."
4. **Action:** Switch to the Google Sheets tab briefly, drag across `A1:L5`, click **Edit → Copy**, return to the Google Docs tab below `2. Vendor Scorecard`, and click **Edit → Paste → Paste** to embed the linked scorecard table.
5. **Speak, then type 3 concise executive summary bullets (~8s typing per bullet, with 20s of mouse pointing & explanation after each!):**
   - **Chunk M1 (~8s typing):**
     > 🎤 "Below the `3. Executive Findings & Remediation Plan` heading in the center page of Google Docs, I will type the first bullet summarizing the portfolio SLA rate."
     ```text
     • Portfolio SLA: 82.5% across 40 resolved tickets ($195,000 Q3 spend).
     ```
     *(Stop typing, point with mouse at the embedded table, and speak for 15s:)*
     > 🎤 "Pointing at the embedded scorecard table in the center of Google Docs, this 82.5% rate reflects thirty-three on-time resolutions and seven breaches after excluding the two duplicate rows `TKT-1006` and `TKT-1026` and the three cancelled tickets `TKT-1041` through `TKT-1043`."
   - **Chunk M2 (~9s typing):**
     > 🎤 "On the second bullet line in the center page of Google Docs, I will type the total service credit recovery."
     ```text
     • Credits Due: $9,900 total ($8,100 Test Company 3; $1,800 Test Company 2).
     ```
     *(Stop typing, point at `Penalty` column in the table, and speak for 15s:)*
     > 🎤 "Looking at the Penalty column on the right side of the embedded scorecard table in Google Docs, Test Company 3 owes a 15% breach credit of $8,100 on its $54,000 spend, and Test Company 2 owes a 5% warning credit of $1,800 on its $36,000 spend."
   - **Chunk M3 (~9s typing):**
     > 🎤 "On the third bullet line in the center page of Google Docs, I will type the mandatory corrective action item for Person 3."
     ```text
     • Action Plan: 30-day CAP required from Person 3 (Test Company 3) for P1 breaches.
     ```
     *(Stop typing, point at the `Test Company 3` bar in the chart, and speak for 15s:)*
     > 🎤 "Pointing at the Test Company 3 bar in the embedded compliance chart in Google Docs, their 60% compliance was driven by P1 Critical Authentication and Database breaches `TKT-1028` and `TKT-1029` plus P2 breaches `TKT-1027` and `TKT-1030`."
6. **Export `.pdf` (`final output 2.pdf`):**
   > 🎤 "In the top menu bar of Google Docs, I will click `File`, hover over `Download`, and select `PDF Document (.pdf)` to export our completed executive audit memo."

---

### SECTION G: 3-Minute Verbal Epilogue (`20:30 – 23:30` — Zero Typing!)

> 🎤 "Let's wrap up with a summary of our workflow, key methodological decisions, and lessons learned.
>
> First, completion and verification: we completed the Q3 Vendor SLA and Incident Performance Audit across Test Company 1 through Test Company 4 by cleaning the raw 45-row incident log in Google Sheets, removing two duplicate ticket entries (`TKT-1006` and `TKT-1026`), filtering out three cancelled tickets (`TKT-1041`, `TKT-1042`, and `TKT-1043`) so they did not distort vendor resolution rates, and evaluating the forty valid resolved incidents against each severity's target SLA hours. We then built the vendor scorecard and compliance chart in `Contract_Terms` and compiled the executive remediation memo in Google Docs, exporting both the Excel workbook and the PDF report.
>
> Second, why this approach was effective: separating raw incident data from the filtered `Cleaned` tab preserves an immutable audit trail of the original log while ensuring downstream `COUNTIF` and `COUNTIFS` scorecard formulas only evaluate valid resolved tickets. Linking the Google Sheets scorecard table and chart directly into the Google Docs executive memo ensures the $9,900 total penalty calculation ($8,100 from Test Company 3 and $1,800 from Test Company 2) stays synchronized with the underlying workbook.
>
> Third, common mistakes that someone less experienced should watch out for in an SLA audit:
> - Number one: failing to deduplicate ticket logs or failing to exclude cancelled tickets before calculating compliance percentages, which inflates total ticket counts and produces inaccurate penalty charges.
> - Number two: using simple averages of resolution hours across mixed severities instead of comparing each individual ticket's actual resolution time against its severity-specific target threshold—since a 6-hour resolution meets an 8-hour P2 SLA (`TKT-1002`) but breaches a 4-hour P1 SLA.
> - Number three: allowing negative overrun hours when a ticket finishes early; wrapping `H2 - G2` in `MAX(0, ...)` prevents early completions from offsetting late breaches.
>
> All deliverables are saved and ready for packaging. Thank you for watching."
