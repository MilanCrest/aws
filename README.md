# AWS Notes

## Table of Contents
1. [Protecting IAM Users and Groups](#protecting-iam-users-and-groups)
2. [Management Console, CLI and SDK](#management-console-cli-and-sdk)
3. [Cloud Shell](#cloud-shell)
4. [IAM Roles](#iam-roles)
5. [IAM Security Tools](#iam-security-tools)
6. [IAM Shared Responsibility Model](#iam-shared-responsibility-model)

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
