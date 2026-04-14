# Secure Engineering Principles & Planning

### 1. Introduction

This document establishes secure engineering principles for Mindset AI Ltd software development and system engineering activities. It defines how security is integrated throughout our Software Development Life Cycle (SDLC) in accordance with ISO 27001:2022 Controls A.8.27, A.8.28, and A.8.29.

Scope: All production software development, infrastructure design, system changes, and third-party integrations.

Related Policies: Secure Development Policy, Operations Security Policy, Change Management Procedure, Risk Management Policy, Data Management Policy.

***

### 2. Core Security Principles

#### 2.1 Secure-by-Design Principles

Mindset AI Ltd engineering decisions are guided by ten fundamental secure-by-design principles formalized in our Secure Development Policy and implemented through our GCP-native serverless architecture:

**Core Principles Applied:**

1. Minimize Attack Surface - Unnecessary services are disabled, production access is restricted to authorized DevOps and team leads only (Access Control Policy), and public API endpoints are limited to essential business functions.
2. Establish Secure Defaults - MFA is required by default for all privileged access, encryption at rest is enabled by default for all data stores, and default-deny network policies require explicit traffic allowance.
3. Principle of Least Privilege - Developers have read-only production access; write access requires explicit DevOps involvement and change management approval. IAM roles follow least-privilege as defined in Access Control Policy.
4. Defense in Depth - Customer data is protected by multiple layers: application authentication, database access controls, encryption (in transit and at rest), rate limiting, and audit logging. Compromise of any single layer does not expose data.
5. Fail Securely - Authentication failures default to access denied. If Firebase Authentication is unavailable, API requests are rejected rather than bypassing authentication checks. Errors do not expose sensitive information.
6. Don't Trust Services - All inputs and data from external sources (including internal services) are validated and sanitized. Data from mobile clients is validated against schemas before processing, regardless of authentication status.
7. Separation of Duties - Code changes require review and approval from someone other than the author (Change Management Procedure). No single person can deploy code to production unilaterally.
8. Avoid Security by Obscurity - API security relies on proper authentication tokens and authorization checks, not on undocumented endpoints or "secret" URL patterns. Security controls are documented and rely on strong authentication, authorization, and cryptography.
9. Keep Security Simple - We leverage GCP native security services and Firebase Authentication rather than building custom solutions, reducing maintenance burden and leveraging Google's security expertise.
10. Fix Security Issues Correctly - When vulnerabilities are identified, we perform root cause analysis, assess for similar patterns elsewhere in the codebase, fix all instances, and add tests to prevent regression (Secure Development Policy, Operations Security Policy).

These principles are implemented through existing policies (Access Control Policy, Operations Security Policy, Secure Development Policy) and verified through our technical architecture and change management processes.

<br>

#### 2.2 Privacy-by-Design Principles

As a data processor under GDPR acting on behalf of data controllers, Mindset AI Ltd integrates seven privacy-by-design principles formalized in our Secure Development Policy and implemented through our B2B2C architecture:

**Principles Applied:**

1. Proactive not Reactive - Privacy considerations are evaluated during Epic specifications and design phase before implementation. New user features explicitly evaluate what personal data is necessary and design to collect only the minimum.
2. Privacy as the Default Setting - Personal data is encrypted at rest by default (Cryptography Policy), access requires explicit authorization, and data retention policies automatically delete data when no longer needed (Data Management Policy) without manual intervention.
3. Privacy Embedded into Design - Firebase Authentication is integrated from initial system design to ensure all customer data access requires authentication, rather than retrofitting security controls after implementation.
4. Full Functionality - Positive-Sum - Analytics provide customers with necessary user-level insights while implementing appropriate access controls and retention policies. Privacy controls do not degrade functionality or user experience.
5. End-to-End Security - Full Lifecycle Protection - Customer data is encrypted when collected, stored encrypted in Firestore, transmitted encrypted to authorized services, and securely deleted at end of retention period per Data Management Policy.
6. Visibility and Transparency - Corporate Data Processing Terms clearly document what personal data we process, processing purposes, and retention periods. Audit logging tracks access to personal data for accountability.
7. Respect for User Privacy - Data collection is minimal and aligned with stated purposes. Data retention periods and deletion obligations are clearly defined in Data Processing Terms, with processes to fulfill customer deletion requirements under GDPR.

These principles are implemented through existing policies (Data Management Policy, Cryptography Policy, Secure Development Policy) and contractual obligations (Corporate Data Processing Terms).

