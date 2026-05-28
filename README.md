#  Zero Trust Conditional Access Lab (Microsoft Entra ID)

## Overview
This project demonstrates the implementation of a Zero Trust identity model using Microsoft Entra ID Conditional Access policies.

The solution enforces strong authentication, blocks legacy protocols, and validates access using device.
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
The following authentication scenarios were executed to validate Conditional Access enforcement:

| Scenario | Result |
|--------|--------|
| Normal login | MFA required
| Admin login | MFA enforced
| Break-glass login | No MFA
| Wrong password | Failed (50126)
| Device compliance | Required 

---

## Screenshots

## 📸 Conditional Access Policies


### ✅ Require MFA for All Users
This policy enforces phishing-resistant MFA across all users.

CA-Require-MFA-All-Users-Assignments.png
IAM/CA-Require-MFA-All-Users-Grant.png
IAM/CA-Require-MFA-All-Users-Resources.png

---

### ✅ Block Legacy Authentication
This policy blocks insecure legacy authentication protocols such as IMAP and POP.

IAM/CA-Block-Legacy-Auth1.png
IAM/CA-Block-Legacy-Auth2.png
IAM/CA-Block-Legacy-Auth_Assignments.png
---

### ✅ Protect Admin Accounts
This policy enforces MFA for privileged roles to prevent unauthorized access.

IAM/CA-Protect-Admins-MFA-Assignments.png
IAM/CA-Protect-Admins-MFA-Grant.png

---

### ✅ Require Compliant Device
This policy ensures that only managed and compliant devices can access company resources.

IAM/Require Compliant Device -Assignments.png
IAM/Require Compliant Device -Grant.png
IAM/Require Compliant Device -Resources.png

---

### ✅ Require MFA for Office 365
This policy enforces MFA specifically for Office 365 applications.

IAM/Require MFA - Office 365 - Assignments.png
IAM/Require MFA - Office 365 - Grant.png
IAM/Require MFA - Office 365 - Resources.png

---

## 💻 Device & Endpoint Security Policies

### ✅ Device Restrictions Policy
This policy enforces password complexity requirements on enrolled devices.

IAM/Device Restriction Policy.png

---

### ✅ BitLocker Policy
This policy ensures encryption is enabled on managed endpoints.

IAM/Bitlocker Policy.png

---

### ✅ Windows Compliance Policy
This policy validates that devices meet security baseline requirements.

IAM/Windows Compliance Policy.png
IAM/Windows Compliance Policy Continued.png

---

## 📊 Sign-In Logs

This log demonstrates successful Conditional Access enforcement and MFA validation.

IAM/Sign-in Logs - Interactive.png
---
##  Sign-In Log Analysis

Analysis of Entra ID sign-in logs revealed:

- MFA satisfied via token claims (PRT behavior)
- Conditional Access evaluated during authentication
- Failed login attempts captured (invalid credentials)

---

## Screenshots are included in the IAM folder 

---

## Outcome
Successfully implemented a Zero Trust model that:
- Reduced attack surface by blocking legacy authentication protocols
- Improved identity security with MFA enforcement
- Implemented secure emergency access (break-glass account)
- Validated Zero Trust principles through real-world testing scenarios
