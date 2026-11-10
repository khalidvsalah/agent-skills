---
name: design-first
description: "New build from scratch, however small or simple it looks (a game, web page, app, tool, script or service): required before the first line of code. Settles the stack with the user, designs, then builds. Example: \"make a snake game\" starts here."
---

# Design first

A new project gets its stack and its shape before its first line of code. A request that looks simple runs every step too: a small game still has a stack to choose. Start each step only after the previous step's criterion holds. The user owns the stack: you propose, the user decides. Coding the first idea that runs is the **shortcut**, and only the user can choose it.

This skill covers projects with no code yet. The target folder already holds a codebase: tell the user this skill is for new projects, and stop.

## Steps

1. **Constraints.** Collect every constraint that applies and tag each one:
   - **written**: `~/.claude/CLAUDE.md`, plus any `CLAUDE.md`, `AGENTS.md` or README already in the target folder or its parents.
   - **stated**: what the user has said about the project: purpose, users, platform, scale, deadlines.
   Done when every written and stated constraint is on the list, each tagged. An empty written list is normal for a new project.
2. **Stack.** Put every technical choice the constraints leave open to the user: language and framework, platform (web, mobile, desktop, CLI), data and backend, hosting, auth, and any approach choice that changes the shape of the build. Ask them in one batch, each with your recommended answer and its reason. When answers open new questions, ask those too.
   Done when each open choice has the user's answer or the user's "you choose". Only those two close a question.
3. **Research.** Study how this kind of project is built well today on the chosen stack: official docs, established libraries, reference implementations.
   Done when you hold at least two whole-approach options, each with its trade-offs and a source, and you have picked one for a reason that cites a constraint or a stack answer.
4. **Architect.** Run the **architect** skill. If the Skill tool cannot invoke it, read `~/.claude/skills/architect/SKILL.md` and follow it. Give its Phase A the constraint list, the stack answers and the step 3 choice.
   Done when architect returns a synthesized sketch (types, signatures, module map, rationale) and every constraint and stack answer maps to a part of it.
5. **Declare and wait.** Tell the user, in two or three sentences, what the approach is, why, and the main option you rejected. Name every choice you made under "you choose". Offer to write the stack, layout and conventions into a `CLAUDE.md` at the project root. Then end your turn.
   Done when the user approves the approach.
   The user asked for a quick prototype or a single file: state the shortcut and its cost here, and wait for the same approval.
6. **Build and check.** Implement against the sketch through architect's Phase D. Then walk the diff against the constraint list and the stack answers, one item at a time.
   Done when every item holds, or you have reported each deviation and its reason.
