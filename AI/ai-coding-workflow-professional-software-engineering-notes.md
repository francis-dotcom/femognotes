# Professional Software Engineering Notes
## Full Walkthrough: Workflow for AI Coding — Matt Pocock

## 1. Central Thesis

AI-assisted software development is not a replacement for software engineering fundamentals.

The same principles that help engineers collaborate effectively with other humans also improve the quality of work produced by AI coding agents:

- Clear requirements
- Small, bounded tasks
- Strong architecture
- Fast feedback loops
- Testable modules
- Explicit dependencies
- Human review
- Incremental delivery
- Well-defined acceptance criteria

The quality of AI-generated software is heavily constrained by the quality of the engineering environment in which the AI operates.

> Bad codebases, weak requirements, poor tests, and unclear architecture produce poor AI output.

---

# 2. Important Constraints of Large Language Models

## 2.1 The Smart Zone and Dumb Zone

An LLM performs best near the beginning of a fresh context window.

As more information is added to the conversation, the model must process more relationships between tokens. Over time, its reasoning and decision quality can deteriorate.

The presenter describes two operating regions:

### Smart Zone

The portion of the context window where the AI:

- Follows instructions reliably
- Understands dependencies
- Makes better architectural decisions
- Produces more coherent code
- Retains the current objective
- Reviews information accurately

### Dumb Zone

The portion where the AI begins to:

- Forget earlier requirements
- Contradict previous decisions
- Make careless changes
- Duplicate functionality
- Misunderstand architecture
- Produce increasingly unreliable code
- Lose track of the original task

A larger advertised context window does not necessarily mean the entire context window provides equally strong reasoning.

Large context windows may be useful for retrieval, but coding tasks should still be kept relatively small and focused.

## Engineering implication

Do not assign an entire large feature to one long-running conversation.

Instead:

1. Break the feature into smaller tasks.
2. Give each task a fresh context.
3. Complete and validate one bounded unit of work.
4. Clear the context before beginning a new implementation or review task.

---

## 2.2 LLMs Behave Like They Have Temporary Memory

Every AI coding session normally follows a pattern:

1. System instructions are loaded.
2. The agent explores the repository.
3. The agent develops an implementation.
4. The agent runs tests and other feedback loops.
5. The context is cleared or compressed.

Once the context is cleared, the AI loses most of the working understanding it developed during that session.

Therefore, important decisions must be stored outside the conversation.

Examples of persistent engineering artifacts include:

- Product requirements documents
- Architecture decision records
- GitHub issues
- Local Markdown issue files
- Tests
- Interface definitions
- Database schemas
- Commit history
- Code comments where appropriate

The codebase and its associated documentation must function as the AI agent’s long-term memory.

---

# 3. Keep the Permanent System Prompt Small

Permanent agent instructions should be concise.

A very large global instruction file consumes context before the agent begins useful work. It may push the agent closer to the degraded reasoning zone.

The permanent instructions should contain only stable, repository-wide rules such as:

- Core commands
- Coding conventions
- Important architectural boundaries
- Testing requirements
- Security restrictions
- Definition-of-done expectations

Task-specific details should be supplied through task files, issues, or focused prompts rather than permanently loaded instructions.

---

# 4. Context Clearing Versus Compaction

## Compaction

Compaction summarizes the existing conversation and carries the summary into the next phase.

Potential benefits:

- Preserves some previous decisions
- Reduces token usage
- Allows a conversation to continue

Potential problems:

- Important details may be lost
- Incorrect assumptions may become part of the summary
- Repeated compaction creates layers of summarized “sediment”
- The model may continue operating from a distorted representation of previous work

## Clearing

Clearing starts the agent again from its stable base instructions.

Advantages:

- Predictable starting state
- Clean context
- Better reasoning capacity
- Reduced accumulation of irrelevant information
- Easier debugging of agent behavior

## Recommended practice

Prefer a workflow where each task can begin from a clean context.

This requires the project state to be recoverable from:

- The repository
- The issue description
- The tests
- Recent commits
- Supporting design documents

---

# 5. End-to-End AI Coding Workflow

The proposed workflow is:

```text
Idea
  ↓
Requirements interrogation
  ↓
Research or prototype when necessary
  ↓
Product Requirements Document
  ↓
Dependency-aware issue backlog
  ↓
Small vertical implementation tasks
  ↓
Automated tests and feedback loops
  ↓
Fresh-context automated review
  ↓
Human code review and QA
  ↓
Merge and deployment
```

