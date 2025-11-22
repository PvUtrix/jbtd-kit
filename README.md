# JBTD Kit

**Job-Driven Development for Software Teams**

> Build software that solves real user jobs, not just features.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## What is JBTD Kit?

JBTD Kit is an open-source toolkit for implementing **Job-Driven Development (JDD)** - a methodology that puts the user's job-to-be-done at the center of software development. Instead of starting with technical specifications, you start with understanding what job the user is trying to accomplish.

### The Core Philosophy

**Jobs are executable.** Your job definitions become the primary artifact that:
- Generates technical solutions
- Creates implementation code through AI agents
- Drives testing and validation
- Remains the source of truth throughout the project lifecycle

### Why Job-Driven Development?

Traditional development often focuses on *what* to build (features, specs) without deeply understanding *why* users need it. JBTD Kit flips this:

1. **Start with the Job**: Understand the user's situation, motivation, and desired outcome
2. **Design the Solution**: Create a technical approach that accomplishes the job
3. **Implement with Purpose**: Every line of code serves the user's job
4. **Validate Job Completion**: Measure success by whether the job gets done

## Quick Start

### Installation

```bash
# Using uvx (recommended)
uvx --from job-cli job init my-project

# Or install globally with uv
uv tool install job-cli
job init my-project
```

### Your First Job

```bash
# Initialize a new JBTD project
job init my-first-job --ai claude

# Navigate to the project
cd my-first-job

# Start the JDD workflow
# 1. Define the user's job
/jbtd.identify

# 2. Create a technical solution
/jbtd.solution

# 3. Break down into tasks
/jbtd.tasks

# 4. Implement the solution
/jbtd.implement
```

## The JBTD Workflow

JBTD Kit provides a structured 7-phase workflow:

### 1. **Constitution** (`/jbtd.constitution`)
Establish project principles and constraints to prevent over-engineering.

### 2. **Identify** (`/jbtd.identify`)
Define the user's job-to-be-done:
- **When** [situation]: What triggers this job?
- **I want to** [motivation]: What does the user want to accomplish?
- **So I can** [outcome]: What benefit do they seek?

**Example**:
> **When** I'm reviewing pull requests on GitHub
> **I want to** quickly understand code changes in context
> **So I can** provide meaningful feedback without context switching

### 3. **Clarify** (`/jbtd.clarify`) *(optional)*
Ask structured questions to de-risk ambiguous areas before designing the solution.

### 4. **Solution** (`/jbtd.solution`)
Create a technical approach that accomplishes the user's job:
- Map job scenarios to system components
- Design with job completion in mind
- Keep it simple - only build what serves the job

### 5. **Analyze** (`/jbtd.analyze`) *(optional)*
Validate that your solution truly serves the job and maintains consistency.

### 6. **Tasks** (`/jbtd.tasks`)
Break down the solution into actionable implementation tasks, organized by job scenario.

### 7. **Implement** (`/jbtd.implement`)
Build the solution with AI assistance, ensuring every component serves the user's job.

## Project Structure

```
my-project/
├── .jbtd/                    # JBTD Kit configuration
│   ├── commands/             # AI agent commands
│   ├── scripts/              # Automation scripts (bash/PowerShell)
│   └── templates/            # Job and solution templates
├── jobs/                     # Your job definitions
│   └── 001-quick-pr-review/
│       ├── job.md            # Job definition
│       ├── solution.md       # Technical solution
│       ├── tasks.md          # Implementation tasks
│       └── research.md       # Technical research
└── src/                      # Your source code
```

## Key Concepts

### Jobs vs Features

| Traditional (Feature-Driven) | JBTD Kit (Job-Driven) |
|----------------------------|---------------------|
| "Add authentication" | "When signing up, I want to create an account securely so I can trust the platform" |
| "Build a dashboard" | "When monitoring my app, I want to see key metrics at a glance so I can spot issues quickly" |
| "Implement search" | "When looking for past work, I want to find it instantly so I can continue where I left off" |

### Job Scenarios

Jobs are broken into **prioritized scenarios** (P1, P2, P3), where each scenario:
- Can be implemented independently
- Delivers standalone value
- Has clear job completion criteria
- Enables incremental delivery

### Solution Alignment

Every technical decision maps back to the user's job:
- **Why this architecture?** → Enables job completion in <1 second
- **Why this framework?** → Matches where users already work
- **Why this feature?** → Directly accomplishes job scenario #2

## AI Agent Support

JBTD Kit works with 14+ AI coding assistants:

