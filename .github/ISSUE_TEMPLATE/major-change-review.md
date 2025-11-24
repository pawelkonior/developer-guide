---
name: "Major Change Review"
about: "Formal review of a major change impacting architecture, SDLC, security, or compliance."
title: "[MAJOR REVIEW] <short descriptive title>"
labels: ["major-change", "review-required"]
assignees: []
---

<!--
Developer Guide – Major Change Review Template
Classification: Internal – Engineering Standards

Use this template when:
- An accepted RFC requires formal review before implementation, OR
- Maintainers/Tech Lead identify a change as major during triage, OR
- A PR introduces architectural, SDLC, security, or compliance impact.
-->

# 1. Summary

Provide a short summary (2–4 sentences):

- What is being changed?
- Why is this considered a major change?
- What is the expected outcome?

---

# 2. Linked Items

- **RFC (if applicable):**  
  - ID / Link:  

- **Original Proposal Issue:**  
  - #  

- **Corresponding PR (if already created):**  
  - #

- **Related internal tickets / architecture decisions:**  
  - 

---

# 3. Change Classification Verification

Maintainers must confirm that this change meets the definition of a **Major Change**.

Select all that apply:

- [ ] Introduces or modifies a `[REQUIRED]` rule  
- [ ] Impacts architecture or design baseline  
- [ ] Alters SDLC processes or CI/CD gating  
- [ ] Introduces breaking changes  
- [ ] Requires cross-team or organization-wide adoption  
- [ ] Has security implications  
- [ ] Has regulatory/compliance implications (SOX, PCI-DSS, DORA)  
- [ ] Has migration/operational overhead  
- [ ] Other (describe):

Provide summary justification:

- 

---

# 4. Impact Assessment

## 4.1 Team / Domain Impact
Which groups will be affected?

- [ ] Single team  
- [ ] Multiple teams (same domain)  
- [ ] Multiple domains  
- [ ] Organization-wide  
- Description:

## 4.2 Technical Impact
Describe expected technical changes:

- architecture impact:  
- patterns affected:  
- CI/CD impacts:  
- testing strategy impacts:  
- other:

## 4.3 Operational Impact
- runtime impact:  
- deployment changes:  
- maintenance implications:  
- rollback complexity:

## 4.4 Migration Impact
Does this require migration?

- [ ] Yes  
- [ ] No  
If Yes:  
- high-level steps:  
- estimated effort:  
- tech debt generated (if any):

## 4.5 Risk Summary
Indicate risk categories involved:

- [ ] Technical  
- [ ] Operational  
- [ ] Security  
- [ ] Compliance  
- [ ] Delivery timelines  
- [ ] Stakeholder misalignment  

Describe risks:

---

# 5. Security & Compliance

Does this change alter or introduce requirements related to:

## Security Posture
- [ ] SAST/DAST/SCA requirements  
- [ ] Dependency policies  
- [ ] Secrets management  
- [ ] Access control / roles  
- [ ] Threat model / attack surface

Explain:

## Compliance / Regulatory Impact
- [ ] SOX  
- [ ] PCI-DSS  
- [ ] DORA  
- [ ] Internal governance  
- [ ] Audit requirements  

Explain:

---

# 6. Alternatives Considered

Summarize alternatives explored in the RFC or during discussion:

- Alternative 1:  
  - Reason rejected:
- Alternative 2:
  - Reason rejected:
- Alternative 3 (if any):

If none exist:

> No reasonable alternatives identified at this time.

---

# 7. Maintainer Review (Technical)

Maintainers must complete this section:

### Maintainer Technical Review Summary
- Alignment with Developer Guide?  
- Conflicts with existing standards?  
- Correctness and clarity?  
- Required updates to related documents?  
- CI/CD and tooling implications?

Maintainer comments:

- 

Maintainer decision:  
- [ ] Recommend Approval  
- [ ] Recommend Rejection  
- [ ] Recommend Revision  

Maintainer signature (GitHub handle):  

---

# 8. Tech Lead Review (Strategic & Compliance)

Tech Lead must complete this section:

### Tech Lead Review Summary
Address:

- architectural alignment  
- SDLC alignment  
- security posture  
- compliance and regulatory considerations  
- organizational impact  
- risk acceptance  

Tech Lead comments:

- 

Tech Lead final decision:  
- [ ] **Approved**  
- [ ] **Rejected**  
- [ ] **Requires RFC revision**  
- [ ] **Requires additional stakeholder input**  

Tech Lead signature (GitHub handle):  

---

# 9. Required Follow-Up Actions

This section defines what must happen after review:

- [ ] Update RFC  
- [ ] Update Developer Guide  
- [ ] Update supporting documentation  
- [ ] Notify impacted teams  
- [ ] Create migration playbook  
- [ ] Update CI/CD templates  
- [ ] Schedule architecture review  
- [ ] Other:  

List assigned owners and deadlines:

| Action | Owner | Due Date |
|--------|--------|----------|
|        |        |          |

---

# 10. Final Notes

Add final comments, context, or decisions not covered in other sections:

- 

---

Thank you for completing this Major Change Review.  
All decisions must be consistent with the **Developer Guide Change Management Policy**.