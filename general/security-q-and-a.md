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

GCP is a recognised industry leader in cloud security, holding ISO/IEC.&#x20;

27001/27017/27018/27701, SOC 1/2/3, PCI DSS, FedRAMP certifications, alignment with HIPAA, GDPR, CCPA, and many other industry certifications.&#x20;

## Authentication

All authentication (and storage of authentication tokens and user’s personally identifiable information) is also handled by Google. Furthermore, the authentication tokens are used in the database security rules; thus, the databases are secured at the user level. This results in the highest data security achievable in modern cloud computing environments.



\