The workflow separates activities requiring human judgment from activities that can be delegated to an AI agent.

---

# 6. Stage One: Begin With an Idea or Client Brief

A feature usually begins with an incomplete request.

Example:

> Student retention is low. Add gamification to the course platform.

This request is not ready for implementation.

It does not specify:

- Which actions earn points
- How many points are awarded
- Whether historical activity is backfilled
- Whether streaks affect points
- How levels are calculated
- Where progress is displayed
- How abuse or gaming is prevented
- What happens when data is corrected
- How the feature is tested
- What is explicitly out of scope

Immediately asking the AI to implement this request would cause it to invent important product decisions.

---

# 7. Stage Two: Requirements Interrogation

The presenter uses a “Grill Me” approach.

The AI interviews the user aggressively, one question at a time, until both parties share a clear understanding of the feature.

A simplified instruction is:

```text
Interview me relentlessly about this feature until we reach a shared
understanding.

Walk through each branch of the decision tree and resolve dependencies
one by one.

Ask one question at a time.

For every question, include your recommended answer and explain why.
```

## Purpose

The objective is not merely to produce a plan.

The objective is to establish a shared design concept between:

- The engineer
- The product owner or domain expert
- The AI agent
- Other relevant team members

## Useful questions

For a gamification feature, the agent might ask:

- Which user actions earn points?
- Are video-watch events included?
- Can users repeatedly trigger an event?
- Should existing users receive historical points?
- What is the progression curve?
- Are streaks independent from points?
- Where does the UI appear?
- What happens when a lesson completion is reversed?
- Are administrators allowed to manually adjust points?
- What data must be auditable?
- What privacy or security restrictions apply?

## Why recommendations matter

The AI should not only ask questions. It should propose a recommended answer.

This makes the process faster because the human can:

- Approve the recommendation
- Reject it
- Modify it
- Ask for alternatives

## Human-in-the-loop requirement

Requirements alignment is not an appropriate AFK task.

Humans must remain involved because the decisions depend on:

- Business intent
- Product taste
- Risk tolerance
- User expectations
- Domain knowledge
- Legal and security considerations
- Organizational priorities

The AI can identify missing questions, but humans remain accountable for the answers.

---

# 8. Use Domain Experts During Interrogation

The requirements session does not need to involve only one engineer.

It can include:

- Product managers
- Designers
- Security engineers
- Backend engineers
- Frontend engineers
- Legal or compliance specialists
- Customers
- Operational staff
- Subject-matter experts

Meeting transcripts, customer interviews, tickets, and existing documentation can be supplied to the AI before the interrogation begins.

The AI can then identify:

- Contradictions
- Missing assumptions
- Ambiguous terminology
- Unresolved dependencies
- Edge cases
- Decisions that require escalation

This turns the AI into a structured facilitator rather than an autonomous product decision-maker.

---

# 9. Research and Prototypes

Not every uncertainty should be resolved through discussion.

Some questions require evidence.

Examples:

- Can a third-party API support the required volume?
- Does a particular browser API work reliably?
- Can the existing database support the query pattern?
- Will a proposed UI interaction be understandable?
- Does the architecture meet latency requirements?
- Can the feature be built without changing a critical subsystem?

In these situations, perform:

- Technical research
- Proofs of concept
- Spikes
- Throwaway prototypes
- Benchmarking
- User testing

The findings should be fed back into the requirements discussion.

---

# 10. Frontend Prototyping

Frontend work is especially dependent on human visual judgment.

AI can generate UI code, but it may struggle to evaluate:

- Visual hierarchy
- Spacing
- Responsiveness
- Usability
- Accessibility
- Brand consistency
- Interaction quality
- Overall taste

A practical workflow is:

1. Ask the agent to generate several alternative prototypes.
2. Place them behind throwaway routes or feature flags.
3. Allow users or designers to compare them.
4. Select one direction.
5. Capture the selected design decisions.
6. Convert those decisions into implementation requirements.

The prototype is a feedback mechanism, not necessarily production code.

---

# 11. Stage Three: Create a Product Requirements Document

After requirements alignment, convert the conversation into a persistent destination document.

The PRD describes where the team is going.

It should not be treated as a magical replacement for understanding the codebase. The architecture and implementation still matter.

