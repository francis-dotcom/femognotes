# Comprehensive Prompt for Creating Professional Technical Notes and Exam-Ready Study Material

I am providing a transcript from a YouTube video, lecture, workshop, course, podcast, conference talk, or technical presentation.

The material may cover topics such as:

- Artificial intelligence
- Software engineering
- AI-assisted coding
- System design
- Cloud computing
- DevOps
- Cybersecurity
- Databases
- Networking
- Programming
- Machine learning
- Data engineering
- Finance
- Business technology
- Enterprise architecture
- Technical certification material

Convert the transcript into comprehensive, structured, professional Markdown notes.

The result must help me:

1. Understand the full context of the material.
2. Learn the technical concepts deeply.
3. Apply the knowledge in real projects.
4. Prepare for exams or interviews.
5. Review the topic later without rewatching the entire video.
6. Identify the speaker’s opinions, assumptions, recommendations, and limitations.
7. Create active-recall questions and revision material.

Do not produce a shallow summary.

---

# General Processing Instructions

## 1. Remove Irrelevant Transcript Content

Remove or significantly reduce:

- Music descriptions
- Applause
- Audience reactions
- Jokes that do not affect the lesson
- Repeated explanations
- Filler words
- Verbal pauses
- Event logistics
- Room announcements
- Off-topic personal stories
- Promotional content
- Unnecessary speaker commentary
- Repeated questions that have already been answered

Preserve a story, analogy, joke, or audience question only when it helps explain an important technical concept.

---

## 2. Preserve All Important Context

Do not remove important technical or conceptual information merely to make the notes shorter.

Preserve:

- Definitions
- Explanations
- Arguments
- Workflows
- Examples
- Demonstrations
- Architecture decisions
- Implementation steps
- Commands
- Code examples
- Tools
- Frameworks
- Best practices
- Trade-offs
- Limitations
- Failure modes
- Risks
- Security concerns
- Testing strategies
- Operational considerations
- Business implications
- Questions and answers that clarify the subject
- Important disagreements or alternative approaches
- Decisions that were explicitly rejected
- Reasons behind recommendations

When a section is unclear or incomplete in the transcript, state that clearly instead of inventing information.

---

## 3. Separate Facts From Opinions

Clearly distinguish between:

- Established technical facts
- The speaker’s personal experience
- The speaker’s recommendation
- An assumption made during the presentation
- A prediction
- A marketing claim
- An inference
- An unresolved question

Use wording such as:

- “The speaker recommends…”
- “The speaker argues…”
- “Based on the demonstration…”
- “This appears to assume…”
- “The transcript does not provide enough evidence to confirm…”

Do not present every speaker statement as universally accepted truth.

---

## 4. Explain Concepts Fully

For every major technical concept, include:

- Formal or professional definition
- Plain-language explanation
- Why it matters
- How it works
- Where it fits in a larger system
- Example from the transcript
- Additional practical example when useful
- Benefits
- Limitations
- Common mistakes
- When to use it
- When not to use it
- Related concepts
- Important distinctions

Do not merely repeat the speaker’s words.

Rewrite the explanation so that a professional learner can understand and reuse the knowledge.

---

## 5. Maintain Technical Accuracy

Do not invent unsupported technical details.

Preserve:

- Tool names
- Framework names
- Commands
- File names
- Configuration names
- Architectural terminology
- Programming terminology
- Product names
- Important numbers
- Limits
- Dependencies
- Sequence of operations

Correct obvious grammar and transcription errors, but do not silently change the meaning.

When a technical claim may be inaccurate, outdated, incomplete, or opinion-based, label it for verification.

---

# Required Markdown Structure

Use the following structure where applicable.

Do not force irrelevant sections into the notes. If a section does not apply, write:

> Not covered in sufficient detail in the source material.

---

# {{VIDEO OR LECTURE TITLE}}

**Speaker:** {{SPEAKER NAME}}  
**Source:** {{SOURCE LINK}}  
**Main Topic:** {{MAIN TOPIC}}  
**Date Watched:** {{DATE}}  
**Difficulty Level:** {{BEGINNER / INTERMEDIATE / ADVANCED}}  
**Note Type:** Professional Technical and Exam-Ready Notes

---

## 1. Executive Summary

Write a clear but substantial overview covering:

