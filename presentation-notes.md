Speaker Notes: Shelf, Git & Collaboration Workflow

Total target time: 5 to 7 minutes. Script below adds up to about 6 minutes. Audience: a new developer joining the team, or a technical stakeholder.

Slide 1: Title & Context (0:00 to 0:20)

What I'll say: "Hi, I'm Andiswa. This is Shelf, my personal reading tracker. Today I'm walking through how work moves from the Asana board I built for it into an actual Git commit."

Timing: 20 seconds

Slide 2: Agenda (0:20 to 0:40)

What I'll say: "Six things. What Shelf is and why it's Kanban. How an Asana card turns into a commit. The tools underneath. What review looks like when I'm working solo. How I keep the planning docs honest. And finally pitfalls plus a live demo."

Timing: 20 seconds

Slide 3: System Context (0:40 to 1:20)

What I'll say: "Shelf is a Board, Column, Card model. The columns are reading stages: Want to Read, Currently Reading, Finished. It's solo, sessions are irregular, and scope shifts as I learn things, which is exactly why I chose Kanban over Scrum. My Asana board is organized into a section per epic, Auth, Boards and Cards, Book Details and Notes, Search and Filter, and Reminders, and every story carries an Epic, Iteration, Priority, Effort, and Story Points."

Timing: 40 seconds

Anticipated question: Why not just use the Asana board and skip the markdown docs? Answer: the markdown files are the source I migrated from, so Asana is now the living version, and the docs stay as a record of the original plan.

Slide 4: Board-to-Commit Workflow (1:20 to 2:05)

What I'll say: "This is the core of the talk. A card starts in To Do on the Asana board. I create a feature branch named after that story, commit against it, and self-review before merging to main. Once it's merged, the card moves to Done. The board tells me what to build next. The branch is where it actually gets built."

Timing: 45 seconds

Anticipated question: What if you start a branch and then change your mind on the approach? Answer: the card stays in progress, I just re-scope the branch or restart it, the Asana card isn't locked to one implementation.

Slide 5: Key Technical Components (2:05 to 2:50)

What I'll say: "Four things underpin how I work. I picked Flutter because one codebase fits the board and card model I'm building. I open feature branches, one per epic or story, and keep them short so they don't drift. I write Conventional Commits, so a message like feat colon add rating field also references the Asana task it closes. And Asana is where I plan everything, the backlog, the sprint views, story points, and my Status field."

Timing: 45 seconds

Slide 6: Solo Review & Definition of Done (2:50 to 3:40)

What I'll say: "Working solo doesn't mean skipping review, it just changes shape. There's no teammate to open a PR to, so review means stepping away and coming back to re-read the diff with fresh eyes against my Definition of Done. Does the feature work, does it match the acceptance criteria, and is the board updated. My Status column, To Do, In Progress, In Review, Done, mirrors exactly where the branch actually is. Right now Sprint 1 is five user stories totaling fourteen story points, two are In Progress and three are still To Do."

Timing: 50 seconds

Anticipated question: Isn't self-review just a formality if there's no one else to catch mistakes? Answer: it still catches a surprising number of issues, and my sprint retro is where anything that slipped through gets flagged for next time.

Slide 7: Documentation & Planning (3:40 to 4:15)

What I'll say: "Two places hold the truth. The repo has the README, epics dot md covering all five epics, and the backlog and sprint one backlog docs. Asana holds the living version, a section per epic plus a Sprint 1 section, every story written as a user story with priority, effort, and story points set. Asana is the one I actually update day to day. The repo docs are the historical record of how the plan started."

Timing: 35 seconds

Slide 8: Common Pitfalls & Risks (4:15 to 4:55)

What I'll say: "Four things to watch for on a solo Kanban project. Asana and Git drifting apart, the fix is moving the card the moment the branch state actually changes, not at the end of the day. Scope creep, because there's no one else to push back on a new idea, so new ideas go to the backlog, not straight into the current iteration. Skipping self-review because it feels unnecessary alone. And calling something Done before it's actually done. Iteration 1 deliberately has no persistence yet, so that's not a bug, it's the plan."

Timing: 40 seconds

Slide 9: Demo Overview (4:55 to 5:30)

What I'll say: "What I'll show live. Picking a card off the Sprint 1 board, branching for it, making the change and committing with a reference back to that task, self-reviewing against the acceptance criteria, then merging and moving the card to Done."

Timing: 35 seconds

Slide 10: Summary & Resources (5:30 to 6:00)

What I'll say: "Three takeaways. The Asana board is the single source of truth for what's next. Every card maps to a branch and every branch maps back to a card. And solo doesn't mean no review, my Definition of Done still applies. Everything's linked here, the repo, the Asana project, and the planning docs. Happy to take questions."

Timing: 30 seconds

Anticipated question: What would you do differently if this became a team project tomorrow? Answer: add a real second reviewer step and branch protection on main, the Asana to branch mapping stays exactly the same.