# Task 4 Master Guide (`DSD`): SQLite Database Integrity Audit, Indexing & Query Optimization (`TablePlus` + `VS Code`)

---

## Why This Task 4 Design Is 100% Validated & Ready to Record
1. **Your Starting Workspace Is Already Built Locally in `/Users/b0a07w6/Downloads/task4_sqlite/`:**
   - [`orders_audit.sqlite`](file:///Users/b0a07w6/Downloads/task4_sqlite/orders_audit.sqlite) — Raw 55-row un-indexed SQLite database (connect **TablePlus** to this file!).
   - [`seed_orders_db.sql`](file:///Users/b0a07w6/Downloads/task4_sqlite/seed_orders_db.sql) — Exact seed script from Gemini (`input 2.sql`).
   - [`input_1_orders_audit_backup.sqlite`](file:///Users/b0a07w6/Downloads/task4_sqlite/input_1_orders_audit_backup.sqlite) — Untouched backup copy of the starting `.sqlite` file so you already have `input 1.sqlite` ready for `Deliverables.zip` after you modify `orders_audit.sqlite` during recording!
   - [`optimize_orders.sql`](file:///Users/b0a07w6/Downloads/task4_sqlite/optimize_orders.sql) & [`db_audit_report.md`](file:///Users/b0a07w6/Downloads/task4_sqlite/db_audit_report.md) — Empty files ready in the folder for you to open in **Visual Studio Code**.
2. **Generous `35%` Typing Limit (`DSD` Domain):**
   - `DSD` gives you up to **35% typing**, while our mouse-driven TablePlus inspection + copy-pasting the verified SQL into VS Code keeps your actual typing around **`14–17%`**.

---

## Part 1: Step-by-Step Studio Idea Submission & Approval

### How to Fill Out Section `1.0 Create your idea` in Studio
1. Click **Create task** in Studio (`Odin Production Full Workflow`).
2. Scroll to **1.0 Create your idea → Describe your Idea**.
3. **Important:** Type the 5 sections below **in your own words** (never copy-paste directly into Studio's text box):

   - **`Domain / Role:`**
     - Write: Database Reliability & Data Engineering Lead (`DSD` — Data Science & Analytics; Software & AI/ML Engineering).
   - **`Goal:`** *(Keep a copy of the exact text you type here—once approved, this exact paragraph goes into your Opening Goal Document, TaskRecorder's Task Description box, and `Metadata.rtf`!)*
     - Paraphrase this in your own words:
       *As a Data Engineering Lead, I need to perform a relational data integrity audit and query performance optimization on our local SQLite order-processing database (`orders_audit.sqlite`) using TablePlus and Visual Studio Code. In TablePlus, I will inspect the `customers` and `orders` table schemas, run diagnostic SQL queries to identify and delete 3 orphaned order records (`customer_id = 999`) and 2 corrupted negative-amount transactions (`total_amount < 0`), analyze slow query execution plans using `EXPLAIN QUERY PLAN`, create a composite B-tree index (`idx_orders_status_date`) to replace a full table scan (`SCAN orders`) with an indexed seek (`SEARCH orders USING INDEX`), and create an aggregated `v_regional_revenue_summary` SQL view totaling `$70,000` across 40 valid Q4 completed orders. Finally, in Visual Studio Code, I will save the production SQL migration script (`optimize_orders.sql`) and the Markdown database optimization audit report (`db_audit_report.md`).*
   - **`Starting materials:`**
     - Paraphrase this in your own words:
       *A synthetic local SQLite database file (`orders_audit.sqlite`) and its seed schema script (`seed_orders_db.sql`) prepared with Gemini prior to recording, containing two tables: (1) `customers` (20 anonymized enterprise customer records `customer_id` `101` to `120` across `Test Client 1`–`20` in `North America`, `EMEA`, `APAC`, and `LATAM`); and (2) `orders` (55 order rows `order_id` `501` to `555`, including 40 valid `COMPLETED` orders, 10 `PENDING`/`REFUNDED` orders, 3 orphaned orders `551–553` referencing non-existent `customer_id = 999`, 2 corrupted rows `554–555` with negative `total_amount` of `-1500.00` and `-2400.00`, and no secondary indexes).*
   - **`Steps (with the apps for each):`**
     - Paraphrase these 2 app bullets in your own words:
       - *TablePlus:* Open the `orders_audit.sqlite` database, inspect the `customers` and `orders` tables in the `Data` and `Structure` tabs, run diagnostic `LEFT JOIN` and range queries in the SQL editor to locate and delete the 3 orphaned order rows (`551–553`) and 2 negative-amount rows (`554–555`) leaving 50 valid rows, run `EXPLAIN QUERY PLAN` on the Q4 completed-orders query to observe the `SCAN orders` full table scan, create the composite B-tree index `idx_orders_status_date ON orders(order_status, order_date)` and re-run `EXPLAIN QUERY PLAN` to verify `SEARCH orders USING INDEX`, and create and query the `v_regional_revenue_summary` view.
       - *Visual Studio Code:* Save the verified production SQL migration script (`optimize_orders.sql`) containing the data cleanup statements, composite index definition, and view definition, and write a concise Markdown technical audit report (`db_audit_report.md`) documenting the integrity cleanup, `EXPLAIN QUERY PLAN` improvement, and `$70,000` Q4 regional revenue summary.
   - **`Deliverable:`**
     - Paraphrase this in your own words:
       *1. The optimized and cleaned 50-row SQLite database file (`final output 1.sqlite`) containing the `idx_orders_status_date` composite index and the `v_regional_revenue_summary` view.*
       *2. The production SQL migration script (`final output 2.sql`) and Markdown database audit report (`final output 3.md`) saved in Visual Studio Code.*

4. **Select Apps in Studio's `Used Apps` Dropdown:**
   - Select **`TablePlus`** and **`Visual Studio Code`** (or if `TablePlus` isn't listed in the dropdown, select **`Visual Studio Code`** and **`SQLite` / `Terminal`**).
5. Click **Submit idea** and wait for approval before recording.

---

## Part 2: Exact Validated Data & SQLite Output Reference

### 1. The 5 Corrupted Rows Detected & Deleted in `orders` (`55 → 50` Valid Rows)

| `order_id` | `customer_id` | `order_date` | `order_status` | `product_sku` | `total_amount` | Anomaly Type |
|---:|---:|---|---|---|---:|---|
| **`551`** | `999` | `2026-12-01` | `COMPLETED` | `SKU-103` | `$1,200.0` | Orphaned (`customer_id = 999` missing in `customers`) |
| **`552`** | `999` | `2026-12-02` | `PENDING` | `SKU-104` | `$800.0` | Orphaned (`customer_id = 999` missing in `customers`) |
| **`553`** | `999` | `2026-12-03` | `COMPLETED` | `SKU-105` | `$950.0` | Orphaned (`customer_id = 999` missing in `customers`) |
| **`554`** | `101` | `2026-12-10` | `COMPLETED` | `SKU-101` | **`-$1,500.0`** | Corrupted negative amount (`total_amount < 0`) |
| **`555`** | `102` | `2026-12-11` | `COMPLETED` | `SKU-102` | **`-$2,400.0`** | Corrupted negative amount (`total_amount < 0`) |

### 2. Exact `EXPLAIN QUERY PLAN` Outputs
- **Query Tested:**
  ```sql
  EXPLAIN QUERY PLAN
  SELECT * FROM orders WHERE order_status = 'COMPLETED' AND order_date >= '2026-10-01';
  ```
- **Before Indexing (`detail` column):**
  ```text
  SCAN orders
  ```
- **After `CREATE INDEX idx_orders_status_date ON orders(order_status, order_date);` (`detail` column):**
  ```text
  SEARCH orders USING INDEX idx_orders_status_date (order_status=? AND order_date>?)
  ```

### 3. Exact `v_regional_revenue_summary` View Output (`ORDER BY region ASC`)

| `region` | `completed_orders` | `total_revenue_usd` | `avg_order_value_usd` | `product_sku` |
|---|---:|---:|---:|---|
| **`APAC`** (`Clients 11–15`) | `10` | **`15000.0`** (`$15,000`) | **`1500.0`** (`$1,500`) | `SKU-103` |
| **`EMEA`** (`Clients 6–10`) | `10` | **`20000.0`** (`$20,000`) | **`2000.0`** (`$2,000`) | `SKU-102` |
| **`LATAM`** (`Clients 16–20`) | `10` | **`25000.0`** (`$25,000`) | **`2500.0`** (`$2,500`) | `SKU-104` |
| **`North America`** (`Clients 1–5`) | `10` | **`10000.0`** (`$10,000`) | **`1000.0`** (`$1,000`) | `SKU-101` |
| **Total Across 4 Regions** | **`40`** | **`70000.0` (`$70,000`)** | **`1750.0` (`$1,750`)** | — |

*(Note: The remaining 10 valid rows `541–550` are `5 PENDING` and `5 REFUNDED` orders on `SKU-105`, making `40 COMPLETED + 10 PENDING/REFUNDED = 50` valid rows in `orders`.)*

---

## Part 3: AutoQC-Hardened Minute-by-Minute Recording Script (`20–23 Minutes`)

### Pre-Recording Setup Checklist (Do Not Skip!)
1. **Change Your Mac UI First (Mandatory Between Every Task!):**
   - `System Settings → Wallpaper`: Pick a **new wallpaper** (different from macOS default and Tasks 1–3).
   - `System Settings → Appearance`: Toggle **Light/Dark mode** and pick a **new Accent Color**.
   - Leave a small margin of desktop wallpaper visible around your application windows.
2. **Window 1 (Google Chrome — Opening Goal Doc):**
   - Open a Chrome window with ONLY one tab showing your approved **Goal** text in Google Docs. Leave this window un-minimized behind TaskRecorder at `00:00:00`.
3. **Window 2 (`TablePlus`):**
   - Open **TablePlus**, click **Create a new connection → SQLite → Create**, name it `orders_audit`, and select `/Users/b0a07w6/Downloads/task4_sqlite/orders_audit.sqlite` → **Connect**.
   - Verify `customers` and `orders` appear in the left sidebar of TablePlus, then **click the yellow Minimize button (`-`)** in the top-left corner of TablePlus!
4. **Window 3 (`Visual Studio Code`):**
   - Open **Visual Studio Code** to the folder `/Users/b0a07w6/Downloads/task4_sqlite` (where empty files `optimize_orders.sql` and `db_audit_report.md` are ready in the left Explorer sidebar), then **click the yellow Minimize button (`-`)** in the top-left corner of VS Code!
   - *(Golden Rule for `covers.json`: Never leave two windows un-minimized at once—always click the yellow `-` button before switching apps!)*

*(If you do a practice run before recording and want to reset `orders_audit.sqlite` back to its clean 55-row starting state, just run `cp /Users/b0a07w6/Downloads/task4_sqlite/input_1_orders_audit_backup.sqlite /Users/b0a07w6/Downloads/task4_sqlite/orders_audit.sqlite` in Terminal before starting TaskRecorder.)*

---

### SECTION A: Opening Goal Document (< 15 Seconds!) (`00:00 – 00:20`)

1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left corner of TaskRecorder.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. In the top-left corner of the Goal document window, I will click the yellow minimize button to minimize the Goal document and open TablePlus from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window, then click **TablePlus** in the Dock.

---

### SECTION B: Inspect `customers` and `orders` in `TablePlus` (`00:20 – 04:30`)

*(100% mouse-driven GUI inspection in TablePlus—zero typing for the first 4 minutes!)*

1. **Speak, then click `customers` in the left sidebar of TablePlus:**
   > 🎤 "In the left sidebar of TablePlus under `Items`, I will click the `customers` table to inspect our twenty anonymized customer accounts in the center data grid. Looking across columns `customer_id`, `company_name`, `region`, and `account_tier`, we have `Test Client 1` through `Test Client 20` (`customer_id` `101` to `120`), distributed evenly with five clients in `North America` (`101–105`), five in `EMEA` (`106–110`), five in `APAC` (`111–115`), and five in `LATAM` (`116–120`)."
2. **Action:** Click `customers` in the left sidebar and point across rows `101` to `120` with the mouse (~35s).
3. **Speak, then click the `Structure` tab at the bottom of TablePlus:**
   > 🎤 "At the bottom bar of TablePlus, I will click `Structure` to inspect the `customers` schema. Here `customer_id` is defined as the `INTEGER PRIMARY KEY`. Now let's click `Data` at the bottom and select the `orders` table in the left sidebar."
4. **Action:** Click **Structure** at the bottom, then click **Data**, and click **`orders`** in the left sidebar.
5. **Speak while scrolling down `orders` (`501` to `555`) with the mouse (~45s):**
   > 🎤 "In the center data grid of the `orders` table, we have fifty-five rows from `order_id` `501` down to `555`. Scrolling down with the mouse: rows `501` through `540` are valid Q4 `COMPLETED` orders, and rows `541` through `550` are `PENDING` and `REFUNDED` orders on `SKU-105`. However, look at the last five rows at the bottom (`551` through `555`):
   > - Rows `551`, `552`, and `553` reference `customer_id = 999`, which does not exist in our `customers` table (`101–120`).
   > - Rows `554` and `555` contain corrupted negative amounts (`-1500.0` and `-2400.0`) in the `total_amount` column."
6. **Speak, then click `Structure` at the bottom of `orders`:**
   > 🎤 "Clicking the `Structure` button at the bottom of TablePlus for `orders`, we can see why the database allowed this: there is no foreign key constraint on `customer_id`, no `CHECK` constraint on `total_amount`, and in the Indexes section at the bottom, there is no secondary index on `order_status` or `order_date`."
7. **Action:** Click **Structure** at the bottom of TablePlus and point to the empty Indexes pane with the mouse.

---

### SECTION C: Diagnose & Delete the 5 Corrupted Rows in TablePlus SQL Editor (`04:30 – 09:30`)

1. **Speak, then open the SQL Query Editor in TablePlus:**
   > 🎤 "In the top toolbar of TablePlus, I will click the `SQL` icon (or press `Command + E`) to open the SQL query editor."
2. **Action:** Click **SQL** in the top toolbar of TablePlus.
3. **Speak, then type and run the Orphan Detection Query (`LEFT JOIN`, ~15s):**
   > 🎤 "First, in the SQL editor pane, I will write a `LEFT JOIN` query between `orders` and `customers` filtering `WHERE c.customer_id IS NULL` and click `Run Current` to isolate the orphaned order records."
4. **Action:** Type:
   ```sql
   SELECT o.*
   FROM orders o
   LEFT JOIN customers c ON o.customer_id = c.customer_id
   WHERE c.customer_id IS NULL;
   ```
   and click **Run Current** (`Cmd + Enter`).
5. **Speak while pointing at the 3 returned orphan rows (`551, 552, 553`) with the mouse (~20s):**
   > 🎤 "In the bottom results pane, the query returns `order_id` `551`, `552`, and `553`, all tied to non-existent `customer_id = 999`. Next, let's check for corrupted negative transaction amounts."
6. **Speak, then type and run the Negative Amount Detection Query (~10s):**
   > 🎤 "Below our first query, I will type `SELECT * FROM orders WHERE total_amount < 0;`, highlight it with the mouse, and click `Run Current`."
7. **Action:** Type:
   ```sql
   SELECT * FROM orders WHERE total_amount < 0;
   ```
   Highlight it with the mouse and click **Run Current**.
8. **Speak while pointing at rows `554` and `555` (`-1500.0` and `-2400.0`) (~15s):**
   > 🎤 "The results pane confirms `order_id` `554` (`-1500.0`) and `555` (`-2400.0`) have negative balances. Now let's execute the two `DELETE` statements to remove both the orphaned records and the negative-balance rows, reducing `orders` from 55 rows to 50 valid rows."
9. **Speak, then type and run the two `DELETE` statements (~18s):**
   > 🎤 "In the SQL editor, I will type the two `DELETE FROM orders` statements, highlight them with the mouse, and click `Run Current`."
10. **Action:** Type:
    ```sql
    DELETE FROM orders
    WHERE customer_id NOT IN (SELECT customer_id FROM customers);

    DELETE FROM orders
    WHERE total_amount < 0;
    ```
    Highlight both statements with the mouse and click **Run Current**.
11. **Speak, then verify `50` valid rows remain in the `orders` Data tab (Mouse-driven):**
    > 🎤 "Let's click the `orders` table tab at the top of TablePlus, click `Data` at the bottom, and click the `Refresh` icon in the top toolbar (`Command + R`). Scrolling to the bottom of the grid with the mouse, `order_id` `551` through `555` are gone, and exactly fifty valid rows (`501` through `550`) remain."
12. **Action:** Switch to the `orders` tab → `Data` → press `Cmd + R`, scroll to row `550` with the mouse, then switch back to the `SQL` tab.

---

### SECTION D: Run `EXPLAIN QUERY PLAN`, Add B-Tree Index & Create Regional View (`09:30 – 15:30`)

1. **Speak, then run `EXPLAIN QUERY PLAN` BEFORE indexing (~18s):**
   > 🎤 "Next, let's inspect the query execution plan when filtering for Q4 completed orders (`order_status = 'COMPLETED' AND order_date >= '2026-10-01'`). In the SQL editor, I will type `EXPLAIN QUERY PLAN` followed by our `SELECT` query, highlight it with the mouse, and click `Run Current`."
2. **Action:** Type:
   ```sql
   EXPLAIN QUERY PLAN
   SELECT * FROM orders
   WHERE order_status = 'COMPLETED' AND order_date >= '2026-10-01';
   ```
   Highlight it with the mouse and click **Run Current**.
3. **Speak while pointing at `SCAN orders` in the bottom results pane (~25s):**
   > 🎤 "Look at the `detail` column in the bottom results pane: SQLite outputs `SCAN orders`. Because `order_status` and `order_date` are unindexed, SQLite must perform a sequential full table scan across every row in `orders`."
4. **Speak, then create the composite index `idx_orders_status_date` (~12s):**
   > 🎤 "To optimize this query path, I will type `CREATE INDEX idx_orders_status_date ON orders(order_status, order_date);`, highlight it with the mouse, and click `Run Current`."
5. **Action:** Type:
   ```sql
   CREATE INDEX idx_orders_status_date ON orders(order_status, order_date);
   ```
   Highlight it with the mouse and click **Run Current**.
6. **Speak, then re-run `EXPLAIN QUERY PLAN` with the mouse (Zero typing!):**
   > 🎤 "Now I will highlight our `EXPLAIN QUERY PLAN` statement above with the mouse and click `Run Current` again to verify the new execution plan."
7. **Action:** Highlight the `EXPLAIN QUERY PLAN` block with the mouse and click **Run Current**.
8. **Speak while pointing at `SEARCH orders USING INDEX` (~25s):**
   > 🎤 "In the bottom results pane, the execution plan now reads `SEARCH orders USING INDEX idx_orders_status_date (order_status=? AND order_date>?)`. Confirming our B-tree index is active, SQLite now performs a direct index seek instead of a full table scan."
9. **Speak, then create and query `v_regional_revenue_summary` (~22s):**
   > 🎤 "Finally, let's create our reporting view `v_regional_revenue_summary` joining `orders` and `customers` for `COMPLETED` orders grouped by `region`, and run `SELECT * FROM v_regional_revenue_summary ORDER BY region ASC;`."
10. **Action:** Type:
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
    Highlight and click **Run Current**.
11. **Speak while pointing at the 4 regional rows in the results pane (~30s):**
    > 🎤 "Examining the view output in the bottom results pane across our forty valid Q4 completed orders:
    > - `APAC` has `10` completed orders, `$15,000` in total revenue, and a `$1,500` average order value.
    > - `EMEA` has `10` completed orders, `$20,000` in total revenue, and a `$2,000` average order value.
    > - `LATAM` leads with `10` completed orders, `$25,000` in total revenue, and a `$2,500` average order value.
    > - `North America` has `10` completed orders, `$10,000` in total revenue, and a `$1,000` average order value—totaling `$70,000` across all four regions."
12. **Copy the SQL statements & minimize TablePlus (`-`):**
    > 🎤 "I will now select our migration SQL statements in the editor, press `Command + C` to copy them, and click the yellow minimize button in the top-left corner of TablePlus to switch to Visual Studio Code."
13. **Action:** Copy the `DELETE`, `CREATE INDEX`, and `CREATE VIEW` SQL statements (`Cmd + C`), then **click the yellow Minimize button (`-`)** in the top-left corner of TablePlus!

---

### SECTION E: Save Migration Script & Audit Report in `Visual Studio Code` (`15:30 – 19:30`)

1. **Speak, then open `Visual Studio Code` from the Dock:**
   > 🎤 "From the Dock, I will click the Visual Studio Code icon to open our project workspace."
2. **Action:** Click **Visual Studio Code** in the Dock.
3. **Speak, then paste into `optimize_orders.sql` and save (`Cmd + S`):**
   > 🎤 "In the left Explorer sidebar of Visual Studio Code, I will click `optimize_orders.sql`, click inside the editor pane, press `Command + V` to paste our verified SQL cleanup, composite index, and view statements, and press `Command + S` to save the migration script."
4. **Action:** Click `optimize_orders.sql`, press `Cmd + V`, press `Cmd + S`, and spend ~20 seconds scrolling through the file with the mouse while narrating the three sections.
5. **Speak, then click `db_audit_report.md` and type the concise Markdown report (~22s of typing):**
   > 🎤 "Next, in the left Explorer sidebar, I will click `db_audit_report.md` and document our three audit sections: the data integrity cleanup, the B-tree execution plan upgrade, and the regional revenue summary."
6. **Action:** Click `db_audit_report.md`, type:
   ```markdown
   # Database Integrity & Optimization Audit

   ## 1. Data Integrity Cleanup
   - Removed 3 orphan orders (`551-553`, `customer_id = 999`) and 2 negative orders (`554-555`), retaining 50 valid rows.

   ## 2. Performance Optimization
   - Created `idx_orders_status_date` on `orders(order_status, order_date)`.
   - Plan upgraded from `SCAN orders` to `SEARCH orders USING INDEX idx_orders_status_date`.

   ## 3. Q4 Completed Regional Revenue ($70,000 Total)
   - APAC: 10 orders | $15,000 total | $1,500 avg
   - EMEA: 10 orders | $20,000 total | $2,000 avg
   - LATAM: 10 orders | $25,000 total | $2,500 avg
   - North America: 10 orders | $10,000 total | $1,000 avg
   ```
   and press `Cmd + S` to save `db_audit_report.md`.

---

### SECTION F: 3-Minute Verbal Epilogue (`19:30 – 22:30`)

*(Move your mouse across `db_audit_report.md` and `optimize_orders.sql` in VS Code while delivering this summary—zero typing!)*

> 🎤 "Let's wrap up with a summary of our workflow, key engineering decisions, and lessons learned.
>
> First, completion and verification: we completed the relational data integrity audit and query performance optimization on `orders_audit.sqlite` using TablePlus and Visual Studio Code. In TablePlus, we inspected the `customers` (`101–120`) and `orders` (`501–555`) schemas, ran diagnostic queries that isolated three orphaned order rows (`551`, `552`, `553` referencing non-existent `customer_id = 999`) and two corrupted rows (`554` and `555` with negative amounts `-1500.0` and `-2400.0`), and deleted those five anomalous records to leave fifty clean, valid rows. We then analyzed the Q4 completed-orders query with `EXPLAIN QUERY PLAN`, created the composite B-tree index `idx_orders_status_date`, verified that SQLite upgraded its execution plan from a full table scan (`SCAN orders`) to an indexed seek (`SEARCH orders USING INDEX`), created the `v_regional_revenue_summary` view totaling `$70,000` across forty completed orders (`$25,000` LATAM, `$20,000` EMEA, `$15,000` APAC, and `$10,000` North America), and saved both `optimize_orders.sql` and `db_audit_report.md` in Visual Studio Code.
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

## Part 4: Packaging Blueprint for `Deliverables.zip` & `Metadata.rtf`

All files are in `/Users/b0a07w6/Downloads/task4_sqlite/`—just copy and rename them into your `Deliverables` folder after recording:

```text
Deliverables/
├── input 1.sqlite        <-- Copy from input_1_orders_audit_backup.sqlite (starting 55-row un-indexed DB)
├── input 2.sql           <-- Copy from seed_orders_db.sql
├── final output 1.sqlite <-- Copy from orders_audit.sqlite (optimized 50-row DB with index & view)
├── final output 2.sql    <-- Copy from optimize_orders.sql
└── final output 3.md     <-- Copy from db_audit_report.md
```

### `Metadata.rtf` Template for This Task
```text
Topology: TablePlus (MODIFY) -> Visual Studio Code (CREATE) -> TablePlus (LOOKUP) -> Visual Studio Code (MODIFY)

Request: <Paste the exact Goal text from Studio / TaskRecorder>

Task Description:
1. Open the orders_audit.sqlite database in TablePlus and inspect the customers and orders table data and structure.
2. Run diagnostic SQL queries to identify and delete 3 orphaned orders (order_id 551-553 referencing customer_id = 999) and 2 corrupted negative-amount orders (order_id 554-555), reducing the orders table from 55 to 50 valid rows.
3. Run EXPLAIN QUERY PLAN on the Q4 completed orders query, create the composite B-tree index idx_orders_status_date on orders(order_status, order_date) to upgrade SCAN orders to SEARCH orders USING INDEX, and create the v_regional_revenue_summary view ($70,000 total revenue across 40 completed orders).
4. Save the production SQL migration script (optimize_orders.sql) and the Markdown database optimization audit report (db_audit_report.md) in Visual Studio Code.
```