- What the presentation is about
- The problem it addresses
- The main solution or argument
- The most important technical lessons
- Who would benefit from the material
- The overall professional relevance

The summary should be detailed enough that a reader can understand the direction of the presentation before reading the full notes.

---

## 2. Learning Objectives

After studying these notes, the reader should be able to:

1. {{OBJECTIVE}}
2. {{OBJECTIVE}}
3. {{OBJECTIVE}}
4. {{OBJECTIVE}}
5. {{OBJECTIVE}}

Include additional learning objectives when necessary.

Use measurable verbs such as:

- Define
- Explain
- Compare
- Design
- Implement
- Evaluate
- Troubleshoot
- Apply
- Distinguish
- Analyze

---

## 3. Central Thesis

> State the speaker’s main argument or central idea.

### Why It Matters

Explain:

- Why the thesis matters technically
- Why it matters professionally
- What problem it solves
- What happens when teams ignore it
- Which roles or projects are affected

---

## 4. Context and Problem Being Addressed

Explain:

- The original problem
- The current or traditional approach
- Why the traditional approach is insufficient
- Constraints
- Stakeholders
- Technical environment
- Business environment
- Assumptions
- Expected outcome

---

## 5. Essential Definitions

Create a table:

| Term | Professional Definition | Simple Explanation | Example |
|---|---|---|---|
| {{TERM}} | {{DEFINITION}} | {{PLAIN LANGUAGE}} | {{EXAMPLE}} |

Include every important term required to understand the presentation.

Do not assume the reader already knows specialized terminology.

---

## 6. Key Concepts

For every major concept, use this structure:

### 6.1 {{CONCEPT NAME}}

**Definition:**  
{{FORMAL DEFINITION}}

**Plain-language explanation:**  
{{SIMPLE EXPLANATION}}

**Why it matters:**  
{{ENGINEERING OR PROFESSIONAL IMPORTANCE}}

**How it works:**  
{{STEP-BY-STEP EXPLANATION}}

**Where it fits:**  
{{POSITION IN THE SYSTEM OR WORKFLOW}}

**Example from the source:**  
{{SOURCE EXAMPLE}}

**Practical example:**  
{{REAL-WORLD EXAMPLE}}

**Benefits:**

- {{BENEFIT}}
- {{BENEFIT}}
- {{BENEFIT}}

**Limitations:**

- {{LIMITATION}}
- {{LIMITATION}}
- {{LIMITATION}}

**When to use it:**

- {{USE CASE}}

**When not to use it:**

- {{NON-USE CASE}}

**Common mistake:**

- {{MISTAKE}}

Repeat this structure for all major concepts.

---

## 7. Important Distinctions

Create comparison sections for concepts that are easy to confuse.

### {{CONCEPT A}} vs. {{CONCEPT B}}

| Comparison Area | {{CONCEPT A}} | {{CONCEPT B}} |
|---|---|---|
| Definition | {{DETAIL}} | {{DETAIL}} |
| Purpose | {{DETAIL}} | {{DETAIL}} |
| How it works | {{DETAIL}} | {{DETAIL}} |
| Best use case | {{DETAIL}} | {{DETAIL}} |
| Advantages | {{DETAIL}} | {{DETAIL}} |
| Limitations | {{DETAIL}} | {{DETAIL}} |
| Example | {{DETAIL}} | {{DETAIL}} |

### Most Important Difference

{{EXPLAIN THE CORE DISTINCTION}}

Include all comparisons likely to appear in an exam, interview, architecture discussion, or implementation decision.

---

## 8. Tools, Platforms, Frameworks, and Technologies

Create a table:

| Tool or Technology | Purpose | Category | Where It Fits | Strengths | Limitations | Best Use Case |
|---|---|---|---|---|---|---|
| {{TOOL}} | {{PURPOSE}} | {{CATEGORY}} | {{STAGE}} | {{STRENGTHS}} | {{LIMITATIONS}} | {{USE CASE}} |

For each tool, explain where appropriate:

- Whether it is code-first or low-code
- Supported languages
- Deployment model
- Integration model
- Security implications
- Operational complexity
- Scalability
- Vendor lock-in
- Target user
- Alternatives

---

## 9. Recommended Workflow

First provide a high-level flow:

```text
{{STARTING POINT}}
    ↓
{{STAGE 1}}
    ↓
{{STAGE 2}}
    ↓
{{STAGE 3}}
    ↓
{{STAGE 4}}
    ↓
{{TESTING OR REVIEW}}
    ↓
{{FINAL OUTCOME}}
```

Then explain each stage.

### Step 1: {{STEP NAME}}

**Objective:**  
{{PURPOSE}}

**Inputs:**

- {{INPUT}}

**Actions:**

1. {{ACTION}}
2. {{ACTION}}
3. {{ACTION}}

**Outputs:**

- {{OUTPUT}}

**Responsible party:**  
{{HUMAN / AI / TEAM / SYSTEM}}

**Risks:**

- {{RISK}}

**Success criteria:**

- {{SUCCESS CONDITION}}

Repeat for all workflow stages.

---

## 10. Architecture and System Design

### Architecture Overview

Explain the main components and how they interact.

```text
{{USER OR CLIENT}}
    ↓
{{INTERFACE}}
    ↓
{{APPLICATION OR API LAYER}}
    ↓
{{ORCHESTRATION OR DOMAIN LAYER}}
    ↓
{{MODEL, DATABASE, TOOL, OR EXTERNAL SERVICE}}
    ↓
{{MONITORING, SECURITY, OR GOVERNANCE}}
```

### Component Responsibilities

| Component | Responsibility | Inputs | Outputs | Dependencies |
|---|---|---|---|---|
| {{COMPONENT}} | {{RESPONSIBILITY}} | {{INPUTS}} | {{OUTPUTS}} | {{DEPENDENCIES}} |

### Data Flow

Explain:

1. Where data originates
2. How it is validated
3. Where it is transformed
4. Where decisions are made
5. Where data is stored
6. How responses are returned
7. How errors are handled
8. How actions are audited

### Architectural Principles

For each principle, explain:

- Meaning
- Benefit
- Trade-off
- Example
- Failure mode when ignored

Possible principles include:

- Modularity
- Separation of concerns
- Loose coupling
- High cohesion
- Observability
- Idempotency
- Scalability
- Reproducibility
- Resilience
- Least privilege
- Human oversight

---

## 11. Human and AI Responsibilities

### Human-in-the-Loop Responsibilities

- {{RESPONSIBILITY}}
- {{RESPONSIBILITY}}
- {{RESPONSIBILITY}}

Explain why human judgment is required.

### Tasks Suitable for AI Automation

- {{TASK}}
- {{TASK}}
- {{TASK}}

Explain why each task is suitable for automation.

### Tasks That Should Not Be Fully Automated

- {{TASK}}
- {{TASK}}
- {{TASK}}

Explain the risks of full automation.

### Responsibility Matrix

| Activity | Human | AI Agent | Automated System | Final Approver |
|---|---|---|---|---|
| {{ACTIVITY}} | {{ROLE}} | {{ROLE}} | {{ROLE}} | {{ROLE}} |

---

## 12. Implementation Guidance

### Recommended Implementation Approach

1. {{STEP}}
2. {{STEP}}
3. {{STEP}}
4. {{STEP}}
5. {{STEP}}

### Prerequisites

- {{PREREQUISITE}}
- {{PREREQUISITE}}

### Configuration

```text
{{CONFIGURATION OR PSEUDOCODE}}
```

### Example Code

```{{LANGUAGE}}
{{CODE EXAMPLE}}
```

For every code example:

- Explain what the code does
- Explain important lines
- Identify dependencies
- Identify expected inputs and outputs
- Explain error handling
- Mention security concerns
- Mention production improvements

### Important Implementation Rules

- {{RULE}}
- {{RULE}}
- {{RULE}}

### Production Considerations

- Scalability
- Error handling
- Retry strategy
- Timeouts
- Rate limits
- Logging
- Secrets management
- Configuration management
- Cost
- Versioning
- Rollback

---

## 13. Testing Strategy

### Unit Tests

- {{TEST CASE}}
- {{TEST CASE}}
- {{TEST CASE}}

### Integration Tests

- {{TEST CASE}}
- {{TEST CASE}}
- {{TEST CASE}}

### End-to-End Tests

- {{TEST CASE}}
- {{TEST CASE}}
- {{TEST CASE}}

### Security Tests

- {{TEST CASE}}
- {{TEST CASE}}

### Performance Tests

- {{TEST CASE}}
- {{TEST CASE}}

