# Codex Usage Efficiency Standard

This is a **mandatory global development standard** for all current and future software projects governed by the Master Instruction Library whenever Codex or another repository-aware/model-based coding agent is used.

Projects inherit this standard automatically by referencing and following the Master Instruction Library. Individual project repositories do **not** need to duplicate the full text of this standard.

**Canonical instruction repository:** `auxz2jz/master-instruction-library`

## Purpose

Reduce unnecessary model usage, repository context, repeated reasoning, generated output, rebuilding, and repeated analysis without reducing:

- correctness
- code/data safety
- recoverability
- required diagnostics
- required guided testing
- maintainability
- cross-platform isolation

Efficiency must never be achieved by skipping required safety checks, ignoring project instructions, bypassing mandatory diagnostics/testing, or making unverified assumptions about important code behavior.

---

## 1. Read only what is needed

Do not automatically scan or reread the entire repository for every task.

Start with the files most likely to be directly relevant to the requested change.

Expand only when:

- dependencies are unclear;
- the feature crosses multiple modules;
- a referenced symbol cannot be located;
- initial files reveal additional dependencies;
- a build/test failure points elsewhere;
- or broader architectural understanding is genuinely required.

Prefer targeted searches for:

- class names
- function names
- IDs
- resource names
- error messages
- configuration keys
- filenames
- known feature names

Do not repeatedly reread unchanged files unless new evidence makes rereading necessary.

---

## 2. Use existing project knowledge first

Before broad repository exploration, use the project's existing:

- project memory
- roadmap
- architecture documentation
- README files
- implementation notes
- diagnostics documentation
- test documentation
- changelog
- known-good/verified baseline information

Do not rediscover information that is already documented.

Always begin with `INSTRUCTION_INDEX.md` and follow all mandatory global and project-specific instructions.

---

## 3. Keep model context small

Do not load large files into model context when only a small section is needed.

When possible:

1. locate the relevant symbol;
2. inspect surrounding code;
3. inspect only the affected function/class/module;
4. expand outward only when required.

Avoid loading unrelated:

- large logs
- generated files
- binaries
- dependency caches
- build directories
- unrelated source trees

Generated/dependency folders should normally be excluded unless directly relevant, including examples such as:

- `build/`
- `dist/`
- `.gradle/`
- `.idea/`
- `node_modules/`
- compiled binaries
- generated sources
- dependency caches

---

## 4. Match reasoning effort to task difficulty

Simple changes should remain simple.

Examples:

- visible text changes
- version-number updates
- spacing/layout adjustments
- color/icon changes
- straightforward settings
- known constants
- obvious typos
- simple button actions
- documentation updates

Do not perform repository-wide architectural analysis for a localized change.

Use deeper reasoning for genuinely difficult work such as:

- persistent bugs
- architecture changes
- concurrency/state problems
- lifecycle problems
- data corruption
- migrations
- complex cross-platform design
- unusual toolchain failures

---

## 5. Model/reasoning escalation

When model/reasoning controls are available, use the least expensive/capable configuration that can reliably perform the task.

### Routine work

Prefer a cost-efficient coding configuration with Low or Medium reasoning for:

- routine implementation
- small fixes
- UI changes
- ordinary refactoring
- documentation
- test additions
- repetitive coding
- straightforward build errors
- well-defined features

### Escalation

If the normal configuration cannot solve the issue after a reasonable evidence-based attempt, escalate to a stronger coding/reasoning configuration.

Prefer Medium reasoning before High reasoning.

Use High or the highest-capability configuration only when complexity genuinely requires it, such as:

- persistent bugs surviving previous attempts
- complex architecture changes
- difficult concurrency/state problems
- large migrations
- unusual compiler/toolchain failures
- highly interconnected cross-platform changes
- repeated failure of the normal approach

Do not use the highest-cost configuration merely because it is available.

Model names, tiers, and available reasoning controls may change over time. The authoritative principle is:

**Use the least expensive model/configuration that can reliably complete the task, and escalate only when task difficulty or evidence shows that escalation is necessary.**

If the active agent cannot change its own model/reasoning setting, record that escalation is recommended rather than pretending it changed models.

---

## 6. Avoid failure loops

This standard supplements, and does not weaken, the anti-loop rules in `CORE_DEVELOPMENT_RECOVERY_RULES.md`.

