# Test Automation Tuesdays: Agent Prompt for Presentation Generation

## Context

You are assisting with a presentation series called **"Test Automation Tuesdays"** designed to cover test automation topics, with a focus on **Web UI testing**. Each presentation is **15–30 minutes** and includes demos or interactive components.

The series is being delivered by a team with the following tech stack:
- **Primary:** WebdriverIO + TypeScript + Cucumber (BDD)
- **Secondary:** Ruby + Watir + Cucumber
- **Cloud:** Mabl (low-code cloud automation)
- **CI/CD Migration:** Moving from Atlassian Bamboo to GitHub Actions
- **Interest in:** Playwright, Cypress, Selenium (Java/C#)

---

## Your Tasks

### Task 1: Collect and Validate the Topic List

Retrieve or confirm the following **20-topic slate** for "Test Automation Tuesdays":

1. WebdriverIO + Cucumber + TypeScript: Modern BDD on the Web
2. Advanced BDD Automation with WDIO (Hooks, Tags, Parallel Runs)
3. Architecting Maintainable WDIO Suites (Page Objects, Screenplay, Test Data)
4. Tackling Flaky WDIO Tests (Smart Waits, Locators, Retries)
5. WDIO in CI/CD: From Developer Laptop to Pipeline
6. Cross‑Browser, Cross‑Cloud WDIO (Grid, BrowserStack/Sauce/Mabl)
7. WDIO + API and Contract Tests as UI's Safety Net
8. Accessibility and Visual Regression in the WDIO World
9. Ruby Cucumber + Watir: What to Keep, What to Retire
10. Low‑Code Cloud Automation with Mabl: Where It Shines
11. Orchestrating WDIO, Ruby/Watir, and Mabl in One Strategy
12. Playwright for the WDIO Engineer
13. Cypress for Front‑End‑Centric Teams
14. Selenium in 2026: Java and C# Still Matter
15. How to Evaluate a New Web UI Tool
16. AI‑Assisted Test Automation (Including Mabl's GenAI)
17. Test Data and Environments for Reliable UI Suites
18. Testing SPAs and Modern Front‑Ends (React/Vue/Angular)
19. Reporting, Observability, and Flaky‑Test Analytics
20. Careers in Test Automation: From Manual QA to SDET Across Stacks

**CI/CD Migration Topics** (integrate into main series or run as special sessions):
- A. Bamboo to GitHub Actions: Strategy and Gotchas
- B. Running WebdriverIO Tests on GitHub Actions
- C. Triggering Ruby/Watir and Mabl Runs from GitHub Actions

**Validation criteria:**
- [ ] All 20 topics present and numbered
- [ ] CI/CD topics identified and mapped to appropriate slots
- [ ] Topics align with the team's tech stack and interests
- [ ] Any additions or deletions noted and justified

---

### Task 2: Create a Presentation Generation Workflow

For **each topic**, generate or prepare the following artifacts:

#### A. Presentation Outline (20–30 min talk)
- **Title:** (exact, as listed above)
- **Duration:** 20–25 minutes
- **Objective:** What should the audience know or be able to do after this talk?
- **Agenda:** 
  - Introduction / Why This Matters (2–3 min)
  - Main Content / Key Concepts (10–12 min)
  - Demo or Live Example (5–7 min)
  - Q&A / Wrap‑Up (2 min)
- **Key Takeaways:** (3–5 bullet points)

#### B. Demo Script (if applicable)
- **Setup:** What does the demo environment need?
- **Step‑by‑step:** Numbered walkthrough of demo actions
- **Expected Output:** What the audience should see at each step
- **Fallback:** If demo fails, what's the backup (recorded video, screenshot, live coding notes)?

#### C. Slide Template (HTML or Markdown)
- Title slide with topic and presenter name
- Agenda slide
- Key concept slides (3–5 content slides)
- Demo walkthrough slides (3–4 slides showing demo flow)
- Key takeaways / conclusion slide
- Q&A slide

#### D. Metadata
- **Topic Number:** (1–20 or A/B/C for CI/CD)
- **Presenter:** (to be assigned)
- **Target Audience Level:** (Beginner / Intermediate / Advanced)
- **Required Tools/Access:** (e.g., "WebdriverIO repo, Node 18+, GitHub account for Actions demo")
- **Related Topics:** (links to prerequisite or follow‑up talks)
- **Estimated Prep Time:** (hours to prepare and rehearse)

---

### Task 3: Workflow Initiation

Once outlines are confirmed, **batch-generate presentations** using the following process:

1. **For each topic:**
   - Create a unique folder: `presentations/topic-[number]-[slug]` (e.g., `presentations/topic-01-wdio-cucumber-ts`)
   - Inside, create:
     - `outline.md` (presentation outline)
     - `demo-script.md` (if demo exists)
     - `slides.html` or `slides.md` (slide template)
     - `metadata.json` (topic metadata)
   - Store related assets (e.g., example code, screenshots, recordings) in `assets/` subfolder

2. **Batch generation options:**
   - **Sequential:** Generate one presentation at a time; confirm outline before creating slides
   - **Parallel:** Generate all outlines first; then all demos; then all slides
   - **Per‑Topic:** Group by theme (WDIO / Alternatives / CI/CD) and batch together

3. **Output repository structure:**
   ```
   test-automation-tuesdays/
   ├── README.md (master index, schedule, contact info)
   ├── presentations/
   │   ├── topic-01-wdio-cucumber-ts/
   │   │   ├── outline.md
   │   │   ├── demo-script.md
   │   │   ├── slides.html
   │   │   ├── metadata.json
   │   │   └── assets/
   │   ├── topic-02-advanced-bdd-wdio/
   │   │   └── [same structure]
   │   └── ... (topics 3–20 + A/B/C)
   └── shared/
       ├── brand-assets/ (logos, color scheme)
       ├── css/ (shared slide styles)
       └── template/ (skeleton for new presentations)
   ```

4. **Scheduling and assignment:**
   - [ ] Confirm presentation schedule (weekly, biweekly, monthly?)
   - [ ] Assign presenters to topics (1 topic per presenter per week recommended)
   - [ ] Generate a `SCHEDULE.md` with dates, presenters, topics, and prep deadlines
   - [ ] Create calendar/issue tracker entries (GitHub Issues, Jira, or Asana) for each talk

---

## Workflow Inputs (From You)

Before I proceed, confirm or provide:

1. **Presentation Schedule:** When do you want to start? Weekly on Tuesday? Biweekly? How many weeks total?
   - Example: "Weeks 1–20, starting April 1, 2026, every Tuesday at 10 AM PT"

2. **Presenter Roster:** Who will deliver talks? Should I assign by topic or let presenters pick?
   - Example: "Alice (WDIO expert), Bob (Playwright lead), Carol (CI/CD), Dan (Mabl champion)"

3. **Slide Format & Branding:** 
   - HTML with embedded styles? Markdown + convert to PowerPoint? Google Slides template?
   - Any color scheme, logo, or template constraints?

4. **Demo Environment:** 
   - What repo/app should demos target? (Internal app? Public demo site? Sandbox?)
   - Can demos be pre-recorded or must they be live?

5. **Distribution & Recording:**
   - Will talks be recorded? If so, where stored (YouTube, internal wiki, GitHub releases)?
   - Should slides + recordings be shared in a public or private repository?

6. **Approval & Iteration:**
   - Who reviews outlines before slides are created?
   - Feedback loop timeline (e.g., 1 week review turnaround)?

---

## Expected Outputs

After all tasks complete, you should have:

✅ A **master topic list** with any adjustments noted  
✅ A **dated schedule** with assigned presenters  
✅ **20 presentation outlines** (one per topic) ready for review  
✅ **20 demo scripts** and environment checklists  
✅ **20 slide templates** in agreed format  
✅ A **GitHub repository** (or equivalent) with all assets organized and version-controlled  
✅ **Calendar entries / issue tickets** for prep, review, and delivery milestones  

---

## Next Steps

1. **Confirm or adjust** the 20-topic list and CI/CD integration
2. **Provide inputs** (schedule, presenters, format, demo environment)
3. **I generate** all outlines and supporting materials
4. **You review** and provide feedback
5. **I refine** and finalize presentations
6. **Presenters receive** their assigned talk(s) with all materials and rehearsal guidance
7. **Tuesdays commence!**

---

## Contact & Questions

If you have questions about specific topics, demo feasibility, or workflow adjustments, raise them now before bulk generation begins.
