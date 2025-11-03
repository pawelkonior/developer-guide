Overview

This Developer Guide repository provides a comprehensive set of coding standards and best practices for Python projects at the company. It is tailored for building and maintaining enterprise-grade applications in a highly regulated financial environment. All developers and teams should adhere to these guidelines to ensure code quality, security, and compliance with internal policies. By following a consistent approach to coding and using the provided tools, we aim to reduce defects, ease maintenance, and satisfy rigorous audit and regulatory expectations.

Purpose and Scope

The primary purpose of this repository is to standardize development practices across the organization. It covers guidelines on Python coding style, project structure, API design with FastAPI, documentation standards, testing practices, and more. Each guideline is crafted to align with industry best practices (such as PEP 8 for Python style) while reflecting the company’s specific quality and compliance requirements. This guide is considered a living document: it will evolve as tools and standards advance. All Python developers (including those working on FastAPI microservices) are expected to familiarize themselves with these recommendations and integrate them into their daily workflow.

Key objectives include:
	•	Ensuring consistency in code style and project structure across teams.
	•	Enforcing strict linting and formatting standards using automated tools (e.g. Ruff, Black, isort) to catch issues early.
	•	Promoting secure and robust code by including guidelines for error handling, input validation, and other practices pertinent to financial systems.
	•	Streamlining code reviews by providing a common understanding of what constitutes acceptable code, thereby reducing subjective debates.

Guideline Categories

Not all rules carry equal weight. For clarity, each guideline in this repository is labeled with a classification indicating its importance and enforcement level:
	•	Mandatory – Must be followed without exception. These are critical rules (often related to security, correctness, or compliance) that all code must adhere to. Violations of mandatory guidelines will typically result in pipeline failures or rejection of pull requests until corrected.
	•	Recommended – Should be followed in most circumstances. These represent strong best practices that developers are expected to apply unless there is a compelling reason not to. Deviations should be rare and might require approval from a Tech Lead or Maintainer, with rationale documented.
	•	Optional – May be followed at the developer’s discretion. These cover suggestions and tips that can improve code quality or readability but are not strictly required. Developers are encouraged to consider optional guidelines, but non-adherence will not be treated as an error.

This categorization helps teams prioritize compliance efforts, focusing on what is absolutely required versus what is advised. Each guideline document clearly marks rules with (Mandatory), (Recommended), or (Optional) tags accordingly.

Repository Structure

The repository is organized to make navigation intuitive. Major components include:
	•	guidelines/ Directory: Contains topic-specific markdown files for various domains of our standards. For example:
	•	guidelines/python_style.md – Python language style guide (naming conventions, formatting rules, etc.).
	•	guidelines/fastapi_best_practices.md – Guidelines specific to building APIs with FastAPI (project layout, router structure, dependency injection patterns, etc.).
	•	guidelines/testing.md – Best practices for unit, integration, and end-to-end testing.
	•	guidelines/security.md – Secure coding guidelines (common pitfalls to avoid, handling secrets, input sanitization).
	•	(Additional files may exist for other topics, such as database access patterns, logging standards, etc.)
	•	Configuration Files: These are the tools that enforce or support the guidelines.
	•	pyproject.toml – Configuration for development tools (like Ruff for linting). It encodes the agreed-upon coding style (e.g., line lengths, target Python version) and lint rules that correspond to our guidelines.
	•	.pre-commit-config.yaml – Defines git pre-commit hooks used to automatically format code and check for guideline compliance before code is committed or pushed. This includes hooks for linting (Ruff), formatting (Black, isort), YAML validation, and other sanity checks.
	•	.github/PULL_REQUEST_TEMPLATE.md – The pull request template developers must fill out when proposing changes to this repository (or by extension, to any project adhering to this guide). It includes a checklist to ensure the contributor has followed the process and considered guideline implications of their change.
	•	CONTRIBUTING.md – Detailed contribution guidelines for proposing changes to the Developer Guide itself. It describes the review process, roles, and responsibilities (e.g. Maintainers, Tech Leads) required for approving changes to these standards.

All documentation files are written in Markdown for easy reading. Diagrams or images (if any) illustrating best practices would reside in a media/ folder and be referenced appropriately.

Using the Developer Guide

For Developers: When starting a new project or contributing to an existing one, use this guide as the baseline for your development. Key steps to using the guide effectively include:
	1.	Initial Setup: Incorporate the provided configuration files (linters, formatters, hooks, CI workflows) into your project. This ensures that many guideline aspects (formatting, import sorting, basic lint checks) are automatically enforced. For example, by using the provided pyproject.toml and pre-commit hooks, your code editor/IDE and git will auto-format code to the standard and flag disallowed patterns.
	2.	During Development: Follow the guidelines in the relevant sections. For instance, when writing a FastAPI endpoint, refer to FastAPI Best Practices to structure your router and use dependency injection as recommended. When writing any Python code, adhere to the naming conventions and code style rules in Python Style Guide. Treat mandatory rules as requirements and recommended rules as default behavior.
	3.	Pre-commit and Pre-push: Install the pre-commit hooks (by running pre-commit install in your repository) to catch issues early. Before pushing code, ensure that running pre-commit run --all-files passes without errors. This will apply auto-formatting (via Black and isort) and run Ruff linting. Address any issues reported by these tools.
	4.	Code Review: When reviewing peers’ code, use this guide as the reference. Reviewers should check that the changes do not violate any mandatory guidelines and that the spirit of recommended guidelines is upheld. The presence of automated checks will assist in this, but manual oversight for more complex or architectural guidelines is necessary.
	5.	Deviation and Exceptions: If a situation arises where adhering to a guideline is impractical or would cause significant harm, the team can decide on an exception. All exceptions to mandatory guidelines must be approved by a Maintainer or Tech Lead and should be documented (for example, as a comment in code or in the project’s documentation) explaining the rationale. Such cases should be very rare and might prompt a re-evaluation of the guideline if the scenario is general enough.

For Project Leads and Maintainers: Ensure that your project’s CI pipeline includes the lint-check.yml (or an equivalent job) so that all pull requests are automatically checked for compliance. Enforce branch protection rules on the main branch so that merges require:
	•	Passing status checks (the linter/formatter workflow and any other test workflows).
	•	Approval from designated code owners or reviewers who are knowledgeable about these guidelines.

Continuous Improvement

This Developer Guide is maintained by the Engineering Excellence team (which includes senior engineers, Tech Leads, and domain experts). We recognize that standards may need to evolve as technology and frameworks change. We encourage developers to propose improvements or updates to the guide when necessary.

Significant changes to mandatory guidelines will be made cautiously and typically require broad agreement. Any update will be communicated across development teams, and versioning of the guide may be used for tracking. Always refer to the latest version of this repository for the current rules.

If you have suggestions, please review the CONTRIBUTING.md￼ for the process to propose changes. Collaboration in refining these standards is welcome – our collective experience will keep the guidelines effective and relevant.

Conclusion

By consolidating these best practices and tools, the Developer Guide ensures that our software development remains consistent, high-quality, and compliant. Adhering to these guidelines will result in more maintainable codebases, smoother code reviews, and fewer production issues. In a financial context where reliability and traceability are paramount, following the Developer Guide is not only about code style—it is about operational excellence and risk mitigation. All team members, from new hires to senior engineers, share the responsibility of upholding these standards and contributing to a culture of quality in code. Thank you for integrating this guide into your development workflow.