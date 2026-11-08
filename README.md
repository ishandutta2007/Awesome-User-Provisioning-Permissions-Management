# Awesome-User-Provisioning-Permissions-Management

# Awesome User Provisioning & Permissions Management

> A curated list of top User Provisioning and Permissions Management platforms — both SaaS/Hosted commercial solutions and open-source alternatives for identity lifecycle automation, SSO, and fine-grained access control.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Okta](#okta)
  - [Microsoft Entra ID](#microsoft-entra-id)
  - [Google Workspace / Cloud Identity](#google-workspace--cloud-identity)
  - [JumpCloud](#jumpcloud)
  - [OneLogin](#onelogin)
  - [Ping Identity](#ping-identity)
  - [Auth0](#auth0)
  - [CyberArk](#cyberark)
  - [AWS IAM](#aws-iam)
- [Open-Source Software](#-open-source-software)
  - [Keycloak](#keycloak)
  - [Evolveum midPoint](#evolveum-midpoint)
  - [Apache Syncope](#apache-syncope)
  - [Nubus](#nubus)
  - [Hanzo IAM](#hanzo-iam)
  - [GoSCIM](#goscim)
  - [scimgateway](#scimgateway)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted User Provisioning and Permissions Management platforms. These are not open-source but are included as reference points for feature comparison.

### Okta
**Type:** Enterprise identity and access management  
Okta is the most widely adopted vendor-neutral IdP, known for its extensive integration catalogue, lifecycle management, adaptive MFA, and Workflows automation. Strengths include neutrality across productivity suites, a mature provisioning engine, and broad SaaS coverage. Watch-outs: features are sold as separate products (MFA, lifecycle, governance), so total cost rises significantly beyond base SSO [citation:1]. The platform is best suited for organizations with complex, multi-vendor SaaS estates rather than those anchored to a single suite [citation:8].

### Microsoft Entra ID
**Type:** Identity platform within Microsoft 365  
Entra ID is the default choice for Microsoft-centric organizations. Basic SSO to third-party apps is included with Microsoft 365 at no extra charge, and the integration with Intune, Conditional Access, and the broader Microsoft security stack reduces operational friction [citation:1][citation:8]. The free tier provides usable standalone basics, while P1/P2 add conditional access and identity protection. Best fit: organizations already paying for Microsoft 365 E3/E5 where the marginal cost of identity is effectively zero [citation:8].

### Google Workspace / Cloud Identity
**Type:** Identity layer for Google-first organizations  
Google Workspace can serve as the IdP for third-party SaaS via SAML and OIDC, with 2-Step Verification, context-aware access, and auto-provisioning for supported apps. Cloud Identity offers the same identity layer without the productivity apps [citation:1]. Fewer lifecycle automation and policy options than dedicated IdPs, but for Google-first organizations under ~100 users, the built-in identity layer often covers the job without adding another vendor [citation:8].

### JumpCloud
**Type:** Open directory platform with device management  
JumpCloud combines cloud directory, SSO, MFA, LDAP/RADIUS, and cross-OS device management (Windows, macOS, Linux) in a single console. It is a common replacement for on-premises Active Directory in small and mid-sized companies [citation:1]. Strengths: breadth in one tool, cloud-native architecture, and strong SMB value. Watch-outs: large enterprises may need deeper policy and governance than JumpCloud provides [citation:15].

### OneLogin
**Type:** Simplified IAM with HR-driven provisioning  
OneLogin (part of One Identity) offers SSO, risk-based MFA (SmartFactor), directory integration, and HR-driven provisioning with a straightforward admin experience. Strengths: simpler than the largest suites, good value for growing businesses. Watch-outs: smaller integration ecosystem than Okta or Entra ID [citation:1].

### Ping Identity
**Type:** Complex enterprise federation and orchestration  
Ping Identity (including PingFederate and PingOne, plus the ForgeRock platform) is built for complex estates: multiple directories, on-premises and cloud apps, legacy protocols, and strict compliance requirements. Strengths: federation depth, orchestration, and deployment flexibility. Watch-outs: heavier implementation effort and quote-based pricing [citation:1].

### Auth0
**Type:** Developer-focused identity platform  
Auth0 is widely used for developer-facing authentication and authorization, with strong SDKs, extensibility, and a free tier for small projects. Often compared with Okta (which acquired Auth0). Pricing can escalate with identity provider connections and advanced features [citation:8].

### CyberArk
**Type:** Privileged access management (PAM)  
CyberArk focuses on privileged user management, credential vaulting, session isolation, and least-privilege enforcement for administrative accounts. While not a general-purpose IdP, it is a critical component of user provisioning for high-risk accounts and is often integrated alongside Okta or Entra ID.

### AWS IAM
**Type:** Cloud provider identity and permissions  
AWS IAM manages users, groups, roles, and policies for AWS resources. It is not a general enterprise IdP but is the foundational permissions layer for organizations running workloads on AWS, often federated with Okta, Entra ID, or Google Workspace for workforce identities.

---

## 🟩 Open-Source Software

Self-hosted, community-driven User Provisioning and Permissions Management tools. All listed projects offer source code you can deploy on your own infrastructure.

### Keycloak
**Stack:** Java | **License:** Apache-2.0  
The most widely deployed open-source IAM platform, providing SSO, identity brokering, user federation (LDAP/AD), social login, and fine-grained authorization. Widely used as the identity backbone in open-source stacks — IBM's Bob on-premises uses Keycloak for authentication, LDAP federation, and SCIM-based user synchronization [citation:4]. Supports OIDC, SAML, OAuth 2.0, and SCIM provisioning. Fine-grained permissions for user management are available via a preview feature [citation:11].  
**Best for:** Organizations wanting a proven, battle-tested IAM foundation with broad protocol support and an active community.

### Evolveum midPoint
**Stack:** Java | **License:** Open Source (subscription model)  
A comprehensive open-source Identity Governance and Administration (IGA) platform used in regulated industries like telecommunications. Provides automated provisioning/deprovisioning, policy-based approvals, segregation of duties controls, access certification campaigns, role mining, and non-human identity governance [citation:5]. MidPoint's approach is subscription-based with **no license fees** — you pay only for support, eliminating vendor lock-in [citation:5]. The UI is technical and case management interfaces could be improved, but the governance depth is unmatched among open-source options [citation:12].  
**Best for:** Organizations needing full IGA (access reviews, SoD, approvals, certifications) without per-identity licensing costs.

### Apache Syncope
**Stack:** Java | **License:** Apache-2.0  
An open-source IAM and IGA platform for managing digital identities, provisioning, authentication, and access control across enterprise environments. Supports user/group/role management, automated provisioning workflows, RBAC, delegated administration, LDAP/AD/database connectors, SAML 2.0, OIDC, and SCIM [citation:13]. Audit logging, compliance reporting, and a web-based admin console are included. Version 4.0 (Notturno) introduced improvements including OpenFGA integration and group relationships [citation:6].  
**Best for:** Organizations seeking a standards-based, Apache-governed IAM/IGA platform with strong connector support.

### Nubus
**Stack:** (Check repository) | **License:** AGPL-3.0-or-later  
A modular open-source IAM solution for centralized management of user identities, roles, permissions, and application access via a central web portal. Integrated SSO, self-service password changes, and user lifecycle management [citation:9]. Supports deployment on Kubernetes, on-premises, and hybrid infrastructures. Used by ZenDiS GmbH, Orange S.A., and several German state education ministries. Professional support available from Univention [citation:9].  
**Best for:** European organizations prioritizing digital sovereignty and open standards, with commercial support options.

### Hanzo IAM
**Stack:** Go | **License:** Apache-2.0  
An AI-first IAM and MCP gateway/auth server with a web UI. Supports OAuth 2.1, OIDC, SAML, CAS, LDAP, SCIM, WebAuthn, TOTP, MFA, and 40+ social login providers [citation:2]. Features RBAC, multi-tenancy, API-first design, and SCIM provisioning for automated user lifecycle management. Deploys via Docker.  
**Best for:** Teams wanting a modern, Go-based IAM with AI/MCP integration and broad protocol support.

### GoSCIM
**Stack:** Go | **License:** Open Source (per project)  
A lightweight, high-performance SCIM 2.0 server for user provisioning. Full RFC 7643/7644 compliance, dynamic schema loading, advanced filter parsing, and integration with Active Directory, LDAP, Salesforce, Slack, and more [citation:10]. Stateless design scales horizontally from small teams to 100,000+ users. Docker deployment.  
**Best for:** Developers needing a focused SCIM provisioning server without the overhead of a full IAM suite.

### scimgateway
**Stack:** Node.js | **License:** Open Source (per project)  
A SCIM gateway that bridges identity providers with target systems. Supports Basic Auth, Bearer Token, JWT, OAuth Client Credentials, and Entra ID-initiated provisioning [citation:3]. Includes IP allow-listing, configurable logging, and fine-grained control over SCIM group/attribute handling. Useful as a translation layer between IdPs and legacy systems that do not natively support SCIM.  
**Best for:** Organizations needing to connect an IdP's SCIM output to systems that lack native SCIM support.

---

## 📊 Comparison at a Glance

| Software | License | Type | Provisioning | Self-Hosted | Best For |
|----------|---------|------|--------------|-------------|----------|
| **Okta** | Proprietary | Enterprise IAM | ✅ SCIM | ❌ | Multi-vendor SaaS estates |
| **Microsoft Entra ID** | Proprietary | M365 identity | ✅ (P1/P2) | ❌ | Microsoft 365 organizations |
| **Google Workspace** | Proprietary | Google identity | ✅ (supported apps) | ❌ | Google-first organizations |
| **JumpCloud** | Proprietary | Directory + device mgmt | ✅ | ❌ | SMBs replacing AD |
| **OneLogin** | Proprietary | IAM | ✅ HR-driven | ❌ | Simpler mid-market IAM |
| **Ping Identity** | Proprietary | Enterprise federation | ✅ | ❌ | Complex hybrid estates |
| **Keycloak** | Apache-2.0 | IAM foundation | ✅ SCIM | ✅ | Proven open-source IAM |
| **Evolveum midPoint** | Open Source | IGA | ✅ Policy-driven | ✅ | Full governance without license fees |
| **Apache Syncope** | Apache-2.0 | IAM + IGA | ✅ Workflow | ✅ | Standards-based IGA |
| **Nubus** | AGPL-3.0 | Centralized IAM | ✅ Lifecycle | ✅ | European sovereignty |
| **Hanzo IAM** | Apache-2.0 | AI-first IAM | ✅ SCIM | ✅ | Modern Go IAM + MCP |
| **GoSCIM** | Open Source | SCIM server | ✅ SCIM 2.0 | ✅ | Focused provisioning server |
| **scimgateway** | Open Source | SCIM gateway | ✅ Bridge | ✅ | Connecting IdP to legacy systems |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source User Provisioning or Permissions Management tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem spans **full IAM/IGA suites** (Keycloak, midPoint, Syncope) and **focused provisioning components** (GoSCIM, scimgateway), which solve different layers of the problem.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