### Failure and Edge-Case Tests

- {{TEST CASE}}
- {{TEST CASE}}
- {{TEST CASE}}

### Manual QA

- [ ] {{QA CHECK}}
- [ ] {{QA CHECK}}
- [ ] {{QA CHECK}}
- [ ] {{QA CHECK}}

### Quality Gates

```bash
{{TEST COMMAND}}
{{TYPE-CHECK COMMAND}}
{{LINT COMMAND}}
{{BUILD COMMAND}}
{{SECURITY SCAN COMMAND}}
```

Explain what each quality gate validates.

---

## 14. Security, Privacy, Compliance, and Governance

### Security Risks

| Risk | Cause | Impact | Mitigation |
|---|---|---|---|
| {{RISK}} | {{CAUSE}} | {{IMPACT}} | {{MITIGATION}} |

Consider:

- Authentication
- Authorization
- Prompt injection
- Data leakage
- Secret exposure
- Unsafe tool execution
- Supply-chain risks
- Dependency vulnerabilities
- Model abuse
- Hallucinations
- Excessive permissions
- Logging sensitive information

### Privacy Considerations

- Data collection
- Data retention
- Personally identifiable information
- User consent
- Model-provider data handling
- Cross-border data transfer
- Data deletion

### Governance Controls

- Approval gates
- Audit logs
- Policy enforcement
- Human review
- Model evaluation
- Version control
- Change management
- Incident response

---

## 15. Operational and Deployment Considerations

Explain:

- Deployment environment
- Infrastructure requirements
- Cloud or on-premises options
- Containerization
- Kubernetes relevance
- CI/CD
- Monitoring
- Logging
- Tracing
- Alerting
- Backup
- Disaster recovery
- Rollback
- Cost monitoring
- Capacity planning
- Service-level objectives
- Failure recovery

Create an operational checklist where useful.

---

## 16. Trade-Offs and Limitations

| Decision or Technique | Benefits | Limitations | Risks | Best Use Case | Avoid When |
|---|---|---|---|---|---|
| {{DECISION}} | {{BENEFITS}} | {{LIMITATIONS}} | {{RISKS}} | {{USE CASE}} | {{CONDITION}} |

Include technical, operational, financial, and organizational trade-offs.

---

## 17. Common Failure Modes

For every major failure mode, use:

### Failure {{NUMBER}}: {{FAILURE NAME}}

**What happens:**  
{{DESCRIPTION}}

**Root cause:**  
{{CAUSE}}

**Impact:**  
{{IMPACT}}

**How to detect it:**  
{{DETECTION}}

**How to prevent it:**  
{{PREVENTION}}

**How to fix it:**  
{{CORRECTION}}

**Example:**  
{{EXAMPLE}}

Include failures described directly by the speaker and failures logically implied by the workflow.

Clearly label implied failures as professional analysis rather than direct transcript content.

---

## 18. Common Misconceptions

### Misconception 1

**Incorrect belief:**  
{{INCORRECT BELIEF}}

**Why it is incorrect:**  
{{EXPLANATION}}

**Correct understanding:**  
{{CORRECT EXPLANATION}}

Repeat for all important misconceptions.

---

## 19. Cause-and-Effect Relationships

Create a table:

| Cause, Decision, or Condition | Immediate Effect | Long-Term Consequence |
|---|---|---|
| {{CAUSE}} | {{EFFECT}} | {{CONSEQUENCE}} |

This section should help explain why certain engineering decisions lead to specific outcomes.

---

## 20. Speaker Recommendations

List the speaker’s recommendations.

For every recommendation, indicate:

- Recommendation
- Reason provided
- Supporting example
- Possible limitation
- Whether it is broadly applicable or context-specific

> Treat recommendations as the speaker’s position unless supported as an established technical standard.

---

## 21. Claims That Require Verification

Create a table:

| Claim | Why It Requires Verification | What Evidence Would Confirm It |
|---|---|---|
| {{CLAIM}} | {{REASON}} | {{EVIDENCE}} |

Include:

- Performance claims
- Security claims
- Cost claims
- Market claims
- “Best tool” claims
- Scalability claims
- Predictions
- Claims without examples or evidence

---

## 22. Professional Assessment

### Strongest Ideas

- {{IDEA}}
- {{IDEA}}
- {{IDEA}}

