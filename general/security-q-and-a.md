---
description: >-
  The purpose of this page is to provide answers to frequently asked security
  questions.
---

# Security Q\&A

## Mindset Data Security Overview&#x20;

The Mindset platform is a modern, serverless architecture hosted by the Firebase PaaS on the Google Cloud Platform (GCP). All client-server communication is via Firebase, and Firebase Authentication handles authentication on GCP. Furthermore, Firebase authentication tokens are used for database segmentation and database security.&#x20;

All client instances running in a browser (as compiled, minimised JavaScript) or as native IOS and Android applications are written in Dart on the Flutter framework.

<figure><img src="https://lh7-us.googleusercontent.com/v9IYkL5Xjfsj7c8j1Mi-OcZ7OTWQYw8rf_888PLbTVSiGsi9Wo77cBfyXHMWSn2VxaJ-LYD870O-O_EuNJ__s4BeY-lbDyJ8ieeexqD77kBtjByPAL6jWyr7B24WmhzlVXAg39APfABjL8rR0GcFhbE" alt=""><figcaption></figcaption></figure>

\
The advantage of this approach is that all security responsibility is held by Google, which is recognised as the industry leader in cloud platform security and compliance. All data is secured in transit and at rest by Google.&#x20;

## Certifications&#x20;

[GCP](https://cloud.google.com/security/compliance/) is a recognised industry leader in cloud security, holding ISO/IEC 27001, 27017, 27018, 27701, SOC 1/2/3, PCI DSS, FedRAMP certifications, alignment with HIPAA, GDPR, CCPA, and many other industry certifications.&#x20;

Additionally, Mindset AI is in the process of obtaining its own ISO 27001 certification.&#x20;

The Mindset AI founders come from a regulated industry background, with over 100 years of combined experience in the legal, government and financial sectors. We rely on the certifications provided by the platform on which we run the application (GCP), and our commitment to a serverless architecture provides the highest level of security available, managed by Google.

## FAQs

### Authentication

All authentication (and storage of authentication tokens and user’s personally identifiable information) is also handled by Google. Furthermore, the authentication tokens are used in the database security rules; thus, the databases are secured at the user level. This results in the highest data security achievable in modern cloud computing environments.

### Which data centre is the data stored in?&#x20;

By default, data is stored in Google’s Europe-west2 data centre in London, UK. Individual customers may request data centres in other countries. Google has comprehensive geographic coverage.

### How is authentication managed?&#x20;

Google handles all authentication through Firebase Authentication. The Mindset platform uses the unique user UID as the database token, which links a user’s data to an authentication session.

### How is the Firebase database secured?&#x20;

Firebase Security Rules secure the data in Firebase: These rules ensure that only the authenticated user can read from/write to data elements owned by the authenticated user. The implication is that you need to be authenticated as a specific user to see that user’s data, which means that if a user’s login credentials are leaked, only that user’s data is at risk.

### Is penetration testing necessary in a serverless architecture?

No, all security is inherited from the GCP/Firebase platform, and the device's operating system handles the application (mobile instance). With authentication handled by Google, authentication governs database access and serverless architecture. Any penetration testing would be on the Firebase PaaS platform itself, which Google conducts regularly.&#x20;

### What personally identifiable data is stored in the Firebase database?&#x20;

We store the users’ email addresses and the names they give themselves. All other data is metadata about the selections they have made in the application. These are stored as GUIDs (large random numbers).

### Is data encrypted in transfer and at rest?&#x20;

All data is encrypted in transfer (HTTPS) and at rest using 2048-bit RSA encryption. Google handles all encryption. Messages sent through the app are end-to-end encrypted.&#x20;

### How long is the data held, and what is the retention strategy?&#x20;

To provide a bespoke user experience, a user’s data is held on the platform for as long as the user is a user. When a user leaves the platform, all personally identifiable information of that user is deleted. Anonymised usage data is kept for all users for up to 24 months after they have left the platform.

### What would the impact be to individuals or the company if an unintended audience accessed the data?&#x20;

By design, the platform stores minimal personal information per user: Most of the stored data pertains to the user’s behaviour while in the application. There is minimal risk to the individual or company if this data is accessed by a bad actor other than the leakage of email addresses.&#x20;

Uploaded files and videos are stored in encrypted buckets, secured by authentication tokens and encrypted at rest. All pointers to these locations are stored in the Firebase database and secured by authentication tokens and Firebase security rules. Revoking a user’s access revokes all access to all data held.&#x20;

### Is static code analysis used?&#x20;

Yes, all code is analysed, and any deviations are marked as compiler warnings. We use Dart’s static code analysis and follow Flutter’s development guidelines.

### How is the source code deployed and compiled?&#x20;

All compilation and deployment to the app stores are handled through integration scripts running on Github as Github actions. We follow an infrastructure-as-code methodology.

### To what extent are development and testing environments separated from operational environments?

Development, Testing and Production (operational) environments are separate instances with full systems, branches, code versions, users, and data separation.

### To what extent are IT systems protected against malware?

We operate a fully remote infrastructure, with all IT systems hosted in Google or with system suppliers. We only operate using market-leading suppliers, offering full enterprise-level encryption and protection.

### To what extent is information security ensured among contractors and cooperation partners?

All partner and contractor organisations operate under a full NDA, with contractual obligations specified and monitored. All proprietary and business information is stored on our IT systems, with access provided based on role requirements and full ability to revoke access at a user and organisational level.

### Do Mindset staff have the ability to access my account data?

Limited staff within Mindset can access account information for the purposes of support and maintenance on an as-required basis. Permissions are managed and monitored closely, requiring authorisation from multiple sources.

### Do you have a formal incident management procedure? What happens if there is a client data breach?

As part of obtaining an ISO 27001 certification, we follow and abide by the standards and guidelines outlined within this certification. We maintain Incident procedure documents and a risk register that are reviewed regularly. Upon becoming aware of an incident or breach, we notify our clients within 24 hours and keep live notifications running until the incident is resolved.