## Recommended PRD structure

### 1. Problem statement

- Who has the problem?
- What is happening today?
- Why is the current situation inadequate?
- What measurable outcome should improve?

### 2. Proposed solution

- What capability will be introduced?
- How will users interact with it?
- What is the intended behavior?

### 3. User stories

Example:

```text
As a student,
I want to receive points when I complete a lesson,
so that I can see progress and remain motivated.
```

### 4. Acceptance criteria

Example:

```text
Given an authenticated student
And an incomplete lesson
When the student completes the lesson
Then the configured number of points is awarded once
And the new total is visible on the dashboard
And a duplicate completion does not award additional points
```

### 5. Implementation decisions

Record decisions such as:

- Storage model
- Event model
- Service ownership
- API boundaries
- Idempotency rules
- Backfill approach
- Error-handling strategy
- Feature-flag behavior

### 6. Testing decisions

Specify:

- Unit tests
- Integration tests
- End-to-end tests
- Migration tests
- Permission tests
- Failure cases
- Performance tests where required

### 7. Out-of-scope items

This section records negative decisions.

Examples:

- Video watch duration will not earn points.
- Social leaderboards are excluded from version one.
- Manual point trading is not supported.
- Existing users will not receive retroactive points.

Out-of-scope decisions are important because they protect the definition of done and prevent uncontrolled scope expansion.

### 8. Proposed modules affected

Identify likely architectural areas:

- Database schema
- Domain service
- API endpoint
- Event handler
- Dashboard component
- Background worker
- Analytics pipeline

---

# 12. Destination Document Versus Journey Document

The workflow distinguishes two artifacts.

## Destination document

The PRD defines:

- What the completed feature should do
- Who it serves
- Required behavior
- Acceptance criteria
- Important constraints
- Definition of done

## Journey document

The issue backlog defines:

- How the work is divided
- Which task comes first
- Which tasks depend on others
- Which tasks can run in parallel
- Which tasks require human involvement
- Which tasks can be performed by an autonomous agent

Both artifacts are necessary.

A PRD without a well-designed implementation journey may lead to an oversized, unmanageable AI task.

---

# 13. Stage Four: Convert the PRD Into a Kanban Backlog

Instead of producing only a linear multi-phase plan, convert the PRD into independently assignable issues.

Each issue should contain:

- Goal
- Context
- Scope
- Dependencies
- Acceptance criteria
- Relevant modules
- Required tests
- Completion signals
- Whether the task is human-in-the-loop or AFK

## Why a Kanban backlog is preferable

A sequential plan assumes:

```text
Phase 1 → Phase 2 → Phase 3 → Phase 4
```

This generally permits only one agent to work through the plan.

A dependency-aware backlog can form a directed acyclic graph:

```text
Task A
  ├── Task B
  └── Task C
       └── Task D
```

After Task A is completed, Tasks B and C may be executed in parallel.

This makes the work:

- Easier to schedule
- Easier to review
- Easier to retry
- Easier to parallelize
- Less likely to exceed the agent’s reasoning capacity

---

# 14. Vertical Slices and Tracer Bullets

AI agents often divide work horizontally by technical layer:

```text
Phase 1: Build all database changes
Phase 2: Build all backend services
Phase 3: Build all APIs
Phase 4: Build all frontend components
```

This is risky because the complete system is not validated until the later phases.

## Better approach: vertical slices

A vertical slice delivers a thin but complete path through the system.

Example:

```text
Award points for one lesson-completion event and display the updated
total on the student dashboard.
```

This slice may include:

- A minimal database migration
- A domain service method
- An API or event integration
- A basic UI representation
- Tests covering the entire flow

## Benefits

At the end of the slice:

- The system has observable behavior.
- Integration between layers has been tested.
- The team can inspect the result.
- Architectural problems appear earlier.
- Later slices can extend a working foundation.

## Tracer bullet concept

A tracer bullet provides immediate feedback about whether the implementation is moving in the correct direction.

The goal is not to build every layer completely. The goal is to create one thin, visible, testable route through all required layers.

---

# 15. Issue Design Guidelines

A strong AI-ready issue should be:

## Small

It should fit within one focused context window.

## Independent

The agent should not need undocumented information from another unfinished task.

## Testable

There must be an objective way to determine whether the task works.

## Reviewable

The resulting change should be understandable as one coherent unit.

