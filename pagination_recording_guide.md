# Screencast Guide v3 (AutoQC-Hardened): Adding Pagination to `/api/process-checks`

> [!IMPORTANT]
> **Workspace Reset Complete:** Your repository is reset to `b4faffd^` on branch `pagination-demo` with `seed.sh`, `.mvn/maven.config`, and `.mvn/settings.xml` ready to go.
>
> **3 Golden Rules That Fix All 4 AutoQC Flags:**
> 1. **Goal Document at `00:00:00` (< 20s Intro):** Before clicking `Start Recording`, **minimize both IntelliJ IDEA and Postman** to the Dock. Leave **only** a Google Docs or Microsoft Word window open behind TaskRecorder showing your exact Goal text. Keep your opening intro sentence under **15 seconds**, then minimize the Goal document window.
> 2. **Never Cover Another Window (`#17` Fix):** Every time you switch apps, **click the yellow Minimize button (`-`) in the top-left corner** of the current window first, and **then** click the next app icon in the Dock. Only **one** window should ever be un-minimized on screen.
> 3. **Speak BEFORE / AS You Act — Never Say "Here", "There", or "This" (`#24` Fix):** Read each `> 🎤` block **verbatim**. Every line names the **exact screen region** (`top-right toolbar`, `bottom Terminal panel`, `left Project sidebar`, `line X in the center editor`) + **control/line name** + **purpose**.

---

## 1. Pre-Recording Setup Checklist (Do Before Clicking "Start Recording")

- [ ] **1. Open the Goal Document (Google Docs in Chrome or Microsoft Word):**
  Display **only** this exact text in large font (do not use Notes.app or TextEdit.app):
  ```text
  Enhance the existing process-check API by implementing pagination for the endpoint that lists process checks, making the resultseasier for API consumers to retrieve in managebale pages.
  ```
- [ ] **2. Pre-open & Minimize IntelliJ IDEA:**
  - Open `SpringBootProcessApiBasicsApplication.java` in the center editor.
  - Open the **Terminal** panel at the bottom (`Option + F12`) so it is visible inside IntelliJ.
  - Expand `src/main/java/de/datatidehh/processapi/processcheck` and `src/test/.../processcheck` in the left Project sidebar.
  - Click the **yellow Minimize button (`-`)** in the top-left corner of IntelliJ IDEA so it sits minimized in the Dock.
- [ ] **3. Pre-open & Minimize Postman:**
  - Have your **Pagination Demo** collection open in the left sidebar with `GET Before`, `GET Page 0`, `GET Page 1`, `GET Page 2`, `GET Page 3`, `GET Filter CRITICAL`, and `GET Size cap`.
  - Click the **yellow Minimize button (`-`)** in the top-left corner of Postman so it sits minimized in the Dock.
- [ ] **4. Position TaskRecorder in front of the Goal Document:**
  - Verify **only** the Goal Document window is visible behind TaskRecorder.

---

## 2. Auto-Import Package Reference (When Selecting from IntelliJ Autocomplete)

| File | Auto-Imported Packages | Unused Import to Delete (Optional) |
|---|---|---|
| `ProcessCheckRepository.java` | `org.springframework.data.domain.Page`<br>`org.springframework.data.domain.Pageable` | `import java.util.List;` |
| `ProcessCheckService.java` | `org.springframework.data.domain.Page`<br>`org.springframework.data.domain.Pageable` | `import java.util.List;` |
| `ProcessCheckController.java` | `org.springframework.data.domain.Pageable`<br>`org.springframework.data.domain.Sort`<br>`org.springframework.data.web.PagedModel`<br>`org.springframework.data.web.PageableDefault` | `import java.util.List;` |

---

## 3. Verbatim Step-by-Step Script (Speak First, Then Click/Type)

---

### SECTION A: Opening Goal Doc (< 20s), Start Server, Seed Data & Baseline (`00:00 – 04:00`)

