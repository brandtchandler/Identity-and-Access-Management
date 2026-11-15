# IAM Foundations Study Sheet
*Source: identity-bytes.com/foundations-iam.html*

## Core Definitions

| Term | Meaning | Example |
|------|---------|---------|
| **Identity** | Real person, service, or device | Asha Smith, finance analyst |
| **Account** | System record for the identity | asmith@northgate.co.uk |
| **Credential** | Secret/key used to prove authenticity | Password + FIDO2 key |
| **Entitlement** | Specific permission granted | Member of Finance-Readers |

**Plain analogy**: Identity = you · Account = staff pass record · Credential = pass + PIN · Entitlement = doors it opens.

## The Four As

1. **Identification** – Claim an identity (username)
2. **Authentication** – Prove the claim (factors)
3. **Authorisation** – Decide what the identity may do
4. **Accountability** – Log actions for tracing

- Authentication = “Who are you?”
- Authorisation = “What are you allowed to do?”

## Authentication Factors & Strength

- **Know** (password/PIN) · **Have** (phone/key) · **Are** (biometrics)
- MFA = ≥2 different families

| Method | Strength |
|--------|----------|
| Password only | Weakest |
| Password + SMS/voice | Phishable (SIM swap) |
| Password + app code | Phishable |
| Push + number matching | Resists fatigue |
| **FIDO2 / passkey / Windows Hello / certificate** | **Phishing-resistant** |

Phishing-resistant methods use public-key crypto bound to the real origin → look-alike sites get nothing usable.

## Directories

| Aspect | Active Directory (AD DS) | Microsoft Entra ID |
|--------|---------------------------|--------------------|
| Runs on | On-prem domain controllers | Microsoft cloud |
| Protocols | Kerberos, NTLM, LDAP | OIDC, OAuth 2.0, SAML |
| Typical use | Domain PCs, file shares, on-prem apps | M365, SaaS, Azure, modern apps |
| Structure | Forests/domains/OUs/GPO | Flat tenant, groups, Conditional Access |

Sync (Entra Connect / Cloud Sync) bridges them — powerful and sensitive.

## Key Protocols

- **Kerberos** – Ticket-based (domain sign-in, Seamless SSO)
- **NTLM** – Legacy challenge-response (being deprecated)
- **LDAP** – Directory read/write
- **SAML 2.0** – XML SSO (enterprise SaaS, AD FS)
- **OAuth 2.0** – Delegated authorisation (access tokens, Graph scopes)
- **OpenID Connect** – Identity layer on OAuth (ID token)
- **SCIM 2.0** – Automated account provisioning

## Identity Types in Entra ID

- **Member users** – Workforce (cloud or synced)
- **Guest users** – External B2B (authenticate at home org)
- **Groups** – Security / M365 (assigned or dynamic)
- **App registrations & service principals** – Apps + secrets/certs
- **Managed identities** – Secret-less service principals for Azure resources
- **Devices** – Registered / joined / hybrid-joined (CA signal)

Non-human identities usually outnumber people and need equal governance.

## Access Models & Principles

- **RBAC** – Roles package permissions
- **ABAC** – Decisions based on attributes (user/resource/context)
- **Least privilege** – Only what’s needed, only while needed (JIT)
- **Separation of duties** – No single person completes a sensitive process alone
- **Need to know** – Access limited to job requirement

**Two role systems**: Entra roles (directory/M365) ≠ Azure RBAC (subscriptions/resources). Holding one does not grant the other.

## Zero Trust (3 Principles)

1. **Verify explicitly** – All available signals (identity, device, location, risk)
2. **Use least privilege** – JIT / just-enough, regular review
3. **Assume breach** – Limit blast radius, segment, detect & respond

Identity is the primary control plane.

## Key Takeaways

- Keep identity / account / credential / entitlement distinct
- Authentication ≠ Authorisation
- Prefer phishing-resistant methods (especially for admins)
- AD and Entra ID are different systems with different protocols
- OAuth scopes and Entra roles are both authorisation (different layers)
- Govern non-human identities as carefully as people