## Dependency-aware

The issue should identify what must already exist.

## Outcome-oriented

The issue should describe user-visible or system-observable behavior rather than only internal files to create.

## Explicitly scoped

It should describe what is not included.

## Reproducible from a fresh context

A new agent should be able to understand the task from:

- The issue
- The repository
- Tests
- Relevant documentation
- Recent commits

---

# 16. Human-in-the-Loop Versus AFK Tasks

## Human-in-the-loop tasks

These require judgment, taste, or accountability.

Examples:

- Requirement clarification
- Product decisions
- Architecture selection
- Security-risk acceptance
- Prototype evaluation
- UI and UX decisions
- Scope prioritization
- Final QA
- Code review
- Deployment approval

## AFK tasks

These can often be delegated after requirements are sufficiently precise.

Examples:

- Implementing a bounded issue
- Writing a database migration
- Adding tests
- Refactoring a well-tested module
- Running static analysis
- Fixing deterministic type errors
- Updating generated files
- Performing repetitive mechanical changes

The goal is not to remove humans from software development.

The goal is to concentrate human attention on decisions where human judgment adds the most value.

---

# 17. The Day-Shift and Night-Shift Model

The presenter describes a useful operating model.

## Human day shift

Humans:

- Define the problem
- Interrogate assumptions
- Research uncertainty
- Prototype alternatives
- Write the PRD
- Design vertical slices
- Establish dependencies
- Define tests and acceptance criteria

## AI night shift

Agents:

- Select eligible AFK issues
- Explore the relevant repository areas
- Implement the selected task
- Write and run tests
- Run type checking and linting
- Commit the change
- Update task status
- Continue to the next unblocked task

The quality of the night shift depends on the preparation completed during the day shift.

---

# 18. The Ralph-Style Implementation Loop

A basic autonomous implementation loop can work as follows:

```text
1. Load the current backlog.
2. Load recent commits.
3. Identify incomplete AFK tasks.
4. Select the highest-priority unblocked task.
5. Explore the relevant code.
6. Implement the task using TDD.
7. Run tests and quality checks.
8. Commit the completed change.
9. Mark or update the issue.
10. Clear the context.
11. Repeat.
```

The agent should stop when:

- No unblocked AFK tasks remain
- Tests cannot be made to pass safely
- Requirements are ambiguous
- A human decision is required
- A security restriction prevents continuation
- The requested change exceeds the task scope

---

# 19. Start With a Single Controlled Run

Do not immediately launch an unattended implementation loop across an important repository.

First run the agent once while observing it.

Inspect:

- Which issue it selects
- How it explores the repository
- Whether it respects scope
- Whether it writes tests first
- Which commands it executes
- Whether it changes unrelated files
- Whether it commits meaningful work
- Whether its completion summary is accurate

Tune the prompt and task structure based on observed failure modes.

Only move toward unattended execution after the behavior is sufficiently predictable.

---

# 20. Sandbox Autonomous Agents

An unattended coding agent has permission to execute commands and modify files.

This creates significant risk.

Potential risks include:

- Deleting files
- Modifying host configuration
- Reading secrets
- Exposing credentials
- Running destructive migrations
- Installing unsafe dependencies
- Sending network requests
- Changing unrelated repositories
- Consuming excessive resources

Run autonomous agents inside an isolated environment such as:

- A Docker container
- An ephemeral virtual machine
- A restricted CI runner
- A disposable development environment
- A tightly permissioned sandbox

Apply least privilege:

- Mount only the required repository.
- Do not expose production credentials.
- Restrict network access where possible.
- Use temporary test databases.
- Limit filesystem access.
- Limit CPU and memory.
- Preserve logs.
- Require human approval for deployment.

---

# 21. Test-Driven Development Is Especially Valuable for AI

The recommended workflow uses red-green-refactor.

## Red

The agent writes one meaningful failing test.

The failure confirms that the desired behavior does not currently exist.

## Green

The agent writes the minimum implementation needed to pass the test.

## Refactor

The agent improves the implementation while keeping the tests passing.

## Why TDD helps agents

Without test-first development, an agent may:

- Build the entire implementation first
- Write tests afterward
- Create tests that mirror its implementation
- Mock away important behavior
- Produce tests that pass without validating the requirement
- Modify tests to conceal defects

Writing the failing test first creates an external constraint before implementation.

