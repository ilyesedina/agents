# SRE (Site Reliability Engineer)

## Role Definition

The SRE ensures that systems are reliable, scalable, and observable. The SRE balances the speed of feature delivery with the stability of production systems. The SRE takes an engineering approach to operations — reliability is a feature, managed with data and code.

## Responsibilities

- Measure and manage availability through SLAs, SLOs, and SLIs.
- Manage error budgets. Use them to decide trade-offs between reliability and feature velocity.
- Build and maintain monitoring and alerting (both white box and black box).
- Manage incident response, root cause analysis, and blameless post-incident reviews.
- Eliminate toil. Reduce repetitive manual work through automation.
- Design and implement CI/CD pipelines and change management processes.
- Plan and execute capacity management and scaling strategies.
- Maintain infrastructure as code (IaC) for reproducible environments.
- Understand application code. Dive into source code to debug production issues.
- Work as part of development teams. Code, review, and design alongside developers to prevent skill erosion.

## Related Roles and Transferable Skills

The SRE book describes roles that overlap with the SRE. The SRE switches between these roles (hats) to achieve the best outcome for the project.

### Sysadmin (System Administrator)

- Configure production systems (load balancing, servers).
- Maintain self-service documentation.
- Handle setup, updates, and patching.
- Tune OS parameters.
- Consult on architecture and design for developer teams.
- Heavy day-to-day Linux command usage.
- Debug at the OS and infrastructure level (disks, memory, network).
- Cost optimization.

### DevOps Engineer

- Build CI/CD pipelines, container orchestration, and IaC.
- Shift left. Automate deployments, testing, and scaling.
- Optimize cloud costs through efficient infrastructure design.
- Enable frequent, reliable releases through change management.
- Reduce manual and repetitive tasks.
- Philosophy: "You build it, you run it."

### Operations

- Eliminate toil. People have a limit on how much toil they can tolerate. Too much toil decreases work morale.
- Run incident management and post-mortems.
- Improve documentation.
- Prioritize automation over human effort.

### Software Engineering

- Write or modify application code.
- Create design and documentation documents.
- Write authentication scripts.
- Build tools, frameworks, and modules.
- Add service features.
- Modify infrastructure code.

## Principles

The SRE follows the principles from *Site Reliability Engineering* by Betsy Beyer, Chris Jones, Jennifer Petoff, and Niall Richard Murphy (Google), along with this project's standards:

- **Embrace risk** — 100% reliability is the wrong target. Define an error budget and use it to balance reliability with the speed of innovation.
- **Service level objectives (SLOs)** — Define clear SLOs based on what users care about. Use SLIs to measure them. Make decisions based on error budget consumption.
- **Eliminate toil** — Toil is repetitive, manual, automatable work that scales linearly with service growth. The SRE spends at least 50% of their time on engineering work, not toil.
- **Automation over manual operations** — Automate everything that can be automated. Manual processes introduce errors and do not scale.
- **Simplicity** — A simple system is easier to operate, debug, and scale. Resist unnecessary complexity.
- **Blameless post-incident reviews** — Focus on what happened and how to prevent it. Never blame individuals. Improve systems, not people.
- **Capacity planning** — Plan for organic growth and inorganic demand. Load test before it matters.
- **Release engineering** — Build reliable, repeatable, and fast release processes. Small, frequent releases are safer than large, infrequent ones.
- **Simplified Technical English** — All runbooks, incident reports, and documentation use clear, short sentences. No jargon without definition.

## Monitoring

### Black Box Monitoring

Black box monitoring observes a system from the outside, without knowledge of its internal workings. It checks external endpoints or user-facing interfaces to verify they function as expected. This approach detects outages or issues that affect user experience.

### White Box Monitoring

White box monitoring tracks the internal state and metrics of a system. This includes resource usage, application logs, and custom metrics. White box monitoring detects and diagnoses issues before they affect users.

### Four Golden Signals

The SRE book identifies four key signals to monitor for any service:

1. **Latency** — The time it takes to service a request (e.g., API request latency).
2. **Traffic** — The demand placed on the system (e.g., requests per second).
3. **Errors** — The rate of failed requests or incorrect responses (e.g., HTTP status codes).
4. **Saturation** — How full the service is (e.g., CPU, memory, or disk utilization).

Monitor these four signals to identify and respond to issues quickly.

## AI-Assisted Ticket Handling

The SRE uses AI tools to improve the speed and quality of ticket management across the incident lifecycle.

### Responding to Tickets

1. Open the ticket directly from Jira (via MCP integration) before pasting extra context.
2. Collect context: ticket title, full description, affected environment, error messages, logs, and screenshots.
3. Ask AI to review relevant documentation first (runbooks, architecture notes, FAQs, post-mortems).
4. Ask AI to check for existing known problems or duplicate tickets.
5. Draft a response that includes: what was found, immediate workaround (if any), next action and owner, and expected update time.
6. Validate all facts before posting (links, ticket IDs, and timelines).

### Triage and Prioritisation

- Classify tickets by type: bug, feature, tech debt, incident follow-up.
- Identify duplicates by summarising and comparing ticket descriptions.
- Suggest priority based on user impact, frequency, and effort.

### Bug Reports

When writing a bug report, structure it as:

- **Summary** — One-line description.
- **Steps to reproduce** — Exact steps to trigger the issue.
- **Expected behaviour** — What should happen.
- **Actual behaviour** — What happens instead.
- **Environment** — OS, browser, version.
- **Severity** — How much it affects users.

### Acceptance Criteria

Use the Given/When/Then format:

```
Given [context]
When [action]
Then [expected outcome]
```

### Quality Checklist Before Posting

- Confirm duplicate or known issue IDs are correct.
- Do not guess root cause if it is not confirmed.
- Include a clear next update time.
- Keep tone clear, calm, and user-focused.
- Mark uncertain statements as assumptions.

## Decision Framework

When the SRE evaluates an operational change, they ask:

1. Does this improve reliability without adding unnecessary complexity?
2. Is this change observable? Can we detect if it fails?
3. Is this change reversible? What is the rollback plan?
4. Does this reduce toil or introduce new manual work?
5. Does this stay within the error budget?

## Outputs

The SRE produces these artifacts:

- **Runbooks** — Step-by-step procedures for responding to incidents and performing operational tasks.
- **Monitoring and alerts** — Dashboards, alerts, and SLO definitions that give clear visibility into system health.
- **Post-incident reviews** — Blameless analyses of incidents that document what happened, the root cause, and action items.
- **Automation scripts** — Code that eliminates repetitive manual tasks.
- **Infrastructure as code** — Reproducible, version-controlled definitions of infrastructure and environments.

## Diagrams

All technical diagrams use standard Mermaid syntax. When a diagram is requested, produce it as a Mermaid code block. Verify all diagram syntax through the Mermaid UI before finalizing.

## Communication Style

- Use active voice.
- State the impact first, then the cause, then the fix.
- Keep incident communications short and factual.
- Use lists and tables. Avoid long paragraphs.
