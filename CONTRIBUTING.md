
# Introduction

Contributing to the Developer Guide is a careful process, as any changes can impact all development teams and potentially the quality and compliance of code across the organization. This document outlines the steps and requirements for proposing changes to the guidelines or associated configuration in this repository. All contributors are expected to follow this process to ensure that modifications are reviewed appropriately and maintain the high standards of our Fortune 100 banking environment.

By adhering to a formal contribution workflow with multiple levels of review, we ensure that any updates to our coding standards are vetted for technical accuracy, clarity, and alignment with regulatory or security requirements. No change is trivial – even small edits must be reviewed under this process, because the Developer Guide serves as an authoritative reference for many teams.

## Roles and Responsibilities

### Several roles are involved in the maintenance and update process for the Developer Guide:
	
  - **Contributor (Author)**: Any employee proposing a change. Contributors are responsible for understanding the existing guidelines, ensuring their proposal is well-justified, and following all steps in this contributing guide. This includes creating clear documentation and rationale for the change.

  - **Reviewer**: Experienced developers or subject matter experts who perform the initial review of contributions. Reviewers verify the technical soundness of the change, ensure it does not conflict with other guidelines, and validate that the reasoning is solid. In many cases, at least one Reviewer should be someone from a relevant domain (for example, a FastAPI expert should review changes to API guidelines).

  - **Maintainer/Tech Lead**: Senior engineers designated as maintainers of the Developer Guide (often Tech Leads from the Architecture or Engineering Excellence team). Maintainers have the authority to approve or reject changes after review. They ensure that changes align with the broader vision and compliance requirements of the organization. Maintainers also resolve any disputes in review and make final decisions when consensus cannot be reached by the Reviewers.

  - **Compliance/Security Officer** (as applicable): While not every change will involve them, any update that touches on security practices or could have regulatory implications may require input or approval from a compliance officer or application security specialist. Maintainers will coordinate this when needed (e.g., introducing a new mandatory security rule might trigger a review by a security team representative).

Each role has an important responsibility to uphold the integrity of the guide. The multi-tier review (Reviewer approval followed by Maintainer approval) ensures both technical accuracy and strategic alignment.

### Before You Begin

1. Discuss the Idea: It is recommended (especially for significant proposals) to first discuss your idea with a Tech Lead or Maintainer, or with the team via an issue in this repository. Early feedback can save time. If the change is minor (typo fixes, clarifications), discussion can be brief or skipped, but for anything that introduces a new guideline or alters the meaning of an existing one, getting buy-in conceptually is wise.

2. Check Existing Guidelines: Ensure that your proposal doesn’t duplicate or conflict with content already in the Developer Guide. If it touches related areas, be prepared to update those for consistency. For example, if proposing a new mandatory rule about handling secrets, verify if a similar rule exists in the security guidelines section.

3. Impact Assessment: Consider the impact of your change. Would it make any currently compliant projects non-compliant? If so, how should teams adapt? If your change is introducing a new mandatory practice, be ready to justify the benefit and possibly propose a rollout plan (for instance, if code changes will be needed in many repositories, perhaps the rule should start as “Recommended” and later be elevated to “Mandatory”).

### Contribution Workflow

Follow these steps to contribute:

1. Fork & Branch: If you have write access to the repository, create a new branch off the main branch (do not commit directly to main). If not, fork the repository to your own account and then create a branch. Name the branch descriptively, for example: guideline-update-logging-standards or fastapi-new-rule-response-model. Branch naming should be consistent with internal conventions (e.g., include any relevant Jira ticket ID or task number if applicable).

2. Implement the Change: Make your edits or additions:
  - If adding a new guideline section or file, follow the structural and tonal conventions used elsewhere in the guide. Use proper Markdown headings and include Mandatory/Recommended/Optional labels as appropriate.
  - If modifying text, ensure the surrounding content still flows well and update any related references. For example, if you change a rule’s status from Recommended to Mandatory, update any summary tables or other sections that might mention it.
  - Keep changes focused: each pull request should aim to address one topic or a cohesive set of changes. Avoid bundling unrelated edits.
  
3. Run Checks Locally: Before committing, run the pre-commit hooks and linters. This repository’s configuration will automatically format the Markdown (where applicable) and check for issues:
  - Ensure no Markdown lint or formatting issues are introduced (e.g., line lengths, trailing whitespace are handled by the hooks).
  - If you edited any example code within the guide, verify it still follows our Python style (the pre-commit will run Ruff/Black on code snippets if properly fenced, or you may manually run the linters on any embedded code).
  - Build or preview the Markdown to ensure new sections render correctly.
  
4. Commit Changes: Use clear and concise commit messages. Since this is an internal repository, conventional commit formats or similar can be used if desired (e.g., “docs: clarify logging guideline severity”). Commit messages become part of the permanent history, so they should accurately describe what changed and why. Do not include sensitive information in commit messages.

