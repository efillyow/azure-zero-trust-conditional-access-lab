#  Zero Trust Conditional Access Lab (Microsoft Entra ID)

## Overview
This project demonstrates a Zero Trust identity model using Microsoft Entra ID Conditional Access policies.

The goal was to secure user authentication by enforcing:
- Multi-Factor Authentication (MFA)
- Device compliance
- Blocking legacy authentication

---

##  Architecture
User → Entra ID → Conditional Access → MFA → Resource Access

---

##  Technologies Used
- Microsoft Entra ID
- Conditional Access (P1)
- Microsoft Intune (Device Compliance)
- Microsoft Authenticator (Number Matching MFA)

---

##  Policies Implemented

###  Require MFA for All Users
- Enforced phishing-resistant MFA (number matching)

###  Block Legacy Authentication
- Prevented IMAP/POP/basic auth attacks

###  Admin Protection
- Required MFA for all privileged roles

###  Break-Glass Account
- Excluded emergency account from all policies

---

##  Testing Scenarios

| Scenario | Result |
|--------|--------|
| Normal login | MFA required
| Admin login | MFA enforced
| Break-glass login | No MFA
| Wrong password | Failed (50126)
| Device compliance | Required 

---

##  Sign-In Log Analysis
- MFA satisfied via token claims (PRT behavior)
- Conditional Access evaluated during authentication
- Failed login attempts captured (invalid credentials)

---

## Screenshots are included in the IAM folder 

---

## Outcome
Successfully implemented a Zero Trust model that:
- Reduced attack surface
- Secured authentication flows
- Validated enforcement through real sign-in logs
