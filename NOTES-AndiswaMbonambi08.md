## Assignment 2.1

### Question 1: Scrum or Kanban, for two different contexts

**Daily App (Shelf):** Kanban.
Shelf is solo, worked in short, irregular sessions, and the scope will shift as I actually
use the app and notice what's missing. Scrum asks me to commit to a fixed sprint scope and
run ceremonies (standup, sprint planning, retro) that only make sense with more than one
person to sync with — running them solo is just talking to myself on a schedule. Kanban's
continuous flow and pull-based WIP limits fit better: I add a card to "To Do" when an idea
occurs to me, pull it when I have a session free, and there's no sprint boundary I need to
hit or re-plan around when a session gets skipped.

**TrackFlow:** Scrum.
TrackFlow has multiple contributors who need to stay in sync, and Scrum's fixed cadence
(sprint boundaries, standups, reviews) gives the whole cohort shared checkpoints to
coordinate merges, demo progress, and re-negotiate scope together. That coordination
overhead is exactly what's missing — and unnecessary — when I'm the only person on the
project.

My answer differs between the two because the deciding factor isn't the type of project,
it's the number of people who need to stay coordinated.

### Question 2: A real trade-off

**Value:** Responding to change over following a plan.

**Decision:** How much detail to put into Shelf's initial epic list before I start building.

I could write a fully detailed backlog now, but since I'm still learning what a reading
tracker actually needs, a detailed upfront plan risks going stale before I even build half
of it. I'll lean toward responding to change: epics.md stays coarse so it can absorb what I
learn without a rewrite. Still, a completely planless backlog would leave me deciding
priorities from scratch every session, so I'll keep just enough structure to know the shape
of the whole project.

### Question 3: Critique and redesign

**Problems with the "TaskBoard Pro" brief:**

1. No demos until the build phase is complete — violates early/continuous delivery and
"working software as the primary measure of progress."
2. Requirements frozen once design begins — violates "welcome changing requirements, even
late in development."
3. Design fully separated from build and from the people who'll use it — violates "business
people and developers must work together daily."
4. One full QA pass and one full launch at the end — violates continuous testing and
sustainable pace.

**Iterative redesign, applied to Shelf:**

* Iteration 1 (MVP): one board, three columns (Want to Read, Currently Reading, Finished);
add a book and move it between columns; no ratings, notes, or persistence yet.
* Iteration 2: persist data between sessions; add rating + notes when a card reaches
Finished; edit/delete a card.

## Assignment 2.2

### Question 1 — Roles, solo and shared

For TrackFlow, the roles get assigned in class since it's cohort-wide, so I don't have a fixed answer yet. My guess is I'll end up in a Dev Team seat by default, with Product Owner and Scrum Master responsibilities split or rotated across the group.

For Shelf, I'm all three roles, and the one I expect to neglect first is Product Owner style discipline, specifically writing a real Definition of Ready before pulling something into a sprint. When you're also the developer, it's tempting to skip straight to building whatever feels interesting that session and skip stating acceptance criteria, since there's no one else who needs the item spelled out. The concrete habit that would stop this: before moving any backlog item into a sprint backlog, I write its Definition of Ready check as an actual short checklist against it, even if it takes two minutes. If I can't check every box, it doesn't move.

### Question 2 — Definition of Ready, Definition of Done

Writing this for Boards \& Cards rather than Auth, since Auth is out of scope for Iteration 1 per my Assignment 2.1 redesign. Boards \& Cards is the epic I'm actually building first.

Definition of Ready (Boards \& Cards):

* The item has a one line user facing description of the interaction, for example "user can add a book card to Want to Read".
* It lists two or three acceptance criteria stated as testable behaviour, not vague goals.
* It has no unresolved dependency on Auth or persistence, since neither exists yet in Iteration 1.
* The screen or component it lives in is named.
* It's small enough to finish in one solo working session, roughly under three hours.

Definition of Done (Boards \& Cards):

* The board renders the three fixed columns: Want to Read, Currently Reading, Finished.
* A card can be added with title and author and appears in the correct column.
* A card can be moved between columns and the UI reflects the move immediately.
* I've manually walked through add, move, move at least once without errors.
* No console errors during that walkthrough.
* The code is committed to main and runs locally without build errors.

### Question 3 — The artifact most at risk

