# Technical Solution: [JOB NAME]

**Branch**: `[###-job-name]` | **Date**: [DATE] | **Job**: [link]
**Input**: Job definition from `/jobs/[###-job-name]/job.md`

**Note**: This template is filled in by the `/jbtd.solution` command. See `.jbtd/templates/commands/solution.md` for the execution workflow.

## Summary

[Extract from job definition: primary job statement + technical approach to accomplish it]

## Job-Solution Alignment

**Job Statement**:
- **When** [situation from job.md]
- **I want to** [motivation from job.md]
- **So I can** [outcome from job.md]

**Solution Approach**:
[Brief description of how this technical solution accomplishes the user's job]

## Technical Context

<!--
  ACTION REQUIRED: Replace the content in this section with the technical details
  for the project. The structure here is presented in advisory capacity to guide
  the iteration process.
-->

**Language/Version**: [e.g., Python 3.11, Swift 5.9, Rust 1.75 or NEEDS CLARIFICATION]
**Primary Dependencies**: [e.g., FastAPI, UIKit, LLVM or NEEDS CLARIFICATION]
**Storage**: [if applicable, e.g., PostgreSQL, CoreData, files or N/A]
**Testing**: [e.g., pytest, XCTest, cargo test or NEEDS CLARIFICATION]
**Target Platform**: [e.g., Linux server, iOS 15+, WASM or NEEDS CLARIFICATION]
**Project Type**: [single/web/mobile - determines source structure]
**Performance Goals**: [domain-specific, aligned with job outcomes, e.g., <1s job completion, 60 fps or NEEDS CLARIFICATION]
**Constraints**: [from job definition, e.g., <200ms p95, <100MB memory, offline-capable or NEEDS CLARIFICATION]
**Scale/Scope**: [domain-specific, e.g., 10k concurrent jobs, 1M operations/day or NEEDS CLARIFICATION]

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

[Gates determined based on constitution file - ensure solution doesn't over-engineer]

## Project Structure

### Documentation (this job solution)

```text
jobs/[###-job]/
├── job.md               # Job definition (/jbtd.identify command output)
├── solution.md          # This file (/jbtd.solution command output)
├── research.md          # Phase 0 output (/jbtd.solution command)
├── data-model.md        # Phase 1 output (/jbtd.solution command)
├── quickstart.md        # Phase 1 output (/jbtd.solution command)
├── contracts/           # Phase 1 output (/jbtd.solution command)
└── tasks.md             # Phase 2 output (/jbtd.tasks command - NOT created by /jbtd.solution)
```

### Source Code (repository root)
<!--
  ACTION REQUIRED: Replace the placeholder tree below with the concrete layout
  for this solution. Delete unused options and expand the chosen structure with
  real paths (e.g., apps/admin, packages/something). The delivered solution must
  not include Option labels.
-->

```text
# [REMOVE IF UNUSED] Option 1: Single project (DEFAULT)
src/
├── models/
├── services/
├── cli/
└── lib/

tests/
├── contract/
├── integration/
└── unit/

# [REMOVE IF UNUSED] Option 2: Web application (when "frontend" + "backend" detected)
backend/
├── src/
│   ├── models/
│   ├── services/
│   └── api/
└── tests/

frontend/
├── src/
│   ├── components/
│   ├── pages/
│   └── services/
└── tests/

# [REMOVE IF UNUSED] Option 3: Mobile + API (when "iOS/Android" detected)
api/
└── [same as backend above]

ios/ or android/
└── [platform-specific structure: job-focused modules, UI flows, platform tests]
```

**Structure Decision**: [Document the selected structure and reference the real
directories captured above. Explain how structure supports job completion.]

## Job-Oriented Design

<!--
  ACTION REQUIRED: Map job scenarios to technical components.
  This ensures the solution directly serves the user's job.
-->

### Job Scenario Mapping

| Job Scenario (from job.md) | Solution Component(s) | How It Accomplishes the Job |
|----------------------------|----------------------|----------------------------|
| [Scenario 1: Brief title] | [Component names] | [Explanation of how component enables job] |
| [Scenario 2: Brief title] | [Component names] | [Explanation of how component enables job] |

### Core Capabilities

[List the key technical capabilities required to accomplish the job, organized by priority matching job scenarios]

**P1 Capabilities** (Must have for MVP):
- [Capability 1]: [How it enables P1 job scenario]
- [Capability 2]: [How it enables P1 job scenario]

**P2 Capabilities** (Important):
- [Capability 3]: [How it enables P2 job scenario]

**P3 Capabilities** (Nice to have):
- [Capability 4]: [How it enables P3 job scenario]

## Data Model (if applicable)

<!--
  ACTION REQUIRED: Define data structures needed to support the job.
  Focus on what data is needed to accomplish the job, not implementation details.
-->

### Entities

- **[Entity 1]**: [Purpose in accomplishing the job, key attributes]
  - Supports job scenario: [Which scenario(s)]
  - Key relationships: [To other entities]

- **[Entity 2]**: [Purpose in accomplishing the job, key attributes]
  - Supports job scenario: [Which scenario(s)]
  - Key relationships: [To other entities]

## User Interaction Flow

<!--
  ACTION REQUIRED: Describe how users interact with the solution to accomplish their job.
  Map to job scenarios from job.md.
-->

### Flow 1: [Job Scenario 1 Title]

```
1. User [action] → System [response]
2. User [action] → System [response]
3. Job accomplished: [outcome from job.md]
```

**Success Indicators**:
- [Observable sign that job is done, from job completion criteria]

### Flow 2: [Job Scenario 2 Title]

```
1. User [action] → System [response]
2. Job accomplished: [outcome from job.md]
```

**Success Indicators**:
- [Observable sign that job is done]

## Complexity Tracking

> **Fill ONLY if Constitution Check has violations that must be justified**

| Violation | Why Needed for Job | Simpler Alternative Rejected Because |
|-----------|-------------------|-------------------------------------|
| [e.g., 4th project] | [specific job requirement] | [why 3 projects insufficient for job] |
| [e.g., Complex architecture] | [job completion needs] | [why simpler approach won't accomplish job] |

## Job Completion Validation

<!--
  ACTION REQUIRED: Define how we'll verify the solution accomplishes the job.
  Reference success criteria from job.md.
-->

### Verification Checklist

From job.md Success Criteria:
- [ ] **JC-001**: [Success criterion from job.md] → Verified by: [How to test]
- [ ] **JC-002**: [Success criterion from job.md] → Verified by: [How to test]
- [ ] **JC-003**: [Success criterion from job.md] → Verified by: [How to test]

### Acceptance Tests

[Define tests that prove the job gets done, not just that code works]

**Test 1: [Job Scenario 1]**
- **Setup**: [Initial conditions matching job context]
- **Action**: [User performs job-related action]
- **Expected**: [Job is accomplished as defined in job.md]

**Test 2: [Job Scenario 2]**
- **Setup**: [Initial conditions matching job context]
- **Action**: [User performs job-related action]
- **Expected**: [Job is accomplished as defined in job.md]

## Open Questions / Clarifications Needed

<!--
  List any aspects of the job or solution that need clarification before implementation
-->

- [Question about job context or requirements]
- [Technical decision that needs validation]
- [Assumption that should be verified with users]
