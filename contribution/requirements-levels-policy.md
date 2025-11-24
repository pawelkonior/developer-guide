# Requirements Levels Policy
**Classification:** Internal – Engineering Standards  
**Owner:** Architecture & Engineering Excellence Office  
**Last Updated:** YYYY-MM-DD

---

## 1. Purpose

This policy defines the mandatory classification system for all rules within the Developer Guide.
Every guideline MUST be assigned one of the approved **Requirement Levels**, ensuring clarity, enforceability, compliance alignment, and consistent interpretation across engineering teams.

The Requirement Levels outlined here are binding and must be applied to all new and existing standards.

---

## 2. Rationale

A controlled, tiered requirement system is essential in a regulated environment.
Without standardized levels, teams may:

- Misinterpret mandatory rules as optional
- Fail audits due to inconsistent application of standards
- Introduce architectural or security risk
- Diverge in SDLC practices across business units

This policy ensures uniform understanding and enforcement of engineering rules.

---

## 3. Requirement Levels Overview

All guidelines in the Developer Guide MUST be labeled with one of the following levels:

- **`[REQUIRED]`** – Mandatory
- **`[RECOMMENDED]`** – Strong Best Practice
- **`[OPTIONAL]`** – Advisory Guidance

Each level carries specific obligations described below.

---

## 4. Level Definitions and Enforcement

### 4.1 `[REQUIRED]` – Mandatory Standards
**Definition:**  
Rules that MUST be followed without exception unless a formal, approved exception is granted.

**Characteristics:**
- Enforceable via CI/CD pipelines, automated checks, architectural gates, or security tooling
- Required for regulatory alignment (e.g., SOX, PCI-DSS, DORA)
- Foundational to system safety, reliability, maintainability, or security

**Compliance Requirements:**
- Non-compliance is a standards violation.
- Exceptions require **written approval** from the **Tech Lead** and may require Security/Compliance involvement.
- Violations may trigger audit findings, corrective actions, or architecture review escalation.

**Examples of REQUIRED rules:**
- Minimum supported language version
- Mandatory secure coding practices
- Required CI checks (linting, tests, SAST)
- Required architecture patterns for regulated workloads

### 4.2 `[RECOMMENDED]` – Strong Best Practice
**Definition:**  
Rules that SHOULD be followed in most scenarios, but justified deviations are allowed.

**Characteristics:**
- Not enforced automatically, but strongly encouraged
- Intended to standardize high-quality engineering practices
- Deviations must be documented and justified in PR review comments

**Compliance Requirements:**
- Maintainers must confirm that any deviation has a reasonable technical justification.
- Repeated or unjustified deviations may escalate to Tech Lead review.

**Examples of RECOMMENDED rules:**
- Preferred logging patterns
- Recommended API naming conventions
- Preferred testing strategies
- Strong—but not mandatory—CI practices

### 4.3 `[OPTIONAL]` – Advisory Guidance
**Definition:**  
Guidance that MAY be followed at the discretion of the engineering team.

**Characteristics:**
- Intended to provide examples, inspiration, or patterns
- Zero enforcement, zero compliance expectations
- Cannot be used as a reason to block a PR

**Compliance Requirements:**
- None.
- Optional rules are not subject to enforcement or validation.

**Examples of OPTIONAL rules:**
- Stylistic preferences outside the enforced standard
- Recommended tooling for local workflows
- Illustrative examples used for teaching or documentation

---

## 5. Governance and Decision Rights

The following roles have the authority to assign or change requirement levels:

| Level | Contributor | Maintainer | Tech Lead |
|-------|-------------|------------|-----------|
| `[REQUIRED]` | Propose | Recommend | **Approve (mandatory)** |
| `[RECOMMENDED]` | Propose | **Approve** | Review if escalated |
| `[OPTIONAL]` | Propose | **Approve** | Optional review |

**Additional requirements:**

- Any escalation from `[RECOMMENDED]` → `[REQUIRED]` **requires a new RFC**.
- Any downgrade from `[REQUIRED]` → `[RECOMMENDED]`/`[OPTIONAL]` must include:
  - Risk analysis
  - Architectural review
  - Tech Lead approval

---

## 6. Enforcement Mechanisms

Mandatory rules MUST be enforced using one or more of the following:

- GitHub branch protection rules
- CI validation (e.g., linting, unit tests, SAST, dependency checks)
- Architectural review gates
- Automated compliance scripts
- Pipeline-enforced baselines (e.g., Python version verification)
- Code scanning tools (SAST/DAST)

Maintainers are responsible for ensuring `[REQUIRED]` rules are enforceable.

---

## 7. Documentation Requirements

Every guideline MUST include a visible requirement label directly in the document header or section heading:

Example:

```markdown
### Logging Requirements [REQUIRED]
### Testing Strategy for New Services
**Level:** RECOMMENDED
```

---

## 8. Change Control and RFC Requirements

An RFC is mandatory for:
- All new `[REQUIRED]` rules
- Any modification of a `[REQUIRED]` rule
- Demotion or removal of a `[REQUIRED]` rule
- Major restructuring of `[RECOMMENDED]`/`[OPTIONAL]` guidelines
- Any rule affecting architecture, SDLC controls, or compliance

No `[REQUIRED]` rule may be introduced, modified, or removed without Tech Lead approval.

---

## 9. Exception Management

Exception requests must include:
- Description of requested deviation
- Justification
- Risk assessment
- Proposed mitigation
- Scope and timeframe of exception

**Approval workflow:**
1. Maintainer: initial screening
2. Tech Lead: final approval
3. Security/Compliance: consulted if relevant

All granted exceptions must be time-bound and documented.

---

## 10. Audit Requirements

The following must be preserved for audit traceability:
- History of requirement-level modifications
- RFC documents linked to changes in `[REQUIRED]` rules
- PR review comments relating to deviations from `[RECOMMENDED]` rules
- Exception approvals and expiration dates
- CI logs demonstrating enforcement of `[REQUIRED]` rules