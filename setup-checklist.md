## Open Clyo v0.1.0 — Manual Setup Checklist
### Before you start
- A Notion workspace on a plan that includes Notion AI (Business or Enterprise). Free and Plus only include a few trial AI responses, not enough to run Clyo day to day.
- You have the Open Clyo genome package (clone or download the repo; everything in it is a Markdown file).
- This checklist assumes a fresh, empty Notion workspace. If a page or database with the same name as any surface below already exists in your workspace, stop. Use a clean workspace or rename the existing surface before proceeding.
### Step 1: Create the context database
Create a new Notion database with these properties: Name (title), Status (select: Active / Archived), Topic (multi-select), Detail (text). This is your persistent context surface. The Detail text property is required because it is what AI retrieval reads. Name it whatever fits your workspace.
### Step 2: Create a Current Focus page
Create a page describing your active priorities and projects in plain text. Keep it short and current. Clyo loads this at conversation start as live context.
### Step 3: Create a Core Profile page
Create a page describing how you think and work: strengths, growth edges, values, and working preferences. Keep it concise but specific enough to guide tone, prioritization, and decision-making.
### Step 4: Create a Clyo Backlog page
Create a page that acts as a running list of system, prompt, and infrastructure improvements. Use it to track changes or upgrades you may want to make to Clyo over time.
### Step 5: Create a Capture Queue page
Create a page that serves as the holding surface for pending capture proposals. This is where proposed captures can sit before they are accepted, rejected, or incorporated elsewhere.
### Step 6: Create a Task Journal database
Create a new Notion database with these properties: Name (title; entry label, typically the date), Entry Date (date; the calendar day the entry covers, used to find or create today's entry). Completed work is appended to the page body as a point list, not stored in a property.
Optional: if you want Clyo to use a structured daily planning format, add a daily entry template to this database. Clyo will apply it automatically when creating today's entry; if no template is configured, Clyo creates a plain dated entry instead. Skip this if you just want Clyo to log completed work without a pre-structured daily format.
### Step 7: Create a Drift Log database
Create a new Notion database with seven properties: Name (title), Severity (select: Low / Medium / High), Status (select: Open / Reviewed), Date (date), Model (select), Model version (text), and Notes (text). This is where Clyo logs drift events it catches or that you flag. Clyo records the running model and version on every entry, which is why Model and Model version are their own properties rather than folded into Notes.
### Step 8: Add the version marker
Create a page titled "Open Clyo Version" and add one line: "Open Clyo v0.1.0 installed [your install date]." This is the install anchor future updates will reference.
### Step 9: Load Clyo's instructions
Navigate to Settings, then Notion AI (you can also open Settings with Cmd+K and search "Notion AI"). Under the Instructions section, click "Add instructions," then "Create your own." Notion will create a dedicated instructions page and open it for editing. Delete any text Notion has pre-filled into the page, then paste the full contents of `clyo-instructions.md` from the repo.
After pasting, scroll to the very bottom and confirm the closing lines of the file are present and intact. Long instruction sets can be silently truncated on paste, and a set cut off partway through will fail in quiet, confusing ways.
### Step 10: Wire your context surfaces into Clyo's instructions
Find each placeholder token in the text and replace it with an @-mention of the correct page or database you created:
- `[PLACEHOLDER: Current Focus page URL]` — @-mention your Current Focus page from Step 2 (appears twice; replace both)
- `[PLACEHOLDER: Core Profile page URL]` — @-mention your Core Profile page from Step 3 (appears twice; replace both)
- `[PLACEHOLDER: context database URL]` — @-mention your context database from Step 1
- `[PLACEHOLDER: Clyo Backlog page URL]` — @-mention your Clyo Backlog page from Step 4
- `[PLACEHOLDER: Capture Queue page URL]` — @-mention your Capture Queue page from Step 5
- `[PLACEHOLDER: Task Journal database URL]` — @-mention your Task Journal database from Step 6
- `[PLACEHOLDER: Drift Log database URL]` — @-mention your Drift Log database from Step 7
There are exactly nine placeholder instances across seven surfaces. Current Focus and Core Profile each appear twice; replace every instance, not just the first.
To insert an @-mention, place your cursor at the placeholder, delete the token, type @, and select the correct page or database from the picker.
### Step 11: Run a final completeness check
Before you close Settings, use Notion's in-page find (Cmd+F on Mac, Ctrl+F on Windows) inside the Instructions page and search the literal text `URL]`.
Every one of the nine wiring tokens ends in `URL]` and nothing else in the instruction set does, so the correct result is zero matches. Zero means every reference has been wired to a live surface. If the search finds even one, you are not done; find it, resolve it, and search again until the count is zero.
One caution: the instruction set also contains the string `[PLACEHOLDER:` in two places inside the Write-target readiness rules. Those are intentional — they are how Clyo detects an unconfigured write target — so leave them exactly as they are. Searching `URL]` rather than `[PLACEHOLDER` is what keeps them safe.
Only then save and close Settings.
### Step 12: Verify
Run these checks in a new Notion AI chat:
- Say "Load my current focus and tell me what you see." Clyo should read and summarize your Current Focus page.
- Say "Load my Core Profile and tell me what you see." Clyo should read and summarize your Core Profile page.
- Say "Search my context database for any Active entries." Clyo should query the database and report results or confirm it is empty.
- Say "Check my Drift Log for any open items." Clyo should read the Drift Log and report results or confirm it is empty.
- Say "Open today's Task Journal entry or create it if it does not exist." Clyo should locate the entry for today's date or create one.
If all checks resolve correctly, setup is complete. If any surface returns an error or "I can't find that," return to Step 10 and confirm the corresponding placeholder was replaced with a live @-mention.
### Step 13: Read the bootstrapping doc
Read `how-to-use-clyo.md` from the repo before your first real session.