Do not repeatedly perform the same unsuccessful edit/build/test cycle without changing the diagnostic approach.

After repeated failure, compare:

- current error
- previous error
- changed files
- dependency state
- configuration
- expected behavior
- known-good implementation
- relevant diagnostics

If two attempts fail for substantially the same reason, stop that approach and reassess before another speculative change.

The Master Instruction Library's stronger anti-loop and three-failure escalation rules remain authoritative.

---

## 7. Target builds and tests

Do not run every possible build/test after every tiny edit.

Use the smallest meaningful verification first, such as:

- compile affected module
- run relevant unit test
- run relevant Gradle/task target
- run specific test case
- verify affected component
- perform targeted static analysis

Run broader verification when:

- targeted verification succeeds;
- shared infrastructure changed;
- the change is large;
- dependencies cross modules;
- release verification is being performed;
- or project instructions require a full build/test.

Never skip required final verification.

---

## 8. Do not flood context with build output

When a build/test produces a large log:

1. preserve the full log on disk when required;
2. identify the first meaningful error;
3. capture the relevant stack trace/surrounding lines;
4. search for related errors;
5. reason from the smallest useful excerpt;
6. retrieve more only when necessary.

Do not repeatedly feed a multi-thousand-line log into model context when a small relevant section contains the problem.

Diagnostic preservation and model-context efficiency are separate concerns.

---

## 9. Prefer targeted patches

Do not rewrite an entire file when a small patch is sufficient.

Prefer:

- focused edits
- small diffs
- existing abstractions
- existing project patterns
- incremental changes

Large refactors should occur only when:

- explicitly requested;
- required for correctness;
- required for maintainability;
- or clearly justified by the task.

Do not reformat unrelated code during a functional change.

---

## 10. Keep explanations proportional

Prioritize completing the requested development work.

Unless detailed explanation is requested, completion reports should be concise and include:

- what changed
- important files changed
- builds/tests performed
- result
- remaining issue/manual test if any

Do not repeatedly restate the user's request or generate long essays about obvious changes.

---

## 11. Plan briefly before large changes

For substantial work, identify:

- affected components
- likely files
- dependencies
- implementation approach
- verification method

Then implement.

Do not create an oversized design document for a small task.

---

## 12. Use known-good versions

When a known-good or user-verified version exists, use it as reference rather than reconstructing behavior from scratch.

For regressions:

1. identify the verified baseline;
2. compare the relevant area;
3. isolate meaningful changes;
4. repair the regression with the smallest justified change.

Do not broadly rewrite working systems to fix a localized regression.

---

## 13. Preserve mandatory diagnostics without wasting context

`DIAGNOSTICS_STANDARD.md` remains mandatory.

Efficiency does **not** mean reducing required application diagnostics.

Instead:

- store detailed diagnostics in files/logs;
- summarize important findings for reasoning;
- inspect detailed logs selectively;
- retrieve more only when needed.

The application may retain rich diagnostics while the coding agent consumes only the relevant diagnostic subset.

---

## 14. Guided testing still applies

`GUIDED_TESTING_STANDARD.md` remains mandatory according to the Master Instruction Library.

Do not eliminate or weaken guided testing merely to save model usage.

Verification should be targeted to the feature/change first, then broadened when required for system-wide confidence.

Do not execute unrelated test procedures unless required by dependency scope or final verification.

---

## 15. Cross-platform efficiency

For cross-platform projects:

- do not analyze both platforms when a change clearly affects only one;
- inspect shared specifications/interfaces only when the change could affect them;
- inspect the other platform only when shared behavior, compatibility, synchronization, file formats, APIs, or architecture may be affected;
- preserve platform ownership boundaries.

Cross-platform status alone does not justify scanning every platform on every task.

Shared source code is **not assumed**. Follow `CROSS_PLATFORM_COLLABORATION_STANDARD.md`: share intent/specifications by default and share implementation code only when it is genuinely platform-neutral and intentionally shared.

---

## 16. Stop when the task is complete

Once:

- the requested change is implemented;
- required verification passes;
- mandatory instructions are satisfied;
- required project documentation/checkpoint updates are complete;
- no unresolved task-related error remains;

stop.

Do not continue with unrelated improvements.

