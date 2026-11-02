# Task 4 Master Guide (`DSD` — v2 Reviewer-Hardened): SQLite Database Integrity Audit, Indexing & Query Optimization (`TablePlus` + `VS Code`)

---

## How This v2 Script Directly Addresses All 8 Reviewer Points
1. **Point 1 & 7 ("Mention 'Where' you are working, line number, how you move to next line, and explicit commands"):**
   - Every SQL block explicitly states the **exact line numbers** (`Line 1` through `Line 31`), states **"I will press the `Enter` key twice to move down to line X"**, and names every keyboard shortcut (`Command + E`, `Command + R`, `Command + A`, `Command + C`, `Command + V`, `Command + S`, `Shift + Command + V`).
2. **Point 2, 3, 5 & 8 ("3Ws: What, Where, Why", "which code line links to preexisting data", "why lines 20–31 are selected"):**
   - Every single SQL line is explained against the preexisting columns in `customers` (`customer_id`, `region`) and `orders` (`order_id`, `customer_id`, `order_date`, `order_status`, `total_amount`).
   - Whenever you highlight a line range (including **lines 20 through 31**) before clicking `Run Current`, the script explicitly explains **WHY**: *"because highlighting only lines X through Y tells TablePlus's `Run Current` button to execute only that statement rather than re-running the previous statements on lines 1 through X-1."*
3. **Point 6 ("`optimize_orders.sql` should be opened in VS Code prior to recording start"):**
   - Added to the Pre-Recording Checklist: open `optimize_orders.sql` as Tab 1 (active tab on Line 1) and `db_audit_report.md` as Tab 2 inside VS Code **before** minimizing VS Code and starting TaskRecorder.
4. **Point 4 ("What's the outcome of Visual Studio coding? Any automated dashboard?"):**
   - At the end of Section E in VS Code, after saving `optimize_orders.sql` and `db_audit_report.md` (which includes a formatted Regional Revenue table), you click the **Open Preview to the Side** button in the top-right corner of the VS Code editor (`Command + K` then `V`) to render the **Visual Database Audit & Regional Revenue Dashboard** side-by-side in VS Code!

---

## Part 1: Exact Line-by-Line SQL Reference (`Lines 1–31` in TablePlus SQL Editor)

Keep this exact line numbering in TablePlus's `SQL Query` editor (`1` empty line between each block) so your line numbers match the narration 100%:

```sql
SELECT o.*                                                        -- Line 1
FROM orders o LEFT JOIN customers c                               -- Line 2
ON o.customer_id = c.customer_id                                  -- Line 3
WHERE c.customer_id IS NULL;                                      -- Line 4
                                                                  -- Line 5 (blank)
SELECT * FROM orders WHERE total_amount < 0;                      -- Line 6
                                                                  -- Line 7 (blank)
DELETE FROM orders                                                -- Line 8
WHERE customer_id NOT IN (SELECT customer_id FROM customers);     -- Line 9
                                                                  -- Line 10 (blank)
DELETE FROM orders                                                -- Line 11
WHERE total_amount < 0;                                           -- Line 12
                                                                  -- Line 13 (blank)
EXPLAIN QUERY PLAN                                                -- Line 14
SELECT * FROM orders                                              -- Line 15
WHERE order_status = 'COMPLETED' AND order_date >= '2026-10-01';  -- Line 16
                                                                  -- Line 17 (blank)
CREATE INDEX idx_orders_status_date                               -- Line 18
ON orders(order_status, order_date);                              -- Line 19
                                                                  -- Line 20 (blank)
CREATE VIEW v_regional_revenue_summary AS                         -- Line 21
SELECT                                                            -- Line 22
c.region,                                                         -- Line 23
COUNT(o.order_id) AS completed_orders,                            -- Line 24
SUM(o.total_amount) AS total_revenue_usd,                         -- Line 25
AVG(o.total_amount) AS avg_order_value_usd                        -- Line 26
FROM orders o                                                     -- Line 27
JOIN customers c ON o.customer_id = c.customer_id                 -- Line 28
WHERE o.order_status = 'COMPLETED'                                -- Line 29
GROUP BY c.region;                                                -- Line 30
                                                                  -- Line 31 (blank)
SELECT * FROM v_regional_revenue_summary ORDER BY region ASC;     -- Line 32
```

