# Development Practices

### Overview

Our software development process ensures that all code changes are properly reviewed, tested, and deployed with appropriate security controls and change management.

### Core Development Practices

#### 1. Code Changes and Review

All code changes follow our formal change management process as documented in the **Change Management Procedure**.

**Key requirements:**

* All changes start with a GitLab Epic or Issue
* Feature branches are created from `develop` (or `release` for hotfixes)
* All changes are supported by full implementation plans
* Merge requests require approval from qualified team member
* Merge requests must include completed change impact assessment

**Reference:** Change Management Procedure

#### 2. Secure Development Practices

All developers must follow secure development principles as documented in the **Secure Development Policy**.

**Key requirements:**

* Apply secure-by-design and privacy-by-design principles
* Follow secure coding standards
* Address identified security vulnerabilities within defined SLAs
* Complete annual secure development training

**Reference:** Secure Development Policy

#### 3. Code Review Process

Code reviews are conducted via GitLab merge requests.

**Review criteria:**

* Code quality and maintainability
* Security implications (injection attacks, authentication, authorization)
* Test coverage and validation
* Breaking vs non-breaking change classification
* Impact on existing systems and dependencies
* Security scanning is performed automatically via GitLab pipelines

**Approvers:** Team leads or experienced developers (different from code author)

#### 4. Weekly Deployment Approval

Production deployments require weekly go/no-go approval from cross-functional team documented in the `#deployment-status` Slack channel.

**Approval team:**

* Tech Leads
* Product Managers
* Test Leads

**Approval criteria:**

* Quality standards met
* Performance acceptable
* Security scans passed
* Functionality validated

### Emergency Changes (Hotfixes)

Emergency changes follow an expedited process for critical production issues:

1. Branch from `release` branch
2. Test on staging environment
3. Deploy to production with same approval requirements
4. Merge back to `develop`
5. **Required:** Post-implementation review within 48 hours documented in GitLab

**Reference:** Change Management Procedure

### Related Documentation

* Change Management Procedure
* Secure Development Policy
* Deploy Review Process Guide
* QA and Testing Procedures

