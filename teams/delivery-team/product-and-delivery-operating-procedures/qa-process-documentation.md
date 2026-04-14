# QA Process Documentation

### Purpose and Scope

This document defines QA and testing processes at Mindset AI Ltd to ensure changes are validated before production deployment, satisfying ISO 27001:2022 testing and change management requirements.

Applies to: All production software changes and personnel involved in development, testing, and deployment.

***

### Testing Types

#### Automated Testing

Unit Tests: Run in GitLab CI/CD pipeline where configured, or executed locally by developers. Coverage varies by module. Evidence: Pipeline logs (where automated) or GitLab ticket verification (where local).

API Functional Tests: Automated tests for key endpoints where implemented. Evidence: Pipeline logs.

Security Scanning: GitLab security templates scan dependencies, containers, and code (SAST) automatically on every merge request. Vulnerabilities remediated per Operations Security Policy SLAs. Evidence: GitLab security scan reports.

#### Manual Testing

Functional Verification: Developers and QA test functionality across environments with progressively focused scope:

* Development: Comprehensive testing of all Epic requirements
* Integration: Regression testing on core functionality
* Staging: Sanity testing on critical paths

Evidence: GitLab ticket state progression (testing → done) and ticket comments.

***

### Testing Workflow

1. Development: Comprehensive Epic testing, automated tests/security scans, developer verification. Gate: Developer sign-off.
2. Integration: Regression testing, integration validation. Gate: Integration tests pass.
3. Merge Request: Code review, pipeline tests pass, security scans reviewed. Gate: Team lead approval.
4. Staging: Sanity testing, Release Manager validation. Gate: Weekly go/no-go.
5. Production: Deploy per Change Management Procedure, monitor, create deploy review ticket (1 week).

***

### Quality Gates

Merge Request: All pipeline tests pass, security scans complete (no critical/high issues introduced), team lead approval, testing verified via GitLab ticket state. Evidence: GitLab MR.

Production Deployment: Weekly go/no-go by cross-functional team (Tech Leads, Product Managers, Test Leads) evaluating quality, performance, security, staging validation. Evidence: #deployment-status Slack channel.

***

### Emergency Changes (Hotfixes)

Workflow: Branch from release → test on staging → deploy to production → merge to develop

Requirements: Pipeline tests pass, security scans complete, focused manual testing, team lead approval

Post-Review (48 hours): Document in GitLab ticket: justification, impact, issues, lessons learned.

***

### Roles and Responsibilities

CTO (Will Evans): Policy owner, exceptions | Release Manager (Tarun): Weekly deployment, go/no-go, deploy reviews | Team Leads: MR approvals, go/no-go | Developers: Testing execution, GitLab documentation | DevOps: CI/CD pipeline, security scanning

***

### Evidence and Documentation

| Testing Activity           | Evidence Type                       | Location                     |
| -------------------------- | ----------------------------------- | ---------------------------- |
| Automated unit/API testing | Pipeline logs                       | GitLab CI/CD                 |
| Security scanning          | Scan reports                        | GitLab Security Dashboard    |
| Manual testing             | Ticket state progression & comments | GitLab Issues                |
| Merge request approval     | Approval workflows                  | GitLab Merge Requests        |
| Weekly deployment approval | Slack messages                      | #deployment-status channel   |
| Post-deployment validation | Deploy review tickets               | GitLab (type::deploy review) |
| Hotfix post-review         | Ticket comments                     | GitLab Issues                |

<br>

***

### Related Policies

This QA process implements testing requirements from:

* Change Management Procedure: Overall change workflow and deployment
* Operations Security Policy: Vulnerability management and remediation SLAs
* Secure Development Policy: Testing requirements in development lifecycle
* Deploy Review Process Guide: Post-deployment validation

***

### ISO 27001:2022 Control Mapping

A.8.29 (Testing Security): Security scanning in CI/CD pipeline (automated on every MR), results reviewed in approvals, remediation per Operations Security Policy. Evidence: Pipeline logs, security scan reports, remediation tickets.

A.8.32 (Change Management): Testing workflow across environments, quality gates for MR and deployment approval, post-deployment validation, emergency change procedures. Evidence: GitLab MRs/tickets, pipeline logs, Slack go/no-go, deploy review tickets.

***

### Version History

| Version | Date             | Description     | Author     | Approver   |
| ------- | ---------------- | --------------- | ---------- | ---------- |
| 1.0     | October 14, 2025 | Initial version | Will Evans | Will Evans |

**Document Owner:** Will Evans, CTO\
**Effective Date:** October 14, 2025\
**Version:** 1.0\
**ISO 27001:2022 Controls:** A.8.32 (Change Management), A.8.29 (Testing)\
**Next Review:** October 2026
