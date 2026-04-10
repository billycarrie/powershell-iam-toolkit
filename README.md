# **PowerShell IAM Toolkit**

> Automation scripts for day-to-day Identity & Access Management operations — built for Microsoft Entra ID in SMB environments.

## **Status**

📋 **Planned** — structure defined, scripts being developed alongside `entra-id-playbook` and `nhi-lifecycle-mgmt`.

---

## **What This Covers**

| Script | Purpose | Status |
|---|---|---|
| `Get-NHIInventory.ps1` | Discover and report all Non-Human Identities in the tenant | 📋 Planned |
| `Get-StaleGuestAccounts.ps1` | Identify guest accounts with no sign-in activity in 90+ days | 📋 Planned |
| `Get-ExpiredSecrets.ps1` | Report app registrations with expired or near-expiry secrets | 📋 Planned |
| `Get-OrphanedApps.ps1` | Find app registrations with no owner assigned | 📋 Planned |
| `Export-CAPolicy.ps1` | Export all Conditional Access policies to JSON for documentation | 📋 Planned |
| `Review-AdminRoleAssignments.ps1` | Report all privileged role assignments for access review | 📋 Planned |
| `New-NHICertificate.ps1` | Generate self-signed certificate for NHI certificate-based auth | 📋 Planned |

---

## **Repo Structure**

```
powershell-iam-toolkit/
│
├── README.md
│
├── scripts/
│   ├── discovery/
│   │   ├── Get-NHIInventory.ps1
│   │   ├── Get-OrphanedApps.ps1
│   │   └── Get-ExpiredSecrets.ps1
│   ├── governance/
│   │   ├── Get-StaleGuestAccounts.ps1
│   │   └── Review-AdminRoleAssignments.ps1
│   └── reporting/
│       └── Export-CAPolicy.ps1
│
└── docs/
    └── script-usage-guide.md
```

---

## **Prerequisites**

```powershell
# Required modules
Install-Module Microsoft.Graph -Scope CurrentUser
Install-Module AzureAD -Scope CurrentUser

# Connect to tenant
Connect-MgGraph -Scopes "User.Read.All","Application.Read.All","Directory.Read.All"
```

---

## **SMB Context**

Scripts built and tested against the **Carrie Cares** Entra ID P2 sandbox — a simulated retail/ecommerce environment with ~200 employees. All scripts are designed to run with read-only permissions where possible, following least privilege principles.

---

## **Related Repos**

| Repo | Focus | Status |
|---|---|---|
| [nhi-lifecycle-mgmt](https://github.com/billycarrie/nhi-lifecycle-mgmt) | Non-Human Identity governance | ✅ Complete |
| [entra-id-playbook](https://github.com/billycarrie/entra-id-playbook) | Entra ID operational runbooks | 🚧 In progress |
| [powershell-iam-toolkit](https://github.com/billycarrie/powershell-iam-toolkit) | IAM automation scripts | 📋 Planned |
| [iam-program-framework](https://github.com/billycarrie/iam-program-framework) | IAM program design templates | 📋 Planned |
| [zero-trust-identity](https://github.com/billycarrie/zero-trust-identity) | Zero Trust identity architecture | 📋 Planned |

---

## **Author**

**Billy Carrie** — IAM Engineer | Founding M&A Security Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/billycarrie/)
