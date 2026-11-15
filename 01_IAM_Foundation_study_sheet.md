# IAM Foundations – Study Guide

## Core Concepts to Know

**Identity vs Account vs Credential vs Entitlement**
- Identity = the actual person, service, or device
- Account = the digital record of that identity in a system
- Credential = what proves the account is real (password, key, etc.)
- Entitlement = the specific rights that account has been given

**The Four As (Access Decision Flow)**
1. Identification – Claiming who you are
2. Authentication – Proving it
3. Authorisation – Deciding what you’re allowed to do
4. Accountability – Logging what happened so it can be traced

Remember: Authentication answers “Who are you?”  
Authorisation answers “What can you do?”

## Authentication Strength

Factors come in three types:
- Something you know
- Something you have
- Something you are

MFA requires at least two different types.

**Phishing resistance ranking (high-level)**
- Password only → weakest
- SMS / app codes → still phishable
- Number matching push → better against fatigue
- FIDO2, passkeys, Windows Hello, certificates → phishing-resistant (public-key crypto bound to the real site)

## Directories

| Feature              | Active Directory          | Entra ID                     |
|----------------------|---------------------------|------------------------------|
| Location             | On-prem domain controllers| Microsoft cloud              |
| Main protocols       | Kerberos, NTLM, LDAP      | OIDC, OAuth 2.0, SAML        |
| Typical resources    | Domain-joined machines, file shares | M365, SaaS, Azure, modern apps |
| Structure            | Forests, domains, OUs     | Flat tenant + groups + Conditional Access |

They are often synced, but they are **not** the same thing.

## Important Protocols (What each one does)

- **Kerberos** – Ticket-based auth inside Windows domains
- **SAML** – Classic enterprise SSO (XML)
- **OAuth 2.0** – Lets an app act on a user’s behalf (access tokens)
- **OpenID Connect** – Adds identity layer on top of OAuth (ID token)
- **SCIM** – Standard way to provision/deprovision accounts automatically

## Identity Types in Entra ID

- Member users (your employees)
- Guest users (external people via B2B)
- Groups (main way to grant access at scale)
- App registrations / service principals
- Managed identities (no secrets to manage)
- Devices (can be used as Conditional Access signals)

Non-human identities usually outnumber people and need the same governance.

## Access Control Principles

- **RBAC** – Permissions bundled into roles
- **ABAC** – Decisions based on attributes
- **Least privilege** – Only what is needed, only while needed
- **Separation of duties** – No single person can do everything sensitive
- **Need to know** – Access limited to those who require it for their job

Note: Entra roles (directory/M365) and Azure RBAC roles (subscriptions/resources) are separate systems.

## Zero Trust Essentials

Three principles:
1. Verify explicitly (use all available signals)
2. Use least privilege (JIT + just-enough)
3. Assume breach (limit blast radius and detect fast)

Identity is the main control plane.
