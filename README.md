# AWS Notes

## Table of Contents
1. [IAM](#iam)
    - [IAM: Users, Groups, Policies](#iam-users-groups-policies)
    - [IAM Policies](#iam-policies)
    - [Protecting IAM Users and Groups](#protecting-iam-users-and-groups)
    - [Management Console, CLI and SDK](#management-console-cli-and-sdk)
    - [Cloud Shell](#cloud-shell)
    - [IAM Roles](#iam-roles)
    - [IAM Security Tools](#iam-security-tools)
    - [IAM Shared Responsibility Model](#iam-shared-responsibility-model)
2. [EC2](#ec2)
    - [EC2: Elastic Compute Cloud](#ec2)
    - [EC2 Instance Types](#ec2-instance-types)
    - [AWS Security Groups](#aws-security-groups)
---
## IAM
### IAM: Users, Groups, Policies

#### **Core Concepts**
- **Root Account**: Only for setup tasks, never for daily use.  
- **IAM Users**: One user per individual, no sharing of credentials.  
- **IAM Groups**: Groups are collections of users, used to assign permissions.  
- **User-Group Association**: Users can belong to multiple groups.  
- **Inline Policies**: Policies attached directly to users, not groups.  
- **IAM Policies**: JSON documents defining permissions (e.g., EC2, CloudWatch).  
- **Least Privilege**: Grant only the minimum required permissions.  

#### **Key Features**
- **Group Restrictions**: Groups can only contain users, not other groups.  
- **Permission Assignment**: Defined via IAM policies.  
- **Policy Syntax**: Policies are written in JSON format (actions, resources, conditions).  

#### **Tools**
- **IAM Console**: Create users, groups, and assign policies.  
- **IAM Policies**: JSON structure to define permissions.  

---

### IAM Policies

#### **Core Concepts**  
- **IAM Policies**: Define permissions for users and resources.  
- **Groups**: Assign policies at the group level for multiple users.  
- **Inline Policies**: User-specific policies, not tied to groups.  
- **Policy Inheritance**: Policies from multiple groups can be combined for a user.  

#### **Policy Structure**  
- **Version**: Policy language version (e.g., 2012-10-17).  
- **ID**: Optional identifier for the policy.  
- **Statements**: Core part of a policy, contains specific permissions.  
- **Sid**: Optional Statement ID.  
- **Effect**: Defines whether access is "Allow" or "Deny".  
- **Principal**: Specifies the user, account, or role the policy applies to.  
- **Action**: Defines which API actions are allowed/denied (e.g., s3:PutObject).  
- **Resource**: Specifies the resource (e.g., S3 bucket) to which the action applies.  
- **Condition**: Optional, specifies when the policy should apply.  

#### **Policy Application**  
- **Group-Level Policy**: Applies to all users within a group.  
- **Inline Policy**: Tied to a specific user.  
- **Multiple Group Policies**: Policies from different groups can be combined for a user.  

---

### Protecting IAM Users and Groups

#### **Core Concepts**  
- **Password Policy:** Strengthens security by enforcing password rules.  
- **Multi-Factor Authentication (MFA):** Adds an extra layer of security by requiring both a password and a physical/virtual device.  

#### **Password Policy Features**  
- Minimum password length.  
- Require character types (uppercase, lowercase, numbers, special characters).  
- Allow/disallow users to change their passwords.  
- Enforce password expiration (e.g., 90 days).  
- Prevent password reuse.  

#### **MFA Device Types**  
1. **Virtual MFA Device:**  
   - Examples: Google Authenticator (single device), Authy (multi-device support).  
   - Use for managing multiple tokens for IAM/root accounts on one device.  
2. **U2F Security Key:**  
   - Example: YubiKey (physical device).  
   - Supports multiple users with a single key.  
3. **Hardware Key Fob:**  
   - Example: Gemalto (physical device, third-party).  
4. **GovCloud Key Fob:**  
   - Example: SurePassID (specific to AWS GovCloud).  

---

### **Management Console, CLI and SDK**
- **Management Console:** Web-based interface for AWS.
- **CLI (Command Line Interface):** Tool to interact with AWS services via command-line commands.
- **SDK (Software Development Kit):** Libraries to integrate AWS APIs in application code.

### **Core Concepts**
- **Access Methods:** 
  - Management Console: Username, password, and optional MFA.  
  - CLI: Uses access keys for authentication.  
  - SDK: Programmatic access with access keys.

- **Access Keys:** Credentials (Access Key ID + Secret Access Key) used for CLI and SDK authentication.  
  - **Important:** Treat like a password; do not share.

### **Key Features**
- **Management Console:**
  - GUI for AWS services.
  - Multi-factor authentication support.
- **CLI:**
  - Command-based interaction.
  - Supports automation via scripts.
  - Open-source; available on GitHub.
- **SDK:**
  - Language-specific libraries (e.g., Python, Java, Node.js).
  - Enables application-level AWS service interaction.
  - Mobile SDK for Android/iOS; IoT SDK for connected devices.

---

### **Cloud Shell**

#### **Core Concepts**
- **Cloud Shell**: AWS browser-based terminal.
- **Region-Specific**: Limited availability; check regions.
- **CLI Pre-installed**: AWS CLI ready to use.
- **Persistent Storage**: Files saved across sessions.

#### **Key Features**
- **Command Execution**: Run AWS CLI commands directly.
- **Customization**: Font size, themes (light/dark).
- **File Operations**: Upload/download files, persistent storage.
- **Multiple Tabs**: Split views, multi-terminal access.

#### **Use Cases**
- **Default Region Testing**: Match login region.
- **Temporary Development**: Script/command execution without local setup.
- **File Management**: Transfer files between local and Cloud Shell.

---

### IAM Roles  

#### **Core Concepts**  
- **IAM Role**: Temporary permissions for AWS services.  
- **AWS Services**: Used by EC2, Lambda, CloudFormation, etc.  
- **Purpose**: Assign permissions to AWS services for secure actions.  

#### **Key Features**  
- **Temporary Credentials**: Secure and short-lived access.  
- **Service Integration**: Works with AWS services (e.g., EC2, Lambda).  
- **No Hard-Coded Keys**: Enhances security by avoiding static credentials.  

#### **Use Cases**  
- **EC2 Instance Role**: Access S3 or other AWS services securely.  
- **Lambda Role**: Interact with DynamoDB or other resources.  
- **CloudFormation Role**: Automate resource provisioning.  

---

### IAM Security Tools

#### **Core Concepts**
- **IAM Credentials Report**: Account-level, user credentials status.
- **IAM Access Advisor**: User-level, service permissions, last accessed.

#### **Key Features**
- **Credentials Report**: Audit credentials, identify inactive.
- **Access Advisor**: Least privilege, unused permissions, optimize access.

#### **Use Cases**
- **Auditing**: Credentials report for account-wide security checks.
- **Permission Reduction**: Access Advisor to remove excess permissions.

---

### IAM Shared Responsibility Model

- **Definition**: Shared responsibility, security **of** the cloud, security **in** the cloud.  
- **AWS Responsibilities**:  
  - Infrastructure  
  - Global network security  
  - Service configuration  
  - Vulnerability analysis  
  - Compliance (SOC, ISO)  
- **Customer Responsibilities**:  
  - IAM (Users, Groups, Roles, Policies)  
  - Permissions (Least privilege, Access patterns)  
  - Multi-Factor Authentication (MFA)  
  - Access key rotation  
  - Monitoring (IAM tools: Credentials Report, Access Advisor)  
- **Key Distinction**:  
  - AWS = Secures the **cloud**  
  - Customer = Secures **usage in the cloud**  

---

## EC2

#### EC2
- EC2 = Elastic Compute Cloud (Infrastructure as a Service, IaaS).  
- Rent virtual servers (EC2 instances) on-demand with full customization.  
- Key components:
  - **Instances:** Virtual servers.
  - **EBS Volumes:** Persistent storage attached to instances.
  - **Elastic Load Balancer (ELB):** Distributes traffic across multiple instances.  
  - **Auto Scaling Group (ASG):** Automatically adjusts instances based on demand.  

#### Customizing EC2 Instances  
- Choose Operating Systems: **Linux, Windows, macOS**.  
- Configure resources:
  - **vCPUs (Compute Power)**  
  - **RAM (Memory)**  
  - **Storage Options:** EBS, EFS (network-attached), or Instance Store (hardware-attached).  
- Networking options:
  - Public or private IPs.
  - Firewall rules via **Security Groups**.  

#### Instance Bootstrapping  
- **EC2 User Data:**
  - Automates setup tasks during instance launch (e.g., installing software, updates).  
  - Runs **once** with **root privileges**.  
- Use cases: Deploying applications, configuring the environment.  

#### EC2 Instance Types to Remember  
- **t2.micro:** Free tier eligible, 1 vCPU, 1 GB RAM. Best for testing or low-traffic apps.  
- **t2.xlarge:** 4 vCPUs, 16 GB RAM. Moderate performance.  
- **c5d.4xlarge:** High compute, 16 vCPUs, 32 GB RAM, 400 GB NVMe SSD, 10 Gbps network.  

#### Benefits of EC2  
- **Flexibility:** Full control over instance configurations.  
- **Scalability:** Scale up or down based on demand with ASG and ELB.  
- **Cost Efficiency:** Pay-as-you-go model, no upfront hardware costs.  
- **Global Reach:** Deploy in AWS Regions and Availability Zones for low latency and high availability.  

#### AWS Free Tier  
- **t2.micro** included: 750 hours/month free usage.  
- Perfect for testing and learning AWS services.

---

#### EC2 Instance Types

- Seven instance types.
- Key attributes: Computing, Memory, Networking.
- ex. c5d.4xlarge (c: Instance class, 5: version, d: Instance variant (optional), 4xlarge: Size)
- Identify Instance Classes:
  - T, M, A: **General purpose** (Web, Repo, etc.)
  - C: **Compute optimized** (High Processing, Game, ML, etc.)
  - R, X, Z: **Memory optimized** (Large in-memory dataset for fast performance, ElastiCache, BI)
  - I, D, H: **Storage optimized** (High performance local storage, Distributed sys., warehouses etc.)
- t2.micro: Free tier eligible, 750 hrs/month FREE

---

#### AWS Security Groups

- **Virtual Firewalls**: Control inbound/outbound traffic for instances.
- **Allow Rules Only**: No deny rules; only allows.
- **Inbound Traffic**: Blocked by default, requires explicit allow.
- **Outbound Traffic**: Allowed by default, can be restricted.
- **Region/VPC Specific**: Tied to a specific Region or VPC.
- **Cross-SG Access**: Can allow from another SG instead of IPs.
- **Timeout/Connection Refused**:
  - **Timeout**: Traffic blocked.
  - **Connection Refused**: Traffic allowed, app not running.
- **Ports and Protocols**:
  - `22`: SSH (for Linux)
  - `21`: FTP
  - `80`: HTTP
  - `443`: HTTPS
  - `3389`: RDP (Remote Desktop for Windows)

---
