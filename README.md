# 🚀 Ansible Role-Based Automation
<img width="1530" height="515" alt="image" src="https://github.com/user-attachments/assets/16ead1e3-3a17-4142-9878-4d207da079a9" />

## 📌 Overview

This project provides a **role-based Ansible automation framework** designed to configure and manage Linux servers in a clean, reusable, and scalable way.

The main focus of this project is to demonstrate:
-  Proper usage of Ansible Roles
-  Clean project structure following best practices
-  Separation of configuration from execution logic
-  Reusable automation suitable for real-world DevOps environments

---

## 🎯 Project Objective

The goal of this project is to automate the creation of a **consistent server baseline** for Linux systems.

Instead of writing monolithic playbooks, this project uses **Ansible Roles** to:
-  Improve maintainability
-  Enable reusability across environments
-  Make automation easier to extend and reason about

---

## ✨ Features

-  Modular role-based architecture
-  Centralized server baseline configuration
-  Variable-driven design for flexibility
-  Idempotent execution using Ansible best practices
-  Secure access model using a dedicated Ansible user
-  Ready to be extended with additional roles (security, monitoring, hardening)

---

## 🔐 Security Design: Dedicated Ansible User

For security and best practices, this project is designed to use a **dedicated system user named ansible** on target hosts.

This approach provides several advantages:
-  No root login over SSH
-  No credentials stored in the inventory file
-  Clear separation between automation access and human users
-  Safer and more auditable automation access

The ansible user is expected to:
-  Authenticate using SSH key-based authentication
-  Have passwordless sudo permissions for required administrative tasks

By using this model, the inventory file remains clean and free of sensitive credentials.

---

## 🗂 Project Structure

The project is organized as follows:

- roles/  
  Contains all Ansible roles used in the project

- roles/server-baseline/  
  Implements the baseline configuration for Linux servers

- inventory/  
  Defines target hosts and groups

- site.yml  
  Main playbook that applies roles to target hosts

This structure keeps the project clean and easy to scale as new roles are added.

---

## 📦 Included Roles

### 🖥 Server Baseline Role

The server-baseline role is responsible for:
-  Applying basic system configuration
-  Installing commonly required packages
-  Managing essential services
-  Enforcing consistent baseline settings

Detailed documentation for this role is available inside:
- roles/server-baseline/README.md

---

## 🧰 Requirements

Before running this project, ensure the following requirements are met:

- Ansible installed on the control machine
- SSH key-based access to target servers
- Python available on target hosts
- A configured ansible user on target machines
- A properly defined inventory file

---

## ▶️ How to Run the Project

### Step 1: Clone the Repository

git clone https://github.com/MohammedMourad1/Ansible-role-based-automation.git  
cd Ansible-role-based-automation

---

### Step 2: Configure Inventory

Edit or create an inventory file to define your target hosts.

The inventory does **not** contain usernames or passwords.  
Ansible connects using the dedicated ansible user and SSH keys.

Example path:
- inventory/hosts

---

### Step 3: Review Variables

Review default variables located in:
- roles/server-baseline/defaults/main.yml

Override variables if needed to match your environment.

---

### Step 4: Run the Playbook

ansible-playbook site.yml -i inventory/hosts --become

Ansible will connect to the target hosts using the ansible user and apply the defined roles.

---

## ✅ Verification

After execution, you can verify the results by:
- 🔍 Checking installed packages
- 🔄 Ensuring required services are running
- 📄 Confirming system configuration changes were applied successfully

---

## 💡 Use Cases

This project can be used for:
-  Preparing newly provisioned servers
-  Enforcing consistent configurations across environments
-  Demonstrating secure Ansible automation practices
-  Serving as a foundation for larger DevOps automation projects

---

## 🛣 Future Improvements

Possible enhancements include:
-  Adding security hardening roles
-  Supporting additional Linux distributions
-  Integrating monitoring and logging roles
-  Introducing CI testing for roles

---

## 👤 Author

Mohammed Ahmed Mourad  
DevOps Engineer

---

## 📄 License

MIT