It gives the agent a precise feedback signal and makes it more difficult to “cheat.”

---

# 22. Test Behavior, Not Implementation Details

Poor AI-generated tests often wrap every small function in its own test.

This creates:

- Excessive mocking
- Brittle tests
- Tight coupling to implementation
- Low confidence in end-to-end behavior
- False positives

Prefer testing meaningful module behavior through stable interfaces.

Good test boundaries answer questions such as:

- Does completing a lesson award points exactly once?
- Is the updated total returned to the dashboard?
- Is the operation idempotent?
- Does an unauthorized user receive an error?
- Does a failed database write leave the system consistent?

Avoid tests whose main purpose is to confirm that an internal helper was called.

---

# 23. Feedback Loops Define the Agent’s Quality Ceiling

An AI agent cannot reliably improve code if it cannot observe whether the code works.

Useful feedback loops include:

- Unit tests
- Integration tests
- End-to-end tests
- Type checking
- Linting
- Formatting
- Build validation
- Database migration checks
- Security scans
- Contract tests
- Performance benchmarks
- Browser automation
- Runtime logs

The quality of the feedback loops places an upper bound on the quality of autonomous implementation.

When an agent repeatedly produces bad code, do not only modify the prompt.

Also investigate:

- Are the tests meaningful?
- Are important flows untested?
- Are errors easy to reproduce?
- Are commands deterministic?
- Is the architecture testable?
- Are interfaces stable?
- Are acceptance criteria executable?

---

# 24. Review in a Fresh Context

The same agent that implemented a change should not perform the only review within the same long context.

By the time implementation finishes, that context may contain:

- Large amounts of exploratory information
- Failed approaches
- Generated code
- Test output
- Repeated corrections
- Unverified assumptions

The reviewer may therefore operate in the degraded reasoning zone and inherit the implementer’s biases.

## Better approach

1. Complete the implementation.
2. Save it as a commit or branch.
3. Clear the context.
4. Start a fresh reviewer agent.
5. Give the reviewer:
   - The issue
   - The PRD section
   - The code diff
   - Test results
   - Relevant architecture rules
6. Ask the reviewer to identify defects and requirement gaps.
7. Apply corrections.
8. Run human review and QA.

The fresh reviewer should attempt to disprove that the implementation is correct rather than merely summarize it.

---

# 25. Human Code Review Remains Necessary

AI can review code, but human review remains necessary for:

- Product correctness
- Architectural coherence
- Security implications
- Maintainability
- Naming quality
- Domain correctness
- User experience
- Operational risk
- Data migration safety
- Business-rule accuracy

As AI produces more code, engineers may spend more time reviewing code.

This changes the engineering role from primarily typing implementations to:

- Designing systems
- Defining constraints
- Reviewing changes
- Testing behavior
- Managing risk
- Maintaining architectural quality

---

# 26. Manual QA Preserves Engineering Taste

Automating every stage can produce software that technically passes tests but lacks quality.

Human QA is where engineers and designers impose:

- Product judgment
- Visual taste
- Usability expectations
- Consistency
- Appropriate error messages
- Sensible workflows
- Real-world domain understanding

During QA, verify:

- Does the feature actually solve the user’s problem?
- Does it behave naturally?
- Are errors understandable?
- Are loading and empty states acceptable?
- Does the feature work with realistic data?
- Are accessibility requirements met?
- Is the feature consistent with the rest of the product?

Passing tests is necessary but not sufficient.

---

# 27. Architecture for AI-Editable Codebases

A codebase made of many tiny, interconnected files can be difficult for both humans and agents to understand.

The agent must trace a large dependency graph and may struggle to determine:

- Where behavior belongs
- Which interfaces are stable
- Which functions are safe to modify
- Where tests should be placed
- Which modules own particular rules

The presenter recommends deeper modules.

---

# 28. Deep Modules

A deep module has:

- A relatively small, stable public interface
- Significant internal capability
- Well-defined ownership
- Strong behavioral tests
- Hidden implementation details

Example:

```ts
interface GamificationService {
  recordLessonCompletion(input: {
    userId: string;
    lessonId: string;
  }): Promise<PointAwardResult>;

  getStudentProgress(userId: string): Promise<StudentProgress>;
}
```

The internal implementation might include:

- Idempotency checks
- Transaction handling
- Level calculations
- Event recording
- Audit information
- Error recovery

