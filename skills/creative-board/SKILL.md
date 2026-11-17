---
name: "creative-board"
description: "Guided brainstorming in three rounds on a shared Whiteboard, with four optional Six Sigma rounds: Claude proposes on the board, the user or a team judges there with stickers and comments. Use for /creative-board, or a brainstorm, creativity session, feature or design ideas when a board, whiteboard or team vote is wanted."
---

# creative-board - a creativity session in rounds, on a Whiteboard

A model predicts; on its own it lands on the obvious. The ideas get good when the user pushes back between the rounds. This skill is the frame for that: one technique per round, then the verdict, then the next technique on top of what survived. Never run the rounds in one go.

The board is the session's memory. Every round is a section, every verdict is visible on it, and every idea names where it came from.

## Board rules (all rounds)

- **One board.** Create it in step 0: list the artifact types, create from the Whiteboard type, and follow that type's own instructions for the format. Never make a second board and never rebuild it.
- **Each round is a new section** to the right of the last, or below it when that keeps it in the person's view.
- **Nothing is deleted.** Dropped ideas stay where they are.
- **Three colours, with a key under the title.** One colour for column headers. One strong colour for Claude's picks. Green for what the people kept. Everything else is plain.
- **A few words per card**, 60 characters at most. Reasons go in the chat or the design note.
- **Origin by name, not by long arrow.** A card that builds on an earlier idea starts with that idea's short name (`Pugh: only +, 0, -`). Arrows join only neighbours: the two cards of a pair, or a task and the task it depends on. Never route an arrow across another section.
- **Stickers and sticky notes belong to people.** Claude adds none.
- **Claude cannot watch the board.** After each round, stop and say so: vote on the board, then write "next" in the chat or comment on the board.

### Reading the verdict

Before every next round, read the board fresh: elements, stickers and comments. Then:

- A face sticker on a card is one vote to keep it. Count them.
- A sticker on either card of a pair counts for the whole pair.
- A comment or a sticky note is the person's own words. Record it word for word; it becomes a rule of the design.
- A card a person added, moved or reworded is theirs. Keep it and build on it.
- A verdict typed in the chat counts the same. If board and chat disagree, the newest statement wins. If you can't tell, ask once.
- A card with no vote, no comment and no mention is dropped.

Say in one or two lines in the chat what you read: kept, changed, dropped. Turn the kept cards green. Then start the next round. People correct you if you misread.

## 0. The question

- State the question in one sentence and what a good answer must do.
- If a ticket or issue holds the session, read it and its comments first; mark it as in progress in the project's tracker.
- Name the constraints already known (platform, budget, audience, what exists). Ask nothing that the code or the ticket answers.
- Board: a short title, the question as the one sentence under it, the constraints as a short list, the colour key, one line on how to vote.

## 1. Round one: "Like X, but ..."

- Pick five existing things that already do what the question asks (products, services, rituals, objects, methods). Prefer famous ones: their strength is proven.
- For each, write at least five sentences of the form "Like X, but ...": each keeps what makes X work and turns one thing toward our project.
- Board: section "Round 1" with five columns. One header card per X, its variations beneath.
- Mark the two or three strongest in the pick colour. Give one line of reason for each in the chat.
- Stop and wait. The user says what is good, what is a problem, and what to dig into.

## 2. Round two: reverse brainstorming

- Take the user's open points from round one as the targets. With none, target the survivors.
- Ask the reverse question: "How do we make this as bad / boring / frustrating as possible?" Write 8 to 12 honest answers.
- Turn each answer around into a rule or mechanic.
- Every open point gets a concrete proposal with numbers or a mechanism, not a mood. Where a proposal needs a decision, give options and a recommendation in the chat.
- Board: section "Round 2". Each pair is two cards joined by an arrow: the bad answer, then its rule. The pairs stay visible.
- Stop and wait. Record the user's decisions word for word.

## 3. Round three: what makes us do it in real life

- Ask why people do the thing without any product around it (the morning coffee, the weekly market, a walk with a friend).
- For each real example: what is the pull (routine, company, a small reward, the place, the season), and what our project can borrow.
- Board: section "Round 3". Each pair is two cards joined by an arrow: the real example with its pull, then what we borrow. Label the arrow adds, confirms or replaces. The second card names the earlier idea it touches.
- Stop and wait.

