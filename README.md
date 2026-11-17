# Creative Board

A guided creativity session in three rounds on a shared Claude Whiteboard. Claude proposes ideas on the board, you or your team judge them there with stickers and comments, and the next round builds on what survived. The session ends with a design note and tasks in dependency order.

Ask a model for ideas and you get the obvious ones. Good ideas come when a human pushes back in between. This plugin gives that a fixed shape: one technique per round, then your verdict, then the next round.

## The rounds

1. **"Like X, but ..."** Five things that already solve the problem, five variations each.
2. **Reverse brainstorming.** How do we make it as bad as possible? Then turn each answer into a rule. The pairs stay on the board, joined by an arrow.
3. **What makes us do it in real life?** Real examples and their pull, and what the project can borrow. The arrow says whether it adds, confirms or replaces an earlier idea.

Every idea must pass one question: how does the code know? A rule that cannot be computed is not a rule.

## How you judge

- Each round is a section on the board.
- Put a face sticker on every card that survives. A comment on a card is a change request in your own words.
- Type "next" in the chat. Claude reads the board, turns the kept cards green and builds the next round on them.
- Nothing is deleted. Dropped ideas stay where they are, so you can see what you decided against.

Claude cannot watch the board. It reads the board when you say "next", not before.

## Four optional rounds

Borrowed from Six Sigma, off by default, at most two per session. Claude proposes one when its trigger is met, and you say yes or no.

| Round | Borrowed from | Trigger |
| --- | --- | --- |
| How do we measure success? | CTQ tree | The goal has no number |
| Must have, nice to have, surprise? | Kano model | More than 6 ideas survive round one |
| Does it beat what we have today? | Pugh matrix | 3 or more ideas still compete after round three |
| How will we know it works? | Control plan | Decisions are made, tickets are not yet written |

## The outcome

- A "Decisions" section on the board: task cards in the order they build on each other, with their tuning numbers.
- A design note: the decisions with their mechanisms and numbers, and what was dropped and why.
- Tickets in your project's tracker, if one is connected. Without a tracker, a numbered task list in the note.

## Usage

Type `/creative-board`, or ask for a brainstorm on a board, a whiteboard session or a team vote on ideas.

The board needs the Whiteboard artifact type in Claude. Without it, the skill says so and runs the same rounds in the chat.

## What this plugin does

The plugin contains one skill and nothing else: no hooks, no scripts, no MCP servers. It sends no data anywhere on its own. It works only through the tools that Claude already has in your session: it creates one Whiteboard artifact, and when you ask for it, a design note and tickets through the document and tracker tools you have connected.

## License

MIT, see [LICENSE](LICENSE).
