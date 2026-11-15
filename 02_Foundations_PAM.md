# PAM Foundations – Study Guide

## What is Privileged Access?
Anything that can change security settings, create/modify identities, or access data it doesn’t own counts as privileged.

Common examples:
- Admin accounts (Global Admin, Domain Admin, DBAs, subscription owners)
- Service accounts and workload identities
- Break-glass / emergency accounts
- Secrets, certificates, API keys, SSH keys
- Local administrator rights on devices
- SaaS admin roles and CI/CD pipelines

Most organisations have far more privileged credentials than they realise.

## Why It Matters
Serious breaches almost always involve privilege escalation. Attackers start with a normal account and move upward. PAM controls are designed to interrupt that climb at multiple points.

## Core PAM Capabilities (Memorise These)

1. Discover – Find all privileged accounts and secrets
2. Vault – Store credentials securely so people check them out
3. Rotate – Change credentials automatically (on schedule and after use)
4. Broker sessions – Proxy the connection so the password never reaches the admin’s device
5. Record & audit – Capture what happened in privileged sessions
6. Just-in-time access – Privilege only when requested and approved
7. Endpoint privilege – Remove standing local admin and elevate only specific apps
8. Secrets management – Give applications short-lived secrets instead of static ones

## Key Microsoft Tools

- Entra PIM → Just-in-time role activation
- Windows LAPS → Local admin password management
- Azure Key Vault + Managed Identities → Application secrets
- Azure Bastion → Session brokering for Azure VMs
- Defender for Identity + Entra ID Protection → Detection

## Tiering / Enterprise Access Model

Keep the highest-value credentials on the cleanest devices.

- Control plane (Tier 0) = Identity systems
- Management plane (Tier 1) = Servers and applications
- Data/workload plane (Tier 2) = User devices

**Golden rule**: A higher-tier credential must never be used on a lower-tier device.

## Essential Hygiene Rules

- Separate admin accounts (no email, no browsing)
- Prefer cloud-only admin accounts (not synced from AD)
- Use Privileged Access Workstations (PAWs)
- No standing privilege — activate just-in-time
- Prefer managed identities / gMSAs over static passwords
- Deny interactive logon for service accounts
- Maintain two monitored break-glass accounts

## Key Terms to Distinguish

| Term  | Meaning |
|-------|---------|
| PAM   | Overall discipline of protecting privileged access |
| PIM   | Managing *who* holds privileged roles and *when* (Entra JIT) |
| PASM  | Vaulting credentials + brokering/recording sessions |
| PEDM  | Elevating specific rights on endpoints instead of full admin |

## Maturity Stages (High-Level)

**Stage 1 – Know & Protect**  
Inventory, strong MFA, separate admin accounts, break-glass accounts

**Stage 2 – Control**  
JIT activation, vaulting & rotation, LAPS, access reviews

**Stage 3 – Isolate & Detect**  
Tiering + PAWs, session brokering/recording, secrets management, alerting
