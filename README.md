# Cloud Concentration Risk — Presentation & Simulation

## Overview

This project is a 5-minute individual academic presentation for the course **CS3406 — Cybersecurity Governance, Risk and Compliance**.

### Presentation Topic

**Cloud Concentration Risk: The Hidden Single Point of Failure in Modern Enterprises**

### Core Question

> **Are modern enterprises actually resilient, or have they simply moved their single points of failure outside the organization?**

The presentation explores how organizations can become heavily dependent on a small number of cloud providers, regions, services, or common technology dependencies, creating the possibility of cascading failures across multiple business systems.

The topic is directly connected to the syllabus concept of **Cloud Concentration Risk** under Module 4, while also drawing on related concepts such as third-party risk, risk scoring limitations, business continuity, disaster recovery, and cyber resilience.

---

# Objectives

The presentation aims to:

1. Explain what cloud concentration risk means.
2. Show how modern cloud adoption created new forms of dependency.
3. Demonstrate how one provider-side incident can affect many organizations.
4. Analyze real-world incidents involving major cloud/internet infrastructure providers.
5. Identify technical, operational, governance, and compliance risks.
6. Discuss strategies for reducing concentration risk.
7. Demonstrate the concept through an interactive CISO/tabletop simulation.

---

# Key Concept

The central idea is:

> **Having multiple applications does not necessarily mean having multiple independent risks.**

For example:

```text
LMS ─────────┐
ERP ─────────┤
Payments ────┤
Email ───────┼──► SAME CLOUD PROVIDER
Analytics ───┤
Backup ──────┘
```

If the common dependency fails, several apparently independent services may fail simultaneously.

This creates **concentration risk** and potentially a much larger **blast radius** than an organization might expect from its individual risk assessments.

---

# Presentation Approach

The presentation will use a **story-driven approach** rather than a traditional definition-heavy format.

The flow is:

```text
Hook
  ↓
What is Cloud Concentration Risk?
  ↓
How did we get here?
  ↓
Real-world incidents
  ↓
What can go wrong?
  ↓
Governance & compliance impact
  ↓
Possible mitigation strategies
  ↓
Audience simulation
  ↓
Final takeaway
```

The goal is to make the audience **experience the dependency problem**, rather than simply hear a definition.

---

# Real-World Case Studies

## 1. AWS

### AWS US-EAST-1 Incident — October 2025

The AWS incident will be used as the **primary case study**.

The presentation will examine:

* Regional concentration
* Dependence on common AWS services
* Cascading service impact
* Hidden dependencies
* Recovery requirements
* Multi-region architecture
* Exit and portability considerations

The important point is not simply that a cloud provider experienced an outage.

The important question is:

> **How many organizations can inherit the consequences of a failure at a common infrastructure provider?**

---

## 2. Cloudflare

### Cloudflare Incident — November 18, 2025

Cloudflare will be used as a supporting case study.

The presentation will highlight the fact that large-scale disruption does not necessarily require a cyberattack.

The incident demonstrates how a provider-side technical/configuration failure can propagate to many downstream services.

The key lesson:

> **Concentration risk can become significant even when the initiating event is not a cyberattack.**

---

# Risk Areas

The presentation will examine several possible risks:

### Operational Risk

Provider outage can make critical applications unavailable.

### Cybersecurity Risk

A compromise of a major provider could potentially affect downstream customers.

### Configuration Risk

A provider-side configuration error can have a very large blast radius.

### Supply-Chain Risk

A dependency underneath a major provider can become a common failure point.

### Geographic Concentration

Critical workloads concentrated in one region can be affected by regional incidents.

### Vendor Lock-In

Organizations may technically have alternatives but lack practical ability to migrate quickly.

### Dependency Opacity

Organizations may not fully understand how many critical systems ultimately depend on the same provider or infrastructure layer.

---

# Governance & Compliance Angle

The project is intentionally framed as a **GRC problem**, not simply a cloud-technology problem.

Key questions include:

### Governance

Who approved the level of cloud dependency?

### Risk Management

Was concentration represented in the organization's risk assessment?

### Risk Scoring

Can traditional risk scores accurately represent correlated/common dependencies?

### Risk Appetite

How much concentration is acceptable for critical services?

### Resilience

Can the organization continue operating if the provider becomes unavailable?

### Board Oversight

Does executive leadership understand the organization's critical external dependencies?

---

# Compliance Considerations

The presentation will avoid claiming that a cloud outage automatically equals a regulatory violation.

Instead, the focus is:

> **A cloud concentration event can become a compliance, regulatory, contractual, or internal-control problem when the resulting disruption causes an organization to fail an applicable obligation.**

Potential areas include:

* Availability and resilience requirements
* Business continuity requirements
* Disaster recovery objectives
* Data protection obligations
* Sector-specific regulatory requirements
* Contractual service obligations
* Internal security controls

---

# Mitigation Strategies

The presentation will evaluate several approaches.

## Multi-Cloud

Use multiple cloud providers to reduce dependence on a single provider.

**Advantages:**

* Reduced provider concentration

**Challenges:**