Do not perform opportunistic refactors that were unnecessary.

Do not search for additional work unless specifically instructed.

---

## 17. Efficiency priority hierarchy

Use this priority order:

1. Correctness
2. Data/code safety
3. Recoverability
4. Required diagnostics/testing
5. Maintainability
6. Efficient model usage

Never save model usage by knowingly risking:

- data loss
- broken builds
- corrupted project state
- destructive unreviewed changes
- security problems
- missing migrations
- untested critical functionality

---

## 18. Default efficient workflow

Unless another instruction overrides it:

1. Read `INSTRUCTION_INDEX.md` and mandatory Master Instruction Library rules.
2. Read current project memory/roadmap/status documentation.
3. Identify the smallest likely affected file set.
4. Search for exact symbols/features involved.
5. Inspect only necessary code.
6. Make a targeted change.
7. Run targeted verification.
8. Diagnose failures before repeating edits.
9. Run broader verification only when justified/required.
10. Update required project documentation/version/checkpoint information.
11. Provide a concise completion report.
12. Stop.

This workflow operates inside the broader development/recovery workflow defined by `CORE_DEVELOPMENT_RECOVERY_RULES.md`.

---

## 19. User override

The user may explicitly request:

- deeper analysis
- full repository review
- exhaustive testing
- additional diagnostics
- architectural review
- extensive documentation
- stronger model/reasoning use

Follow that explicit instruction even when it consumes more model usage, unless another higher-priority safety/platform requirement prevents it.

---

## 20. Long-running authorized work and milestone boundaries

The user's default preference is to complete as much **authorized, useful, verified work** as possible within the active task without asking for approval after every routine step. Divide substantial work into independently recoverable milestones:

1. Select the next in-scope milestone from the user's request and approved project plan.
2. Implement it using focused changes.
3. Run the relevant checks and preserve results.
4. Save a concise checkpoint at a meaningful boundary.
5. Continue to the next authorized milestone unless the task is done, a genuine blocker/safety gate requires input, the user stops work, or an actual platform/tool limit prevents continuation.

Do **not** manufacture extra features, run unrelated refactors, or assume permission to continue after the task is complete. Existing rule 16 ("Stop when the task is complete") still applies. A milestone is not automatically the end of a multi-milestone task. A pause or approval request that the platform actually requires must be honored.

## 21. Account usage awareness without fabricated monitoring

Account usage/rate limits, model context-window capacity, and individual tool budgets are **different**. Do not confuse a context-usage indicator with remaining account allowance.

- If the active Codex interface exposes a reliable current **remaining account allowance**, use it when available without repeatedly querying. Above 30%: normal work; 15–30%: prioritize completing in-progress milestones and durable checkpoints; below 15%: finish only the current safe operation, checkpoint, and stop before a substantial new operation.
- These percentages are **conditional guidance**, not proof Codex has a usage meter or an automatic threshold trigger. If the information is unavailable, stale, or ambiguous, state that and do not invent percentages or deadlines.
- Do not waste model calls repeatedly trying to obtain unavailable rate-limit information. Do not claim an automatic pause, warning, or usage-based shutdown exists without verifying the actual interface and its capabilities.
- Continue working in bounded milestones with frequent recovery points when limits cannot be measured. An abrupt hard limit may prevent a final save.

Never deliberately trigger usage errors to estimate remaining allowance. Never enter an automatic retry loop when a limit is reached. Do not promise automatic resumption after an account quota resets unless a verified, user-authorized mechanism exists.

## 22. Lightweight durable handoff during work

Use the project's **existing designated checkpoint/handoff mechanism** when present. Do not require a universal filename or duplicate an established project-memory system. If a project has no suitable concise handoff, create `docs/CODEX_HANDOFF.md` (or an equivalent documented path) as a lightweight recovery entry point, referencing rather than duplicating larger project records.

After each significant milestone and immediately before high-risk, lengthy, or disruptive operations, update the handoff with only the information needed to resume:

- active objective and next **single concrete action**;
- completed versus incomplete work, with accurate VERIFIED/CANDIDATE/PARTIAL statuses;
- files changed, current branch/commit and any uncommitted changes;
- exact build/test commands and outcomes, latest meaningful failures and diagnostic references;
- last **user-physically-verified baseline** kept separate from unverified work;
- assumptions/blockers and relevant roadmap or evidence links.

