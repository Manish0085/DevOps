# Day 7 – Password-less SSH Authentication Setup 🔐

## 📌 Task Overview
The system administration team requires **password-less SSH access** from the **jump host** to all **app servers** so that automation scripts can run without manual intervention.

This task focuses on setting up **secure key-based authentication** using SSH.

---

## 🎯 Objective
Configure password-less SSH login from:
- **User:** `thor` (Jump Host)
- **To:** All app servers using their **respective sudo users**

---

## 🖥️ Environment Details

| Component | Details |
|--------|--------|
| Jump Host User | `thor` |
| App Server 1 | `tony@stapp01.stratos.xfusioncorp.com` |
| App Server 2 | `steve@stapp02.stratos.xfusioncorp.com` |
| App Server 3 | `banner@stapp03.stratos.xfusioncorp.com` |
| Datacenter | Stratos Datacenter |
| Organization | xFusionCorp Industries |

---

## 🛠️ Steps Performed

### 1️⃣ Generate SSH Key on Jump Host
```bash
ssh thor@jumphost
# Login to Jump Host as thor


ssh-keygen -t rsa -b 4096
# Generate SSH key pair (press ENTER for all prompts)


ls ~/.ssh
# Verify SSH keys exist (id_rsa, id_rsa.pub)


chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
# Set correct permissions for SSH keys


ssh-copy-id tony@stapp01.stratos.xfusioncorp.com
# Copy public key to App Server 1 (sudo user tony)


ssh-copy-id steve@stapp02.stratos.xfusioncorp.com
# Copy public key to App Server 2 (sudo user steve)


ssh-copy-id banner@stapp03.stratos.xfusioncorp.com
# Copy public key to App Server 3 (sudo user banner)


ssh tony@stapp01.stratos.xfusioncorp.com
# Verify password-less SSH to App Server 1


ssh steve@stapp02.stratos.xfusioncorp.com
# Verify password-less SSH to App Server 2


ssh banner@stapp03.stratos.xfusioncorp.com
# Verify password-less SSH to App Server 3


sudo -i
# Verify sudo access on app server
```