## 4. Hard questions to ask yourself every round

- How does the code know? A rule that cannot be computed is not a rule. If it cannot, propose the data that makes it computable or drop it.
- What does it cost to run: model calls, storage, screen space, the user's attention?
- What happens at scale (many users, many items, a long time)?
- Can it be tuned without a deploy? Every number goes into the project's config, never into code.
- Is it fair and kind to the people who use it (no dark patterns, no punishing absence)?

If the question is not about software, translate the five questions to its domain and say on the board how. The first becomes: who or what carries the rule out, and from which information?

Board: after round three, one table. Rows are the surviving ideas, columns are the five questions, cells are a word or a number.

## 5. The outcome

- **Decisions on the board.** A last section "Decisions": the decided ideas as task cards in the order they build on each other, an arrow from each task to the task that depends on it, tuning numbers on the cards.
- **Design note.** A doc, or a comment on the session ticket or a file in the project's docs when working in a repo. The decisions first, each with its mechanism and its tuning numbers; what was dropped and why in one line each. Facts only, no tour of how we got there. Put its link card next to the Decisions section and link the note back to the board.
- **Tickets.** Build tickets in the project's tracker, small enough for one session each, in dependency order, with the tuning numbers named in them. No tracker: the task cards and a numbered task list in the note.
- Move the session ticket to review.
- Report to the user: the board, the note, the new ticket ids, what needs a decision before building starts.

## Optional rounds

Four extra rounds, borrowed from Six Sigma. The three core rounds never change.

Rules for all of them:

- Off by default. At most 2 optional rounds per session.
- Trigger, not a fixed slot. When a round's trigger is met, propose that one round with one sentence of reason and wait for a yes. Never propose two at once. The user can also ask for a round by its name.
- Each optional round is 1 board section, 1 stop for the verdict, and at most 12 cards.
- Call each round by its question, never by the tool's name.

### "How do we measure success?"

- Trigger: the goal in step 0 has no number.
- When: before round one.
- Do: break the goal into what must be true for it to be reached. At most 3 branches and 2 levels. Every leaf is a number with a unit.
- Board: the goal card on the left, its branches and leaves to the right, joined by arrows.
- Verdict: the kept leaves become the success criteria for the rest of the session.

### "Must have, nice to have, surprise?"

- Trigger: more than 6 ideas survive round one.
- When: after the round one verdict.
- Do: sort the survivors into three stacks in everyday words: must have, nice to have, surprise. Claude sorts first; the people move the cards.
- Mark a card with `?` where no user evidence backs its stack. Say so; do not guess silently.
- Board: three columns, one short card per surviving idea, named as in round one.
- Verdict: the stacks as the people left them. Round two targets the must-haves first.

### "Does it beat what we have today?"

- Trigger: 3 or more ideas still compete after round three.
- When: after the round three verdict, before the Decisions section.
- Do: compare every surviving idea with today's state. The criteria are the success criteria from step 0, or the kept leaves of "How do we measure success?" if that round ran.
- Cells hold only +, 0 or -. No weights, no decimals, no totals that pretend to be precise.
- Board: one table. Rows are the ideas, columns are the criteria. Today's state is the 0.
- Verdict: the table recommends, the people decide. They vote on the idea cards or comment on the table.

### "How will we know it works?"

- Trigger: decisions are made and the tickets are not yet written.
- When: in the outcome, before the tickets.
- Do: give every decision one measure with its source, its target value and a check date. A measure with no source is dropped; say which.
- Board: one card beside each task card: measure, source, target, date.
- Verdict: the kept measures go into the design note. Each check date becomes a ticket with that date.

## Without a board

If no Whiteboard type is available, say so in one line and run the same rounds in the chat.

## Style

- Chat and board text in the user's language; the note and tickets follow the project's language rule.
- Short sentences, concrete examples from the project, numbers where they help.
- Disagree when a point does not hold, and say why; the user wants a partner, not an echo.