| Agent | Status | CLI Required |
|-------|--------|--------------|
| [Claude Code](https://docs.anthropic.com/en/docs/claude-code/setup) | ✅ Full Support | Yes |
| [GitHub Copilot](https://github.com/features/copilot) | ✅ Full Support | No (IDE) |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | ✅ Full Support | Yes |
| [Cursor](https://cursor.sh) | ✅ Full Support | No (IDE) |
| [Windsurf](https://codeium.com/windsurf) | ✅ Full Support | No (IDE) |
| Plus 9+ more... | See `job check` | Varies |

Run `job check` to see which agents are available on your system.

## Examples

### Example 1: Developer Tool

**Job**:
> When debugging production issues, I want to see logs and metrics together so I can identify root causes faster

**Solution Approach**:
- Unified log + metrics viewer
- Time-correlation between events
- Quick filters for common patterns

**Key Insight**: Traditional approach might build separate log viewer + separate metrics dashboard. Job-driven approach combines them because the *job* is "identify root cause" not "view logs" or "view metrics".

### Example 2: User Onboarding

**Job**:
> When starting with a new tool, I want to accomplish my first real task quickly so I can see value before investing time in learning

**Solution Approach**:
- Skip lengthy tutorials
- Guide through one complete job scenario
- Provide templates for common jobs

**Key Insight**: The job isn't "learn the tool" - it's "accomplish something valuable". Job-driven design focuses on success, not features.

## Philosophy

### Jobs Are Executable

JBTD Kit treats job definitions as the source of truth:

```
Job Definition (job.md)
    ↓
Technical Solution (solution.md)
    ↓
Implementation Tasks (tasks.md)
    ↓
Working Code (via AI agents)
```

Changes flow from job → solution → code, ensuring alignment.

### Simplicity Through Purpose

Job-driven development naturally fights over-engineering:
- **Does this serve a job?** → Keep it
- **Nice to have but no clear job?** → Skip it
- **Adds complexity without job benefit?** → Remove it

### Measurable Success

Success isn't "feature shipped" - it's "job accomplished":
- 95% job completion rate
- <1 minute to complete job
- Users prefer this over alternatives

## Commands Reference

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `job init` | Create new JBTD project | Starting a new project |
| `job check` | Verify AI agents installed | Setup validation |
| `/jbtd.constitution` | Set project principles | Start of project |
| `/jbtd.identify` | Define user's job | For each new job |
| `/jbtd.clarify` | Ask clarifying questions | When job is ambiguous |
| `/jbtd.solution` | Design technical solution | After job definition |
| `/jbtd.analyze` | Validate alignment | Before implementation |
| `/jbtd.tasks` | Break down implementation | After solution design |
| `/jbtd.implement` | Build the solution | Ready to code |
| `/jbtd.checklist` | Generate quality checks | Quality validation |

## Documentation

- **[JBTD Methodology](jbtd-driven.md)**: Deep dive into Job-Driven Development
- **[Installation Guide](docs/installation.md)**: Detailed setup instructions
- **[Quick Start Guide](docs/quickstart.md)**: Step-by-step tutorial
- **[Agent Integration](AGENTS.md)**: Adding new AI agent support
- **[Contributing](CONTRIBUTING.md)**: How to contribute to JBTD Kit

## Comparison to Spec-Driven Development

JBTD Kit is inspired by Spec-Driven Development but focuses on **jobs** instead of **specifications**:

| Aspect | Spec-Driven | Job-Driven |
|--------|-------------|------------|
| Primary artifact | Feature specification | User's job-to-be-done |
| Starting point | What to build | Why users need it |
| Success metric | Spec implemented correctly | Job gets done successfully |
| Focus | Technical requirements | User outcomes |
| Validation | Matches specification | Accomplishes job |

Both share the philosophy of making the primary artifact executable through AI agents.

## Real-World Use Cases

### Startup MVP
- Define core user jobs (P1 only)
- Build minimal solution that accomplishes those jobs
- Skip features that don't serve core jobs
- Launch faster with purpose-driven scope

### Enterprise Feature
- Understand diverse user jobs across teams
- Prioritize job scenarios by business impact
- Design scalable solution aligned with jobs
- Measure adoption by job completion rates

### Developer Tooling
- Identify friction in existing workflows (the job)
- Build solutions that fit into current jobs
- Validate by whether developers "hire" your tool for the job

## FAQ

**Q: Is this just user stories with a different name?**
A: No. User stories describe features ("As a user, I want to..."). Jobs describe the underlying need and context ("When [situation], I want to [motivation], so I can [outcome]"). Jobs are deeper and more focused on the user's world.

**Q: Can I use this with existing projects?**
A: Yes! Run `job init --here` in an existing project to add JBTD Kit. Identify jobs for new features or refactoring efforts.

**Q: Do I need to use all 7 phases?**
A: No. The core flow is Constitution → Identify → Solution → Tasks → Implement. Clarify, Analyze, and Checklist are optional quality enhancements.

**Q: How does this work with Agile/Scrum?**
A: JBTD Kit complements Agile. User jobs inform story prioritization. Job scenarios become sprint goals. Job completion metrics track progress.

**Q: What if a feature serves multiple jobs?**
A: Great question! Either: (1) Split it into separate job definitions if jobs are independent, or (2) Document all jobs in one definition if they're tightly coupled. Prioritize by which job has highest impact.

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- Adding new AI agent support
- Improving templates and commands
- Sharing job definition patterns
- Documentation improvements

## License

MIT License - see [LICENSE](LICENSE) for details.

## Community

- **Issues**: [GitHub Issues](https://github.com/PvUtrix/jbtd-kit/issues)
- **Discussions**: [GitHub Discussions](https://github.com/PvUtrix/jbtd-kit/discussions)

## Acknowledgments

JBTD Kit is inspired by:
- **Jobs To Be Done** theory by Clayton Christensen
- **Spec-Driven Development** and the original Spec Kit
- The AI-assisted development community

---

**Start with the job. Build with purpose.** 🎯