<br>

#### 2.3 Additional Engineering Principles

Beyond formal secure-by-design and privacy-by-design principles, Mindset AI Ltd applies additional principles derived from our GCP-native serverless architecture:

**Infrastructure as Code** - Infrastructure changes follow change management processes and are tracked through GitLab. Configuration baselines for new environments are version controlled where feasible, with ongoing work to expand IaC coverage.

**Leverage GCP Native Services** - We utilize Google Cloud Platform's mature security services rather than building custom controls: Security Command Center for vulnerability management, Cloud Audit Logs for activity logging, IAM for fine-grained access control, and Cloud KMS for key management. This approach provides enterprise-grade security aligned with zero-budget constraints.

**Segregation of Environments** - Development, testing, and production environments are strictly segregated per Secure Development Policy:

* Production (monkee-prod, mindset-prod2, mindset-prod3, mindset-usw-prod4): Live customer data, access restricted to authorized DevOps and team leads, changes require change management approval
* Staging: Production-like configuration with non-production data for pre-deployment validation
* Integration: Merged feature testing and regression testing with non-production data
* Epic-specific: Isolated feature development and testing environments
* Development/Local: Individual developer environments with no production data access

**Critical Rule:** Confidential customer data must not be used in non-production systems without specific customer approval (Data Management Policy).

**Automated Security Controls** - Security controls are automated wherever feasible to reduce human error: vulnerability scanning in CI/CD pipelines, code linting and style enforcement, automated unit testing, Security Command Center scanning, and deployment automation following change management approval.

These principles are implemented through existing policies and technical architecture, providing defense in depth while maintaining operational efficiency.

<br>

### 3. Security Integration in Epic Workflow

Security is integrated throughout Mindset AI Ltd's Epic-based software development workflow, not treated as a separate phase. Security and privacy considerations scale with project phase—early phases require awareness and preliminary assessment, while later phases require detailed implementation.

**Epic Workflow Progression:** Product Document → UX Plan → Specification Document (Requirements) → Implementation Plan (Design) → Delivery (Development → Testing → Deployment) → Operations

#### 3.1 Product Document Phase

**Primary Focus:** Problem statements, use cases, business justification

**Security Role:** Preliminary identification of security considerations when initiative involves customer data, PII, authentication/authorization, sensitive operations, external integrations, or changes to data flows.

**Security Activities:**

* Data Sensitivity Assessment - Determine if feature involves customer data, PII, or confidential information; classify data per Data Management Policy
* High-Level Risk Identification - Identify new attack vectors, expanded attack surface, trust boundary changes, or regulatory compliance implications (GDPR, data processing agreements)
* Early Stakeholder Engagement - Engage CTO or senior developers if significant security implications identified; flag compliance requirements or potential Data Protection Impact Assessment needs

**Outputs:** Initial determination of security implications documented in Product Document; identification of showstopper security concerns.

**Example:** Product Document for customer data export feature identifies processing of customer PII, GDPR right to data portability requirement, need for secure export mechanism and audit logging, triggering early CTO engagement on technical approach.

#### 3.2 UX Plan Phase

**Primary Focus:** User flows, interface concepts, rough UX guidelines

**Security Role:** Technical teams provide security input on UX plans when they involve authentication/authorization, sensitive data display, privacy controls, or third-party integrations. Feedback captured in Specification document phase.

**Security Activities:**

* Authentication/Authorization UX Review - Verify security-sensitive actions are clearly marked, appropriate confirmation steps exist for sensitive actions, and UX supports security controls
* Data Exposure Review - Assess what sensitive data is displayed, whether masking/hiding controls are needed, and whether error messages avoid information disclosure
* Third-Party Integration UX - Ensure users are informed when interacting with external services, data sharing is transparent, and authentication flows are secure (OAuth 2.0)
* Privacy Controls - Consider whether UX should provide privacy controls or user data access capabilities, and whether privacy defaults align with privacy-by-design principles where applicable

**Outputs:** Security feedback integrated into UX plan; identification of UX patterns that could create security issues; suggestions for security-enhancing improvements.

**Example:** UX Plan for admin dashboard reviews role-based UI patterns, adds confirmation dialog before customer data deletion, and includes audit trail visibility for admin actions.

#### 3.3 Specification Document Phase (Requirements)

**Primary Focus:** Detailed feature requirements, acceptance criteria, functional specifications

