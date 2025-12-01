# Azure Security Study Plan

This study plan is designed to help you master Azure Security, from foundational concepts to advanced security engineering and operations. It aligns with Microsoft certifications like AZ-500 and SC series.

## ToC
1. [Azure Fundamentals](#azure-fundamentals) - 2 weeks
2. [Identity and Access Management](#identity-and-access-management) - 2 weeks
3. [Platform Protection](#platform-protection) - 2 weeks
4. [Security Operations](#security-operations) - 2 weeks
5. [Resources](#resources)

## Azure Fundamentals
**Duration: 2 weeks**

Start here if you are new to Azure.

### Week 1-2: Cloud Basics (AZ-900 level)
1. **Core Concepts:**
   - Regions, Availability Zones, Subscriptions, Resource Groups.
   - IaaS, PaaS, SaaS in Azure context.
2. **Core Services:**
   - Compute (VMs, App Service, AKS).
   - Networking (VNet, NSG, Load Balancers).
   - Storage (Blob, File, Disk).
3. **Basic Security:**
   - Shared Responsibility Model.
   - Azure Policy & Blueprints basics.
   - Microsoft Defender for Cloud (Free tier).

## Identity and Access Management
**Duration: 2 weeks**

Identity is the new perimeter.

### Week 3-4: Microsoft Entra ID (formerly Azure AD)
1. **Core Identity:**
   - Users, Groups, Service Principals, Managed Identities.
   - Hybrid Identity (Azure AD Connect).
2. **Access Control:**
   - **RBAC:** Built-in roles, Custom roles, Scope (Mgmt Group > Sub > RG > Resource).
   - **Conditional Access:** Policies based on location, device state, risk.
3. **Identity Protection:**
   - PIM (Privileged Identity Management).
   - MFA and Passwordless auth.
   - Identity Protection (Risk detection).

## Platform Protection
**Duration: 2 weeks**

Securing the infrastructure and data.

### Week 5-6: Network & Compute
1. **Network Security:**
   - NSGs vs ASGs.
   - Azure Firewall & Azure Firewall Manager.
   - DDoS Protection (Basic vs Standard).
   - Private Link & Service Endpoints.
2. **Compute & Container Security:**
   - VM security (Bastion, JIT access, Disk Encryption).
   - AKS Security (Network policies, private clusters).
3. **Data Security:**
   - Key Vault (Secrets, Keys, Certs).
   - Storage Security (SAS tokens, Access Keys, Encryption).
   - SQL Database Security (TDE, Firewall, Auditing).

## Security Operations
**Duration: 2 weeks**

Monitoring and responding to threats.

### Week 7-8: Defender & Sentinel
1. **Microsoft Defender for Cloud:**
   - CSPM (Cloud Security Posture Management) - Secure Score.
   - CWP (Cloud Workload Protection) - Alerts for VMs, Storage, SQL, Containers.
2. **Microsoft Sentinel (SIEM/SOAR):**
   - Connecting data sources.
   - KQL (Kusto Query Language) basics for hunting.
   - Creating Analytics Rules and Incidents.
   - Automation with Playbooks (Logic Apps).

## Resources
### Certifications
- **AZ-500:** Azure Security Technologies (Core certification).
- **SC-900:** Security, Compliance, and Identity Fundamentals.
- **SC-200:** Security Operations Analyst (Sentinel/Defender focus).
- **SC-300:** Identity and Access Administrator (Entra ID focus).

### Learning Paths
- [Microsoft Learn: Azure Security Engineer](https://learn.microsoft.com/en-us/credentials/certifications/azure-security-engineer/)
- [Microsoft Learn: SC-200](https://learn.microsoft.com/en-us/credentials/certifications/security-operations-analyst/)

### Labs & Practice
- [Azure Citadel](https://azurecitadel.com/)
- [Microsoft GitHub Labs](https://github.com/MicrosoftLearning) (Search for AZ-500)