Prefer replacing stale handoff fields rather than growing an endless chronological transcript. Preserve useful full logs and evidence separately where required. Do not commit secrets or personal data, overwrite someone else's changes, create excessive micro-commits, or lose uncommitted work.

Checkpointing is best-effort: saved files and verified Git history survive session loss, but a model blocked mid-operation may not be able to write a final handoff. Update at milestone boundaries, not just at session end.

## 23. Efficient resumption after interrupted or exhausted sessions

When asked to continue, or when a new agent picks up a documented interrupted task:

1. Follow the mandatory startup instructions from the master index. Use verified unchanged local references when permitted; do not blindly re-ingest unrelated source or entire conversation history.
2. Open the designated current checkpoint/handoff, newest relevant evidence, and exact next action.
3. Check actual branch/commit, working-tree changes, and affected files. Reconcile any mismatch before editing; source and test evidence outrank stale handoff descriptions.
4. Confirm the last user-verified baseline and distinguish it from subsequent candidates.
5. Execute the next supported in-scope step **once**; do not rerun completed investigation, full builds, or identical failed commands without a reason.
6. Refresh the checkpoint and continue through approved milestones.

Do not silently restart the whole project, repeat already documented analysis, or infer a command succeeded just because it was attempted. If the required evidence is unavailable, request only the specific missing information or checkpoint the blocker.

## 24. Stopping, pausing, and tool-control honesty

Treat user commands such as **STOP**, **PAUSE**, and **SAVE AND STOP** as high-priority interruption requests and stop at the earliest safe opportunity the active tool/interface permits. If tools still allow saving, checkpoint first; do not start another milestone.

Distinguish an **agent instruction to stop at a milestone** from a **real application-level pause/interrupt control**. An instruction file cannot create a Windows Codex pause button, force-interrupt an already executing tool call, or observe account limits that the interface does not expose. Explain which controls are actually verified rather than making promises.

Existing core recovery commands (including `STOP LOOP. CHECKPOINT ONLY.` and `CONTINUE FROM CHECKPOINT.`) remain available and authoritative.

---

## 25. Next-stage model and reasoning recommendation at every checkpoint

At **every meaningful task completion, milestone, backup, or progress checkpoint**, include a **brief, actionable recommendation for the next authorized development stage** in both the user-facing report and the project's existing durable handoff/checkpoint (without duplicating entire history).

Include:
- **Next task/stage:** the single highest-priority next in-scope action and its principal verification or safety gate. If the authorized task is finished and no further task is approved, say **"No next task authorized"**; do not invent new work.
- **Recommended model/reasoning:** identify the most economical **available** model or reasoning setting likely to complete that next task reliably (for example Low/Medium/High/highest-capability or the actual controls exposed in the user's tool). If the model menu is unknown, use a **generic reasoning level** instead of guessing product model names.
- **Why and when to change:** one short complexity/risk explanation; mention whether to keep, raise, or lower the current setting, plus a concrete trigger to escalate (e.g. evidence-based failure, novel hardware/architecture uncertainty) or de-escalate (e.g. routine tests, implementation, documentation).
- **Usage/recovery:** when relevant, recommend a bounded next milestone and checkpoint timing appropriate to observable usage limits; never invent remaining quota, automatic monitoring or model-switching abilities.

Default to a **one- or two-line report**, for example:

`Next: Validate decompression against stored manifests (targeted offline tests). Recommended: High reasoning; lower to Medium for documentation, escalate only if parser evidence is contradictory. Checkpoint after verification.`

This is a **recommendation, not an automatic setting change**. The user or application must select the model/reasoning control when the agent cannot change it. Apply task-specific safety and testing requirements independently of usage optimization.

Do not spend substantial tokens estimating the optimal model. Reuse the project's current roadmap and results; update the recommendation if the actual next task changes. Never recommend a high-cost setting for routine work without a technical reason.

---

## Primary rule

**Spend model intelligence where intelligence is actually needed.**

Routine work should remain targeted and inexpensive.

Difficult problems should receive deeper reasoning only when the difficulty justifies it.

Never sacrifice correctness to save usage, and never waste high-cost reasoning, repository context, or repeated agent cycles on work that a smaller targeted operation can safely complete.