Consumers should not need to understand these internal details.

## Benefits for AI

Deep modules:

- Reduce the amount of context the agent must understand
- Create clearer test boundaries
- Limit the impact of changes
- Make interfaces easier to reason about
- Permit implementation details to be delegated
- Reduce cross-repository exploration

The engineer can understand the overall system through module shapes and contracts without manually reading every line of implementation.

---

# 29. Treat Modules as Gray Boxes

A gray-box module is understood through:

- Its purpose
- Its public interface
- Its inputs
- Its outputs
- Its side effects
- Its invariants
- Its tested behavior

The engineer does not need to know every internal statement.

This provides a practical balance:

- The system is not treated as an unknowable black box.
- The engineer does not need to inspect every implementation detail.
- AI can work inside bounded areas.
- Humans retain an architectural understanding of the system.

---

# 30. Refactoring a Codebase for AI

To make an existing codebase more agent-friendly:

1. Identify clusters of highly related files.
2. Determine which domain behavior they collectively represent.
3. Create a stable module interface.
4. Move related behavior behind that interface.
5. Reduce unnecessary exports.
6. Remove cross-module knowledge.
7. Add behavior-focused tests around the module boundary.
8. Document invariants and ownership.
9. Refactor incrementally.
10. Keep tests passing throughout the process.

Do not ask an agent to rewrite the entire architecture at once.

Use small, tested vertical refactoring slices.

---

# 31. Parallel Agent Execution

Parallel execution becomes possible when tasks are:

- Independent
- Clearly scoped
- Based on stable interfaces
- Explicitly dependency-aware
- Protected by automated tests

A dependency graph might look like:

```text
A: Establish points domain model
├── B: Add lesson-completion integration
├── C: Add quiz-completion integration
└── D: Add historical backfill

B + C
  └── E: Add unified dashboard display
```

After Task A is complete, B, C, and D may be assigned to separate agents.

## Risks

Parallel agents may:

- Modify the same files
- Change shared interfaces differently
- Produce incompatible migrations
- Duplicate functionality
- Introduce merge conflicts
- Make contradictory assumptions

## Mitigation

- Use separate branches or worktrees.
- Assign tasks with minimal file overlap.
- Stabilize shared interfaces first.
- Run the full test suite after integration.
- Merge foundational tasks before dependent tasks begin.
- Use an integration review step.
- Keep commits small and reversible.

---

# 32. AI Does Not Eliminate Software Engineering Knowledge

Strong technical knowledge remains important.

Engineers still need to understand:

- Programming languages
- Type systems
- Runtime behavior
- Databases
- Networking
- Security
- Testing
- Distributed systems
- Architecture
- Performance
- Deployment
- Observability

Without this knowledge, an engineer may be unable to recognize when the AI has produced:

- Incorrect abstractions
- Inefficient queries
- Security vulnerabilities
- Broken concurrency
- Invalid transactions
- Poorly designed APIs
- Brittle tests
- Unmaintainable architecture

AI increases the leverage of engineering judgment. It does not remove the need for that judgment.

---

# 33. Common Failure Modes

## Failure 1: Giving the AI a vague feature request

Result:

- Hidden assumptions
- Invented requirements
- Scope creep
- Incorrect behavior

Correction:

- Conduct structured requirements interrogation.

## Failure 2: One enormous implementation session

Result:

- Context degradation
- Forgotten decisions
- Contradictory changes

Correction:

- Use small tasks and fresh contexts.

## Failure 3: Relying only on compaction

Result:

- Lossy summaries
- Accumulated misunderstanding

Correction:

- Persist decisions in external artifacts and clear context.

## Failure 4: Horizontal implementation phases

Result:

- Integration problems discovered late
- No early user-visible result

Correction:

- Use vertical slices and tracer bullets.

## Failure 5: Allowing the AI to create its own requirements

Result:

- Product decisions are made without business accountability.

Correction:

- Keep requirements and architecture human-reviewed.

## Failure 6: Weak tests

Result:

- The agent has no trustworthy feedback.
- Incorrect code appears complete.

Correction:

- Improve behavior-focused automated tests.

## Failure 7: Reviewing in the same exhausted context

Result:

- The reviewer inherits the implementer’s assumptions.

Correction:

- Review from a fresh context.

## Failure 8: Fully automating QA

Result:

- Product taste and real-world usability are lost.

Correction:

