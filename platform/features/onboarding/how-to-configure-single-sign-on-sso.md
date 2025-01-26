---
description: This article explains how to configure SSO in the platform.
---

# How to configure Single Sign-On (SSO)

### What Single Sign-On do we support?

For added convenience, you can now log in to the platform using either your password or Single Sign-On (SSO). We currently support Microsoft and Google SSO sign-in . If you would like SSO enabled please let your Customer Success representative know. Please note that SSO will not be enforced for users if turned on.

### End-user perspective

1. On the login screen, choose to sign in using your email and password, or select "Continue with" to log in via Google or Microsoft.
2. Follow the prompts to authenticate using your Google or Microsoft account.

<figure><img src="../../../.gitbook/assets/Screenshot (55).png" alt=""><figcaption></figcaption></figure>

### Frequently Asked Questions

**Can an application have both MFA and SSO enabled?**

Yes, an application can support both MFA and SSO. However, users electing to use SSO will not be asked to complete an MFA challenge within the application itself. This is because authentication is handled by the external SSO provider, which is trusted to provide secure access.

**Will new users using SSO be required to set up MFA?**

No, new users who use SSO from the beginning will never be prompted to set up MFA within the application. The authentication process, including any MFA requirements, will rely on the SSO provider.

**What happens to existing users with MFA if they switch to SSO?**

Existing users who already have MFA enabled and choose to switch to SSO will go through a process to disable MFA. This ensures their account transitions to being managed by the SSO provider seamlessly.

**How does account creation work with SSO?**

When SSO is enabled, it will be offered as an option during account creation alongside traditional email and password setup. Users can choose SSO to create their account if they prefer.

**How does login work for SSO users?**

* SSO options will appear on the login screen once enabled.
* SSO users attempting to log in with an email and password will be denied access.
* SSO users cannot request a password reset within the application but will log in through their SSO provider as usual.
* If an SSO user switches to another provider (e.g., switching from Google to Microsoft), the application will update their account to use the new provider without additional setup.

**How does login work for users with email and password accounts?**

* Email and password users will log in as usual.
* If they choose to log in with an SSO provider using the same email, they will gain access to their account as normal. From that point on, email and password login will no longer be available for them, and they will be registered to the selected SSO provider.

**Can existing users enable SSO later?**

Yes, users who do not initially use SSO can enable it later through the profile section of their account or by choosing to use SSO during the login process.

* If they already have MFA enabled, they will receive a warning that MFA will be removed during this process.
* Once the transition is completed, they will become SSO users and log in through the chosen provider moving forward.

If you encounter any issues enabling or using SSO, ensure that your Google or Microsoft account is associated with your platform account. Otherwise, please contact your Customer Success Representative.
