# AWS Notes

## Table of Contents
1. [Protecting IAM Users and Groups](#protecting-iam-users-and-groups)
2. [Management Console, CLI and SDK](#management-console-cli-and-sdk)
3. [Cloud Shell](#cloud-shell)

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
