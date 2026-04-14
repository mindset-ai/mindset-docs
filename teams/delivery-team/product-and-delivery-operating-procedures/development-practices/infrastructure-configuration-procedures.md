# Infrastructure Configuration Procedures

**⚠️ Note:** This document requires review and confirmation by DevOps team.

### Overview

This document describes procedures for configuring and managing infrastructure resources in our GCP environment. All infrastructure changes must follow the change management process.

### Configuration Standards

All infrastructure must be configured according to the standards defined in **Operations Security Policy Appendix A**.

**Key standards include:**

* System hardening requirements
* Network security controls
* Cloud-specific security configurations
* Container and CI/CD security

**Reference:** Operations Security Policy Appendix A

### Common Infrastructure Procedures

#### 1. Managing Secrets and Credentials

**When needed:**

* Adding API keys for third-party integrations
* Storing database credentials
* Managing service account keys
* Storing encryption keys

**Procedure:**

1. Never commit secrets to Git repositories
2. Store secrets in GCP Secret Manager
3. Use appropriate access controls (least privilege)
4. Request access to secrets via standard access request process
5. Rotate secrets according to policy requirements
6. Document secret purpose and ownership

**Access control:** Access to secrets requires approval per Access Control Policy

**Reference:** Access Control Policy, Cryptography Policy

#### 2. Creating and Modifying GCP Resources

**When needed:**

* Provisioning new Cloud Functions
* Creating Firestore databases or collections
* Configuring Cloud Storage buckets
* Setting up Cloud Run services
* Modifying IAM roles and permissions

**Procedure:**

1. Create GitLab ticket documenting the change
2. Include business justification and impact assessment
3. Follow change management approval workflow
4. Apply security hardening standards from Operations Security Policy
5. Use infrastructure-as-code where feasible
6. Document configuration in ticket
7. Test in non-production environment first
8. Deploy to production following change management process

**Key security requirements:**

* Enable audit logging (Cloud Audit Logs)
* Configure appropriate network access controls
* Implement least-privilege IAM roles
* Enable encryption at rest and in transit
* Follow principle of least privilege for service accounts

**Reference:** Change Management Procedure, Operations Security Policy

#### 3. Requesting Infrastructure Changes

All infrastructure changes require:

* GitLab ticket with change request
* Approval from system owner or DevOps lead
* Change impact assessment
* Testing in non-production environment (where applicable)

**For standard access requests:** See Access Control Policy Appendix A

### Network and Security Configuration

#### Firewall Rules and Network Access

Network configuration changes must:

* Follow change management approval process
* Be documented in GitLab ticket
* Include business justification
* Follow principle of least privilege (minimum necessary access)
* Be reviewed at least annually

**Reference:** Operations Security Policy (Network Standards section)

#### Production Environment Access

Access to production infrastructure is restricted to:

* Authorized DevOps engineers
* Team leads with production responsibilities
* All access requires MFA
* All changes require change management approval

**Reference:** Access Control Policy

### Infrastructure Security Scanning

Infrastructure security is validated through:

* GCP Security Command Center (Standard tier)
* Annual penetration testing
* Quarterly vulnerability scanning
* Continuous security monitoring and alerting

**Reference:** Operations Security Policy (Vulnerability Management section)

### Related Documentation

* Change Management Procedure
* Operations Security Policy
* Access Control Policy
* Cryptography Policy