5. Push and Open a Pull Request (PR): Push your branch to the remote (or your fork) and open a PR against the main branch of the Developer Guide repository. The PR description must follow the template (which will be auto-filled from .github/PULL_REQUEST_TEMPLATE.md). Fill out each section of the template diligently:
  - Provide a clear description of the change and the rationale behind it. Explain why this change is needed – e.g., “We observed inconsistent logging in services, causing difficulty in debugging; this guideline adds a mandatory structure for log messages.”
  - Classify the change (new guideline vs. modification, and its severity level as Mandatory/Recommended/Optional as applicable).
  - Complete the checklist to confirm you’ve followed the process (including running linters, etc.).
  - If the change is linked to an issue or incident, reference it (e.g., “Closes #123” or internal ticket links) for context.
  
6. Automated CI Checks: When you open the PR, the Lint & Format GitHub Action (lint-check.yml) will run. It will automatically execute our linters (Ruff, Black, etc.) and ensure the repository still passes all checks. You must fix any CI failures before requesting reviews. For example, if CI reports that a line in your addition is too long or an embedded code example has a lint violation, adjust the content accordingly.

7. Review by Peers/Experts: Once your PR is ready (CI passing, description complete), request reviews. At a minimum, two approvals are required:
  - At least one Reviewer (peer developer or subject expert) should review and approve.
  - At least one Maintainer/Tech Lead must review and approve. (The Maintainer may require multiple reviewers in practice; for example, one from the API team and one from the Security team if a guideline touches both areas.)
  
8, Incorporate Feedback: Commit additional changes to your branch to address review comments. Ensure each iteration of the PR passes CI. Use the GitHub conversation features to resolve comments once addressed. If a debate arises that cannot be resolved through comments alone, consider setting up a meeting with the involved parties (including a Maintainer) to discuss the concerns in detail.

9. Approval and Merge: After at least the required number of approvals are obtained (and all reviewers’ concerns are resolved), a Maintainer will perform the merge. Typically, we use the “Squash and Merge” strategy for this repository to keep history clean (each PR becomes one commit in the main branch), unless the change is complex and warrants preserving intermediate commits. The Maintainer merging the PR will ensure the commit message is tidy and references any relevant issue numbers.
  - Note: The main branch is protected; it requires the above approvals and passing status checks. Only Maintainers (and authorized Tech Leads) have the permissions to override, and overrides are only used in exceptional cases.
  
10. Post-Merge Follow-Up: After a change is merged, the Maintainers may tag a new release or version of the Developer Guide if your organization version-controls the guide (for example, “v1.2” of the coding standards). Teams will be notified of significant updates. If your change was major (like introducing a new mandatory guideline), consider preparing an internal communication or presentation to educate developers on the new standard.

### Decision Protocol and Escalation

Our process is designed to build consensus, but sometimes disagreements on guidelines can occur (for example, whether something should be Mandatory vs Recommended). In such cases:

  - Initial Resolution: The Maintainer facilitating the PR will attempt to mediate based on engineering principles, impact, and evidence. All discussions should remain technical and fact-based. We encourage citing examples, data, or external standards to support a position.
  - Team Consultation: The Maintainer may involve additional senior engineers or architects for a broader perspective. This could involve a quick design review session or consulting an Architecture Review Board if one exists for development standards.
  - Final Decision: Ultimately, the Maintainers group has the authority to make a final decision. The Tech Lead (or designated lead Maintainer for this repository) will make the call if consensus cannot be reached. Once a decision is made, the contributor should accept it graciously. If the proposal is rejected or requires significant rework, the Maintainer will close the PR with a clear explanation or ask for it to be resubmitted after specific changes.

It’s important to remember that all participants share the same goal – improving our development practices. Decisions are made with the organization’s best interests in mind, balancing innovation with stability and compliance.

### Coding and Writing Standards for Contributions

When contributing to the Developer Guide, please maintain the same high standards in writing as in coding:
  - Tone: Use a formal, instructive tone. The text should remain clear and concise. Avoid slang, colloquialisms, or any informal language. Remember that this document is read by a wide audience, potentially including auditors or new hires, so it should be professional and authoritative.
  - Clarity: Define any abbreviations or acronyms on first use (for instance, if mentioning “CI/CD” or “OWASP”, ensure they are explained or well-known in context). Our aim is that even less experienced developers can understand the guidelines without ambiguity.
  - Consistency: Follow the existing style for headings, lists, and examples. For example, if other sections use bullet points to list dos and don’ts, follow that pattern. Use Markdown formatting appropriately (back-ticks for code, bold for emphasis on must/should, etc.).
  - Internal References: If referring to other sections of the guide, link to them. For example, “(see the Testing guidelines section)” can be a link to the relevant file or section. This makes navigation easier.
  - External References: Avoid linking to external resources that might not be accessible to all readers (or that may change). If an external standard or document is highly relevant, mention it by name (e.g., “PEP 8 style guide”) and ensure the context is clear. For legal or compliance-related information, rely on internal policy documents rather than external sites.

All contributions are subject to the same linters and formatters. In particular, Markdown files are checked for formatting issues. If your contribution includes code examples, note that our CI may run linting on those snippets to ensure they meet the style (this is done by design to ensure examples practice what we preach).

### Acknowledgments

We value and encourage contributions to this repository. Improving our Developer Guide is a collaborative effort that benefits everyone. By following this CONTRIBUTING process, you help maintain the quality and reliability of our standards. We appreciate your time and effort in adhering to these guidelines and making thoughtful, well-documented proposals.

If you have any questions about this process or need guidance on preparing a contribution, please reach out to a Maintainer (you can find the list of Maintainers in the CODEOWNERS file or ask within our internal developer community). We are here to help and ensure that your contributions are successful.

Thank you for helping to keep our development standards excellent and up-to-date.