* Higher complexity
* Higher cost
* Operational overhead
* Integration challenges

---

## Multi-Region

Distribute critical workloads across independent geographic regions.

This reduces regional concentration but does not necessarily eliminate provider concentration.

---

## Hybrid Architecture

Keep selected critical capabilities on alternative or private infrastructure.

This can provide an additional recovery path.

---

## Dependency Mapping

Map:

```text
Business Service
      ↓
Application
      ↓
SaaS
      ↓
Cloud
      ↓
Region
      ↓
Underlying Service
```

The goal is to identify hidden common dependencies.

---

## Exit Strategy

Organizations should know:

* What data can be exported
* How portable applications are
* Whether APIs are portable
* How long migration would take
* What migration would cost
* What contractual restrictions exist
* What dependencies would prevent rapid migration

---

## Resilience Testing

Instead of simply documenting a disaster recovery plan, organizations should test it.

Example:

> **"Primary cloud provider becomes unavailable for six hours. What happens?"**

This connects the topic with tabletop exercises and cyber resilience.

---

# Interactive Simulation

A major component of the project will be a small **CISO decision-making simulation**.

## Scenario

A fictional organization called:

**RVU Digital Services**

depends on a single cloud provider.

```text
             RVU DIGITAL
                  │
       ┌──────────┼──────────┐
       ↓          ↓          ↓
      LMS        ERP       Payments
       │          │          │
       └──────────┼──────────┘
                  ↓
              CLOUD X
```

The audience is told:

> **"You are the CISO. Cloud X is currently hosting all three critical services."**

Then:

# CLOUD X BECOMES UNAVAILABLE

The audience chooses a response:

### A — Wait for recovery

### B — Fail over to another region

### C — Move critical services to another provider

### D — Activate hybrid/on-premises fallback

Each choice produces different:

* Recovery time
* Cost
* Availability
* Complexity
* Compliance implications
* Business impact

---

# Proposed Risk Dashboard

The simulation can display something similar to:

```text
CLOUD CONCENTRATION DASHBOARD

Critical Services:          8
Single Provider Dependency: HIGH
Portability:                LOW
Alternate Provider:         NONE
Recovery Capability:        MEDIUM

OVERALL CONCENTRATION:      HIGH
```

The audience can then modify the architecture and observe how the risk changes.

For example:

```text
Single Cloud
     ↓
Provider Dependency: HIGH

Add Second Provider
     ↓
Provider Dependency: LOWER
Cost/Complexity: HIGHER
```

This demonstrates an important GRC principle:

> **Risk reduction usually involves trade-offs rather than a perfect solution.**

---

# Possible Future Extension

The simulation can eventually be expanded into a small browser-based interactive application with:

* Enterprise dependency map
* Cloud-provider status
* Failure injection
* Risk scoring
* Business impact calculation
* Recovery timer
* Compliance-impact indicators
* Architecture selection
* Multi-cloud/hybrid options
* Resilience score
* Final CISO decision report

The initial classroom version should remain simple enough to operate within the 5-minute presentation.

---

# Recommended Presentation Ending

The presentation should conclude with:

> **"If your business has ten applications but all of them depend on the same provider, do you really have ten independent systems?"**

Final takeaway:

> **"Cloud concentration risk isn't about whether the cloud is secure. It's about what happens when everyone depends on the same cloud."**

---

# Syllabus Alignment

The project connects primarily to:

### Module 4

* Cloud concentration risk
* Global threat landscape
* Emerging cyber paradigms

### Module 2

* Cyber risk lifecycle
* Risk identification
* Risk scoring limitations
* Supply Chain & Third-Party Risk Management
* Risk appetite vs. risk tolerance
* Risk quantification concepts

### Module 3

* Security controls
* Control assurance and testing
* Cloud Posture Management
* SaaS security
* Cloud security architecture

### Module 5

* Cyber resilience
* Business continuity planning
* Disaster recovery
* Cyber recovery
* Cyber Range and Tabletop Exercises

---

# Project Status

### Current Stage

* [x] Topic selected
* [x] Syllabus alignment identified
* [x] Presentation storyline designed
* [x] AWS case study selected
* [x] Cloudflare case study selected
* [x] Risk categories identified
* [x] Governance/compliance angle defined
* [x] Mitigation strategies identified
* [x] Interactive simulation concept designed
* [ ] Verify final case-study facts from primary sources
* [ ] Build final PPT
* [ ] Build interactive simulation
* [ ] Conduct 5-minute rehearsal
* [ ] Optimize timing

---

# Important Presentation Rule

The presentation is only **5 minutes**.

Therefore:

* Avoid excessive history.
* Avoid explaining cloud computing from scratch.
* Avoid too many case studies.
* Avoid long regulatory definitions.
* Avoid overly technical cloud architecture.

Focus on:

> **One concept → two real incidents → one governance problem → one interactive simulation → one memorable conclusion.**

---

# Final Topic

## Cloud Concentration Risk: The Hidden Single Point of Failure in Modern Enterprises

### Core message

> **A system can be individually secure and still be collectively vulnerable when too many critical services depend on the same underlying provider.**
