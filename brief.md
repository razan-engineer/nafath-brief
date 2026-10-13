Version: NAFATH-V1
Track: Networking 

## Overview
A national single sign-on service lets citizens log in to many government services with one account, so its security depends on several IT fields working together. Software standards such as OpenID Connect define how the login itself works. Mobile apps on Android must request permissions carefully to protect user data. Network protections keep traffic private while it travels between the user and the service. Strong, phishing-resistant authentication stops attackers from stealing accounts, and an AI model can help spot suspicious logins, but it brings risks that must be managed. Finally, data protection law sets the rules for how citizens' personal data is collected and stored. If one field is weak, the whole service becomes less trustworthy.
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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
