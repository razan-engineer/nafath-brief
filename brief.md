Version: NAFATH-V1
Track: Networking 

## Overview
A national single sign-on service lets citizens log in to many government services with one account, so its security depends on several IT fields working together. Software standards such as OpenID Connect define how the login itself works. Mobile apps on Android must request permissions carefully to protect user data. Network protections keep traffic private while it travels between the user and the service. Strong, phishing-resistant authentication stops attackers from stealing accounts, and an AI model can help spot suspicious logins, but it brings risks that must be managed. Finally, data protection law sets the rules for how citizens' personal data is collected and stored. DNS over HTTPS (DoH) is the networking safeguard that protects users' DNS lookups from on-path eavesdropping and tampering.
## Software
OAuth 2.0 is an authorization framework. It lets a third-party application obtain limited access to resources over HTTP. By itself it does not define a standard way to give identity information. OpenID Connect is a simple identity layer built on top of OAuth 2.0. It lets a client verify who the user is, and returns the login result in an ID Token. So OpenID Connect is designed for user login, and OAuth 2.0 for delegated access.

Resource: OpenID Connect Core 1.0 incorporating errata set 2 - https://openid.net/specs/openid-connect-core-1_0.html
## AI
The NIST AI Risk Management Framework organizes risk work into four functions: Govern, Map, Measure and Manage. Before a login-flagging model goes live, the authority should check that it is valid and reliable, secure, explainable and fair. False alarms could lock out real citizens, missed attacks could let intruders in, and the model's use of login data creates privacy risk. Ownership and human oversight must be defined first.

Resource: NIST AI Risk Management Framework (AI RMF 1.0) - https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
## Mobile
Android apps run in a sandbox, and permissions protect restricted data and actions beyond it. Normal install-time permissions are granted automatically when the app is installed. Dangerous (runtime) permissions, such as location or contact access, must be requested while the app is running, and checked before each use. The login app should ask only when the user starts the related action, and explain what stops working if the user denies it.

Resource: Permissions on Android - https://developer.android.com/guide/topics/permissions/overview
## Networking
DNS over HTTPS (DoH) sends DNS queries and responses inside HTTPS, so they get TLS protection for confidentiality and integrity. It protects users from passive surveillance and from on-path devices that tamper with or divert DNS traffic to rogue servers. It does not hide queries from the DoH server itself, and the client's IP address and HTTP details can still be used to correlate requests. It also does not replace DNSSEC.

Resource: RFC 8484 - DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484
## Cybersecurity
Phishing-resistant authentication is designed so a fake website cannot capture something an attacker can reuse. CISA says FIDO/WebAuthn is the most widely available option, and PKI-based MFA, such as smart cards, also qualifies. SMS or voice codes, app-based codes and push approvals do not qualify, because attackers can intercept them or trick users. Number matching is only an interim mitigation.

Resource: Implementing Phishing-Resistant MFA (CISA fact sheet) - https://www.cisa.gov/sites/default/files/publications/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf
## Data
Under Royal Decree 6/2022, the authority, as controller, needs the data subject's explicit, provable consent, with a clear request naming the controller, the purpose and how to contact the data protection officer (Article 10). It must appoint that officer (20), set risk controls and security measures (13), keep data confidential (21), erase it when its purpose ends (15), and report breaches to the ministry and the person (19).

Resource: Royal Decree 6/2022 Issuing the Personal Data Protection Law (Consolidated) - https://decree.om/2022/l20220006/
## Misconception in My Track
Common wrong belief: DoH makes browsing anonymous, so nobody can see which sites a user visits. Correct version: DoH only encrypts DNS between the client and the DoH server, which protects against on-path eavesdropping and tampering. The DoH server still sees every query, and the client's IP address can be used to correlate requests. RFC 8484 supports this in Section 8.2 (In the Server), which says the client address provides obvious correlation information.
## Open Question
Does Article 3(b) of the Personal Data Protection Law exempt a government authority's login service, and which policy would apply to it instead?