**Security Role:** Active CTO or technical lead participation; formal security requirements assessment for features with security implications

**Security Activities:**

* Data Classification and Handling - Identify data collected, processed, stored, or transmitted; classify per Data Management Policy; define retention requirements and storage locations (GCP services/projects)
* Access Control and Authorization - Consider who should access the feature/data, any role or permission requirements, authentication verification approach, access levels if applicable (read/write, admin/user)
* Compliance Requirements - Assess GDPR requirements (data subject rights, lawful basis), ISO 27001 controls, and customer contractual requirements (Data Processing Terms)
* Integration Security - Identify external systems, data shared with third parties, authentication mechanisms (API keys, OAuth), API security requirements (rate limiting, input validation), and vendor security assessments per Third-Party Management Policy
* Privacy Considerations - Document personal data involved, processing purpose and legal basis, required privacy controls (consent, deletion, access), and privacy-enhancing techniques (pseudonymization, anonymization)

**Outputs:** Security considerations documented appropriately in the Requirement specification document.

**Example:** Specification for third-party CRM integration documents data classification (Confidential customer contact information), OAuth 2.0 authentication, customer DPA compliance requirements, rate limiting per Operations Security Policy, and personal data minimization with deletion support.

#### 3.4 Implementation Plan Phase (Design)

**Primary Focus:** Technical architecture, detailed design, implementation approach

**Security Role:** Active CTO and technical lead participation; detailed architectural security assessment and threat analysis

**Security Activities:**

* Architecture Security Assessment - Assess architecture for potential weaknesses, consider defense in depth, evaluate segregation of concerns and least privilege where applicable, review whether design meets Specification phase security requirements
* Data Flow and Trust Boundary Analysis - Consider data flows, assess trust boundaries between components/services/environments, determine if additional controls are needed at boundaries, review encryption requirements per Cryptography Policy
* Authentication and Authorization Design - Determine appropriate authentication mechanisms (Firebase Auth, service accounts, API keys), consider authorization model (roles, permissions, policies), evaluate session management and token handling approaches
* Encryption Requirements - Consider any impacts to standard encryption patterns, evaluate key management approach per Cryptography Policy
* Third-Party Service Security - Document services used, their security controls, data sharing arrangements, contractual requirements; consider vendor assessment per Third-Party Management Policy if new critical vendor
* Infrastructure Security - Identify required GCP services/configurations, review compliance with hardening standards (Operations Security Policy Appendix A), determine IAM roles/permissions, consider secrets management approach
* Threat Identification and Mitigation - Consider potential threats relevant to the implementation; assess likelihood and impact per Risk Management Policy where relevant; document mitigation approach for significant threats

**Outputs:** Security considerations documented appropriately within the implementation plan. This may include technical architecture with security controls, authentication/authorization design, encryption requirements, infrastructure security requirements, and threat identification with mitigations. All implementations must address security requirements from the Specification phase.

**Example:** Implementation Plan for automated customer onboarding API documents RESTful API architecture behind Google Cloud Load Balancer with TLS, Firebase Auth token validation, custom claims authorization, Firestore with encryption at rest, rate limiting (100 req/min per IP at API Gateway, progressive limiting in Cloud Function), and input validation against schemas with parameterized queries.

#### 3.5 Delivery Phase (Development, Testing, Deployment)

**Primary Focus:** Implementation, testing, deployment to production

**Security Role:** Continuous integration of security controls, testing, and validation

**3.5.1 Development**

* Secure Coding Practices - Follow Secure Development Policy standards: input validation, output encoding, parameterized queries, secure libraries
* Linter Enforcement - Code should pass configured linters, with checking during development phases.
* Code Review and Approval - All changes require merge request approval from team lead or experienced developer (different from author). Review covers input validation, authentication/authorization, error handling, and secure configuration
* Secret Management - Secrets must be managed via GCP Secret Manager and should not be committed to Git. Accidental secret commits are identified via scanning and remediated immediately.

**3.5.2 Testing**

* Unit Testing - Unit testing includes security-relevant test cases. (Authentication, authorization, input validation, error handling)
* API Functional Testing - Validates authentication, authorization, rate limiting, and input validation
* Security Vulnerability Scanning - Automated scanning via GitLab pipeline (dependencies) and Security Command Center (infrastructure). Critical/High findings remediated within 30 days per Operations Security Policy
* Manual Verification Testing - Manual Verification Testing progresses through appropriate environments based on change risk and complexity. Typical progression includes:
* Epic-specific: Full functional and primary security testing
* Integration: Regression and secondary security verification
* Staging: Sanity testing and minimal security validation