---

## Part 2: Reviewer-Hardened Minute-by-Minute Recording Script (`21–24 Minutes`)

### Pre-Recording Setup Checklist (Critical — Do Every Item Before Hitting Start!)
1. **Change Your Mac UI First (Mandatory Between Every Task / Re-Record!):**
   - Change your macOS **Wallpaper** (`System Settings → Wallpaper`), toggle **Light/Dark mode** or change **Accent Color** (`System Settings → Appearance`), and leave a thin strip of wallpaper visible around your windows.
2. **Verify `TablePlus` Is Refreshed (`55` Rows) & Minimized:**
   - In **TablePlus**, press **`Command + R`** so `orders` shows all **55 rows** (`501–555`) and `v_regional_revenue_summary` is gone from the left sidebar.
   - Click the `SQL` button in the top toolbar, clear any old text in the SQL Query editor so **Line 1 is blank**, return to the `customers` table tab (`Data` view), and **click the yellow Minimize button (`-`)** in the top-left corner of TablePlus.
3. **Verify `optimize_orders.sql` Is Already Open in `Visual Studio Code` (Reviewer Point #6!):**
   - In **Visual Studio Code**, open `/Users/b0a07w6/Downloads/task4_sqlite`.
   - Click `db_audit_report.md` so it opens as Tab 2, and then click **`optimize_orders.sql` so it is already open as the active editor tab on Line 1** prior to recording!
   - **Click the yellow Minimize button (`-`)** in the top-left corner of VS Code.
4. **Open `Accessibility Inspector` & Goal Document:**
   - Ensure `Accessibility Inspector` is running, and leave your **Opening Goal Document** (Google Docs in Chrome) un-minimized behind TaskRecorder.

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, wait **2 seconds** (`00:00:02`) so TaskRecorder is clearly captured on video, then click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open TablePlus from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click **TablePlus** in the Dock on the left side of the screen.

---

### SECTION B: Inspect Preexisting Data & Schema in `TablePlus` (`00:20 – 04:30`)

*(Speak slowly and clearly, stating **What**, **Where**, and **Why** before every click!)*

1. **Speak, then inspect `customers` (`Data` tab):**
   > 🎤 "**What:** I will inspect the preexisting `customers` table data. **Where:** In the left `Items` sidebar of TablePlus, I will click `customers` and review the center data grid. **Why:** We need to know the valid `customer_id` range and regional mapping before auditing foreign keys in the `orders` table. Looking at rows 1 through 20 in the center grid, `customer_id` runs strictly from `101` (`Test Client 1` in `North America`) to `120` (`Test Client 20` in `LATAM`), with five customers in each of our four regions: `North America`, `EMEA`, `APAC`, and `LATAM`."
2. **Action:** Click `customers` in the left sidebar and slowly move your mouse across rows `101` to `120` and columns `customer_id`, `company_name`, `region`, and `account_tier` (~35s).
3. **Speak, then inspect `customers` (`Structure` tab):**
   > 🎤 "**What:** Next, I will inspect the schema definition of `customers`. **Where:** At the bottom-left bar of the TablePlus window, I will click the `Structure` button. **Why:** To confirm that `customer_id` is the primary key (`INTEGER PRIMARY KEY`) that the `orders` table should reference."
4. **Action:** Click **Structure** at the bottom-left of TablePlus, point at `customer_id` (`INTEGER PRIMARY KEY`), then click **Data** at the bottom-left.
5. **Speak, then click `orders` in the left sidebar and scroll to the bottom (`rows 501–555`):**
   > 🎤 "**What:** Now I will inspect the preexisting `orders` table. **Where:** In the left `Items` sidebar of TablePlus, I will click `orders` and scroll down the center data grid from row 1 (`order_id 501`) to row 55 (`order_id 555`). **Why:** To see how `orders` links to `customers` via `customer_id` and spot any data corruption in `customer_id` or `total_amount`. Notice rows `501` through `540` are valid Q4 `COMPLETED` orders (`$1,000` to `$2,500`), and rows `541` through `550` are `PENDING` and `REFUNDED` orders. However, at the bottom of the table on rows `51` through `55` (`order_id` `551` through `555`), we see two serious integrity issues:
   > - First, `order_id` `551`, `552`, and `553` have `customer_id = 999`, which does not exist in `customers` (`101–120`).
   > - Second, `order_id` `554` and `555` have corrupted negative values (`-1500.0` and `-2400.0`) in the `total_amount` column."
6. **Action:** Click `orders` in the left sidebar, scroll down to rows `551–555` with the mouse, and point at `customer_id = 999` and `total_amount = -1500.0 / -2400.0`.
7. **Speak, then click `Structure` on `orders`:**
   > 🎤 "**What:** I will check the `orders` table structure and indexes. **Where:** At the bottom-left bar of TablePlus, I will click the `Structure` button. **Why:** To verify why SQLite allowed orphan `customer_id` values and negative `total_amount` entries, and to check whether any secondary index exists on `order_status` and `order_date`. Looking at the schema grid in the center and the `Indexes` bar at the bottom, there is no foreign key constraint, no `CHECK` constraint, and zero secondary indexes."
8. **Action:** Click **Structure** at the bottom-left of TablePlus and point to the empty Indexes area.

---

### SECTION C: Diagnose & Clean Corrupted Rows in TablePlus SQL Editor (`04:30 – 10:00`)

*(Remember Reviewer Points 1, 2, 3, 5, 7: explicitly state the **line number**, **how you move to the next line (`Enter` key)**, **how each line links to the preexisting table columns**, and **why you highlight specific lines before clicking `Run Current`**!)*

1. **Speak, then open the SQL Query Editor:**
   > 🎤 "**What:** I will open the interactive SQL Query editor. **Where:** In the top-left toolbar of TablePlus, I will click the `SQL` button (shortcut `Command + E`). **Why:** So we can write and execute diagnostic and remediation SQL statements against `orders_audit.sqlite`."
2. **Action:** Click the **SQL** button in the top toolbar of TablePlus.
3. **Speak, then type Block 1 (Orphan Detection Query on `Lines 1–4`):**
   > 🎤 "**What:** I will write a 4-line `LEFT JOIN` diagnostic query to detect orphaned orders. **Where:** Starting on **line 1** in the top-center SQL Query editor pane of TablePlus, pressing the `Enter` key at the end of each line to advance from **line 1** to **line 4**:
   > - On **line 1**, I type `SELECT o.*` to return all columns from the `orders` table.
   > - I press `Enter` to move to **line 2** and type `FROM orders o LEFT JOIN customers c` to join our `orders` table (aliased as `o`) to our preexisting `customers` table (aliased as `c`).
   > - I press `Enter` to move to **line 3** and type `ON o.customer_id = c.customer_id` to link `customer_id` in `orders` with `customer_id` in `customers`.
   > - I press `Enter` to move to **line 4** and type `WHERE c.customer_id IS NULL;` **Why:** Because any order whose `o.customer_id` (`999`) has no matching primary key in `customers` (`101–120`) will produce `NULL` on the right side of the `LEFT JOIN`."
4. **Action:** Type on **lines 1–4**:
   ```sql
   SELECT o.*
   FROM orders o LEFT JOIN customers c
   ON o.customer_id = c.customer_id
   WHERE c.customer_id IS NULL;
   ```
5. **Speak, then select `Lines 1–4` and click `Run Current`:**
   > 🎤 "**What:** I will execute our orphan detection query. **Where:** In the SQL Query editor pane, I will drag-select **lines 1 through 4** with the mouse and click the `Run Current` button in the middle-right toolbar (or press `Command + Enter`). **Why:** Highlighting lines 1 through 4 ensures TablePlus executes this specific diagnostic query and displays the orphaned records in the bottom results grid."
6. **Action:** Drag-select **lines 1–4** and click **Run Current**. Point at the 3 returned rows (`551, 552, 553` with `customer_id = 999`) in the bottom results grid (~15s).
7. **Speak, then move to `Line 6` and type Block 2 (Negative Amount Query on `Line 6`):**
   > 🎤 "**What:** Next, I will write a query to isolate corrupted negative transaction amounts. **Where:** At the end of **line 4** in the SQL Query editor, I will press the `Enter` key twice—leaving **line 5** blank for readability—to move the cursor to **line 6**, and type `SELECT * FROM orders WHERE total_amount < 0;`. **Why:** This filters the preexisting `total_amount` column in `orders` for any value below zero. I will now drag-select **line 6** with the mouse and click `Run Current` so TablePlus runs only line 6 without re-running lines 1 through 4."
8. **Action:** Press `Enter` twice to move to **line 6**, type:
   ```sql
   SELECT * FROM orders WHERE total_amount < 0;
   ```
   Drag-select **line 6** with the mouse and click **Run Current**. Point at rows `554` (`-1500.0`) and `555` (`-2400.0`) in the bottom results pane (~15s).
9. **Speak, then move to `Lines 8–12` and type Block 3 (Two `DELETE` Statements on `Lines 8–12`):**
   > 🎤 "**What:** Now I will write two `DELETE` statements to purge the 3 orphaned rows and 2 negative-amount rows. **Where:** At the end of **line 6**, I will press the `Enter` key twice to move to **line 8**:
   > - On **line 8**, I type `DELETE FROM orders`, press `Enter` to move to **line 9**, and type `WHERE customer_id NOT IN (SELECT customer_id FROM customers);` to delete any row in `orders` whose `customer_id` (`999`) is not present in the `customer_id` column of `customers` (`101–120`).
   > - Next, I press the `Enter` key twice—leaving **line 10** blank—to move to **line 11**, where I type `DELETE FROM orders`, press `Enter` to move to **line 12**, and type `WHERE total_amount < 0;` to delete rows `554` and `555`.
   > **Why:** Removing these five invalid rows restores referential and domain integrity before we index and aggregate Q4 revenue. I will now drag-select **lines 8 through 12** with the mouse and click `Run Current` so TablePlus executes only these two `DELETE` commands."
10. **Action:** Press `Enter` twice to move to **line 8**, type **lines 8–12**:
    ```sql
    DELETE FROM orders
    WHERE customer_id NOT IN (SELECT customer_id FROM customers);

    DELETE FROM orders
    WHERE total_amount < 0;
    ```
    Drag-select **lines 8–12** with the mouse and click **Run Current**.
11. **Speak, then verify `50` rows remain in the `orders` tab:**
    > 🎤 "**What:** Let's verify that the 5 corrupted rows have been removed from the preexisting `orders` table. **Where:** In the top tab bar of TablePlus, I will click the `orders` tab, click `Data` in the bottom-left bar, and press `Command + R` to refresh the table grid. **Why:** To confirm that `order_id` `551` through `555` are deleted and exactly `50` valid rows (`501` to `550`) remain. Now I will click the `SQL Query` tab at the top of TablePlus to return to our SQL editor."
12. **Action:** Click the `orders` tab, click `Data`, press `Cmd + R`, point at row 50 (`order_id 550`) at the bottom of the grid, then click the `SQL Query` tab at the top.

---

### SECTION D: `EXPLAIN QUERY PLAN`, Composite B-Tree Index & Regional View (`10:00 – 16:00`)

1. **Speak, then move to `Lines 14–16` and type Block 4 (`EXPLAIN QUERY PLAN` on `Lines 14–16`):**
   > 🎤 "**What:** Next, I will analyze the query execution plan for filtering Q4 completed orders. **Where:** At the end of **line 12** in the SQL Query editor, I will press the `Enter` key twice—leaving **line 13** blank—to move to **line 14**:
   > - On **line 14**, I type `EXPLAIN QUERY PLAN` to instruct SQLite to return its internal query execution strategy rather than row data.
   > - I press `Enter` to move to **line 15** and type `SELECT * FROM orders` to target our cleaned 50-row `orders` table.
   > - I press `Enter` to move to **line 16** and type `WHERE order_status = 'COMPLETED' AND order_date >= '2026-10-01';` to filter the preexisting `order_status` column for `'COMPLETED'` and the `order_date` column for Q4 dates starting October 1st, 2026.
   > **Why:** We need to prove whether SQLite is currently performing a slow full table scan. I will drag-select **lines 14 through 16** with the mouse and click `Run Current` so TablePlus executes only this `EXPLAIN QUERY PLAN` block."
2. **Action:** Press `Enter` twice to move to **line 14**, type **lines 14–16**:
   ```sql
   EXPLAIN QUERY PLAN
   SELECT * FROM orders
   WHERE order_status = 'COMPLETED' AND order_date >= '2026-10-01';
   ```
   Drag-select **lines 14–16** with the mouse and click **Run Current**.
3. **Speak while pointing at `SCAN orders` in the bottom results pane (~20s):**
   > 🎤 "Look at the `detail` column in the bottom results pane of TablePlus: SQLite returns `SCAN orders`. Because there is no index on `order_status` and `order_date`, SQLite has to read all 50 rows sequentially—including the 10 `PENDING` and `REFUNDED` rows (`541–550`)—to find the matching records."
4. **Speak, then move to `Lines 18–19` and type Block 5 (`CREATE INDEX` on `Lines 18–19`):**
   > 🎤 "**What:** I will create a composite B-tree index named `idx_orders_status_date`. **Where:** At the end of **line 16** in the SQL Query editor, I will press the `Enter` key twice—leaving **line 17** blank—to move to **line 18**:
   > - On **line 18**, I type `CREATE INDEX idx_orders_status_date`, press `Enter` to move to **line 19**, and type `ON orders(order_status, order_date);`.
   > **Why:** Placing `order_status` first (our equality filter `= 'COMPLETED'`) and `order_date` second (our range filter `>= '2026-10-01'`) allows SQLite's B-tree index to jump directly to completed Q4 orders without scanning the table. I will now drag-select **lines 18 and 19** with the mouse and click `Run Current` to build the index."
5. **Action:** Press `Enter` twice to move to **line 18**, type **lines 18–19**:
   ```sql
   CREATE INDEX idx_orders_status_date
   ON orders(order_status, order_date);
   ```
   Drag-select **lines 18–19** with the mouse and click **Run Current**.
6. **Speak, then re-select `Lines 14–16` to verify the upgraded execution plan:**
   > 🎤 "**What:** I will now re-run our `EXPLAIN QUERY PLAN` statement. **Where:** In the SQL Query editor pane, I will drag-select **lines 14 through 16** with the mouse and click `Run Current`. **Why:** Selecting lines 14 through 16 re-runs the exact same `EXPLAIN QUERY PLAN` query after index creation so we can verify that SQLite now uses `idx_orders_status_date` instead of `SCAN orders`."
7. **Action:** Drag-select **lines 14–16** with the mouse and click **Run Current**. Point at `SEARCH orders USING INDEX idx_orders_status_date (order_status=? AND order_date>?)` in the bottom results pane (~20s).
8. **Speak, then move to `Lines 21–32` and type Block 6 (`CREATE VIEW` & `SELECT` on `Lines 21–32` — Addresses Reviewer Point #5 Directly!):**
   > 🎤 "**What:** Now I will create a reusable SQL reporting view named `v_regional_revenue_summary` and query it to produce our Q4 regional revenue scorecard. **Where:** At the end of **line 19** in the SQL Query editor, I will press the `Enter` key twice—leaving **line 20** blank—to move to **line 21**, pressing `Enter` after each line down to **line 32**:
   > - On **line 21**, I type `CREATE VIEW v_regional_revenue_summary AS` to define the persistent reporting view.
   > - On **lines 22 and 23**, I type `SELECT` and `c.region,` to pull the preexisting `region` column from the `customers` table.
   > - On **line 24**, I type `COUNT(o.order_id) AS completed_orders,` to count the valid completed orders per region from `orders.order_id`.
   > - On **line 25**, I type `SUM(o.total_amount) AS total_revenue_usd,` to sum the cleaned dollar amounts from `orders.total_amount`.
   > - On **line 26**, I type `AVG(o.total_amount) AS avg_order_value_usd` to compute the average order value per region.
   > - On **lines 27 and 28**, I type `FROM orders o` and `JOIN customers c ON o.customer_id = c.customer_id` to link each order's `customer_id` to its customer's `region`.
   > - On **lines 29 and 30**, I type `WHERE o.order_status = 'COMPLETED'` (which now uses our new `idx_orders_status_date` index) and `GROUP BY c.region;` to aggregate the metrics across our four regions.
   > - Finally, I press `Enter` twice—leaving **line 31** blank—to move to **line 32**, and type `SELECT * FROM v_regional_revenue_summary ORDER BY region ASC;` to display the view's output sorted alphabetically by region."
9. **Action:** Press `Enter` twice to move to **line 21**, and type **lines 21–32**:
   ```sql
   CREATE VIEW v_regional_revenue_summary AS
   SELECT
   c.region,
   COUNT(o.order_id) AS completed_orders,
   SUM(o.total_amount) AS total_revenue_usd,
   AVG(o.total_amount) AS avg_order_value_usd
   FROM orders o
   JOIN customers c ON o.customer_id = c.customer_id
   WHERE o.order_status = 'COMPLETED'
   GROUP BY c.region;

   SELECT * FROM v_regional_revenue_summary ORDER BY region ASC;
   ```
10. **Speak BEFORE selecting `Lines 21–32` (Reviewer Point #5!):**
    > 🎤 "**What:** I will now select and execute **lines 21 through 32**. **Where:** In the center SQL Query editor of TablePlus, I will drag-select **lines 21 through 32** with my mouse and click the `Run Current` button. **Why:** In TablePlus, when multiple SQL statements exist in the same editor buffer, highlighting **lines 21 through 32** tells `Run Current` to execute **only** the `CREATE VIEW` statement (lines 21–30) and the `SELECT * FROM v_regional_revenue_summary` query (line 32), without re-running the `DELETE` or `CREATE INDEX` statements on lines 1 through 19 (which would throw an `'index idx_orders_status_date already exists'` error if re-run)."
11. **Action:** Drag-select **lines 21–32** with the mouse and click **Run Current**.
12. **Speak while pointing at the 4 regional rows in the bottom results pane (~25s):**
    > 🎤 "In the bottom results grid of TablePlus, `v_regional_revenue_summary` returns our exact Q4 completed revenue across all 40 valid completed orders (`10` orders per region, `$70,000` total):
    > - Row 1 (`APAC`): `10` completed orders, `$15,000.0` total revenue, `$1,500.0` average order value.
    > - Row 2 (`EMEA`): `10` completed orders, `$20,000.0` total revenue, `$2,000.0` average order value.
    > - Row 3 (`LATAM`): `10` completed orders, `$25,000.0` total revenue, `$2,500.0` average order value.
    > - Row 4 (`North America`): `10` completed orders, `$10,000.0` total revenue, `$1,000.0` average order value."
13. **Speak, then copy all 32 lines (`Command + A`, `Command + C`) and minimize TablePlus (`-`):**
    > 🎤 "**What:** I will copy our complete 32-line SQL script and switch to Visual Studio Code. **Where:** Inside the TablePlus SQL Query editor pane, I will press `Command + A` to select **lines 1 through 32**, press `Command + C` to copy them to the clipboard, and then click the yellow minimize button (`-`) in the top-left corner of the TablePlus window. **Why:** So we can save the reproducible `.sql` migration file and render our visual Markdown audit dashboard in Visual Studio Code without overlapping windows."
14. **Action:** Press `Cmd + A`, press `Cmd + C`, then **click the yellow Minimize button (`-`)** in the top-left corner of TablePlus!

---

### SECTION E: Save Migration Script & Render Visual Audit Dashboard in `VS Code` (`16:00 – 20:30`)

*(Addresses Reviewer Points #4 and #6: `optimize_orders.sql` is already open on Line 1 when VS Code is restored, and at the end we open the side-by-side **Markdown Preview Dashboard** so the viewer sees the rendered visual report outcome!)*

1. **Speak, then open `Visual Studio Code` from the Dock:**
   > 🎤 "**What:** I will restore Visual Studio Code. **Where:** From the macOS Dock on the left side of the screen, I will click the Visual Studio Code icon. **Why:** To save our production SQL migration script in `optimize_orders.sql`—which is already open on **line 1** in the main editor tab—and build our visual audit dashboard report in `db_audit_report.md`."
2. **Action:** Click **Visual Studio Code** in the Dock. (`optimize_orders.sql` is already open in the active editor tab on **line 1**!)
3. **Speak, then paste into `optimize_orders.sql` (`Command + V`) and save (`Command + S`):**
   > 🎤 "**What:** I will paste and save our 32-line SQL script in `optimize_orders.sql`. **Where:** Clicking on **line 1** inside the already-open `optimize_orders.sql` editor tab in the center of Visual Studio Code, I will press `Command + V` to paste all 32 lines from TablePlus, and press `Command + S` to save the file to disk. **Why:** Persisting these statements in `optimize_orders.sql` gives the engineering team a repeatable migration script covering orphan detection (lines 1–6), data deletion (lines 8–12), execution plan verification (lines 14–16), composite B-tree index creation (lines 18–19), and regional view creation (lines 21–32)."
4. **Action:** Click **line 1** of `optimize_orders.sql`, press `Cmd + V`, and press `Cmd + S`. Slowly scroll from line 1 to line 32 with the mouse (~15s).
5. **Speak, then click the `db_audit_report.md` tab, type the report (`Lines 1–16`), save (`Command + S`), and open the Visual Preview Dashboard (`Command + K` then `V` or Top-Right Preview Icon):**
   > 🎤 "**What:** Next, I will switch to `db_audit_report.md`, write our structured audit report on **lines 1 through 16** (pressing `Enter` at the end of each line to move to the next line), save it with `Command + S`, and open VS Code's side-by-side Markdown Preview dashboard. **Where:** In the top editor tab bar of Visual Studio Code, I will click the second tab `db_audit_report.md` starting on **line 1**. **Why:** Writing the audit findings and regional revenue metrics in Markdown and rendering them in VS Code's live preview produces a clean, visual executive summary dashboard comparing our before-and-after database states."
6. **Action:** Click the `db_audit_report.md` tab at the top of VS Code, type **lines 1–16** (pressing `Enter` at the end of each line):
   ```markdown
   # Database Integrity & Optimization Audit

   ## 1. Data Integrity Cleanup
   - Removed 3 orphan orders (`551-553`, `customer_id = 999`) and 2 negative orders (`554-555`), retaining 50 valid rows.

   ## 2. Performance Optimization
   - Created `idx_orders_status_date` on `orders(order_status, order_date)`.
   - Plan upgraded from `SCAN orders` to `SEARCH orders USING INDEX idx_orders_status_date`.

   ## 3. Q4 Completed Regional Revenue ($70,000 Total)
   | Region | Completed Orders | Total Revenue | Avg Order Value |
   | --- | --- | --- | --- |
   | APAC | 10 | $15,000 | $1,500 |
   | EMEA | 10 | $20,000 | $2,000 |
   | LATAM | 10 | $25,000 | $2,500 |
   | North America | 10 | $10,000 | $1,000 |
   ```
   Press **`Cmd + S`** to save `db_audit_report.md`.
7. **Speak, then click the `Open Preview to the Side` icon in the top-right of the VS Code editor tab bar (Reviewer Point #4!):**
   > 🎤 "**What:** Now I will render the live visual preview of our audit report and regional revenue table. **Where:** In the top-right corner of the Visual Studio Code editor tab bar, I will click the `Open Preview to the Side` split-pane icon (or press `Command + K` followed by `V`). **Why:** This renders our Markdown code on the left into a formatted visual audit dashboard and revenue table on the right side of Visual Studio Code so stakeholders can review the integrity fixes, index upgrade, and `$70,000` Q4 regional breakdown at a glance."
8. **Action:** Click the **Open Preview to the Side** icon in the top-right corner of VS Code (next to the split editor button) so the formatted Markdown preview opens in the right half of VS Code! Point with your mouse across the rendered headings and the rendered 4-row Regional Revenue table for ~20 seconds.

---

### SECTION F: 3-Minute Verbal Epilogue (`20:30 – 23:30`)

*(Move your mouse slowly across the rendered Markdown Preview dashboard on the right side of VS Code and the `optimize_orders.sql` tab while delivering this summary—zero typing!)*

> 🎤 "Let's wrap up with a summary of our workflow, key engineering decisions, and lessons learned.
>
> First, completion and verification: we completed the relational data integrity audit and query performance optimization on `orders_audit.sqlite` using TablePlus and Visual Studio Code. In TablePlus, we inspected the preexisting `customers` (`customer_id` `101–120`) and `orders` (`order_id` `501–555`) tables, wrote diagnostic queries on lines 1 through 6 of the SQL editor that isolated three orphaned order rows (`551`, `552`, `553` referencing non-existent `customer_id = 999`) and two corrupted rows (`554` and `555` with negative `total_amount` values `-1500.0` and `-2400.0`), and executed `DELETE` statements on lines 8 through 12 to leave fifty clean, valid rows. We then analyzed the Q4 completed-orders query on lines 14 through 16 with `EXPLAIN QUERY PLAN`, created the composite B-tree index `idx_orders_status_date` on lines 18 and 19, verified that SQLite upgraded its execution plan from a full table scan (`SCAN orders`) to an indexed seek (`SEARCH orders USING INDEX`), created and queried the `v_regional_revenue_summary` view on lines 21 through 32 totaling `$70,000` across forty completed orders (`$25,000` LATAM, `$20,000` EMEA, `$15,000` APAC, and `$10,000` North America), and saved `optimize_orders.sql` and our rendered `db_audit_report.md` summary dashboard in Visual Studio Code.
>
> Second, why this approach was effective: ordering the columns in `idx_orders_status_date` with the equality column (`order_status`) first and the range column (`order_date`) second satisfies the B-tree leftmost-prefix rule—enabling SQLite to jump directly to the `'COMPLETED'` partition of the index and traverse `order_date >= '2026-10-01'` sequentially without scanning `PENDING` or `REFUNDED` rows.
>
> Third, common mistakes that someone less experienced should watch out for in SQLite administration:
> - Number one: assuming SQLite enforces foreign key constraints out of the box—because `PRAGMA foreign_keys` defaults to `OFF` unless explicitly enabled, orphan child rows like `customer_id = 999` can enter the table and silently drop out of inner-joined regional reports if not audited with a `LEFT JOIN ... WHERE c.customer_id IS NULL` check.
> - Number two: running revenue aggregations (`SUM` and `AVG`) before purging negative corrupted amounts (`-1500.0` and `-2400.0`), which artificially depresses both total revenue and average order value in North America.
> - Number three: placing the range column (`order_date`) ahead of the equality column (`order_status`) in a composite index, which prevents the query planner from using both columns in a single B-tree range seek.
>
> All deliverables are saved and ready for packaging. Thank you for watching."

---

## Part 3: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

**Important Tip When Packaging `Deliverables/`:**
Use **Copy (`cp` or `Option + Drag`)** instead of moving (`mv`) `orders_audit.sqlite` out of `task4_sqlite/` so TablePlus never loses its file path!

```text
Deliverables/
├── input 1.sqlite        <-- Copy from input_1_orders_audit_backup.sqlite (starting 55-row un-indexed DB)
├── input 2.sql           <-- Copy from seed_orders_db.sql
├── final output 1.sqlite <-- Copy from orders_audit.sqlite (optimized 50-row DB with index & view)
├── final output 2.sql    <-- Copy from optimize_orders.sql
└── final output 3.md     <-- Copy from db_audit_report.md
```