#### Step A1 — Intro on Goal Document (MUST finish under 20 seconds!)
1. **Action:** Click **Start Recording** in TaskRecorder, then immediately click the **yellow Minimize button (`-`)** in the top-left of the TaskRecorder window so the Goal document is clearly visible.
2. **Speak (`~10 seconds`):**
   > 🎤 "I will be beginning my task soon. Here is the workflow I have in mind. I will click the yellow minimize button in the top-left corner of the Goal document window to minimize the document and open IntelliJ IDEA from the Dock."
3. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of the Goal document window. Then click the **IntelliJ IDEA icon** in the Dock on the left side of the screen.

---

#### Step A2 — Start the Spring Boot Server in IntelliJ IDEA
1. **Speak, then click:**
   > 🎤 "In the top-right toolbar of IntelliJ IDEA, I will click the green Run triangle button to start the Spring Boot application on port 8080 so we have a live baseline server."
2. **Action:** Click the green **Run (`▶`)** button in the top-right toolbar of IntelliJ IDEA. Wait ~3 seconds for the bottom Run console to print `Started SpringBootProcessApiBasicsApplication`.
3. **Speak, then point:**
   > 🎤 "In the bottom Run console panel of IntelliJ IDEA, I will hover over the Started log line to confirm the server is listening on port 8080."

---

#### Step A3 — Run `seed.sh` in the Bottom Terminal Panel
1. **Speak, then click:**
   > 🎤 "In the bottom-left tool window bar of IntelliJ IDEA, I will click the Terminal tab to switch from the Run console to the command-line terminal."
2. **Action:** Click the **Terminal** tab at the bottom of IntelliJ IDEA.
3. **Speak, then type (`cat seed.sh` + Enter):**
   > 🎤 "Inside the bottom Terminal panel of IntelliJ IDEA, I will type `cat seed.sh` and press Enter to display the shell script that seeds our twelve synthetic process-check records."
4. **Action:** Type `cat seed.sh` and press **Enter**.
5. **Speak while pointing at the output in the bottom Terminal panel:**
   > 🎤 "In the bottom Terminal panel output, notice the `for` loop runs from 01 to 12 and sends a curl POST request to localhost 8080 `/api/process-checks`, cycling through OK, WARNING, and CRITICAL statuses so four records of each status are created."
6. **Speak, then type (`./seed.sh` + Enter):**
   > 🎤 "Inside the bottom Terminal panel of IntelliJ IDEA, I will type `./seed.sh` and press Enter to execute the seed script and insert all twelve records into the H2 database."
7. **Action:** Type `./seed.sh` and press **Enter**. Point at the twelve `201` status codes printed in the bottom Terminal panel.
8. **Speak:**
   > 🎤 "In the bottom Terminal panel output, we see twelve HTTP 201 status codes, confirming all twelve records were created."

---

#### Step A4 — Minimize IntelliJ IDEA & Inspect Baseline in Postman
1. **Speak, then click:**
   > 🎤 "In the top-left corner of the IntelliJ IDEA window, I will click the yellow minimize button to minimize IntelliJ IDEA before opening Postman, so no window covers another."
2. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of IntelliJ IDEA.
3. **Speak, then click:**
   > 🎤 "In the Dock on the left side of the screen, I will click the Postman icon to open the Postman window."
4. **Action:** Click **Postman** in the Dock.
5. **Speak, then click:**
   > 🎤 "In the left Collections sidebar of Postman, I will click the request named `Before` under `Pagination Demo` to open the baseline GET request."
6. **Action:** Click **`GET Before`** in the left sidebar of Postman.
7. **Speak, then click:**
   > 🎤 "In the top-right corner of the Postman request panel, I will click the blue Send button to fetch the current unpaginated list of process checks."