Of Product Backlog, Sprint Backlog and Increment, Sprint Backlog is the one most at risk of being skipped or faked in a solo daily cadence project like Shelf. The Product Backlog is just a running list, easy to keep honest since it's low stakes to add or remove an item. The Increment happens almost automatically, since working solo means whatever I build each session is the increment by definition.

The Sprint Backlog is different because it's a commitment made in advance, and without a partner checking whether I stuck to it, it's easy to quietly swap items mid sprint and then write the sprint backlog after the fact to match whatever I actually did. The real cost of skipping it isn't that the work doesn't get done. It's that I lose the one artifact that would tell me whether my planning and estimates were any good. Without a genuine sprint backlog, there's no way to notice scope creep while it's happening, and no learning signal for the next planning session.



### NOTES.md Updates

1. The role I said I'd neglect first was Product Owner style discipline, specifically writing a real Definition of Ready before pulling something into a sprint. Actually doing Part 2 confirmed rather than changed that. It was genuinely tempting to skip straight to listing backlog items I found interesting and skip writing acceptance criteria for the Boards \& Cards items until I forced myself to check each one against the Definition of Ready.
2. Yes. The Definition of Ready blocked every Auth item from Sprint 1, even though Auth is listed first in my epics and instinctively felt like it should come first. It also blocked persistence and the rating and notes feature, both of which I expected to sneak into Sprint 1 since they felt small. Writing the Definition of Ready down made it obvious they all depend on something that doesn't exist yet in Iteration 1.

## Assignment 2.3

### Question 1 - Choosing a view

Board will be my Daily app's primary view day to day. Shelf data model already is Board > Column >Card, So basically the Board view in Asana just mirrors the app: I open it, see Want to Read / Currently Reading / Finished as columns, and drag cards across as I read. That's the daily-use motion.

List still earns a place for anything Board hides: bulk-editing custom fields across many cards at once, or scanning every backlog item as a flat, sortable table when I'm grooming the backlog rather than working through it.

Timeline is for iteration planning, not daily work. When I'm laying Iteration 1 and Iteration 2 out against each other, or checking that a dependency (say, persistence landing before ratings/notes can work) actually lines up in time, Timeline shows that sequencing in a way Board can't.

### Question 2 - Custom fields, deliberately

* **Epic** (Auth / Boards \& Cards / Book Details \& Notes / Search \& Filter / Reminders) - lets me filter the project down to one epic and see at a glance how much of it is done, so I know which epic to pull the next card from.
* **Iteration** (Iteration 1 / Iteration 2 / Backlog) - the filter that answers "what's actually in scope this week" versus everything else sitting in the backlog for later.
* **Priority** (High / Medium / Low) - decides what I pull in next whenever I have slack time inside an iteration instead of working top-to-bottom by instinct.
* **Effort** (S / M / L) - a capacity check before I commit a card to an iteration; if Iteration 1's cards are mostly L, that's a signal I've overcommitted a one-week MVP.

Each one exists because it changes a decision I actually make. I left Story Points off on purpose: Shelf is solo with irregular sessions, so point estimation for velocity tracking has nobody to report to and nothing to calibrate against. Effort as a rough S/M/L sizing does the one job I need (sanity-check iteration scope) without the overhead.

### Question 3 - Tag or field?

**Tag:** something like "learning" or "spike", a loose, cross-cutting label for a card that's really about exploring or practicing something rather than shipping a feature. It's not specific to Shelf; I'd want the same tag on cards in other Bitcube assignments too.

**Field:** Iteration. It's structured, single-select, and only makes sense scoped to this one project.

If I swapped them:

* Iteration as a tag would lose the "exactly one value" constraint. A card could end up tagged both Iteration 1 and Iteration 2, and I couldn't group Board columns or build a clean iteration filter off something that isn't enforced to be single-valued.
* "Learning" as a custom field would get trapped inside the Shelf project. It wouldn't follow the card if I wanted to spot every learning-type task across Assignment 1.3, Assignment 2.2, and Shelf at once. I'd end up rebuilding the same field per project instead of reusing one tag across the whole workspace.



### NOTES.md Updates

1\. What the given backlog exercise revealed

Building QuickNotes first with status sections (Backlog, In Progress, Done) rather than epic sections is what made me confident sectioning Shelf by epic instead was the right call for a backlog view, status only matters once something is being worked, and Shelf's Product Backlog isn't there yet. QuickNotes also surfaced a mechanical thing I didn't expect: a tag has to actually be applied to at least one task before Asana will offer it as a filter option, which changed the order I did things in on the real project, tag or set the field first, filter second, not the other way round.



