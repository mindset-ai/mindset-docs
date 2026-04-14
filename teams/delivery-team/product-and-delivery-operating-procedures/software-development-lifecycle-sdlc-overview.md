# Software Development Lifecycle (SDLC) Overview

### Purpose

This document defines Mindset AI Ltd's software development lifecycle and shows how information security is integrated throughout the development process from initial concept through production operations.

### SDLC Phases Overview

Mindset AI Ltd follows a 6-phase SDLC that integrates security, quality assurance, and change management at every stage:

| Phase                  | Purpose                                                                                              | Outputs                                                     |
| ---------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Product document       | Problem statement, Personas, Business justification, Risk review                                     | Product document, Epic                                      |
| UX plan                | User flows, interface concepts, rough UX guidelines, Initial security review                         | UX documentation, Security notes                            |
| Specification document | Detailed feature requirements, acceptance criteria, functional specifications, Security requirements | Specification document                                      |
| Implementation plan    | Technical architecture, detailed design, implementation approach, Secure design architecture         | Implementation plan, Implementation issue tickets (Stories) |
| Delivery               | Implementation, testing, deployment to production, Security testing                                  | Product updates                                             |
| Operations             | Ongoing monitoring, maintenance, incident response, continuous improvement                           | Ongoing product and process improvements                    |

### Phase 1: Product Document

**Primary Focus:** Problem statements, use cases, business justification

**Key Outputs:**

* Product vision and business case
* Initial risk assessment (if material changes to security posture)
* Data classification requirements

**Applicable Policies:**

* Risk Management Policy
* Data Management Policy

### Phase 2: UX Plan

**Primary Focus:** User flows, interface concepts, rough UX guidelines

**Security Activities:**

* Privacy-by-design considerations (data minimization, consent flows)
* Authentication and authorization requirements
* Sensitive data display considerations
* Accessibility and security balance

**Key Outputs:**

* User flow diagrams
* Interface concepts
* UX guidelines with privacy considerations

**Applicable Policies:**

* Secure Development Policy (privacy-by-design principles)
* Data Management Policy (data handling in UI)

**Gate Criteria:** UX concept approval, security requirements identified

### Phase 3: Specification Document (Requirements)

**Primary Focus:** Detailed feature requirements, acceptance criteria, functional specifications

**Security Activities:**

* Detailed security requirements definition
* Threat modeling for new functionality
* Data flow analysis and classification
* Access control requirements
* Integration security requirements

**Key Outputs:**

* GitLab Epic with detailed requirements
* Acceptance criteria including security requirements
* Identified security controls to be implemented

**Applicable Policies:**

* Secure Development Policy (secure engineering principles)
* Access Control Policy (access requirements)
* Data Management Policy (data classification and handling)

**Gate Criteria:** Requirements approved, security requirements documented, Epic created

### Phase 4: Implementation Plan (Design)

**Primary Focus:** Technical architecture, detailed design, implementation approach

**Security Activities:**

* Application of secure-by-design principles
* Architecture review for security implications
* Cryptography approach (if applicable)
* API security design
* Infrastructure security requirements
* Impact assessment for existing systems

**Key Outputs:**

* Technical design documentation
* Security architecture decisions
* Implementation plan with security controls
* Change impact assessment

**Applicable Policies:**

* Secure Development Policy (secure engineering principles)
* Cryptography Policy (encryption requirements)
* Operations Security Policy (infrastructure standards)
* Change Management Procedure (impact assessment)

**Gate Criteria:** Design approved, security architecture validated, implementation plan documented

### Phase 5: Delivery (Development, Testing, Deployment)

**Primary Focus:** Implementation, testing, deployment to production

This is the most controlled phase with multiple quality gates and security validations.

#### 5.1 Development

**Activities:**

* Code implementation following secure coding standards
* Version control in GitLab
* Local testing and security consideration
* Commit to feature branch

**Applicable Policies:**