8. **Action:** Click the blue **Send** button in the top-right of Postman.
9. **Speak while pointing at the bottom Response pane in Postman:**
   > 🎤 "In the bottom Response body panel of Postman, notice the response starts with a raw square bracket on line 1 and returns all twelve JSON objects in a single flat array with no page metadata. I will scroll down inside the bottom Response body panel of Postman to show that all twelve records are returned at once."
10. **Action:** Scroll down in the bottom Response body panel to item 12.
11. **Speak, then click:**
    > 🎤 "In the top-left corner of the Postman window, I will click the yellow minimize button to minimize Postman before returning to IntelliJ IDEA."
12. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of Postman, then click **IntelliJ IDEA** in the Dock on the left side of the screen.

---

### SECTION B: Code Tour in IntelliJ IDEA (`04:00 – 05:00`)

1. **Speak, then click:**
   > 🎤 "In the left Project sidebar of IntelliJ IDEA, under the `processcheck` package, I will double-click `ProcessCheckController.java` to inspect how GET requests enter the application."
2. **Action:** Double-click `ProcessCheckController.java` in the left Project sidebar. Point at lines 29–34 in the center editor.
3. **Speak:**
   > 🎤 "On line 30 in the center editor of `ProcessCheckController.java`, the `findAll` method currently returns a `List<ProcessCheckResponse>` and calls `service.findAll(status)`. We will update the repository, the service, and the controller from the bottom up so each layer supports Spring Data `Pageable`."

---

### SECTION C: Edit `ProcessCheckRepository.java` (`05:00 – 06:30`)

1. **Speak, then click:**
   > 🎤 "In the left Project sidebar of IntelliJ IDEA, I will double-click `ProcessCheckRepository.java` to open the repository interface in the center editor."
2. **Action:** Double-click `ProcessCheckRepository.java` in the left Project sidebar.
3. **Speak, then edit line 9 (Chunk R1 — ~18s):**
   > 🎤 "On line 9 in the center editor of `ProcessCheckRepository.java`, I will change the return type from `List<ProcessCheck>` to `Page<ProcessCheck>`, and inside the parentheses at the end of line 9, I will add `, Pageable pageable` so Spring Data JPA generates a paginated query and a count query."
4. **Action — Type on line 9 (selecting `org.springframework.data.domain` in autocomplete):**
   ```java
       Page<ProcessCheck> findAllByStatus(ProcessStatus status, Pageable pageable);
   ```
5. **Speak while pointing at lines 7–11:**
   > 🎤 "Looking at lines 7 to 11 in the center editor of `ProcessCheckRepository.java`, IntelliJ automatically imported `Page` and `Pageable` from `org.springframework.data.domain`, and `JpaRepository` already provides `findAll(Pageable)` out of the box, so we only needed to update `findAllByStatus`."

---

### SECTION D: Edit `ProcessCheckService.java` (`06:30 – 09:00`)

1. **Speak, then click:**
   > 🎤 "In the left Project sidebar of IntelliJ IDEA, I will double-click `ProcessCheckService.java` to open the service class in the center editor."
2. **Action:** Double-click `ProcessCheckService.java` in the left Project sidebar.
3. **Speak, then edit line 18 (Chunk V1 — ~20s):**
   > 🎤 "On line 18 in the center editor of `ProcessCheckService.java`, I will change the return type from `List<ProcessCheckResponse>` to `Page<ProcessCheckResponse>`, and inside the parentheses on line 18, I will add `, Pageable pageable` as the second parameter."
4. **Action — Edit line 18:**
   ```java
       public Page<ProcessCheckResponse> findAll(ProcessStatus status, Pageable pageable) {
   ```
5. **Speak, then edit lines 21–23 (Chunk V2 — ~25s):**
   > 🎤 "On lines 21 to 23 in the center editor of `ProcessCheckService.java`, I will change the local variable type from `List<ProcessCheck>` to `Page<ProcessCheck>`, and pass `pageable` into both `repository.findAll(pageable)` and `repository.findAllByStatus(status, pageable)`."
