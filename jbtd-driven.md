# Job-Driven Development: A Comprehensive Guide

**Building Software That Gets Jobs Done**

> "People don't want a quarter-inch drill. They want a quarter-inch hole." - Theodore Levitt

## Table of Contents

1. [What is Job-Driven Development?](#what-is-job-driven-development)
2. [The Jobs To Be Done Framework](#the-jobs-to-be-done-framework)
3. [Why Job-Driven Development?](#why-job-driven-development)
4. [Core Principles](#core-principles)
5. [The JBTD Workflow](#the-jbtd-workflow)
6. [Job Definition Template](#job-definition-template)
7. [Solution Design](#solution-design)
8. [Implementation Strategy](#implementation-strategy)
9. [Measuring Success](#measuring-success)
10. [Common Patterns](#common-patterns)
11. [Anti-Patterns to Avoid](#anti-patterns-to-avoid)
12. [Case Studies](#case-studies)

---

## What is Job-Driven Development?

**Job-Driven Development (JDD)** is a software development methodology that makes the user's job-to-be-done the primary artifact and source of truth. Rather than starting with technical specifications or feature lists, JDD begins by deeply understanding what job the user is trying to accomplish.

### The Core Insight

Users don't hire software for its features—they hire it to get a job done. A "job" is the progress a user is trying to make in a particular circumstance.

**Traditional Thinking:**
- "We need to build a file sharing feature"
- "Users want better search"
- "Add real-time collaboration"

**Job-Driven Thinking:**
- "When collaborating remotely, I want to share work-in-progress quickly so I can get timely feedback"
- "When remembering past decisions, I want to find them in context so I can avoid redoing research"
- "When working simultaneously, I want to see what's changing so I can avoid conflicts"

### Jobs Are Executable

In JDD, job definitions are not passive documentation—they're executable artifacts that:

1. **Generate technical solutions** through structured analysis
2. **Drive AI-assisted implementation** via agent commands
3. **Validate completeness** through job completion criteria
4. **Measure success** by whether the job gets done
5. **Evolve the codebase** as jobs change

```
User's Job → Technical Solution → Implementation → Validation
     ↑                                                    ↓
     └─────────────── Feedback Loop ────────────────────┘
```

---

## The Jobs To Be Done Framework

### Job Statement Structure

Every job follows this structure:

**When** [situation/circumstance]
**I want to** [motivation/goal]
**So I can** [expected outcome/benefit]

### Components Explained

1. **When (Circumstance)**
   - The triggering situation or context
   - Describes when this job arises
   - Can be time-based, event-based, or state-based
   - Examples:
     - "When onboarding a new team member"
     - "When production is down"
     - "When reviewing code at end of day"

2. **I want to (Motivation)**
   - The core action or change the user seeks
   - Describes what they're trying to accomplish
   - Should be technology-agnostic
   - Examples:
     - "I want to get them productive quickly"
     - "I want to identify the root cause fast"
     - "I want to understand changes without deep focus"

3. **So I can (Outcome)**
   - The ultimate benefit or value
   - Why accomplishing this matters
   - Often reveals deeper goals
   - Examples:
     - "so I can maintain team velocity"
     - "so I can restore service before users are impacted"
     - "so I can provide useful feedback despite being tired"

### Real-World Examples

#### Developer Tools

**Job:** API Development
```
When: integrating a third-party API for the first time
I want to: see real request/response examples immediately
So I can: start building without reading extensive documentation
```

**Job:** Debugging
```
When: investigating a production bug under time pressure
I want to: see what changed recently in related code
So I can: quickly narrow down the likely cause
```

#### SaaS Products

**Job:** Customer Support
```
When: a customer reports a confusing error
I want to: see their complete interaction history in one view
So I can: resolve their issue without asking them to repeat information
```

**Job:** Data Analysis
```
When: presenting findings to stakeholders in a meeting
I want to: update dashboards with fresh data in real-time
So I can: answer questions with current information
```

---

## Why Job-Driven Development?

### The Problem with Feature-Driven Development

Traditional feature-driven development focuses on **what** to build:
- ❌ "Build a notification system"
- ❌ "Add export to PDF"
- ❌ "Implement two-factor authentication"

This creates several problems:

1. **Over-engineering**: Features accumulate complexity without clear purpose
2. **Misalignment**: Building features users don't need
3. **Missing context**: Solutions don't fit actual usage patterns
4. **Poor prioritization**: All features seem equally important
5. **Maintenance burden**: Code exists without clear job it serves

### The Job-Driven Advantage

JDD focuses on **why** users need something:
- ✅ "When receiving urgent updates, I want to be notified immediately so I can respond quickly"
- ✅ "When sharing analysis externally, I want to export to familiar formats so I can maintain professional presentation"
- ✅ "When accessing sensitive data remotely, I want extra security so I can trust the platform"

This provides:

1. **Natural scope control**: Only build what serves a job
2. **Clear prioritization**: Jobs have measurable urgency and impact
3. **Better solutions**: Design fits actual user context
4. **Measurable outcomes**: Success = job gets done
5. **Evolution clarity**: Jobs change, revealing what to modify

### Comparison Table

| Aspect | Feature-Driven | Job-Driven |
|--------|---------------|------------|
| **Starting Point** | Product roadmap | User research |
| **Primary Question** | "What should we build?" | "What job needs doing?" |
| **Prioritization** | Business value estimates | Job urgency × frequency |
| **Success Metric** | Feature shipped | Job completed successfully |
| **Scope Management** | Feature creep | Job boundaries |
| **Technical Decisions** | Best practices | What enables job best |
| **User Validation** | Do they use it? | Does it accomplish their job? |
| **Maintenance** | Keep features working | Keep jobs getting done |

---

## Core Principles

### 1. Jobs Are the Source of Truth

The job definition is the authoritative description of what needs to be accomplished. All other artifacts (solutions, code, tests) derive from it.

**Implication**: When job and code diverge, update the code (or realize the job definition was wrong and update that).

### 2. Solutions Serve Jobs, Not Vice Versa

Technical solutions exist only to accomplish jobs. Elegant architecture that doesn't help users complete jobs is waste.

**Implication**: Ruthlessly cut technical complexity that doesn't directly enable job completion.

### 3. One Job, Multiple Solutions

Different user contexts may require different solutions for the same underlying job.

**Example**:
- Job: "Quickly review code changes"
- Desktop solution: IDE integration with diff viewer
- Mobile solution: Focused notification → approve/comment flow
- CLI solution: Terminal-based review with vim bindings

### 4. Jobs Reveal Priorities

Not all jobs are equally important. Prioritize by:
- **Frequency**: How often does this job arise?
- **Urgency**: What happens if the job doesn't get done?
- **Struggle**: How difficult is it currently?
- **Importance**: How critical to user's success?

### 5. Job Completion is Measurable

Every job has observable completion criteria:
- Time to complete job
- Success rate on first attempt
- User satisfaction with outcome
- Preference vs. alternatives

### 6. Jobs Evolve, Code Follows

As users' work changes, jobs evolve. This naturally drives refactoring priorities.

**Example**: If "searching code" becomes "asking questions about code" (AI shift), solutions must evolve.

---

## The JBTD Workflow

### Overview

```
1. Constitution    → Establish principles
2. Identify       → Define the job
3. Clarify        → Remove ambiguity (optional)
4. Solution       → Design technical approach
5. Analyze        → Validate alignment (optional)
6. Tasks          → Break down implementation
7. Implement      → Build the solution
```

### Phase 1: Constitution

**Goal**: Establish project principles that prevent over-engineering.

**Activities**:
- Define technical constraints
- Set complexity boundaries
- Establish quality gates
- Document architectural principles

**Example Principles**:
```markdown
- Maximum 3 backend services
- No frameworks heavier than React
- API responses < 200ms p95
- No feature without clear job
```

**Output**: `constitution.md`

### Phase 2: Identify (Job Definition)

**Goal**: Deeply understand the user's job.

**Activities**:
1. **Research the Job**
   - Interview users in context
   - Observe actual workflows
   - Understand current solutions (even non-software)
   - Identify job triggers and outcomes

2. **Define Job Statement**
   - When: Specific circumstance
   - I want to: Clear motivation
   - So I can: Ultimate benefit

3. **Map Job Scenarios**
   - Break into prioritized scenarios (P1, P2, P3)
   - Each scenario = independent deliverable
   - Define job completion criteria
   - Identify edge cases

4. **Document Context**
   - User types with this job
   - Frequency and urgency
   - Current solutions and pain points
   - Constraints and assumptions

**Output**: `jobs/###-job-name/job.md`

**Command**: `/jbtd.identify`

### Phase 3: Clarify (Optional)

**Goal**: De-risk ambiguity before designing solution.

**Use When**:
- Job context is unclear
- Multiple interpretations possible
- Assumptions need validation
- Edge cases are complex

**Activities**:
- Generate structured questions
- Identify assumptions to test
- Clarify success criteria
- Validate job boundaries

**Output**: `jobs/###-job-name/clarifications.md`

**Command**: `/jbtd.clarify`

### Phase 4: Solution Design

**Goal**: Create technical approach that accomplishes the job.

**Activities**:
1. **Map Job to Components**
   - Which job scenarios need which components?
   - How do components enable job completion?
   - What's the minimal set needed?

2. **Design with Job in Mind**
   - Data model that serves job
   - APIs that match job flow
   - UI that enables job steps
   - Performance that meets job timing

3. **Validate Against Constitution**
   - Does this respect complexity limits?
   - Are we over-engineering?
   - Can we simplify and still accomplish the job?

4. **Define Acceptance Criteria**
   - How will we know job is done?
   - What are observable success signals?
   - How to measure job completion?

**Output**: `jobs/###-job-name/solution.md`

**Command**: `/jbtd.solution`

### Phase 5: Analyze (Optional)

**Goal**: Validate solution truly serves job.

**Use When**:
- Complex solution with many components
- Multiple jobs share components
- Concerned about alignment
- Pre-implementation review

**Activities**:
- Cross-check solution against job scenarios
- Verify all job completion criteria are testable
- Check for over-engineering
- Identify gaps or conflicts

**Output**: `jobs/###-job-name/analysis.md`

**Command**: `/jbtd.analyze`

### Phase 6: Task Breakdown

**Goal**: Organize implementation by job scenario.

**Activities**:
1. **Group by Job Scenario**
   - P1 scenario tasks (MVP)
   - P2 scenario tasks
   - P3 scenario tasks

2. **Maintain Independence**
   - Each scenario can be implemented alone
   - Each delivers standalone value
   - Dependencies explicit

3. **Follow TDD**
   - Write tests that verify job completion
   - Tests before implementation
   - Tests as job completion proof

**Output**: `jobs/###-job-name/tasks.md`

**Command**: `/jbtd.tasks`

### Phase 7: Implementation

**Goal**: Build solution with AI assistance.

**Activities**:
- Work through tasks by scenario
- Implement with job context in mind
- Validate against job completion criteria
- Iterate based on job testing

**Output**: Working code that accomplishes the job

**Command**: `/jbtd.implement`

---

## Job Definition Template

### Structure

```markdown
# Job Definition: [JOB NAME]

## Job Statement
When [situation]
I want to [motivation]
So I can [outcome]

## User's Context

### Current Situation
[What user is doing now, pain points, alternatives]

### User Type(s)
[Who has this job]

### Frequency & Context
[How often, in what situations, time-sensitive?]

## Desired Outcomes

### Primary Outcomes (Must Have)
- O-001: [Measurable outcome]
- O-002: [Measurable outcome]

### Secondary Outcomes (Nice to Have)
- O-003: [Additional benefit]

## Job Scenarios & Testing

### Job Scenario 1 - [Title] (Priority: P1)
[Specific instance of the job]

**Why this priority**: [Explanation]
**Independent Test**: [How to verify job is done]

**Job Completion Criteria**:
1. When [trigger], User can [action], Achieving [outcome]

## Functional Requirements

### Must-Have Capabilities
- FR-001: Solution MUST [capability that enables job]

### Key Entities
- [Entity]: [Purpose in job context]

## Success Criteria

### Job Completion Metrics
- JC-001: [Job completion rate]
- JC-002: [Time metric]
- JC-003: [Satisfaction metric]

### Constraints
- Technical: [e.g., "Must work offline"]
- User: [e.g., "No installation required"]
- Business: [e.g., "Free tier must serve core job"]
```

---

## Solution Design

### Mapping Jobs to Architecture

Every technical decision should trace back to a job:

```markdown
## Job-Oriented Design

| Job Scenario | Solution Component | How It Accomplishes Job |
|--------------|-------------------|------------------------|
| [JS1: Quick review] | Diff viewer + AI summary | Shows changes and explains them in <5s |
| [JS2: Find related changes] | Git blame integration | Links to commits that touched same code |
```

### Solution Principles

1. **Minimal Viable Solution**
   - What's the simplest thing that accomplishes the job?
   - Can we do it without [complex component]?
   - Every component must serve a job scenario

2. **Job-Flow Alignment**
   - Does the solution match how users actually do the job?
   - Are we forcing users to adapt to our technical model?
   - Can users accomplish the job in their natural flow?

3. **Performance as Job Requirement**
   - Job timing determines performance requirements
   - "Quick review" might mean <5 seconds, not <100ms
   - Optimize for job completion, not micro-benchmarks

4. **Constraints from Jobs**
   - "Work remotely" → offline-capable
   - "While commuting" → mobile-friendly
   - "During incident" → extremely reliable

---

## Implementation Strategy

### Scenario-Driven Development

Implement one job scenario at a time:

**Phase 1: P1 Scenario (MVP)**
```
1. Implement minimal components for P1
2. Validate job completion
3. Ship and observe
```

**Phase 2: P2 Scenario**
```
1. Add only what P2 needs
2. Reuse P1 components where possible
3. Validate both scenarios still work
```

**Phase 3: P3 Scenario**
```
1. Extend for P3
2. Refactor if patterns emerge
3. Validate all scenarios
```

### Testing Strategy

**Test Job Completion, Not Implementation**

Traditional test:
```python
def test_user_repository_returns_user():
    user = UserRepository().get(id=1)
    assert user.name == "Alice"
```

Job-completion test:
```python
def test_user_can_review_pr_quickly():
    """Job: When reviewing PR, see changes in <5s"""
    start = time.time()

    # Simulate job flow
    pr = open_pull_request(id=123)
    diff = pr.get_diff()
    summary = pr.get_ai_summary()

    elapsed = time.time() - start

    # Job completion criteria
    assert elapsed < 5.0  # Time requirement
    assert diff.is_complete  # Can see all changes
    assert summary.is_helpful  # AI provides value
```

### Refactoring Driven by Jobs

Only refactor when:
1. **Job gets harder**: Current structure makes jobs difficult
2. **New job blocked**: Can't add job without refactor
3. **Job performance suffers**: Solution too slow for job timing
4. **Multiple jobs conflict**: Structure serves one job, breaks another

Don't refactor because:
- ❌ "Code is messy" (if job still gets done)
- ❌ "Better pattern exists" (if current one works)
- ❌ "Want to learn new framework" (not job-serving)

---

## Measuring Success

### Job Completion Metrics

**Primary Metrics**:
1. **Completion Rate**: % of attempts where job gets done
2. **Time to Complete**: How long the job takes
3. **First-Attempt Success**: % who succeed without retries
4. **User Satisfaction**: How users rate the experience

**Secondary Metrics**:
1. **Job Frequency**: How often job arises
2. **Alternative Usage**: Are users finding workarounds?
3. **Job Evolution**: Is the job changing?
4. **Hiring Rate**: Do users choose this solution?

### Example Measurement

**Job**: "When debugging, find root cause quickly"

```markdown
Success Criteria:
- JC-001: 90% of debugging sessions identify root cause
- JC-002: Average time to root cause < 15 minutes
- JC-003: 80% satisfaction rating ("helped find issue")

Measurement:
- Track: time from "bug reported" to "cause identified"
- Survey: "Did this help you find the issue?"
- Observe: Do they use it or skip to other tools?
```

### Validation Techniques

1. **Job Shadowing**
   - Watch users attempt the job
   - Observe without interfering
   - Note where they struggle
   - Measure completion time

2. **A/B Testing**
   - Job completion rate: old vs new solution
   - Time to complete: before/after
   - User preference: which do they choose?

3. **Instrumentation**
   - Log job start/complete events
   - Track drop-off points
   - Measure timing automatically
   - Count retries/errors

---

## Common Patterns

### Pattern 1: Progressive Job Disclosure

**Problem**: Complex job with many scenarios

**Solution**: Implement P1 first, validate, then add P2, P3

**Example**:
```
Job: Code Review
P1: See what changed (basic diff)
P2: Understand why (git history context)
P3: Suggest improvements (AI analysis)
```

Ship P1 → measure job completion → if successful, add P2

### Pattern 2: Job Substitution

**Problem**: Original job becomes obsolete

**Solution**: Identify new job, keep solution if it still serves

**Example**:
```
Original: "Search codebase for function definition"
New: "Ask where this function is defined"
Solution: Search still works, but add chat interface
```

### Pattern 3: Job Composition

**Problem**: Users have sequence of related jobs

**Solution**: Enable job flow, don't force into single mega-job

**Example**:
```
Job 1: Find suspicious code
Job 2: Understand what it does
Job 3: Determine if it's a bug

Don't combine into "find and fix bugs"
Instead: Enable smooth flow between jobs
```

### Pattern 4: Context-Dependent Jobs

**Problem**: Same job, different contexts need different solutions

**Solution**: Design adaptive solution or context-specific paths

**Example**:
```
Job: "Review code changes"
Context 1: At desk, IDE open → Deep diff in IDE
Context 2: On phone, between meetings → Quick summary + approve/reject
Context 3: Offline, on plane → Downloaded state, sync later
```

---

## Anti-Patterns to Avoid

### Anti-Pattern 1: Fake Jobs

**Problem**: Defining features as jobs

❌ "When I want to export data, I want an export button"
✅ "When sharing analysis with stakeholders, I want to send them data in their preferred format so they can make decisions"

**Why it's bad**: "Export button" is a feature, not a job. True job reveals **why** they need export, which might suggest better solutions.

### Anti-Pattern 2: Solution-Oriented Jobs

**Problem**: Embedding solution in job definition

❌ "When managing tasks, I want a Kanban board"
✅ "When prioritizing work, I want to see what's urgent and what's blocked so I can work on what matters most"

**Why it's bad**: Kanban is one solution. Job definition should be solution-agnostic.

### Anti-Pattern 3: Over-Generic Jobs

**Problem**: Job too broad to guide design

❌ "When using the app, I want it to be fast"
✅ "When loading my dashboard in the morning, I want to see today's metrics in <2 seconds so I can start work immediately"

**Why it's bad**: Generic jobs don't provide design constraints or measurable criteria.

### Anti-Pattern 4: Ignoring Job Context

**Problem**: Designing solution without understanding circumstance

**Example**: Building collaboration feature assuming users are always online, when job often happens "while commuting on subway with spotty connection"

**Why it's bad**: Solution won't work in actual job context.

### Anti-Pattern 5: Job Creep

**Problem**: Adding features not tied to any job

❌ "Users might want to customize colors, add that to backlog"
✅ "What job requires customization? If none, don't build it"

**Why it's bad**: Features accumulate without purpose, increasing maintenance burden.

### Anti-Pattern 6: Premature Generalization

**Problem**: Building flexible system before understanding jobs

**Example**: Creating plugin architecture before shipping for even one job

**Why it's bad**: You don't know what needs to be flexible until you solve actual jobs.

---

## Case Studies

### Case Study 1: GitHub Pull Requests

**Job Analysis**:
```
When: Code review needs to happen
I want to: See changes and discuss them
So I can: Ensure quality before merging
```

**Job Scenarios**:
- P1: See what changed (diff view)
- P2: Discuss specific lines (inline comments)
- P3: Approve or request changes (review state)
- P4: Track conversation over time (discussion threads)

**Job-Driven Decisions**:
- Diff view optimized for readability (job: quickly understand changes)
- Inline comments (job: discuss without losing context)
- Review state machine (job: track approval progress)
- Email notifications (job: stay updated async)

**What They Didn't Build** (no clear job):
- Video chat in PR (can use separate tool)
- Advanced text editor (job is review, not editing)
- Project management (separate job, separate tool)

### Case Study 2: Stripe API Documentation

**Job Analysis**:
```
When: Integrating payments for first time
I want to: Go from zero to working code quickly
So I can: Launch and start accepting money
```

**Job-Driven Decisions**:
- Examples first, API reference second (job: get working code)
- Copy-paste ready snippets (job: minimize time to working)
- Test keys built in (job: try without commitment)
- Clear success states (job: know when it's working)

**Impact**:
- Reduced time-to-first-payment
- Higher integration completion rate
- Less support load (job accomplished independently)

### Case Study 3: Slack Threads

**Original Job**:
```
When: Multiple conversations happening in same channel
I want to: Keep different topics separate
So I can: Follow conversations without confusion
```

**Solution**: Threads

**New Job** (emerged later):
```
When: Important announcement in busy channel
I want to: Make sure everyone sees it
So I can: Ensure critical info reaches team
```

**Job Conflict**: Threads reduce noise (job 1) but hide important info (job 2)

**Resolution**: Pin messages, thread summaries, notification settings

**Lesson**: Jobs evolve and sometimes conflict. Design must adapt.

---

## Conclusion

Job-Driven Development is about **starting with why**. By making the user's job the source of truth, you:

- Build less (only what serves jobs)
- Build better (solutions fit actual context)
- Measure clearly (job completion)
- Evolve naturally (jobs change, code follows)

The JBTD Kit provides tools to make this methodology practical:
- Templates for defining jobs
- Commands for AI-assisted implementation
- Structure for organizing by job scenario
- Validation through job completion criteria

**Remember**: Users don't want your software. They want their job done. Give them that.

---

## Further Reading

- **Books**:
  - "Competing Against Luck" by Clayton Christensen (JTBD theory)
  - "The Mom Test" by Rob Fitzpatrick (Job discovery through interviews)
  - "Demand-Side Sales" by Bob Moesta (Jobs in sales context)

- **Resources**:
  - [Jobs To Be Done Playbook](https://jtbd.info)
  - [Intercom on Jobs To Be Done](https://www.intercom.com/books/jobs-to-be-done)

- **JBTD Kit Docs**:
  - [README.md](README.md) - Quick start and overview
  - [AGENTS.md](AGENTS.md) - AI agent integration
  - [docs/quickstart.md](docs/quickstart.md) - Step-by-step tutorial

---

**Start with the job. Build with purpose.** 🎯
