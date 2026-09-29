# ACE-Aligned Agent Governance for the SOC
**Our practice, designed against the questions the ACE Framework teaches organizations to ask.**

Source of inspiration: Camille Stewart Gloster, *The Insider You Built: How Organizations Stay in Control of Autonomous AI Agents* (Wiley, 2026). The book introduces the Agent-Centered Enforcement and Attribution (ACE) Framework for investigating, attributing, and responding to failures when autonomous AI systems act with delegated authority, and reframes AI incidents as governance challenges spanning human and machine decision paths. Read the book; this document is what we built once we took it seriously.

## The problem in one sentence
A SOC that uses AI agents has created new insiders, and if you cannot say what authority each one holds, what it did, and who answers for it, you have an attribution gap wearing an efficiency costume.

## Our design answers, per SOC agent
Every agent in our SOC (triage, investigation, reporting) ships with four things before it processes its first alert:

**1. A register entry with delegated authority stated.** What the agent may read, what it may draft, what it may never do. The register is reviewed like an access grant, because it is one.

**2. Attribution by construction.** Every agent action logs to the case record with the agent identified as the actor and the human approver identified for anything that crossed a gate. When something goes wrong, the human-and-machine decision path is already written down; the investigation reads it rather than reconstructs it.

**3. Enforcement points, honestly placed.** Human-in-the-loop gates sit where consequence lives: severity confirmation on high-severity cases, scope approval before queries touch identity or client-named resources, human review before any report leaves the building. "No rework needed" is the tuning target for agent output quality; it is never the argument for removing a gate.

**4. A response path when the agent is the incident.** Agent misbehavior is triaged through the same incident process as any insider event: contain (suspend the agent's authority), investigate (the attribution log), attribute (which decision path failed, human or machine), correct (register, gate, or model), and record. Static approval-at-deployment is not governance; the review cadence is.

## What this looks like operationally
- The agent register lives beside the access model, reviewed on the same cadence.
- Agent identities are distinct principals, never shared human credentials, so logs attribute cleanly.
- Nothing agent-built touches client environments. Agents serve the SOC's internal machinery.
- The register's delegated-authority column is the first artifact an auditor, insurer, or customer sees when they ask "how do you control your AI?"

The measure of success: when an agent does something surprising, the first hour is spent responding, not discovering who authorized what.