- Preserve human QA and product review.

## Failure 9: Running agents with unrestricted permissions

Result:

- Security and operational risk.

Correction:

- Use isolated sandboxes and least privilege.

## Failure 10: A fragmented architecture

Result:

- The agent cannot understand ownership or test boundaries.

Correction:

- Refactor toward deep modules with stable interfaces.

---

# 34. Recommended Practical Workflow

## Step 1: Capture the request

Store the original request in a ticket or brief.

## Step 2: Run a requirements interview

Resolve product, technical, security, data, migration, and testing questions.

## Step 3: Research uncertain areas

Use prototypes and technical spikes where discussion alone is insufficient.

## Step 4: Write the PRD

Include acceptance criteria, implementation decisions, testing decisions, and out-of-scope items.

## Step 5: Identify affected modules

Verify that the proposed change fits the existing architecture.

## Step 6: Create a dependency-aware backlog

Break the work into small, independently assignable issues.

## Step 7: Convert horizontal tasks into vertical slices

Every early slice should deliver observable, testable behavior.

## Step 8: Label tasks

Classify them as:

- Human-in-the-loop
- AFK
- Blocked
- Ready
- Review required

## Step 9: Test one agent run

Observe behavior before enabling unattended loops.

## Step 10: Execute in a sandbox

Use isolated branches, worktrees, containers, and test data.

## Step 11: Require TDD and quality gates

At minimum:

```bash
npm test
npm run typecheck
npm run lint
npm run build
```

Use the equivalent commands for the project’s stack.

## Step 12: Review from a fresh context

Use a separate AI reviewer.

## Step 13: Perform human code review

Inspect architecture, security, maintainability, and domain correctness.

## Step 14: Perform manual QA

Validate the actual user experience.

## Step 15: Merge incrementally

Prefer small, reversible, well-tested changes.

---

# 35. Professional Engineering Takeaways

1. AI coding is primarily a context-management problem.

2. Requirements alignment is more valuable than generating an early plan.

3. Important knowledge must live in persistent engineering artifacts, not only in conversations.

4. PRDs define the destination; issues define the journey.

5. Small vertical slices outperform large horizontal implementation phases.

6. Human judgment is most important during requirements, architecture, review, and QA.

7. Implementation is the part most suitable for autonomous execution.

8. TDD gives agents reliable feedback and reduces dishonest or meaningless tests.

9. Fresh-context review is more reliable than asking an exhausted implementation agent to review itself.

10. The quality of automated feedback loops sets the ceiling for AI-generated code quality.

11. Deep modules make codebases easier for both humans and AI agents to understand.

12. Parallel agents require explicit dependencies and stable module contracts.

13. Autonomous agents should run in restricted, disposable environments.

14. Engineers still need deep technical knowledge to evaluate AI-generated work.

15. AI increases implementation speed, but it may also increase the volume of code requiring review.

---

# 36. Condensed Workflow Checklist

```text
[ ] Capture the original feature request
[ ] Interrogate assumptions one question at a time
[ ] Include domain experts where required
[ ] Research or prototype unresolved areas
[ ] Create a PRD
[ ] Define user stories and acceptance criteria
[ ] Record implementation and testing decisions
[ ] Record out-of-scope decisions
[ ] Identify affected architectural modules
[ ] Break the PRD into dependency-aware issues
[ ] Use vertical slices rather than horizontal layers
[ ] Mark human-in-the-loop and AFK tasks
[ ] Test the agent with one supervised run
[ ] Run autonomous work in a sandbox
[ ] Require red-green-refactor
[ ] Run tests, type checks, linting, and builds
[ ] Commit each bounded task separately
[ ] Review the change in a fresh AI context
[ ] Perform human code review
[ ] Perform manual product QA
[ ] Merge only after all quality gates pass
```

# Final Summary

The workflow is not “give an AI a specification and accept whatever code it produces.”

It is a disciplined software engineering process in which humans define the problem, establish the architecture, structure the work, and evaluate the outcome. AI agents perform bounded implementation tasks inside a system designed to provide clear requirements, limited context, strong tests, stable module boundaries, and rapid feedback.

The most effective AI coding workflow therefore depends less on clever prompting and more on good engineering:

```text
Clear requirements
+ Small tasks
+ Deep modules
+ Strong tests
+ Fresh contexts
+ Human judgment
= Higher-quality AI-assisted software
```
