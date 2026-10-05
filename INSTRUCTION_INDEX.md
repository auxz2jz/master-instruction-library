# Instruction Index

Read this file first.

**Canonical repository:** `auxz2jz/master-instruction-library`

## Mandatory for all software projects

1. **CORE_DEVELOPMENT_RECOVERY_RULES.md**
   - Project memory
   - Verified baseline
   - Checkpoints
   - Small-change workflow
   - Anti-loop rules
   - Three-failure escalation
   - Evidence-first debugging
   - Recovery commands
   - End-of-session handoff

2. **DIAGNOSTICS_STANDARD.md**
   - Mandatory for every program
   - Inspect actual controls/workflows before instrumentation
   - Persistent action trace
   - Button/user-action logging
   - Request/state/result separation
   - Error and stack-trace logging
   - Crash preservation
   - Correlation IDs
   - Stall/watchdog monitoring
   - Diagnostic export
   - Privacy/redaction

3. **GUIDED_TESTING_STANDARD.md**
   - Tests derived from the program's actual features
   - "Test This Version" workflow
   - Step-by-step user instructions
   - Expected results
   - Automatic verification
   - Human visual confirmation
   - Manual failure control
   - Persistent test progress
   - Test-report generation

4. **CROSS_PLATFORM_COLLABORATION_STANDARD.md**
   - Required when a project has Android/mobile and Windows/PC implementations or multiple platform agents.
   - Shared product/feature information
   - Separate platform ownership
   - Shared feature propagation
   - Separate checkpoints and verified baselines
   - Concurrent-work and overwrite protection

5. **CODEX_USAGE_EFFICIENCY_STANDARD.md**
   - Mandatory global standard automatically inherited by all current and future projects that use the Master Instruction Library when Codex/repository-aware/model-based coding agents are involved.
   - Individual project repositories do not need to duplicate the standard when they already reference and follow this Master Instruction Library.
   - Targeted repository reading and small context
   - Reasoning/model escalation only when justified
   - Targeted builds/tests and concise logs
   - Small patches and known-good version comparison
   - Stop when the requested task is complete
   - Efficiency never overrides correctness, diagnostics, testing, or recoverability

## Repository maintenance

6. **RULE_INTAKE_WORKFLOW.md**
   - Defines how new reusable rules are reviewed, merged, split, or added as new categories.

7. **RULE_CHANGELOG.md**
   - Permanent history of global rules added, changed, clarified, or retired.

## Required startup order for a new project

1. Read this index.
2. Read all mandatory global instruction files.
3. If using Codex or another repository-aware coding agent, read CODEX_USAGE_EFFICIENCY_STANDARD.md.
4. If the project is cross-platform or has multiple platform workers, read CROSS_PLATFORM_COLLABORATION_STANDARD.md before touching project source.
5. Read the project's own project-memory/checkpoint file.
6. Read the project's roadmap.
7. Read the project's testing/diagnostic documentation.
8. Identify the last user-verified baseline for the platform being worked on.
9. Only then plan or modify code.

## Conflict priority

When instructions conflict, use this order:

1. User's latest explicit instruction.
2. Safety/platform requirements.
3. Project-specific explicit instructions.
4. These global master instructions.
5. Older chat discussion or assumptions.

Never silently ignore a conflict. Record an important conflict in the project checkpoint when it affects implementation.
