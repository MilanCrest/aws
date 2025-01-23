# AWS Notes

## Table of Contents
1. [Protecting IAM Users and Groups](#protecting-iam-users-and-groups)

### Protecting IAM Users and Groups**  

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

### **Topic Overview**
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

### **Use Cases**
- **Management Console:**  
  - Beginners or GUI-based interactions.  
- **CLI:**  
  - Automating tasks and scripting.  
  - Example: Copying files to S3 with `aws s3 cp`.  
- **SDK:**  
  - Embedding AWS services in applications.  
  - Example: Build an app using Python's Boto SDK to query AWS APIs.

### **Exam Focus**
- **Management Console:** User credentials, MFA importance.  
- **CLI:** Access keys, command usage, automation capabilities.  
- **SDK:** Programming language support, integration for applications.  
- **Access Keys:** Private and non-shareable; treat like passwords.  
- **Boto SDK:** Python library used for AWS CLI and other applications.  
