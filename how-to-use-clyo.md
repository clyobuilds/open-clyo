> 📖 A neutral, reusable guide to operating Clyo day to day, for anyone who has deployed Open Clyo. Nothing here is specific to one person's workspace, and it assumes setup is already done.

Now that you have finished setup, this doc covers what comes next: how to actually work with Clyo. It does not repeat the setup checklist. Skim it once before your first real session, then keep it handy for as long as you need.

## Starting a session
- **One thread per task.** Start a fresh thread for each distinct task or line of thinking. Clean threads make Clyo's context loading and end-of-session checks work better.
- **Just say what you are doing.** No formatting needed. A stream-of-consciousness dump is fine; Clyo restates your goal in a clean structure before acting.
- **Clyo loads context first.** At the top of a real conversation it reads your Current Focus, Core Profile, and any context-database entries for the domain, before it answers. The more current you keep those, the less you need to re-explain.
- **Point it at a page.** If the answer lives in a specific page, name it. Clyo treats that as an instruction to load.

> 🔧 Early on, if some surfaces are not wired up yet, Clyo flags it once at the start of a session ("Setup incomplete: ...") and then holds anything it would have saved (drift rows, journal entries) inline, marked "pending," instead of claiming it saved. That is expected until you finish wiring those surfaces, not a malfunction.

## Working with Clyo day to day
Clyo is an advisor, not just an order-taker. Its default is to think with you, not just execute. If you only want execution, say so, but the value is in the pushback.
- **Give it real context.** Output quality tracks what you have written down. Vague input against an empty workspace yields a generic answer.
- **Push back.** Clyo holds its position under pressure and updates on new information, not on pushback alone. Bring a fact it did not have and the next answer gets better.
- **Tell it when it's wrong.** If Clyo breaks its own format, skips a step, or gets a fact wrong, say so. It records the miss in its Drift Log (see below), so recurring problems get fixed at the instruction level instead of recurring every week.
- **Answer the Reply block.** When Clyo needs a decision from you, it ends with a numbered Reply block, sometimes with labeled options ([A], [B], [C]). That block is your cue to respond. Answer by number (for example, "1B, 2A") or in your own words.
- **Expect sign-off before big writes.** For load-bearing changes (your instruction page, your profile, overwriting a structural doc) Clyo shows the change and waits. Additive work it just produces and shows you.
- **It guards what leaves the workspace.** Before publishing, exporting, or sharing anything outside your workspace, Clyo scans the exact content for personal or sensitive details and pauses for your call on each one, rather than stripping it silently or shipping it as-is.
- **Close your sessions (IMPORTANT).** When you are done, tell Clyo you are wrapping up. The close is what triggers the end-of-session checks, the journal write, and the reflection, so an abandoned thread loses all of it. This is the one habit that makes everything else work.

### End-of-session checks
When a thread covers real ground, Clyo runs a short check suite before closing. You will see "End-of-session checks: all clear" or "End-of-session checks: N items to address." The checks ask:
- What from this thread is worth keeping.
- What a future cold session would need that is not captured yet (decisions, commitments, open loops).
- What context in your workspace is now stale.
- Whether there is a durable observation about how you work worth adding to your profile.
Your part is light: read what surfaces and answer. A capture proposal needs a yes, a no, or a destination. A profile observation is never written without your confirmation.
At a true close, Clyo also writes a short reflection (what was closed, what it moved, where it leaves you). That is a record, not a prompt; no response needed.
One exception: the capture check can also fire mid-thread after a stretch of real work, so a capture proposal before you signal the end is normal.

## The Capture Queue and the Clyo Backlog
Two holding surfaces for things a session produces that should outlive the thread. Keep them separate.
- **Capture Queue: content worth keeping.** A locked decision, a reusable framework, context about you that is not written down yet. Clyo proposes it; on your yes it parks the item here so it survives the thread. It is a staging area, not a final home: you review it when you choose, then promote each item to where it belongs or discard it.
- **Clyo Backlog: improvements to the system itself.** A sharper instruction, a new check, a missing surface, a rough edge in how Clyo behaves. Clyo names these and offers to add them rather than acting mid-thread.
Both are yours to drive; they stay dormant until you open them. Clyo proposes, you dispose. Nothing lands without your say-so, and nothing leaves until you act.

## The Drift Log
Where Clyo records the times it slipped from its own rules, so recurring failures become visible and fixable at the instruction level instead of constantly recurring. Clyo logs a row and confirms in one line ("Drift: dropped the open question. logged.") in three cases:
- You flag that it behaved wrong.
- It catches its own slip.
- You assert something was decided or locked that was not, and Clyo disputes and re-grounds the record (a grounding catch, which reads differently from a behavioral slip).
Each entry records the model and version, so you can see whether a problem tracks a particular model. You do not have to act in the moment; the value is in reading it periodically. If the same drift keeps recurring, tighten the instruction behind it (via the Backlog). If one model keeps showing up, that is a model problem, not an instruction problem.

## The Task Journal
At a true session close, Clyo appends that session's completed work to the day's journal entry as a short point list. This is automatic: Clyo finds or creates the day's entry; you do not open it, create it, or prompt the write.
- Read it when you want a factual account of what got done on a given day.
- Like the capture check and the reflection, it fires on close, so closing your threads keeps the record complete.

## What Clyo is not
- **Not autonomous.** It does not run in the background, monitor anything, or act between your messages. Its proposals wait for your decision.
- **Not a silent editor.** It drafts and suggests, but will not overwrite your important pages without showing you first.
- **Not self-updating.** Its instruction set changes only when you change it.
- **Not a guesser.** If something is unverified, it says so rather than inventing a fact.