* Secure Development Policy (coding standards, version control)
* Change Management Procedure

#### 5.2 Integration and Testing

**Activities:**

* Merge request creation with impact assessment
* Automated testing (unit tests, API tests where configured)
* Security scanning (SAST, dependency scanning, container scanning)
* Code review by qualified team member
* Manual testing across environments (Development → Integration → Staging)
* GitLab ticket state progression documenting test completion

**Quality Gate:** Merge Request Approval

* All pipeline tests pass
* Security scans complete (no critical/high vulnerabilities introduced)
* Code review approval from team lead
* Testing verified via GitLab ticket state and comments
* Change impact assessment documented

**Applicable Policies:**

* Change Management Procedure
* QA Process Documentation
* Secure Development Policy (vulnerability management)
* Operations Security Policy (vulnerability SLAs)

#### 5.3 Deployment

**Activities:**

* Weekly deployment cycle
* Cross-functional go/no-go decision
* Production deployment per change management procedure
* Monitoring and validation
* Deploy review ticket creation (within 1 week)

**Quality Gate:** Production Deployment Approval

* Staging validation complete
* Weekly go/no-go approval from cross-functional team (Tech Leads, Product Managers, Test Leads)
* Documented in #deployment-status Slack channel
* Evaluation based on quality, performance, security, functionality

**Applicable Policies:**

* Change Management Procedure
* Deploy Review Process Guide

**Emergency Changes (Hotfixes):**

* Expedited workflow: Branch from release → Test on staging → Deploy → Merge to develop
* Same approval requirements but accelerated timeline
* Post-implementation review required within 48 hours

### Phase 6: Operations

**Primary Focus:** Ongoing monitoring, maintenance, incident response, continuous improvement

**Security Activities:**

* System monitoring and logging
* Deploy review and validation (within 1 week of deployment)
* Security incident monitoring and response
* Vulnerability management and patching
* Access reviews and compliance monitoring
* Continuous improvement and lessons learned

**Key Outputs:**

* Deploy review tickets documenting post-deployment validation
* Incident response records (if applicable)
* Vulnerability remediation tickets
* Quarterly access reviews
* Lessons learned and process improvements

**Applicable Policies:**

* Deploy Review Process Guide
* Operations Security Policy (monitoring, logging, vulnerability management)
* Incident Response Plan
* Access Control Policy (quarterly access reviews)
* Change Management Procedure (continuous improvement)

**Ongoing Activities:**

* Monitor system performance and security alerts
* Respond to incidents per Incident Response Plan
* Remediate vulnerabilities per Operations Security Policy SLAs
* Review and update documentation
* Capture lessons learned for process improvement

### Security Integration Throughout SDLC

Security is implemented throughout the SDLC.

See [secure-software-development-practices.md](development-practices/secure-software-development-practices.md "mention") for summary of practices followed and the [secure-engineering-principles-and-planning.md](development-practices/secure-engineering-principles-and-planning.md "mention") for detailed requirements at each stage of the process, and practical guides for implementation.

### Quality Gates Summary

| Gate                           | Phase                               | Criteria                                        | Evidence                         |
| ------------------------------ | ----------------------------------- | ----------------------------------------------- | -------------------------------- |
| **Concept Approval**           | Product Document → UX Plan          | Business justification, initial risk review     | Epic/product docs                |
| **Requirements Approval**      | Specification → Implementation Plan | Security requirements defined, Epic created     | GitLab Epic                      |
| **Design Approval**            | Implementation Plan → Delivery      | Architecture reviewed, impact assessed          | Implementation plan              |
| **Merge Request Approval**     | Development → Integration           | Tests pass, security scans clear, code reviewed | GitLab MR, pipeline logs         |
| **Production Deployment**      | Testing → Production                | Staging validated, go/no-go approval            | Slack #deployment-status, GitLab |
| **Post-Deployment Validation** | Delivery → Operations               | Deploy review completed                         | Deploy review ticket             |

### Issue type breakdown

