# Hi — I'm Sammatha Adams | System Administration & Cloud Infrastructure

IT professional with hands-on experience in **Windows Server administration, Active Directory Domain Services (AD DS), ServiceNow ITSM workflows, and PowerShell automation**.

My background combines production help desk experience with lab-based infrastructure deployments in **Microsoft Azure and AWS**, focusing on identity management, access control, and automation-driven system operations.

---

## 🗂️ Lab Series: Azure IaC with Terraform

A two-part lab series building progressively from file server infrastructure to cloud access control — each lab building directly on the last.

---

### 🔗 [Lab 1 — NTFS File Server Lab](https://github.com/sammathaadams/ntfs-lab-terraform)

Used **Terraform (HCL)** to provision a full three-VM Azure environment from code — defining all VMs, networking, and resource groups as Infrastructure-as-Code — then configured NTFS permissions, SMB file shares, and Active Directory group-based access control on top of it.

**Infrastructure (all provisioned via Terraform):**

* DC01 — Domain Controller (Windows Server 2022)
* FS01 — File Server (Windows Server 2022)
* CLIENT01 — Client Workstation (Windows 11 Pro)
* Domain: `lab.local` | VNet: `10.0.0.0/16` | Region: Central US

**Terraform / IaC Skills Practiced:**

* Wrote and applied `.tf` config files to deploy a multi-VM Azure environment reproducibly
* Defined variables, outputs, and resource dependencies in HCL
* Used `terraform init`, `plan`, `apply`, and `destroy` through the full IaC lifecycle
* Separated concerns across `main.tf`, `variables.tf`, `outputs.tf`, and `versions.tf`

**Additional Areas Practiced:**

* AD DS forest promotion and domain-join automation via PowerShell
* NTFS permission configuration with inheritance flags (Full Control, Modify, Read, Deny)
* SMB share creation and department-level access segmentation (Finance, HR, Sales, IT)
* GPO configuration for RDP access control

---

### 🔗 [Lab 2 — Azure RBAC Access Control Lab](https://github.com/sammathaadams/rbac-lab-terraform)

Used **Terraform** to layer Azure RBAC role assignments onto the existing Lab 1 infrastructure — scoped to the FS01 file server at the VM level for least-privilege access. Validated automatically with PowerShell and Azure CLI.

**Terraform / IaC Skills Practiced:**

* Used Terraform `data` sources to reference existing Lab 1 infrastructure without recreating it — a real-world IaC pattern for managing live environments
* Configured a **remote state backend** (Azure Blob Storage) so state is stored securely in the cloud, not locally
* Separated RBAC logic into a dedicated `rbac.tf` file, keeping infrastructure concerns modular
* Marked sensitive values (`sensitive = true`) in `variables.tf` to redact Object IDs from plan/apply output
* Applied the full IaC lifecycle across two connected repos with separate state keys

**Additional Areas Practiced:**

* Azure RBAC vs. NTFS permissions — understanding two distinct access control layers
* Assigning built-in Azure roles (Owner, VM Contributor, Reader) scoped to a specific resource
* Automated validation with a PowerShell script (`validate-lab.ps1`) — pass/fail per assignment
* Live permission testing per persona (SysAdmin, SupportTech, Auditor)
* Least-privilege design: role scope limited to FS01 only, not the subscription or resource group

| Role | Start/Stop VM | RDP | Delete VM | Manage RBAC |
| --- | --- | --- | --- | --- |
| Owner (SysAdmin) | ✅ | ✅ | ✅ | ✅ |
| VM Contributor (SupportTech) | ✅ | ✅ | ❌ | ❌ |
| Reader (Auditor) | ❌ | ❌ | ❌ | ❌ |

---

## 🖥️ System Administration & Infrastructure Labs

### 🔗 [Active Directory VM Lab — AWS](https://github.com/sammathaadams/active-directory-vm-lab-AWS-)