6. **Action — Edit lines 21–23:**
   ```java
           Page<ProcessCheck> processChecks = status == null
                   ? repository.findAll(pageable)
                   : repository.findAllByStatus(status, pageable);
   ```
7. **Speak, then edit lines 25–27 (Chunk V3 — ~15s):**
   > 🎤 "On lines 25 to 27 in the center editor of `ProcessCheckService.java`, I will remove `.stream()` and `.toList()` so the return statement calls `processChecks.map(ProcessCheckResponse::fromEntity)` directly on the `Page` object, which maps each entity to a response DTO while preserving total elements and total pages."
8. **Action — Edit the return statement:**
   ```java
           return processChecks.map(ProcessCheckResponse::fromEntity);
   ```

---

### SECTION E: Edit `ProcessCheckController.java` (`09:00 – 11:30`)

1. **Speak, then click:**
   > 🎤 "In the left Project sidebar of IntelliJ IDEA, I will double-click `ProcessCheckController.java` to open the REST controller in the center editor."
2. **Action:** Double-click `ProcessCheckController.java` in the left Project sidebar.
3. **Speak, then edit line 30 (Chunk K1 — ~15s):**
   > 🎤 "On line 30 in the center editor of `ProcessCheckController.java`, I will replace `List<ProcessCheckResponse>` with `PagedModel<ProcessCheckResponse>` so our endpoint serializes a stable JSON object containing `content` and `page` metadata."
4. **Action — Edit line 30:**
   ```java
       public PagedModel<ProcessCheckResponse> findAll(
   ```
5. **Speak, then edit lines 31–37 (Chunk K2 — ~25s):**
   > 🎤 "At the end of line 31 in the center editor of `ProcessCheckController.java`, I will add a comma and then type `@PageableDefault` with `size = 20`, `sort = \"lastCheckedAt\"`, and `direction = Sort.Direction.DESC` followed by `Pageable pageable` so requests default to twenty items sorted newest first."
6. **Action — Type lines 31–37:**
   ```java
               @RequestParam(required = false) ProcessStatus status,
               @PageableDefault(
                       size = 20,
                       sort = "lastCheckedAt",
                       direction = Sort.Direction.DESC
               ) Pageable pageable
       ) {
   ```
7. **Speak, then edit the return line (Chunk K3 — ~15s):**
   > 🎤 "On line 41 in the center editor of `ProcessCheckController.java`, I will update the return statement to `return new PagedModel<>(service.findAll(status, pageable));` so the controller wraps the service's `Page` result in a `PagedModel`."
8. **Action — Edit return line:**
   ```java
           return new PagedModel<>(service.findAll(status, pageable));
   ```

---

### SECTION F: Edit `application.properties` (`11:30 – 12:15`)

1. **Speak, then click:**
   > 🎤 "In the left Project sidebar of IntelliJ IDEA, under `src/main/resources`, I will double-click `application.properties` to open the configuration file in the center editor."
2. **Action:** Double-click `application.properties` in the left Project sidebar.
3. **Speak, then type on line 14 (Chunk P1 — ~10s):**
   > 🎤 "On line 14 in the center editor of `application.properties`, right below `spring.jpa.open-in-view=false`, I will type `spring.data.web.pageable.max-page-size=100` to cap the maximum page size at 100 records per page."
4. **Action — Type on line 14:**
   ```properties
   spring.data.web.pageable.max-page-size=100
   ```

---

### SECTION G: Run Existing Tests, Fix Assertions & Add Pagination Test (`12:15 – 16:30`)

#### Step G1 — Open & Run `ProcessCheckApiIntegrationTests.java`
1. **Speak, then click:**
   > 🎤 "In the left Project sidebar of IntelliJ IDEA, under `src/test`, I will double-click `ProcessCheckApiIntegrationTests.java` to open the integration test class in the center editor."