**3.5.3 Deployment**

* Change Management Approval - Weekly go/no-go decision by cross-functional team documented in #deployment-status Slack channel per Change Management Procedure
* Deployment Execution - Performed by authorized DevOps or team leads following deployment procedures
* Post-Deployment Monitoring - Monitor systems via GCP logs and Security Command Center for errors, security alerts, and anomalies. Significant findings documented in deploy review ticket.
* Deploy Review - Release Manager creates and completes deploy review ticket (type::deploy review) within one week per Deploy Review Process Guide
* Emergency Changes (Hotfixes) - Follow expedited process with same security standards but accelerated timeline. Post-implementation review required within 48 hours per Change Management Procedure.

#### 3.6 Operations Phase

**Primary Focus:** Ongoing monitoring, maintenance, incident response, continuous improvement

**Security Role:** Sustained security operations, threat detection, vulnerability management, continuous assessment

**Security Activities:**

* Ongoing Monitoring - Security Command Center monitors GCP infrastructure, application logs track anomalies, #infosec-alerts Slack channel receives security advisory RSS feeds, audit logs reviewed for suspicious activity per Operations Security Policy.
* Incident Detection and Response - Security incidents detected through monitoring, alerts, or user reports; reported to infosecreports@mindset.ai or #infosec-alerts Slack channel; handled per Incident Response Plan with post-incident review to identify improvements.
* Vulnerability Management - Continuous scanning via Security Command Center and GitLab pipeline. Vulnerabilities remediated per Operations Security Policy SLAs (Critical/High: 30 days, Medium: 60 days, Low: 90 days). Security patches deployed following the change management process (may be expedited for critical vulnerabilities).
* Access Reviews and Audit Logging - Quarterly access reviews per Access Control Policy. Audit logs maintained per Operations Security Policy (minimum 30 days, longer for compliance).
* Continuous Security Assessment - Annual penetration testing and risk assessment per Operations Security Policy and Risk Management Policy. Evaluation of new threats via threat intelligence.
* Outputs: Ongoing security monitoring, incident response and reviews, vulnerability remediation within SLAs, quarterly access reviews, annual security assessments, continuous improvement of security posture.

***

### 4. Practical Application

#### 4.1 Role-Based Security Responsibilities

**Developers:**

* Use Claude Code for review and enrichment of implementation to assess secure-by-design principles
* Apply secure-by-design principles (least privilege, fail securely, input validation)
* Use approved cryptography per Cryptography Policy; never commit secrets to Git
* Write security-relevant unit tests; follow secure coding practices from Secure Development Policy
* Review code for security issues (injection vulnerabilities, improper error handling, hardcoded secrets)
* Verify authentication/authorization implementation and input validation
* Test security controls and review vulnerability scan results

**Team Leads and Architects:**