### Ideas That Depend on Context

- {{IDEA}}
- {{IDEA}}

### Ideas That Need Further Validation

- {{IDEA}}
- {{IDEA}}

### Missing Topics

- {{TOPIC}}
- {{TOPIC}}
- {{TOPIC}}

### Overall Assessment

Explain:

- Technical depth
- Practical usefulness
- Accuracy
- Bias
- Completeness
- Intended audience
- Whether the advice is production-ready

---

## 23. Application to Real Projects

For each relevant project, use:

### Project: {{PROJECT NAME}}

**Relevant concept:**  
{{CONCEPT}}

**Current problem:**  
{{PROBLEM}}

**How the concept can be applied:**  
{{APPLICATION}}

**Required changes:**

1. {{CHANGE}}
2. {{CHANGE}}
3. {{CHANGE}}

**Expected benefit:**  
{{BENEFIT}}

**Risk:**  
{{RISK}}

**How to validate success:**  
{{VALIDATION}}

**Next action:**  
{{ACTION}}

---

## 24. Facts and Processes to Memorize

### Important Facts

- {{FACT}}
- {{FACT}}
- {{FACT}}

### Important Process

```text
{{STEP 1}}
    ↓
{{STEP 2}}
    ↓
{{STEP 3}}
    ↓
{{FINAL RESULT}}
```

### Memorization Notes

- {{MEMORY POINT}}
- {{MEMORY POINT}}
- {{MEMORY POINT}}

---

## 25. Likely Exam or Interview Questions

### Short-Answer Questions

1. {{QUESTION}}
2. {{QUESTION}}
3. {{QUESTION}}
4. {{QUESTION}}
5. {{QUESTION}}

### Long-Answer Questions

1. {{QUESTION}}
2. {{QUESTION}}
3. {{QUESTION}}

### Comparison Questions

1. Compare {{CONCEPT A}} and {{CONCEPT B}}.
2. Explain when to use {{TOOL A}} instead of {{TOOL B}}.

### Scenario-Based Questions

1. {{SCENARIO}}
2. {{SCENARIO}}
3. {{SCENARIO}}

### Architecture Questions

1. {{QUESTION}}
2. {{QUESTION}}

### Troubleshooting Questions

1. {{QUESTION}}
2. {{QUESTION}}

---

## 26. Multiple-Choice Practice Questions

Generate at least 10 high-quality questions.

Use this format:

### Question 1

{{QUESTION}}

A. {{OPTION}}  
B. {{OPTION}}  
C. {{OPTION}}  
D. {{OPTION}}

**Correct answer:** {{ANSWER}}

**Explanation:**  
{{EXPLANATION}}

**Why the other options are incorrect:**

- **A:** {{EXPLANATION}}
- **B:** {{EXPLANATION}}
- **C:** {{EXPLANATION}}
- **D:** {{EXPLANATION}}

Questions should test understanding, not merely wording memorization.

Include:

- Definition questions
- Comparison questions
- Workflow questions
- Architecture questions
- Scenario questions
- Failure-mode questions

---

## 27. Active-Recall Questions

Create at least 15 questions that the learner should answer without looking at the notes.

Examples:

1. What is {{CONCEPT}}?
2. Why is it important?
3. How does it work?
4. What are its main components?
5. What are its limitations?
6. When should it be used?
7. When should it not be used?
8. How does it differ from {{RELATED CONCEPT}}?
9. What failure modes can occur?
10. How can those failures be prevented?
11. What does the recommended workflow look like?
12. Which decisions require human review?
13. Which tasks can be automated?
14. What security risks exist?
15. How would you apply this to a real system?

---

## 28. Flashcards

Create concise flashcards using exactly this format:

```text
Q1. {{QUESTION}} :: {{ANSWER}}
Q2. {{QUESTION}} :: {{ANSWER}}
Q3. {{QUESTION}} :: {{ANSWER}}
```

Requirements:

- Do not leave blank lines between flashcards.
- Use `{{double curly braces}}` around the most important answer term or fill-in-the-blank concept.
- Include definitions, comparisons, workflows, tools, risks, and key facts.
- Create enough flashcards to cover all major concepts.

---

## 29. Teach-Back Exercise

Write a simplified explanation of the topic as if teaching an intelligent beginner.

The explanation must:

- Avoid unnecessary jargon
- Preserve technical accuracy
- Explain why the topic matters
- Include a practical example
- Explain the complete workflow

Then provide:

### Questions the Learner Should Be Able to Answer

- {{QUESTION}}
- {{QUESTION}}
- {{QUESTION}}

### Signs of Incomplete Understanding

- Inability to explain {{CONCEPT}}
- Confusion between {{CONCEPT A}} and {{CONCEPT B}}
- Inability to reproduce {{WORKFLOW}}
- Inability to identify {{RISK OR FAILURE MODE}}

---

## 30. Knowledge Gaps

| Topic | Covered Well? | What Is Missing? | How to Resolve It |
|---|---|---|---|
| {{TOPIC}} | {{YES/PARTLY/NO}} | {{MISSING DETAIL}} | {{ACTION}} |

Identify gaps in the transcript, not only gaps in the learner’s knowledge.

---

## 31. One-Page Revision Summary

Create a concise revision section containing:

### Core Thesis

{{ONE-SENTENCE THESIS}}

### Five Most Important Concepts

1. {{CONCEPT}}
2. {{CONCEPT}}
3. {{CONCEPT}}
4. {{CONCEPT}}
5. {{CONCEPT}}

### Key Workflow

```text
{{CONDENSED WORKFLOW}}
```

### Important Distinctions

- {{DISTINCTION}}
- {{DISTINCTION}}
- {{DISTINCTION}}

### Main Risks

- {{RISK}}
- {{RISK}}
- {{RISK}}

### Key Tools

- {{TOOL}} — {{PURPOSE}}
- {{TOOL}} — {{PURPOSE}}

### Final Memory Statement

> {{PARAGRAPH THAT SUMMARIZES THE WHOLE TOPIC}}

---

## 32. Professional Engineering Takeaways

List at least 10 high-value takeaways.

Each takeaway should be:

- Specific
- Actionable
- Technically meaningful
- Supported by the source
- Useful in real engineering work

---

## 33. Action Items

Create actionable next steps:

- [ ] {{ACTION}}
- [ ] {{ACTION}}
- [ ] {{ACTION}}
- [ ] {{ACTION}}
- [ ] {{ACTION}}

Separate actions into:

- Study actions
- Research actions
- Implementation actions
- Validation actions

---

## 34. Final Comprehension Checklist

- [ ] I can explain the central thesis without looking at the notes.
- [ ] I understand all essential definitions.
- [ ] I can distinguish similar concepts.
- [ ] I can reproduce the main workflow.
- [ ] I understand the system architecture.
- [ ] I know the responsibilities of each component.
- [ ] I understand the implementation approach.
- [ ] I understand the testing strategy.
- [ ] I know the main security risks.
- [ ] I understand the trade-offs.
- [ ] I can identify common failure modes.
- [ ] I can explain which tasks require human oversight.
- [ ] I can answer the practice questions.
- [ ] I can apply the knowledge to a real project.
- [ ] I know which claims require additional verification.
- [ ] I can teach the topic clearly to another person.

---

## 35. Final Summary

Write a complete concluding summary covering:

- The main problem
- The central thesis
- The key concepts
- The recommended workflow
- The architecture
- Important tools
- Main trade-offs
- Security concerns
- Testing requirements
- Common failures
- Real-world application
- Limitations of the source
- Final professional recommendation

---

# Output Requirements

1. Produce the entire result in valid Markdown.
2. Use clear headings and subheadings.
3. Use tables only when comparison improves understanding.
4. Use code blocks for code, commands, configurations, workflows, and architecture diagrams.
5. Do not use excessive repetition.
6. Preserve technical depth.
7. Do not invent unsupported facts.
8. Label speaker opinions and uncertain claims.
9. Explain concepts in both professional and plain language.
10. Make the notes useful for study, implementation, interviews, exams, and future reference.
11. Create a downloadable `.md` file containing the complete notes.
12. Use a lowercase kebab-case filename based on the title.
13. Do not omit a major concept simply because the output becomes long.
14. When the source is incomplete, explicitly identify the missing information.
15. At the beginning, include a short statement estimating whether the notes provide:
    - Introductory understanding
    - Working understanding
    - Strong professional understanding
    - Exam-ready understanding

Transcript or source material:

[PASTE THE TRANSCRIPT HERE OR USE THE ATTACHED FILE]