2. **Action:** Double-click `ProcessCheckApiIntegrationTests.java` in the left Project sidebar.
3. **Speak, then click the green gutter icon:**
   > 🎤 "On line 30 in the left gutter of the center editor, next to `class ProcessCheckApiIntegrationTests`, I will click the green double-triangle Run button and select `Run ProcessCheckApiIntegrationTests` to see which existing tests fail after our response structure change."
4. **Action:** Click the green gutter icon on line 30 and run the test class. Wait for the bottom Run panel to show the 3 failing list tests.
5. **Speak while pointing at the bottom test runner panel:**
   > 🎤 "In the bottom Test Runner panel of IntelliJ IDEA, three list tests failed because they assert against the root JSON path `$` instead of `$.content`."

---

#### Step G2 — Update the 3 Existing Tests (Lines 72–101)
1. **Speak, then select lines 69–102 and open Replace:**
   > 🎤 "In the center editor of `ProcessCheckApiIntegrationTests.java`, I will highlight lines 69 through 102 covering the three list tests, and press `Command + R` to open the Replace bar at the top of the center editor."
2. **Action:** Select lines 69–102 and press `Cmd + R`.
3. **Speak, then type in the Find and Replace boxes (Chunk F1 — ~15s):**
   > 🎤 "In the top Find text box of the center editor, I will type `\"$` and in the Replace text box below it, I will type `\"$.content`, then click the `Replace All` button to update all six JSON path assertions inside the selected list tests."
4. **Action:** Type `"$` in Find, `"$.content` in Replace, and click **Replace All** (updates lines 72, 74, 84, 86, 90, 101). Press `Escape` to close the Replace bar.

---

#### Step G3 — Add New Pagination Test on Line 110 (Chunks TA1–TA4)
1. **Speak, then click line 110:**
   > 🎤 "On line 110 in the center editor of `ProcessCheckApiIntegrationTests.java`, right below `findAllWithInvalidStatusReturnsBadRequest`, I will add a new test method named `findAllReturnsSecondPage` to verify page slicing, sorting, and page metadata."
2. **Speak, then type Chunk TA1 (~22s):**
   > 🎤 "Starting on line 110 in the center editor of `ProcessCheckApiIntegrationTests.java`, I will type the `@Test` annotation, the method header `void findAllReturnsSecondPage() throws Exception`, and `mockMvc.perform(get(\"/api/process-checks\")`."
   ```java
       @Test
       void findAllReturnsSecondPage() throws Exception {
           mockMvc.perform(get("/api/process-checks")
   ```
3. **Speak, then type Chunk TA2 (~18s):**
   > 🎤 "On the next three lines in the center editor of `ProcessCheckApiIntegrationTests.java`, I will chain `.param(\"page\", \"1\")`, `.param(\"size\", \"1\")`, and `.param(\"sort\", \"processName,asc\"))` so we request the second page with one item per page sorted alphabetically."
   ```java
                           .param("page", "1")
                           .param("size", "1")
                           .param("sort", "processName,asc"))
   ```
4. **Speak, then type Chunk TA3 (~25s):**
   > 🎤 "Continuing in the center editor of `ProcessCheckApiIntegrationTests.java`, I will add `.andExpect(status().isOk())` and `.andExpect(jsonPath(\"$.content[0].processName\", is(\"Monthly finance export\")))` to verify the second alphabetical record is returned."
   ```java
                   .andExpect(status().isOk())
                   .andExpect(jsonPath("$.content[0].processName", is("Monthly finance export")))
   ```
5. **Speak, then type Chunk TA4 (~24s):**
   > 🎤 "On the final lines of this test method in the center editor of `ProcessCheckApiIntegrationTests.java`, I will assert `jsonPath(\"$.page.number\", is(1))` and `jsonPath(\"$.page.totalPages\", is(2))`, and close the method with a curly brace."
   ```java
                   .andExpect(jsonPath("$.page.number", is(1)))
                   .andExpect(jsonPath("$.page.totalPages", is(2)));
       }
   ```