* Identify security and privacy implications during Requirements/Specification phase
* Define security requirements (data classification, access control, compliance)
* Review architecture for security weaknesses; analyze data flows and trust boundaries
* Identify threats and plan mitigations
* Enforce segregation of duties (don't approve your own code); provide security-focused review

**Product Team:**

* Identify and suggest potential security concerns early in the process:
* Features involving customer data, PII, or sensitive operations
* Authentication/authorization requirements in user flows
* Privacy implications and data handling considerations
* Third-party integrations and data sharing
* Include security considerations in product outputs.
* Ensure security requirements are incorporated into product specifications

**DevOps Engineers:**

* Follow hardening standards (Operations Security Policy Appendix A)
* Apply least privilege to IAM roles; enable encryption per Cryptography Policy
* Configure logging and monitoring per Operations Security Policy; use Infrastructure as Code where feasible
* Verify change management approval before deploying; monitor post-deployment
* Complete deploy review per Deploy Review Process Guide
* Monitor security alerts; review Security Command Center findings; perform quarterly access reviews

**Everyone:**

* Report security concerns to infosecreports@mindset.ai or #infosec-alerts Slack channel
* Question security assumptions; stay informed on security advisories
* Learn continuously about evolving threats and defenses

#### 4.2 When to Escalate to CTO

Escalate when you identify significant security vulnerabilities, have design decisions with uncertain security implications, need guidance on security requirements, observe suspicious activity, receive customer security concerns, or need policy exception approval. Better to ask than assume.

#### 4.3 Key Resources

**Internal Policies:** Secure Development Policy, Operations Security Policy, Change Management Procedure, Access Control Policy, Data Management Policy, Cryptography Policy, Risk Management Policy, Deploy Review Process Guide

**External References:** OWASP Top 10, OWASP Proactive Controls, GCP Security Best Practices

Training: Annual secure development training required per Secure Development Policy covering injection attacks, authentication flaws, XSS/CSRF, vulnerable libraries, and insecure configurations

**Contact Points:**

* CTO (Will Evans): Security design questions, policy exceptions, significant concerns
* VP of Operations (Niamh Mulhall): Data protection, privacy, compliance questions
* Release Manager (Tarun): Deploy review process, deployment questions
* Security Incidents: infosecreports@mindset.ai or #infosec-alerts Slack channel

***

### 5. NIST SP 800-160v1r1 Alignment

#### 5.1 Overview

NIST Special Publication 800-160 Volume 1 Revision 1 provides guidance for developing trustworthy secure systems through systems security engineering. This section describes how Mindset AI Ltd's practices align with key NIST concepts relevant to our environment.

#### 5.2 Key NIST Concepts Applied

Security Throughout System Life Cycle - Security integrated at every Epic workflow phase (Section 3), from Product Document through Operations, treated as continuous thread rather than separate phase.

Trustworthiness and Assurance - Multiple validation layers (unit tests, security scans, manual verification), post-deployment monitoring, regular security assessments (penetration tests, vulnerability scans), and audit logging provide assurance of security control effectiveness.

Security Design Principles - Formal secure-by-design principles (Section 2.1) aligned with NIST principles including least privilege, defense in depth, and fail secure guide architecture and implementation decisions.

Threat and Vulnerability Identification - Threat identification during Implementation Plan phase (Section 3.4), vulnerability management per Operations Security Policy, continuous scanning via Security Command Center, annual risk assessment per Risk Management Policy.

Security Requirements - Defined during Specification Document phase (Section 3.3) addressing data protection, access control, compliance, and integration security; traced through design, implementation, and testing.

System Context and Environment - Zero-budget constraint drives use of GCP native services (Section 2.3), serverless architecture shapes security approach, B2B2C data processor model influences privacy-by-design emphasis, startup environment favors practical security over bureaucracy.

Third-Party and Supply Chain - Governed by Third-Party Management Policy, dependency scanning in CI/CD pipeline, integration security evaluated during Implementation Plan phase, vendor security requirements in contracts (Data Processing Terms).

Continuous Monitoring and Improvement - Ongoing monitoring via Security Command Center, Cloud Audit Logs, and application logs; incident response per Incident Response Plan; post-incident reviews drive improvements.

#### 5.3 Limitations and Adaptations

**What We Don't Do:**

* Formal threat modeling frameworks (STRIDE, PASTA) - We use lightweight threat identification focused on highest-priority threats
* Extensive separate security architecture documentation - Security documented within Epic specifications, implementation plans, and merge requests
* Security-specific governance bodies - Security decisions made by CTO with stakeholder input
* Dedicated security team - Security integrated into engineering roles; leverages GCP security services

**Why This Works:** Startup environment requires lightweight integrated security; GCP architecture provides enterprise-grade controls without dedicated security team; clear CTO accountability; risk-based approach focuses efforts where risks are highest per Risk Management Policy.

#### 5.4 Continuous Alignment

As Mindset AI Ltd grows, we will continue evaluating security practices against NIST SP 800-160 and other frameworks, adopting additional practices where they provide value aligned with our risk profile and resources.

***

### Version History

| Version | Date             | Description         | Author     | Approver   |
| ------- | ---------------- | ------------------- | ---------- | ---------- |
| 1.0     | October 13, 2025 | Initial version     | Will Evans | Will Evans |
| 1.1     | October 14, 2025 | Updated for clarity | Will Evans | Will Evans |

**Document Owner:** Will Evans, CTO\
**Version:** 1.1\
**Effective Date:** October 13, 2025\
**Classification:** Company Restricted\
**Related Policies:** Secure Development Policy, Operations Security Policy, Change Management Procedure, Risk Management Policy, Data Management Policy<br>

### Document Classification

Classification: Company Restricted

Handling: This document contains information about Mindset AI Ltd's security practices and should be handled in accordance with the Data Management Policy. This document may be shared with customers under NDA for security assessment purposes.

<br>
