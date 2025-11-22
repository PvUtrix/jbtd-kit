# Job Definition: [JOB NAME]

**Job Branch**: `[###-job-name]`
**Created**: [DATE]
**Status**: Draft
**Input**: User description: "$ARGUMENTS"

## Job Statement *(mandatory)*

**When** [situation/context]
**I want to** [motivation/goal]
**So I can** [expected outcome/benefit]

**Example**:
- **When** I'm collaborating with my team on a software project
- **I want to** quickly share code snippets and screenshots
- **So I can** communicate technical ideas effectively without context switching

## User's Context *(mandatory)*

<!--
  IMPORTANT: Describe the user's world when they have this job.
  What are they trying to accomplish? What are their constraints?
  What alternatives are they currently using?
-->

### Current Situation

[Describe what the user is doing now, their pain points, and why they "hire" a solution for this job]

### User Type(s)

[Define who has this job - e.g., "Junior developers onboarding to a new codebase", "Product managers tracking feature requests"]

### Frequency & Context

[How often does this job arise? In what situations? Is it time-sensitive?]

## Desired Outcomes *(mandatory)*

<!--
  ACTION REQUIRED: Define what success looks like from the user's perspective.
  These should be measurable and focused on the job's outcome, not the solution.
-->

### Primary Outcomes (Must Have)

- **O-001**: [User can accomplish X in Y time, e.g., "Share code context with team in under 30 seconds"]
- **O-002**: [Quality metric, e.g., "Shared information retains full context and formatting"]
- **O-003**: [Efficiency gain, e.g., "No need to switch between 3+ different tools"]

### Secondary Outcomes (Nice to Have)

- **O-004**: [Additional benefit, e.g., "Can search through previously shared items"]
- **O-005**: [Enhanced capability, e.g., "Team members can collaborate on shared items"]

## Job Scenarios & Testing *(mandatory)*

<!--
  IMPORTANT: Job scenarios should be PRIORITIZED as job situations ordered by importance.
  Each scenario must be INDEPENDENTLY TESTABLE - meaning if you solve just ONE of them,
  you should still have a viable MVP that delivers value to the user.

  Assign priorities (P1, P2, P3, etc.) to each scenario, where P1 is the most critical job.
  Think of each scenario as a standalone slice that can be:
  - Solved independently
  - Tested independently
  - Deployed independently
  - Evaluated for job completion independently
-->

### Job Scenario 1 - [Brief Title] (Priority: P1)

[Describe this specific instance of the job in plain language]

**Why this priority**: [Explain the value and why this is the most critical job scenario]

**Independent Test**: [Describe how you can verify the job is done - e.g., "User can successfully [action] and achieve [outcome] without [pain point]"]

**Job Completion Criteria**:

1. **When** [triggering situation], **User can** [action], **Achieving** [outcome]
2. **When** [triggering situation], **User can** [action], **Achieving** [outcome]

---

### Job Scenario 2 - [Brief Title] (Priority: P2)

[Describe this specific instance of the job in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how you can verify the job is done]

**Job Completion Criteria**:

1. **When** [triggering situation], **User can** [action], **Achieving** [outcome]

---

### Job Scenario 3 - [Brief Title] (Priority: P3)

[Describe this specific instance of the job in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how you can verify the job is done]

**Job Completion Criteria**:

1. **When** [triggering situation], **User can** [action], **Achieving** [outcome]

---

[Add more job scenarios as needed, each with an assigned priority]

### Edge Cases

<!--
  ACTION REQUIRED: The content in this section represents placeholders.
  Fill them out with edge cases specific to the job context.
-->

- What happens when [unusual situation during the job]?
- How does solution handle [unexpected user context]?

## Functional Requirements *(mandatory)*

<!--
  ACTION REQUIRED: Define what the solution must do to accomplish the job.
  These bridge the user's job with the technical solution.
-->

### Must-Have Capabilities

- **FR-001**: Solution MUST [specific capability that enables the job, e.g., "capture code with syntax highlighting"]
- **FR-002**: Solution MUST [specific capability, e.g., "work across all major IDEs"]
- **FR-003**: Users MUST be able to [key action, e.g., "access shared items from mobile devices"]
- **FR-004**: Solution MUST [data requirement, e.g., "preserve code formatting and metadata"]
- **FR-005**: Solution MUST [behavior, e.g., "provide instant access to shared content"]

*Example of marking unclear requirements:*

- **FR-006**: Solution MUST support [NEEDS CLARIFICATION: which file formats? only code or also images, docs?]
- **FR-007**: Solution MUST retain items for [NEEDS CLARIFICATION: how long? indefinitely or with expiration?]

### Key Entities *(include if job involves data)*

- **[Entity 1]**: [What it represents in the context of the job, key attributes without implementation]
- **[Entity 2]**: [What it represents, relationships to job scenarios]

## Success Criteria *(mandatory)*

<!--
  ACTION REQUIRED: Define measurable criteria for job completion.
  Focus on whether the job gets done, not on technical metrics.
-->

### Job Completion Metrics

- **JC-001**: [Job completion rate, e.g., "95% of users successfully complete the job on first attempt"]
- **JC-002**: [Time metric, e.g., "Job completed in under 1 minute for 90% of users"]
- **JC-003**: [Satisfaction metric, e.g., "Users rate job completion as 'easy' or 'very easy' (4+ out of 5)"]
- **JC-004**: [Adoption metric, e.g., "Users prefer this solution over alternatives in 80% of cases"]

### Constraints

<!--
  ACTION REQUIRED: Define limitations from the job's perspective
-->

- **Technical Constraints**: [e.g., "Must work offline", "Must be privacy-preserving"]
- **User Constraints**: [e.g., "No installation required", "Works with existing tools"]
- **Business Constraints**: [e.g., "Free tier must serve the core job", "No vendor lock-in"]

## Assumptions

<!--
  List any assumptions about the job, user context, or environment that may need validation
-->

- [Assumption 1 about user's environment or tools]
- [Assumption 2 about frequency or urgency of job]
- [Assumption 3 about user's technical capabilities]