2\. Where Sprint 1 Backlog and reality disagreed

Nothing about which items belonged in Sprint 1 changed, the Definition of Ready check from Assignment 2.2 held up. What moving it into Asana did surface is how uneven the three Sprint 1 items are once Effort sits next to them in a column: "move a card between columns" clearly carries more real work than its one-line phrasing suggested, enough that it's the one item I broke into subtasks, while "add a book card with a title and author" and "see a board representing my whole shelf" are comparatively small. On paper the three read as roughly equivalent scope; side by side with an Effort field, they aren't.



3\. The field vs. tag call you almost got wrong

When I got to Task 9's saved filter, my first instinct was to solve it the same way as Task 5, tag the Sprint 1 items and filter by tag. That would have worked by accident, but it's the wrong mechanic for the same reason Question 3 argues Iteration should be a field: tags don't enforce one value, so nothing would stop a task from picking up both a "Sprint 1" tag and a "Sprint 2" tag later, and the filter would quietly start returning wrong results. Using the Iteration field instead means the filter can only ever be accurate.





#### \### Asana Projects



###### \- QuickNotes (practice):

https://app.asana.com/1/1218293804888571/project/1218294161837579/list/1218296317073426



###### \- Shelf (Daily App):

https://app.asana.com/1/1218293804888571/project/1218333052944223/list/1218333673620846



## Assignment 2.4

### Question 1 - Rewrite Sprint 1 as real user stories

1. As a returning reader, I want to see a board representing my whole shelf so that I can tell at a glance what I'm reading, what's next, and what I've finished without scanning a flat list.

2\. As a reader who just picked up a new book, I want to add a book card with a title and author so that I can start tracking it immediately.

3\. As a reader progressing through a book, I want to move a card between columns (Want to Read, Currently Reading, Finished) so that my shelf reflects where I actually am with each book.

4\. As a reader who made a mistake or learned new details, I want to edit a card's title or   author after adding it so that my shelf stays accurate.

5\. As a reader who added something by mistake or no longer cares to track it, I want to delete a card so that my shelf only shows books I'm actually tracking.





### Question 2 - Acceptance criteria

1. See the board: Three columns render with the labels Want to Read, Currently Reading, Finished, in that order. An empty column shows a visible empty state rather than blank space. All existing cards appear in the correct column on load.

2\. Add a card: A visible "add card" action exists on at least the Want to Read column. Submitting with a title and author creates a card showing both fields. Submitting with an empty title is rejected with a visible message, no blank card is created.

3\. Move a card: A card can be dragged (or moved via an equivalent control) from any column to any other column. The card's column position updates immediately without a page reload. The card retains its title/author after the move.

4\. Edit a card: An edit action is reachable from the card. Changing the title or author and confirming updates the visible card text immediately. Cancelling an edit leaves the original values unchanged.

5\. Delete a card: A delete action is reachable from the card. Confirming removes the card from the board immediately. The action requires a confirmation step (e.g. a confirm dialog) so an accidental click can't silently delete.



### Question 3 - INVEST check

Picking story 3 (move a card between columns):



Independent — fails. It can't be built or demoed without stories 1 (the board existing) and 2 (a card existing to move), so it's not truly independent of the rest of Sprint 1.

Negotiable — passes. Whether it's drag-and-drop or a dropdown/button-based move is still an open implementation choice.

Valuable — passes. This is the core loop of the whole app.

Estimable — passes, now that it's broken into the 3 subtasks from 2.3 (drag handler, persist state, handle invalid drops).

Small — borderline fail. Needing 3 subtasks to even estimate it is itself a sign it's carrying more than one story's worth of work.

Testable — passes, per the acceptance criteria above.