Deployed and configured a Windows Server domain controller in **AWS EC2**, implementing Active Directory Domain Services in a cloud-hosted lab environment.

**Key Areas Practiced:**

* AD DS installation and domain controller configuration
* Organizational Unit (OU) creation and structure
* User and group provisioning
* Security group–based access control
* Domain authentication and DNS configuration
* Group Policy (GPO) configuration fundamentals

---

### 🔗 [AD PowerShell Automation Lab](https://github.com/sammathaadams/AD-PowerShell-automation-LAB-)

Automated Active Directory administrative tasks using **PowerShell** within a Windows domain environment.

**Automation Focus:**

* Scripted user account creation
* Group membership assignment and OU placement logic
* Streamlined identity lifecycle workflows
* Reduced manual provisioning steps through scripting

---

## ☁️ Cloud Infrastructure & Deployment Labs

### 🔗 [Azure Static Website CI/CD](https://github.com/sammathaadams/azure-static-website-github-actions)

Deployed a static website to **Azure Blob Storage** with automated deployment using **GitHub Actions** and **Azure CLI**.

**Infrastructure Components:**

* Azure resource configuration and Blob Storage hosting
* CI/CD pipeline automation with branch-based deployment workflow
* Service principal authentication for GitHub Actions

---

## 🛠️ ITSM & Administrative Automation Labs

### 🔗 [ServiceNow PowerShell Automation Lab](https://github.com/sammathaadams/SNOW-PowerShell-automation-lab)

Integrated **PowerShell** with the ServiceNow REST Table API to simulate automated incident management workflows.

**Technical Highlights:**

* REST API authentication and JSON payload handling
* Programmatic incident creation and ITSM workflow automation

---

### 🔗 [ServiceNow Password Reset Lab](https://github.com/sammathaadams/ServiceNow-PW-reset-Lab)

Simulated help desk password reset workflows using a **ServiceNow Developer Instance** aligned with Active Directory identity processes.

**Workflow Practice:**

* Identity verification simulation and password reset lifecycle handling
* Incident documentation and access restoration procedures

---

## ⚙️ Core Technical Areas

### Systems Administration

* Windows Server | Active Directory Domain Services (AD DS) | Group Policy (GPO)
* NTFS Permissions & SMB File Shares | User Lifecycle Management
* DNS & Domain Troubleshooting | Identity & Access Management

### Cloud Platforms & IAM

* Microsoft Azure (VMs, Blob Storage, VNets, RBAC, Remote State)
* AWS EC2 (Windows Server Lab Environment)
* Azure Role-Based Access Control (RBAC) | Least-Privilege Design

### Infrastructure-as-Code — Terraform

* Multi-VM Azure environment provisioning with HCL
* Resource modularization across `main.tf`, `variables.tf`, `outputs.tf`, `rbac.tf`
* Remote state management with Azure Blob Storage backend
* Terraform `data` sources for referencing live infrastructure without recreation
* Sensitive variable handling and output redaction
* Full IaC lifecycle: `init` → `plan` → `apply` → `destroy` across multi-repo lab series

### Automation & Scripting

* PowerShell (AD automation, RBAC validation, permission testing)
* Azure CLI | GitHub Actions (CI/CD) | ServiceNow REST API
* RDP / Remote Administration

---

## 📈 Current Focus

* Expanding hybrid identity knowledge (On-Prem AD + Microsoft Entra ID)
* Advanced Group Policy and security baseline configuration
* Infrastructure automation and state management within Azure (Terraform)
* Strengthening cloud networking fundamentals (DNS, VNets, NSGs, TCP/IP)

---

## 🎯 Career Direction

Seeking a **System Administrator or Cloud Infrastructure Support role** where I can apply Windows domain administration, access control design, automation scripting, and cloud infrastructure knowledge in a production environment.

---

📧 [SammDion@gmail.com](mailto:SammDion@gmail.com)
🔗 linkedin.com/in/sammatha-adams