6. **Speak, then re-run the test class:**
   > 🎤 "In the top-right toolbar of IntelliJ IDEA, I will click the green Run triangle button to re-run `ProcessCheckApiIntegrationTests` and verify all thirteen tests in this class pass."
7. **Action:** Click the green Run button (or gutter icon) to run `ProcessCheckApiIntegrationTests`. Point at the green checkmarks in the bottom Test Runner panel.
8. **Speak:**
   > 🎤 "In the bottom Test Runner panel of IntelliJ IDEA, all thirteen tests are green."

---

### SECTION H: Restart Server, Re-Seed & Verify in Postman (`16:30 – 20:00`)

#### Step H1 — Restart Spring Boot & Re-Seed in IntelliJ IDEA
1. **Speak, then select the Application run configuration:**
   > 🎤 "In the top-right run configuration dropdown of IntelliJ IDEA, I will select `SpringBootProcessApiBasicsApplication` and click the green Run button next to it to restart the application server with our new pagination code."
2. **Action:** Select `SpringBootProcessApiBasicsApplication` in the top-right run configuration dropdown and click the green **Run / Rerun** button. Wait ~3 seconds for `Started SpringBootProcessApiBasicsApplication` in the bottom Run console.
3. **Speak, then click the Terminal tab and re-seed:**
   > 🎤 "In the bottom-left tool window bar of IntelliJ IDEA, I will click the Terminal tab, type `./seed.sh` inside the bottom Terminal panel, and press Enter to re-seed the twelve sample records into the fresh H2 database."
4. **Action:** Click the **Terminal** tab at the bottom, type `./seed.sh`, and press **Enter**. Point at the twelve `201` status codes.
5. **Speak, then minimize IntelliJ IDEA:**
   > 🎤 "In the top-left corner of the IntelliJ IDEA window, I will click the yellow minimize button to minimize IntelliJ IDEA before opening Postman from the Dock."
6. **Action:** Click the **yellow Minimize button (`-`)** in the top-left corner of IntelliJ IDEA. Then click **Postman** in the Dock on the left side of the screen.

---

#### Step H2 — Run Requests 1–6 in Postman
For **each** of the 6 requests in the left Collections sidebar of Postman:
1. **Speak, then click `GET Page 0`:**
   > 🎤 "In the left Collections sidebar of Postman, I will click `Page 0`, and then in the top-right corner of the Postman request panel, I will click the blue Send button to request `page=0&size=5`."
   - **After response appears, speak while pointing at the bottom Response & Test Results panels:**
   > 🎤 "In the bottom Response panel of Postman, `content` contains five items sorted newest first starting with Process 12, and at the bottom of the JSON response, the `page` object shows `size: 5`, `number: 0`, `totalElements: 12`, and `totalPages: 3`. In the Test Results tab of the bottom panel, all four assertions passed."

2. **Speak, then click `GET Page 1`:**
   > 🎤 "In the left Collections sidebar of Postman, I will click `Page 1`, and in the top-right corner of the request panel, I will click the blue Send button to fetch the second page of five records."
   - **Speak while pointing at the bottom Response panel:**
   > 🎤 "In the bottom Response panel of Postman, the `page` block shows `number: 1` with five items, and all four test assertions in the Test Results tab are green."

3. **Speak, then click `GET Page 2`:**
   > 🎤 "In the left Collections sidebar of Postman, I will click `Page 2`, and in the top-right corner of the request panel, I will click the blue Send button to fetch the final page."
   - **Speak while pointing at the bottom Response panel:**
   > 🎤 "In the bottom Response panel of Postman, `content` contains the remaining two records, Process 02 and Process 01, and `page.number` is 2."

4. **Speak, then click `GET Page 3`:**
   > 🎤 "In the left Collections sidebar of Postman, I will click `Page 3`, and in the top-right corner of the request panel, I will click the blue Send button to test a page index beyond the last page."
   - **Speak while pointing at the bottom Response panel:**
   > 🎤 "In the bottom Response panel of Postman, `content` is an empty array while `totalElements` remains 12 and the HTTP status in the top-right of the response panel is `200 OK`."