It fails Independent structurally (that's fine, sequencing handles it) but the Small failure is the one worth fixing: I'd split "handle invalid drop targets" out into its own follow-up story instead of a subtask, since it's really an edge-case/robustness concern rather than core to "move a card." That shrinks story 3 down to just drag + persist, and moves error handling to a Sprint 2 candidate.



### Question 4 - Estimating alone, again



Using "add a book card" as the reference story (2 points, a simple form + list insert):



Story: See the board

Points: 3

Why: More structural than it sounds, three columns, empty states, initial load logic



Story: Add a book card

Points: 2

Why: Reference story



Story: Move a card between columns

Points: 5

Why: The 3-subtask breakdown from 2.3 makes this the biggest item by a clear margin



Story: Edit a card

Points: 3

Why: Similar shape to add, plus needing to locate/update the right card



Story: Delete a card

Points: 1

Why: Smallest, removal plus a confirm step

&#x20;

The surprise: "move a card" felt like a Medium effort item back in Assignment 2.3 (that's literally what I tagged it), but once it's decomposed into real subtasks it's the biggest story in the sprint at 5 points, more than double the reference story. Breaking it down revealed complexity the one-line phrasing hid.



### NOTES.md Updates-Assignment 2.4



NOTES.md Updates



1\. What changed between backlog phrase and real story

"Delete a card" looked like the smallest, most obvious item in Sprint 1, a one-line phrase with an equally obvious meaning. Writing the full story ("As a reader who added something by mistake or no longer cares to track it, I want to delete a card so that my shelf only shows books I'm actually tracking") forced me to name why someone deletes a card, and that surfaced two different reasons: a mistake versus genuinely losing interest. That distinction is what led to the acceptance criteria requiring a confirmation step, a raw backlog phrase like "user can delete a note" gives no reason to think about accidental deletion at all, it just reads as a CRUD checkbox.



2\. The retro, from the inside

\[To be filled in after TrackFlow's mock sprint retro in class, this needs an actual thing someone in the group said or a pattern that came up live, not something I can draft in advance.]



3\. Estimating with real stories vs. rough backlog items

Less confident, in a useful way. In Assignment 2.2 I estimated Boards \& Cards items as roughly equivalent effort just from their one-line phrasing. With real acceptance criteria in front of me in Assignment 2.4, "move a card between columns" clearly needed 5 points against a 2-point reference story, more than double, once I could see the actual conditions (drag handling, state persistence, invalid drop targets) rather than a short sentence. The estimates feel more trustworthy now specifically because they were harder to produce, I couldn't estimate from a vibe, I had to check the story against something concrete.



### Assignment 3.1



#### Question 1 - Suggesting mode vs. comments vs. direct edits



Direct edits: for content I own outright and have sole authority over, e.g. fixing a typo in Shelf's own epic list inside the Project Doc.



Suggesting mode: when a teammate proposes a change to content that isn't theirs and needs my sign-off, e.g. if a reviewer proposed rewording my Scope section, that goes through Suggesting so I can accept or reject it rather than it silently overwriting what I wrote.



Comments: when I want to flag something without touching the text itself, e.g. a comment on the Timeline section asking whether it accounts for the INT226C deadline, without editing the timeline.



#### Question 2 - Permissions, deliberately



Editor: just me. I'm the only one actually writing or restructuring the doc, sheet, and deck for Shelf.



Commenter: my Bitcube reviewer, invited to leave real feedback without being able to silently rewrite my plan.



Viewer: anyone who only needs visibility, no reason to interact with the content, e.g. a cohort-mate comparing notes.



A solo project doesn't need broad Editor access. The risk of everyone being an Editor by default is that an accidental edit from a reviewer gets mistaken for my own decision, and Version history gets noisier than it needs to be.



#### Question 3 - Sync or async?



Live (Meet): blocking questions that genuinely need back-and-forth, e.g. deciding whether Iteration 2 includes ratings or pushes that to Iteration 3, plus the kickoff stand-up itself since it's short and benefits from real-time clarity.



Async (Docs/Sheets/Calendar): goal-setting, written once in the Doc rather than debated live; task assignment, already visible in the Sheet/Asana without needing to be announced; status updates, which the tracker Sheet is inherently designed for.



Since Shelf is solo, almost everything defaults to async by necessity. The one place live conversation earns its cost is a genuine blocker, where waiting on an async reply would stall the work.



### NOTES.md Updates-Assignment 3.1



1\. What the TidyUp practice revealed

Working the sample first, I nearly filled the TidyUp Sheet with actual Shelf tasks instead of the sample chore data, since it felt faster to skip straight to something real. Catching that before building the sheet made me keep the practice and real deliverables cleanly separate, which meant the mechanics (dropdown, conditional formatting, formula) landed as their own rep before I touched real Shelf content.



2\. The permission you almost got wrong

I set Editor to just me, Commenter for my reviewer, and Viewer for anyone else, from the very first setup. Nothing needed correcting.



3\. Sync vs. async, in practice

It held. Everything (Goal, Scope, Timeline, task assignment, status) stayed async in the Doc/Sheet, and the only live piece was the short kickoff stand-up itself, exactly as planned in Question 3.



Shelf Drive folder: https://drive.google.com/drive/folders/15MRbV0ReYwTBScXs7faTpLwrR7WEUbkB?usp=drive\_link



Doc: https://docs.google.com/document/d/1\_sxL-yiE6vE1qE0pLGsaYaFSt08BaitmsyH9pHmfpjg/edit?usp=drive\_link



Sheet: https://docs.google.com/spreadsheets/d/1uz376IUDlSPAPsXstz91k0vbPsJI0dHdQRoX5kX6Ktc/edit?usp=drive\_link



Slides: https://docs.google.com/presentation/d/1AGgVYA8FW7Tyya4esP-wVpg36-m7tGm0-qcMTwCl6k8/edit?usp=drive\_link



Calendar event: https://calendar.google.com/calendar/event?action=TEMPLATE\&tmeid=M25wdTZiYzljMjZuc2liZzQ4bG43MmIwOHEgYW5kaXN3YW1ib25hbWJpMTJAbQ\&tmsrc=andiswambonambi12%40gmail.com



### Assignment 3.1



#### Question 1 - Beyond the core four

My README currently has Purpose and a rough "How to run," but no real Setup or Contribution guide. The section I'd add is Known limitations: app.py hardcodes the search term ("Andiswa") and the filter term ("Software Developer Trainee") directly in the script instead of taking them as arguments. Someone cloning this expecting a general-purpose directory tool would run it, get one fixed result, and have no way to search for anything else without editing the source. Leaving that undocumented means a new user assumes the tool is broken rather than realizing it's a demo script wired to fixed examples on purpose.



#### Question 2 - Comment audit

Shouldn't be there: app.py, line 1 - "# Entry point for the team directory tool". This restates what's already obvious from the file being run directly with print() statements at module level, it adds nothing a reader doesn't get from reading the next line.



Missing, should be there: app.py, line 40 - print(open("team.txt").read()). This opens and reads team.txt a second time, completely separately from get\_entries(), which already opens and parses the same file elsewhere in the script. There's no comment explaining why the raw file is printed directly here instead of reusing get\_entries(), intentional (showing the raw unparsed file) or just duplicated logic. That's exactly the kind of "why" a future reader has to guess at right now.



#### Question 3 - What makes a decision ADR-worthy

The real decision: splitting team.txt entries on blank lines (\\n\\n) instead of using a structured format like CSV or JSON. That's worth an ADR because it isn't obvious, CSV or JSON is the more conventional choice for structured team data, and someone extending this tool later might reach for csv.reader without realizing the file format assumes double-newline-separated blocks. A routine detail like using .lower() for case-insensitive search doesn't need an ADR, there's no real alternative anyone would reasonably reach for instead, it's just the obvious way to do it.



### Assignment 3.3 — Part 2 (Practice: BudgetBuddy)



\### Task 1 — Channel rewrite



The original message mixes two things that don't belong together: a bug report and a scope decision. They should go in different places.



\*\*Slack (the bug):\*\*

"Heads up, budget sync looks broken. Opening a ticket with details now, will link it here. Doesn't look like it's blocking anyone else yet."



\*\*Email (the scope decision):\*\*

Subject: Export feature, in or out of this sprint?



"Hi team,



We haven't confirmed whether the export feature is in scope for this sprint. It's not in the sprint backlog, but it came up in planning and I don't want to just assume either way.



My take: leaving it out keeps the sprint achievable, and it can go to the top of next sprint's backlog instead. If anyone thinks it needs to land this sprint, let me know by Thursday so there's still time to re-plan.



Thanks,

Andiswa



Why the split: the bug is short-lived and needs eyes on it now, that's what Slack is for. The scope question needs a decision people will want to look back on later, and it affects the whole team's sprint commitment, so that goes in email where it won't just scroll away and "no rush" doesn't quietly turn into "forgotten."



\### Task 2 — Question rewrite



"\*\*Context:\*\* Working on the category totals in BudgetBuddy. After adding a transaction to the Groceries category, the category subtotal updates fine but the overall monthly total doesn't match the sum of its categories.



\*\*What I tried:\*\* Logged each category subtotal on its own, they're all correct. Ran it again with a fresh database and a single transaction, and the mismatch is still there, so it's not stale data. Also checked that the recalculation runs after the insert, not before.



\*\*Exact behaviour:\*\* With one R100 grocery transaction, Groceries shows R100, but the monthly total sits at R0.00 until I refresh the page, then it shows R100.



\*\*Ask:\*\* Is the monthly total supposed to recalculate on write, or only on read? If it's meant to happen on write, I think the recalculation is firing before the insert actually commits, and I'd like another pair of eyes on the ordering in updateBudget()."



\### Task 3 — PR feedback



"updateBudget() is doing three separate jobs right now in one 40-line block: validating input, recalculating category totals, and writing to the database. That makes it hard to test any one part on its own, if a total comes out wrong there's no way to tell whether validation let bad input through or the recalculation logic is off.



Suggested direction: split it into three functions, validateBudgetInput(), recalculateTotals(), and a thin updateBudget() that just calls them in order. That also gives a place to unit test the recalculation on its own, since that's the part most likely to hide a subtle bug.



Not blocking if this needs to ship now, but worth a follow-up ticket if so."



\### Task 4 — Receiving it well



"Thanks for this, the point about not being able to tell validation failures apart from calculation failures is a good one, hadn't thought about it from that angle.



Quick question before I refactor: would you split recalculateTotals() further, one function per category type, or keep it as one function that loops through them? I'd lean toward keeping it as one, but you've worked with this code longer than I have.



Happy to do the split in this PR instead of a follow-up, shouldn't take long."



\## Assignment 3.3 - Part 1



\### Question 1 — Channel choice, for real



What should've happened: before touching either repo, I should have just sent a quick Slack message to my mentor asking whether this documentation belongs in team-directory or in daily-app. Instead I didn't send anything, I guessed, started working, and only found out it was wrong after I'd already committed app.py from team-directory into my daily-app repo by mistake. Slack is the right channel here specifically because it's a fast yes or no clarification, not something that needs a written record the way email would.



\### Question 2 — The self-check you did or skipped



The blocker: I wasn't sure which repo, team-directory or daily-app, a piece of documentation belonged in, and ended up accidentally committing app.py from team-directory into my daily-app repo. Before asking anyone, I could have just reread the assignment brief itself, it says "your own Daily App" right there, which would have told me straight away. I didn't check that first. I picked a repo on instinct and only found out it was wrong afterward, so this is a case of skipping the self-check rather than actually doing it.



\### Question 3 — Specific vs. vague feedback, side by side



Specific: "sprint-1-review.md groups items by status (Backlog/In Progress/Done), but nothing's actually in progress yet at this stage, grouping by epic instead would make it easier to see which epic to pull the next card from."

Vague: "This doc needs some work."

The difference: the specific version names the actual structural choice, explains why it doesn't fit where the project is right now, and points to what to do instead. The vague version doesn't give you anything to actually act on.



\## Assignment 3.3 — Part 3 (Real work)



\### Task 5 — Real help request

"Hi Skye, I'm not sure whether Assignment 3.2's documentation tasks belong in my team-directory repo or my daily-app repo. I already went back and reread the assignment brief, and it mentions 'Daily App,' but I've got real code history in both. I accidentally committed app.py from team-directory into daily-app while trying to sort this out. Could you confirm which repo this should actually live in so I can clean up the wrong commit?"



\### Task 6 — Real PR feedback

"sprint-1-backlog.md lists the three Sprint 1 items with roughly equal-looking phrasing, but 'move a card between columns' actually carries more real work once Effort is factored in, it's the one that ended up needing 3 subtasks. Worth flagging Effort next to each item earlier, before Sprint 1 starts, instead of finding out about the imbalance after the fact."



\### Task 7 — Reflect on real feedback received

Pending feeback....



\### Task 8 — Before/after a real message

Before (what actually happened): nothing was sent, the confusion just got sorted out through trial and error, committing to the wrong repo and then fixing it.

After (applying async norms): "Quick check before I start Assignment 3.2, should this go in team-directory or daily-app? Want to avoid committing to the wrong one again like last time." Sent as one clear async Slack message instead of just guessing silently. The real fix here isn't the wording, it's that a message should have existed at all before acting.

