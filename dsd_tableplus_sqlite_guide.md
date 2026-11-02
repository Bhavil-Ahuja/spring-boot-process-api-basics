# Task 4 Master Guide (`DSD`): SQLite Database Integrity Audit, Indexing & Query Optimization (`TablePlus` + `VS Code`)

---

## Why This Task 4 Design Is a Home Run
1. **Generous `35%` Typing Limit (`DSD` Domain):**
   - Because this task is in **`DSD` (`Data Science & Analytics; Software & AI/ML Engineering`)**, AutoQC gives you the **35% typing threshold** (instead of `25%`), and **TablePlus**'s visual GUI tabs (`Data`, `Structure`, `Filter`, `SQL`) still keep your actual typing down around **`16–20%`**.
2. **Zero Spreadsheets — 100% Visual Database Engineering:**
   - Uses **TablePlus** (native macOS GUI database client) + **Visual Studio Code** (plus **Google Docs** only for the 10-second Opening Goal Document at `00:00:00`).
3. **Clear, Measurable Engineering Before/After Proof:**
   - **Data Integrity Fix:** Find and remove **3 orphan order records** (`customer_id = 999` with no matching customer in `customers`) and **2 negative-amount corrupted rows** (`total_amount < 0`).
   - **Query Plan Optimization (`EXPLAIN QUERY PLAN`):** Prove that a filtered reporting query does a slow full table scan (`SCAN orders`) before indexing, and switches to a fast B-tree index search (`SEARCH orders USING INDEX idx_orders_status_date`) after creating a composite index.
   - **Reusable SQL View + Migration Script:** Create a reporting view `v_regional_revenue_summary` in SQLite and save the reproducible migration script (`optimize_orders.sql`) and audit summary (`db_audit_report.md`) in **VS Code**.

---

## Part 1: Step-by-Step Studio Idea Submission & Approval (Do This First!)

Before you generate the SQLite file or record, submit your idea in Studio and wait for the status to move from **`Idea Draft`** → **`Idea Approved: Confirm Tech Setup`** → **`Idea Approved: Start Recording`**.

