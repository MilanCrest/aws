## Table of Contents
- [AWS Identity and Access Management (IAM)](#aws-identity-and-access-management-iam-overview)
- [IAM Policies](#iam-policies)
- [Docker](#Docker)
- [ECS, Fargate, and ECR](#ecs-fargate-and-ecr)
- [Amazon EKS](#amazon-eks-elastic-kubernetes-service)
- [Amazon Kinesis](#amazon-kinesis)

---
### **1. What is IAM?**
- **IAM** stands for **Identity and Access Management** in AWS.
- It’s a **global service** used to manage who can access your AWS account and what they can do.

### **2. Root User**
- The **Root User** is created when you first set up your AWS account. 
- It has **full access** to everything in AWS but should only be used for **account setup**.
- **Best Practice**: Don’t use or share the root user for daily tasks.

### **3. Users and Groups**
- **Users** represent people in your organization who need access to AWS.
- **Groups** are collections of users with similar responsibilities.
  
   **Example**:
   - **Developers group**: Alice, Bob, and Charles (work as developers).
   - **Operations group**: David and Edward (work in operations).

- A **user** can belong to **multiple groups**.
- Some users may not belong to any group, but **best practice** is to group users for better management.

### **4. Permissions (Policies)**
- To allow users or groups to do specific tasks in AWS, you assign them **permissions**.
- Permissions are defined in **policies** (JSON documents).
  
   **Example**:
   - A policy might allow users to:
     - Use **EC2** (virtual servers).
     - Use **Elastic Load Balancing** (traffic management).
     - Use **CloudWatch** (monitoring).
  
- Policies are written in a readable format that explains what users can or cannot do.

### **5. Least Privilege Principle**
- The **Least Privilege Principle** means giving users only the minimum permissions they need.
  
   **Example**:
   - If a user only needs access to EC2, don’t give them access to other services like S3 or Lambda.
  
- This reduces security risks and prevents unnecessary costs.

### **6. Next Steps**
- In the next session, you will practice creating users and groups in IAM.