| Issue/Ticket type | Definition/Purpose                                                                  |
| ----------------- | ----------------------------------------------------------------------------------- |
| **Epics**         | strategic, large features                                                           |
| Stories           | Functional changes                                                                  |
| Bugs              | Quality issues                                                                      |
| Tasks             | Breakdown of functional changes if required                                         |
| Jobs              | Activities that do not result in technical change e.g. documentation, investigation |
| Spike             | Technical POC or exploration                                                        |
| Hot fix           | Critical patch                                                                      |
| Rollback          | Rollback actions and review                                                         |
| Deploy review     | Deployment review process                                                           |

### Roles and Responsibilities

| Role                | SDLC Responsibilities                                                         |
| ------------------- | ----------------------------------------------------------------------------- |
| **CTO**             | SDLC policy owner, design review, exception approvals                         |
| **Product Team**    | Product documents, specifications, acceptance criteria                        |
| **UX Team**         | User flows, interface design with privacy considerations                      |
| **Tech Leads**      | Architecture review, design approval, code review, go/no-go approval          |
| **Developers**      | Implementation, testing, security best practices, GitLab documentation        |
| **DevOps**          | Infrastructure implementation, CI/CD pipelines, security scanning, deployment |
| **Release Manager** | Deployment coordination, go/no-go facilitation, deploy reviews                |
| **QA Team**         | Test planning, execution, validation, go/no-go input                          |

### Evidence and Audit Trail

The SDLC process produces comprehensive evidence for compliance auditing:

| SDLC Phase           | Evidence Type                              | Location                     |
| -------------------- | ------------------------------------------ | ---------------------------- |
| Product/Requirements | Epic documentation                         | GitLab Epics                 |
| Specification        | Requirements, acceptance criteria          | GitLab Issues                |
| Design               | Design docs, impact assessments            | GitLab, Google Drive         |
| Development          | Code commits, commit messages              | GitLab repository            |
| Testing              | Pipeline logs, test results, ticket states | GitLab CI/CD, Issues         |
| Code Review          | Merge requests, approvals                  | GitLab MRs                   |
| Security Scanning    | SAST, dependency, container scans          | GitLab Security Dashboard    |
| Deployment Approval  | Weekly go/no-go decisions                  | Slack #deployment-status     |
| Deployment           | Deployment logs, release tags              | GitLab CI/CD, repository     |
| Post-Deployment      | Deploy review tickets                      | GitLab (type::deploy review) |
| Operations           | Monitoring logs, incident records          | GCP, GitLab Issues           |

### Relationship to Other Procedures

This SDLC Overview provides the framework. Detailed procedures are documented separately:

* [development-practices](development-practices/ "mention")
* [qa-process-documentation.md](qa-process-documentation.md "mention")
* [infrastructure-configuration-procedures.md](development-practices/infrastructure-configuration-procedures.md "mention")
* [secure-engineering-principles-and-planning.md](development-practices/secure-engineering-principles-and-planning.md "mention")

Supporting policies:

* Change Management Procedure
* Secure Development Policy
* Operations Security Policy
* Access Control Policy
* Data Management Policy
* Risk Management Policy
* Cryptography Policy

### Continuous Improvement

The SDLC process is reviewed and improved through:

* Deploy review lessons learned
* Post-mortem analysis of incidents
* Quarterly change management metrics review
* Annual policy and procedure reviews
* Feedback from development team
* Audit findings and recommendations

**Next Review:** October 2026

***

### Version History

| Version | Date             | Description           | Author     | Approver   |
| ------- | ---------------- | --------------------- | ---------- | ---------- |
| 1.0     | October 14, 2025 | Initial SDLC overview | Will Evans | Will Evans |

**Document Owner:** Will Evans, CTO\
**Effective Date:** October 14, 2025\
**Version:** 1.0\
**ISO 27001:2022 Controls:** A.8.25 (Secure Development Lifecycle), A.8.32 (Change Management)