### How to Fill Out Section `1.0 Create your idea` in Studio
1. Click **Create task** in Studio (`Odin Production Full Workflow`).
2. Scroll to **1.0 Create your idea → Describe your Idea**.
3. **Important:** Type the 5 sections below **in your own words** (never copy-paste directly into Studio's text box):

   - **`Domain / Role:`**
     - Write: Database Reliability & Data Engineering Lead (`DSD` — Data Science & Analytics; Software & AI/ML Engineering).
   - **`Goal:`** *(Keep a copy of the exact text you type here—once approved, this exact paragraph goes into your Opening Goal Document, TaskRecorder's Task Description box, and `Metadata.rtf`!)*
     - Paraphrase this in your own words:
       *As a Data Engineering Lead, I need to perform a relational data integrity audit and query performance optimization on our local SQLite order-processing database (`orders_audit.sqlite`) using TablePlus and Visual Studio Code. In TablePlus, I will inspect the `customers` and `orders` table schemas, run diagnostic `LEFT JOIN` and range queries to identify and delete orphaned order records (pointing to non-existent customer IDs) and corrupted negative-amount transactions, analyze slow reporting query execution plans using `EXPLAIN QUERY PLAN`, create a composite B-tree index (`idx_orders_status_date`) to eliminate full table scans, and create an aggregated `v_regional_revenue_summary` SQL view. Finally, in Visual Studio Code, I will document the production SQL migration script (`optimize_orders.sql`) and the before-and-after query execution plan audit report (`db_audit_report.md`).*
   - **`Starting materials:`**
     - Paraphrase this in your own words:
       *A synthetic local SQLite database file (`orders_audit.sqlite`) and its seed schema script (`seed_orders_db.sql`) prepared with Gemini prior to recording, containing two tables: (1) `customers` (20 anonymized enterprise customer records `CUST-101` to `CUST-120` across `North America`, `EMEA`, `APAC`, and `LATAM`); and (2) `orders` (55 order rows `ORD-501` to `ORD-555`, including 3 orphaned orders referencing non-existent `customer_id = 999`, 2 corrupted rows with negative `total_amount`, and no secondary indexes on `order_status` or `order_date`).*
   - **`Steps (with the apps for each):`**
     - Paraphrase these 2 app bullets in your own words:
       - *TablePlus:* Open the `orders_audit.sqlite` database, inspect the `customers` and `orders` tables in the `Data` and `Structure` tabs, use the GUI filter bar and SQL query editor to locate and delete the 3 orphaned order rows (`LEFT JOIN` where `customers.customer_id IS NULL`) and 2 negative-amount rows (`total_amount < 0`), run `EXPLAIN QUERY PLAN` on the regional completed-orders query to observe the `SCAN orders` full table scan, create the composite index `idx_orders_status_date ON orders(order_status, order_date)` and re-run `EXPLAIN QUERY PLAN` to verify `SEARCH orders USING INDEX`, create the `v_regional_revenue_summary` view, and export the cleaned summary results.
       - *Visual Studio Code:* Create and save the production SQL migration file (`optimize_orders.sql`) containing the data cleanup statements, composite index definition, and view definition, and write a concise Markdown technical audit report (`db_audit_report.md`) comparing the before-and-after `EXPLAIN QUERY PLAN` outputs and regional revenue totals.
   - **`Deliverable:`**
     - Paraphrase this in your own words:
       *1. The optimized and cleaned SQLite database file (`final output 1.sqlite`) containing the 50 valid orders, the `idx_orders_status_date` composite index, and the `v_regional_revenue_summary` view.*
       *2. The production SQL migration script (`final output 2.sql`) and Markdown query optimization report (`final output 3.md`) saved from Visual Studio Code.*

4. **Select Apps in Studio's `Used Apps` Dropdown:**
   - Select **`TablePlus`** and **`Visual Studio Code`** (or if `TablePlus` is not in the dropdown list, select **`Visual Studio Code`** and **`Terminal`** / **`SQLite`**—check the dropdown when submitting!).
5. Click **Submit idea** and wait for approval before moving to Phase 2.

---

## Part 2: Complete 3-Hour (`180-Minute`) End-to-End Time Plan (Includes Gemini + Recording!)

| Time Window | Duration | Phase | What You Actively Do |
|---|---:|---|---|
| **0:00 – 0:25** | `25 min` | **1. Ideation & Studio Idea Submission** | Review the DSD workflow, run **Prompt 1** below with Gemini to design the `customers` and `orders` SQLite schema and query plan bottleneck, and type your 5-part idea into Studio's **Describe your Idea** in your own words. |
| **0:25 – 1:10** | `45 min` | **2. SQLite Seed Script Generation & Audit with Gemini (After Approval)** | Once your idea is approved, run **Prompts 2–4** with Gemini to generate the `seed_orders_db.sql` script, build `orders_audit.sqlite` using `sqlite3 orders_audit.sqlite < seed_orders_db.sql`, and paste the Gemini output here so we validate the exact row counts and totals before you record. |
| **1:10 – 1:45** | `35 min` | **3. Scratch Dry-Run in TablePlus & VS Code** | Open a scratch copy of `orders_audit.sqlite` in **TablePlus**, practice switching between the `Data` tab, `Structure` tab, and `SQL` tab (`Cmd + E`), and practice minimizing TablePlus (`-`) before opening **VS Code**. |
| **1:45 – 2:00** | `15 min` | **4. Desktop Appearance Change & Pre-Recording Setup** | Change your macOS Wallpaper + toggle Light/Dark mode + change Accent Color + adjust Dock size (Task Variety requirement). Reset `orders_audit.sqlite` from `seed_orders_db.sql` so it is back in its raw 55-row state. Open Window 1 (Opening Goal Document in Google Docs), minimize TablePlus and VS Code into the Dock. |
| **2:00 – 2:25** | `25 min` | **5. Actual Video Recording (In TaskRecorder)** | Record the complete 20–23 minute workflow and 3-minute Epilogue in one uninterrupted take using the verbatim What/Where/Why script in Part 5. |
| **2:25 – 3:00** | `35 min` | **6. Verification, `Deliverables.zip`, `Metadata.rtf` & AutoQC** | Spot-check `video.mp4` and `screenshots/`, package `Deliverables.zip`, fill out `Metadata.rtf`, upload all 4 files to Studio, verify AutoQC passes with 0 required findings, and submit. |

---

## Part 3: Professional Gemini Interaction Strategy & Prompt Playbook (45–60 Mins of Logged Work)

Use these **4 progressive prompts** in Gemini during your logged session to generate the SQLite seed script, verify the query plans, and send me the generated SQL so I can lock in the exact numbers for your script:

### Prompt 1 — Designing the Relational Schema, Integrity Bugs & Indexing Scenario (Phase 1 — ~15 mins)
```text
I am a Data Engineering Lead preparing a SQLite database integrity audit and query performance optimization task in TablePlus and Visual Studio Code (`orders_audit.sqlite`).
Help me design a realistic two-table relational schema (`customers` and `orders`) with:
1. `customers` table (20 rows, `customer_id` 101 to 120): columns `customer_id INTEGER PRIMARY KEY, company_name TEXT, region TEXT, account_tier TEXT` using anonymized company names (`Test Client 1` to `Test Client 20`) across `North America`, `EMEA`, `APAC`, and `LATAM`.
2. `orders` table (55 rows, `order_id` 501 to 555): columns `order_id INTEGER PRIMARY KEY, customer_id INTEGER, order_date TEXT, order_status TEXT, product_sku TEXT, total_amount REAL`.
3. Include three realistic database engineering problems that I will diagnose and fix in TablePlus:
   - Missing Foreign Key enforcement that allowed 3 "orphan" orders (`order_id` 551, 552, 553 referencing non-existent `customer_id = 999`) to be inserted.
   - Missing `CHECK (total_amount >= 0)` constraint that allowed 2 corrupted negative-amount orders (`order_id` 554 and 555 with negative `total_amount`) to be inserted.
   - Missing secondary B-tree index on `(order_status, order_date)` causing queries filtering by `order_status = 'COMPLETED' AND order_date >= '2026-10-01'` to perform a full table scan (`SCAN orders`).
```

### Prompt 2 — Generating the Complete `seed_orders_db.sql` Script (Phase 2 — ~15 mins)
```text
Now generate the complete, self-contained SQLite script `seed_orders_db.sql` (`CREATE TABLE` + `INSERT INTO`) for `customers` (20 rows) and `orders` (55 rows):
1. Ensure all company names are anonymized (`Test Client 1` to `Test Client 20`).
2. Among the 50 valid rows (`order_id` 501 to 550):
   - Include 40 `'COMPLETED'` orders (`order_date` in Q4 2026 between `'2026-10-01'` and `'2026-12-31'`) and 10 `'PENDING'` or `'REFUNDED'` orders.
   - Make sure the 40 valid `'COMPLETED'` Q4 orders produce clean, exact regional totals across `North America`, `EMEA`, `APAC`, and `LATAM` (e.g., 10 completed orders per region with clean round dollar amounts).
3. Include the 3 orphan rows (`order_id` 551, 552, 553 with `customer_id = 999`) and the 2 negative corrupted rows (`order_id` 554, 555 with `total_amount` = `-1500.00` and `-2400.00`).
```

### Prompt 3 — Auditing the Exact Diagnostic Queries, `EXPLAIN QUERY PLAN` & Regional View Totals (Phase 2 — ~10 mins)
```text
Using the exact data in `seed_orders_db.sql` you just generated, show me:
1. The exact SQL query to detect the 3 orphaned orders (`LEFT JOIN customers c ON o.customer_id = c.customer_id WHERE c.customer_id IS NULL`) and the 2 negative-amount orders (`WHERE total_amount < 0`), followed by the `DELETE` statements to remove those 5 invalid rows (reducing `orders` from 55 rows to 50 valid rows).
2. The exact `EXPLAIN QUERY PLAN` output before and after running:
   `CREATE INDEX idx_orders_status_date ON orders(order_status, order_date);`
   for our Q4 completed orders query.
3. The exact regional revenue totals (`region`, `completed_orders`, `total_revenue_usd`, `avg_order_value_usd`) returned when we create and query `v_regional_revenue_summary`.
```

### Prompt 4 — Production Migration Script (`optimize_orders.sql`) & Markdown Report Template (Phase 2 — ~10 mins)
```text
Draft a clean, concise SQL migration file (`optimize_orders.sql`) and a short 15-line Markdown summary (`db_audit_report.md`) that I can save in Visual Studio Code documenting:
1. Data integrity cleanup (3 orphan rows + 2 negative rows removed; 50 valid rows retained).
2. Execution plan improvement (`SCAN orders` -> `SEARCH orders USING INDEX idx_orders_status_date`).
3. Final Q4 regional completed revenue table from `v_regional_revenue_summary`.
```

---

## Part 4: Exact Workflow & SQL Commands in `TablePlus` and `VS Code`

### How to Build the Starting `.sqlite` File Once Gemini Gives You `seed_orders_db.sql`
Once Gemini generates `seed_orders_db.sql`, save it in `/Users/b0a07w6/Downloads/task4_sqlite/` and run:
```bash
sqlite3 /Users/b0a07w6/Downloads/task4_sqlite/orders_audit.sqlite < /Users/b0a07w6/Downloads/task4_sqlite/seed_orders_db.sql
```
*(Or paste Gemini's `seed_orders_db.sql` output here first, and I will build `orders_audit.sqlite` for you and verify every single query output!)*

### The 5 Short SQL Blocks You Will Run in TablePlus (and Save in `optimize_orders.sql`)

```sql
-- 1. Audit Orphaned Orders (missing customer_id in customers) & Negative Amounts
SELECT o.order_id, o.customer_id, o.order_status, o.total_amount
FROM orders o
LEFT JOIN customers c ON o.customer_id = c.customer_id
WHERE c.customer_id IS NULL OR o.total_amount < 0;

-- 2. Delete the 5 Invalid Rows (3 Orphans + 2 Negative Amounts -> 55 to 50 rows)
DELETE FROM orders
WHERE customer_id NOT IN (SELECT customer_id FROM customers)
   OR total_amount < 0;

-- 3. Check Execution Plan BEFORE Indexing (Shows full table scan: SCAN orders)
EXPLAIN QUERY PLAN
SELECT c.region, COUNT(o.order_id) AS orders_cnt, SUM(o.total_amount) AS revenue
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
WHERE o.order_status = 'COMPLETED' AND o.order_date >= '2026-10-01'
GROUP BY c.region;

-- 4. Create Composite Index & Re-Check Execution Plan (Shows SEARCH orders USING INDEX)
CREATE INDEX idx_orders_status_date ON orders(order_status, order_date);

-- 5. Create Reporting View & Query Final Regional Totals
CREATE VIEW v_regional_revenue_summary AS
SELECT c.region,
       COUNT(o.order_id) AS completed_orders,
       SUM(o.total_amount) AS total_revenue_usd,
       ROUND(AVG(o.total_amount), 2) AS avg_order_value_usd
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
WHERE o.order_status = 'COMPLETED' AND o.order_date >= '2026-10-01'
GROUP BY c.region
ORDER BY total_revenue_usd DESC;

SELECT * FROM v_regional_revenue_summary;
```

---

## Part 5: AutoQC-Hardened Minute-by-Minute Recording Script (`20–23 Minutes`)

### Pre-Recording Setup Checklist (Critical!)
1. **Change Your Mac UI First (Mandatory Between Every Task!):**
   - `System Settings → Wallpaper`: Pick a **new wallpaper** (different from macOS default and Tasks 1–3).
   - `System Settings → Appearance`: Toggle **Light/Dark mode** and pick a **new Accent Color**.
   - Leave a small margin of desktop wallpaper visible around your application windows.
2. **Window 1 (Google Chrome — Opening Goal Doc):**
   - Open a Chrome window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder at `00:00:00`.
3. **Window 2 (`TablePlus`):**
   - Open `TablePlus`, connect to `/Users/b0a07w6/Downloads/task4_sqlite/orders_audit.sqlite` so the left sidebar shows `customers` and `orders`, and then **click the yellow Minimize button (`-`)** in the top-left corner of TablePlus!
4. **Window 3 (`Visual Studio Code`):**
   - Open `Visual Studio Code` to the `/Users/b0a07w6/Downloads/task4_sqlite` folder with two empty files ready in the sidebar (`optimize_orders.sql` and `db_audit_report.md`), and then **click the yellow Minimize button (`-`)** in the top-left corner of VS Code!
   - *(Golden Rule: Never have two app windows un-minimized at the same time—always minimize `-` before switching apps!)*

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open TablePlus from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click **TablePlus** in the Dock.

---

### SECTION B: Inspect Tables & Structure in `TablePlus` Using Mouse GUI (`00:20 – 04:30`)

*(100% mouse-driven GUI exploration in TablePlus—zero typing for the first 4 minutes!)*

1. **Speak, then click `customers` in the left sidebar of TablePlus:**
   > 🎤 "In the left tables sidebar of TablePlus, I will click on the `customers` table to inspect our twenty enterprise customer accounts in the center data grid. Looking across columns `customer_id`, `company_name`, `region`, and `account_tier`, we have `Test Client 1` through `Test Client 20` with `customer_id` values ranging from `101` to `120` across `North America`, `EMEA`, `APAC`, and `LATAM`."
2. **Action:** Click `customers` in the left sidebar and scroll across rows `101` to `120` with the mouse (~35s).
3. **Speak, then click the `Structure` tab at the bottom of TablePlus:**
   > 🎤 "At the bottom bar of the TablePlus window, I will click the `Structure` button to inspect the `customers` table schema. Notice `customer_id` is the `INTEGER PRIMARY KEY`, and at the bottom under Indexes, only the primary key index exists."
4. **Action:** Click **Structure** at the bottom of TablePlus, point with the mouse, then click **Data** at the bottom to return to the data grid.
5. **Speak, then click `orders` in the left sidebar of TablePlus:**
   > 🎤 "Now in the left sidebar of TablePlus, I will click on the `orders` table, which currently holds fifty-five rows from `order_id` `501` down to `555`. Let's scroll down to the bottom of the data grid using the mouse to inspect the recent entries. Notice rows `551`, `552`, and `553` reference `customer_id = 999`—which does not exist in our `customers` table—and rows `554` and `555` contain negative values in the `total_amount` column."
6. **Action:** Click `orders`, scroll down to rows `551–555` with the mouse, and point at `customer_id = 999` and the negative `total_amount` values.
7. **Speak, then click the `Structure` tab on `orders`:**
   > 🎤 "Clicking the `Structure` tab at the bottom of TablePlus for the `orders` table, we can see why this happened: there is no foreign key constraint enforcing `customer_id`, no `CHECK` constraint preventing negative amounts, and in the Indexes pane at the bottom, there is no index on `order_status` or `order_date`."
8. **Action:** Click **Structure** at the bottom of TablePlus and point to the empty Indexes pane with the mouse.

---

### SECTION C: Diagnose & Clean Orphan and Corrupted Rows in TablePlus SQL Editor (`04:30 – 09:30`)

1. **Speak, then open the SQL Query Editor in TablePlus:**
   > 🎤 "In the top toolbar of TablePlus, I will click the `SQL` icon (or press `Command + E`) to open the interactive SQL query editor."
2. **Action:** Click the **SQL** button in the top toolbar of TablePlus.
3. **Speak, then type the diagnostic `LEFT JOIN` query (~18s):**
   > 🎤 "In the top query pane of TablePlus, I will write a diagnostic `SELECT` query joining `orders` to `customers` with a `LEFT JOIN` to isolate any order where `c.customer_id IS NULL` or `o.total_amount < 0`, and then click the `Run Current` button."
4. **Action:** Type and run:
   ```sql
   SELECT o.order_id, o.customer_id, o.order_status, o.total_amount
   FROM orders o
   LEFT JOIN customers c ON o.customer_id = c.customer_id
   WHERE c.customer_id IS NULL OR o.total_amount < 0;
   ```
   Click **Run Current** (`Cmd + Enter`).
5. **Speak while pointing at the 5 returned rows in the results pane (~25s):**
   > 🎤 "In the bottom results pane of TablePlus, the query returns the exact five anomalous records: `order_id` `551`, `552`, and `553` are orphaned records pointing to non-existent `customer_id` `999`, and `order_id` `554` and `555` have negative transaction amounts. Let's delete these five corrupted rows so they do not distort our Q4 financial reporting."
6. **Speak, then type and run the `DELETE` statement (~15s):**
   > 🎤 "Below our diagnostic query in the SQL editor, I will type `DELETE FROM orders WHERE customer_id NOT IN (SELECT customer_id FROM customers) OR total_amount < 0;` and click `Run Current`, then verify the remaining row count with `SELECT COUNT(*) FROM orders;`."
7. **Action:** Type and run:
   ```sql
   DELETE FROM orders
   WHERE customer_id NOT IN (SELECT customer_id FROM customers)
      OR total_amount < 0;

   SELECT COUNT(*) AS valid_order_count FROM orders;
   ```
   Point with the mouse at `valid_order_count = 50`.

---

### SECTION D: Analyze `EXPLAIN QUERY PLAN`, Create Composite Index & Build View (`09:30 – 15:30`)

1. **Speak, then run `EXPLAIN QUERY PLAN` BEFORE indexing (~20s):**
   > 🎤 "Next, let's examine how SQLite executes our Q4 regional revenue query filtering for `order_status = 'COMPLETED'` and `order_date >= '2026-10-01'`. In the SQL editor, I will prefix the query with `EXPLAIN QUERY PLAN` and click `Run Current`."
2. **Action:** Type and run:
   ```sql
   EXPLAIN QUERY PLAN
   SELECT c.region, COUNT(o.order_id) AS orders_cnt, SUM(o.total_amount) AS revenue
   FROM orders o
   JOIN customers c ON o.customer_id = c.customer_id
   WHERE o.order_status = 'COMPLETED' AND o.order_date >= '2026-10-01'
   GROUP BY c.region;
   ```
3. **Speak while pointing at `SCAN orders` in the bottom results pane (~25s):**
   > 🎤 "Look at the `detail` column in the bottom results pane of TablePlus: SQLite reports `SCAN orders`. Because there is no index on `order_status` and `order_date`, the database engine is forced to scan every single row in the `orders` table before joining to `customers`."
4. **Speak, then create the composite B-tree index (`idx_orders_status_date`, ~12s):**
   > 🎤 "To eliminate this full table scan, I will create a composite B-tree index on `orders(order_status, order_date)` with `order_status` first (for the equality predicate `=`) and `order_date` second (for the range predicate `>=`), and click `Run Current`."
5. **Action:** Type and run:
   ```sql
   CREATE INDEX idx_orders_status_date ON orders(order_status, order_date);
   ```
6. **Speak, then re-run `EXPLAIN QUERY PLAN` with the mouse (`Run Current`):**
   > 🎤 "Now I will highlight our `EXPLAIN QUERY PLAN` statement above with the mouse and click `Run Current` to inspect the updated execution plan."
7. **Action:** Highlight the `EXPLAIN QUERY PLAN` block with the mouse and click **Run Current**.
8. **Speak while pointing at `SEARCH orders USING INDEX` (~25s):**
   > 🎤 "In the bottom results pane, notice the execution plan has changed from `SCAN orders` to `SEARCH orders USING INDEX idx_orders_status_date (order_status=? AND order_date>?)`. SQLite now jumps directly to the matching Q4 completed orders via the B-tree index without scanning unrelated rows."
9. **Speak, then create and query `v_regional_revenue_summary` (~22s):**
   > 🎤 "Finally, let's persist this optimized query as a database view named `v_regional_revenue_summary` and select from it to inspect the final Q4 regional revenue totals."
10. **Action:** Type and run:
    ```sql
    CREATE VIEW v_regional_revenue_summary AS
    SELECT c.region,
           COUNT(o.order_id) AS completed_orders,
           SUM(o.total_amount) AS total_revenue_usd,
           ROUND(AVG(o.total_amount), 2) AS avg_order_value_usd
    FROM orders o
    JOIN customers c ON o.customer_id = c.customer_id
    WHERE o.order_status = 'COMPLETED' AND o.order_date >= '2026-10-01'
    GROUP BY c.region
    ORDER BY total_revenue_usd DESC;

    SELECT * FROM v_regional_revenue_summary;
    ```
11. **Speak while pointing at the view results and export/copy the SQL:**
    > 🎤 "In the bottom results pane, our view returns all forty valid Q4 completed orders aggregated cleanly across our four regions. I will select all the SQL statements in our editor, press `Command + C` to copy them, and then click the yellow minimize button in the top-left corner of TablePlus so we can document the migration script and audit report in Visual Studio Code."
12. **Action:** Press `Cmd + A` and `Cmd + C` inside the TablePlus SQL editor, then **click the yellow Minimize button (`-`)** in the top-left corner of TablePlus!

---

### SECTION E: Save Migration Script & Audit Report in `Visual Studio Code` (`15:30 – 19:30`)

1. **Speak, then open `Visual Studio Code` from the Dock:**
   > 🎤 "From the macOS Dock, I will click the Visual Studio Code icon to restore our workspace window."
2. **Action:** Click **Visual Studio Code** in the Dock.
3. **Speak, then paste into `optimize_orders.sql` and save (`Cmd + S`):**
   > 🎤 "In the left Explorer sidebar of Visual Studio Code, I will click `optimize_orders.sql`, click inside the editor pane, press `Command + V` to paste our verified SQL cleanup, index, and view migration script, and press `Command + S` to save the file."
4. **Action:** Click `optimize_orders.sql`, press `Cmd + V`, and press `Cmd + S`. Spend ~20 seconds scrolling through the SQL file with your mouse while explaining the 3 sections (data cleanup, composite index, and reporting view).
5. **Speak, then click `db_audit_report.md` and type a concise 3-bullet summary (~20s of typing total):**
   > 🎤 "Now in the left Explorer sidebar of Visual Studio Code, I will click `db_audit_report.md` and type our three-bullet engineering summary documenting the 5 removed anomalous rows, the B-tree index execution plan upgrade, and the regional view."
6. **Action:** Click `db_audit_report.md` and type:
   ```markdown
   # Q4 SQLite Database Integrity & Query Optimization Audit

   - **Data Integrity Cleanup:** Removed 3 orphaned orders (`customer_id = 999`) and 2 negative-amount rows (`55 -> 50` valid rows).
   - **Execution Plan Upgrade:** Added `idx_orders_status_date(order_status, order_date)`, replacing `SCAN orders` with `SEARCH orders USING INDEX`.
   - **Reporting View (`v_regional_revenue_summary`):** Aggregated 40 valid Q4 `COMPLETED` orders across 4 regions.
   ```
   Press `Cmd + S` to save `db_audit_report.md`.

---

### SECTION F: 3-Minute Verbal Epilogue (`19:30 – 22:30`)

*(Move your mouse across `db_audit_report.md` and `optimize_orders.sql` in VS Code while delivering this summary—zero typing!)*

> 🎤 "Let's wrap up with a summary of our workflow, key engineering decisions, and lessons learned.
>
> First, completion and verification: we completed the relational data integrity audit and query performance optimization on `orders_audit.sqlite` using TablePlus and Visual Studio Code. In TablePlus, we inspected the `customers` and `orders` table schemas, wrote a diagnostic `LEFT JOIN` query that identified three orphaned order rows referencing non-existent `customer_id = 999` and two corrupted rows with negative `total_amount` values, and deleted those five invalid rows to restore referential and domain integrity across the fifty valid orders. We then analyzed the Q4 completed-orders reporting query with `EXPLAIN QUERY PLAN`, created the composite B-tree index `idx_orders_status_date`, verified that SQLite switched from a full table scan (`SCAN orders`) to an indexed range lookup (`SEARCH orders USING INDEX`), created the `v_regional_revenue_summary` view, and saved both the `.sql` migration script and `.md` audit report in Visual Studio Code.
>
> Second, why this approach was effective: ordering the columns in our composite index `idx_orders_status_date` with `order_status` first and `order_date` second matches the left-prefix rule for B-tree indexes—allowing SQLite to narrow down to the equality match (`order_status = 'COMPLETED'`) first and then scan the sorted `order_date >= '2026-10-01'` range in place without touching unrelated rows.
>
> Third, common mistakes that someone less experienced should watch out for in SQLite database administration:
> - Number one: assuming SQLite enforces `FOREIGN KEY` constraints by default—unless `PRAGMA foreign_keys = ON;` is enabled per connection, orphaned child records can silently enter the database and must be audited with a `LEFT JOIN ... WHERE parent.id IS NULL` check.
> - Number two: reversing the column order in a composite index by placing the range column (`order_date`) before the equality column (`order_status`), which prevents the B-tree index from filtering both predicates efficiently.
> - Number three: aggregating revenue before removing negative or orphaned rows, which corrupts regional order counts and average order value metrics.
>
> All deliverables are saved and ready for packaging. Thank you for watching."

---

## Part 6: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

```text
Deliverables/
├── input 1.sqlite       <-- Starting un-indexed 55-row orders_audit.sqlite database
├── input 2.sql          <-- Starting seed_orders_db.sql script
├── final output 1.sqlite <-- Optimized 50-row orders_audit.sqlite with index & view
├── final output 2.sql   <-- Saved optimize_orders.sql migration script
└── final output 3.md    <-- Saved db_audit_report.md report
```

### `Metadata.rtf` Template for This Task
```text
Topology: TablePlus (MODIFY) -> Visual Studio Code (CREATE) -> TablePlus (LOOKUP) -> Visual Studio Code (MODIFY)

Request: <Paste the exact Goal text from Studio / TaskRecorder>

Task Description:
1. Open the orders_audit.sqlite database in TablePlus and inspect the customers and orders table data and structure.
2. Run a diagnostic LEFT JOIN query to identify and delete 3 orphaned orders (customer_id = 999) and 2 negative-amount orders, leaving 50 valid order rows.
3. Run EXPLAIN QUERY PLAN on the Q4 regional revenue query, create the composite B-tree index idx_orders_status_date on orders(order_status, order_date) to replace SCAN orders with SEARCH orders USING INDEX, and create the v_regional_revenue_summary view.
4. Save the production SQL migration script (optimize_orders.sql) and the query optimization audit report (db_audit_report.md) in Visual Studio Code.
```
