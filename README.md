# Expense Application Deployment using Ansible

# Project Overview
This project demonstrates automated deployment of a multi-tier Expense application using Ansible.

The objective is to eliminate manual configuration and ensure consistent, repeatable deployments across multiple servers by leveraging Infrastructure as Code (IaC) principles.

The setup includes application provisioning, dependency installation, and service configuration using Ansible playbooks.

---

# Objectives

- Automate application deployment using Ansible
- Ensure consistent configuration across servers
- Reduce manual errors and deployment time
- Implement reusable and scalable automation
- Simulate real-world DevOps deployment workflow

---

# Tech Stack

- Configuration Management: Ansible
- Language: YAML (Playbooks)
- Application: Expense App (Node.js / Web-based)
- Infrastructure: Linux Servers (AWS EC2 / VM)
- Connectivity: SSH (Agentless)
- Version Control: Git

---

# Architecture

- Control Node: Executes Ansible playbooks
- Managed Nodes:
  - Backend/Application Server
  - Database Server
  - Frontend/Web Server
- Inventory: Defines server groups
- Playbooks: Automate deployment and configuration

Ansible uses agentless architecture and communicates securely over SSH to configure target systems.

---

# Repository Structure
├── inventory
├── playbooks/
│ ├── backend.yml
│ ├── frontend.yml
│ ├── database.yml
│ └── common.yml
├── roles/
├── ansible.cfg
└── README.md


---

# Deployment Workflow

# 1. Inventory Configuration
- Define target servers and groups
- Configure SSH access

# 2. Common Setup
- Install required packages
- Configure system dependencies

# 3. Database Setup
- Install and configure database
- Create required schema and users

# 4. Backend Deployment
- Install runtime (Node.js)
- Deploy backend application
- Configure service management

# 5. Frontend Deployment
- Install and configure web server (Nginx)
- Deploy frontend application
- Configure reverse proxy

---

# Key Features

- Agentless automation using Ansible
- Idempotent playbook execution
- Modular playbook design
- Multi-tier application deployment
- Scalable and reusable configuration

---

# Engineering Highlights

### Automation
Automates complete application deployment process across multiple servers.

### Idempotency
Ensures consistent results even when playbooks are executed multiple times.

### Modularity
Uses structured playbooks for different application layers.

### Scalability
Supports deployment across multiple environments with minimal changes.

---

# Execution Steps

### Step 1: Install Ansible
```bash
sudo apt update
sudo apt install ansible -y

Step 2: Configure Inventory
nano inventory
Step 3: Test Connectivity
ansible all -m ping -i inventory
Step 4: Execute Playbooks
ansible-playbook -i inventory playbooks/database.yml
ansible-playbook -i inventory playbooks/backend.yml
ansible-playbook -i inventory playbooks/frontend.yml


Application Flow
User accesses frontend via browser
Frontend routes requests to backend
Backend processes logic
Backend interacts with database
Response is returned to user

Challenges & Solutions
Challenge	Solution
Managing multi-tier dependencies	Sequential execution of playbooks
SSH connectivity issues	Configured key-based authentication
Debugging failures	Used verbose logging
Reusability	Modularized playbooks


Future Enhancements
Integrate with CI/CD pipeline (Jenkins)
Use Terraform for infrastructure provisioning
Implement dynamic inventory (AWS)
Convert playbooks into reusable roles
Add monitoring and logging setup

Key Learnings
Ansible simplifies application deployment automation
Infrastructure as Code improves consistency and scalability
Modular design enhances maintainability
Automation reduces deployment time and human errors