5. **Speak, then click `GET Filter CRITICAL`:**
   > 🎤 "In the left Collections sidebar of Postman, I will click `Filter CRITICAL`, and in the top-right corner of the request panel, I will click the blue Send button to request `status=CRITICAL&page=0&size=3`."
   - **Speak while pointing at the bottom Response panel:**
   > 🎤 "In the bottom Response panel of Postman, only CRITICAL records are returned, and the `page` block shows `totalElements: 4` and `totalPages: 2`."

6. **Speak, then click `GET Size cap`:**
   > 🎤 "In the left Collections sidebar of Postman, I will click `Size cap`, and in the top-right corner of the request panel, I will click the blue Send button to request `size=500` and verify our maximum page-size cap."
   - **Speak while pointing at the bottom of the JSON in the bottom Response panel:**
   > 🎤 "Scrolling to the bottom of the JSON in the bottom Response panel of Postman, `page.size` is capped at `100` instead of `500`, confirming `spring.data.web.pageable.max-page-size=100` is enforced."

---

### SECTION I: Epilogue (`20:00 – 23:10` — ~3 minutes, no typing needed)

Leave Postman open on screen (with IntelliJ still minimized in the Dock so no window covers another) and read the Epilogue below at a steady pace:

> 🎤 "Let's wrap up with a summary of what we accomplished and key takeaways.
>
> First, completion and verification: we added pagination to the `/api/process-checks` GET endpoint across all three layers of our Spring Boot application—`ProcessCheckRepository`, `ProcessCheckService`, and `ProcessCheckController`—and configured a maximum page-size cap of 100 in `application.properties`. We verified the implementation in two ways: first with automated `MockMvc` integration tests in IntelliJ IDEA checking both the `content` slice and the `page` metadata, and second with six live HTTP requests in Postman covering page 0, page 1, the partial last page, an out-of-bounds page, status-filtered pagination, and the 100-item size cap.
>
> Second, why Spring Data's `Pageable` and `PagedModel` are the most effective approach: instead of manually parsing `page`, `size`, and `sort` query parameters or writing custom SQL `LIMIT` and `OFFSET` clauses, Spring MVC's `PageableHandlerMethodArgumentResolver` binds the query string automatically. In the service layer, `Page.map` converts each `ProcessCheck` JPA entity into a `ProcessCheckResponse` record while preserving total element and page counts. Wrapping the result in `PagedModel` at the controller boundary guarantees a clean, stable JSON structure with `content` and `page` fields.
>
> Third, important pitfalls a junior developer should watch out for when implementing pagination:
> - Number one: page numbers in Spring Data are zero-based, meaning `page=0` is the first page and `page=1` is the second page.
> - Number two: always specify a deterministic default sort in `@PageableDefault`, such as sorting by `lastCheckedAt` descending. Without a stable sort order, database engines do not guarantee row ordering across pages, which can cause duplicate or skipped records.
> - Number three: always cap the maximum page size using `spring.data.web.pageable.max-page-size` so a client cannot request millions of rows in a single call.
> - Number four: changing an endpoint from a flat JSON array to a paged object is a breaking API contract change, as we saw when our three original integration tests failed until we updated their JSON paths from `$` to `$.content`.
> - Number five: if a client passes an unknown property name in the `sort` query parameter, Spring Data throws an unhandled property reference exception resulting in a 500 response, so a production improvement would be validating allowed sort fields and returning a `400 Bad Request` Problem Detail.
>
> Finally, after stopping the recording, all deliverables are packaged into `Deliverables.zip`. Thank you for watching."

---

### Stop Recording
1. Bring **TaskRecorder** to the front from the Dock.
2. Click **Stop Recording** and wait until TaskRecorder status changes from `Stopping` → `Archiving` → `Idle`.
