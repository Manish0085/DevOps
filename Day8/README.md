# 🚀 Ansible Installation on Jump Host (Global Setup)

This repository documents the steps to install **Ansible version 4.10.0** on a **Jump Host** using **pip3 only**, ensuring that Ansible is **globally available to all users** on the system.

---

## 📌 Objective
- Install **Ansible 4.10.0**
- Use **pip3 only** (no yum/dnf)
- Ensure **system-wide (global) availability**
- Verify access for multiple users

---

## 🖥️ Environment Details
- OS: CentOS Stream 9  
- Python: 3.9+  
- User: `thor` (sudo access)  
- Node Type: Jump Host (Ansible Controller)

---

## ⚙️ Installation Steps

### 1️⃣ Verify `pip3` is installed
```bash

ssh thor@jumphost
# Login to Jump Host as thor


pip3 --version
# Verify that pip3 is installed on the system


sudo yum install -y python3-pip
# Install pip3 (only if not already installed)


sudo pip3 install ansible==4.10.0
# Install Ansible version 4.10.0 globally using pip3


which ansible
# Verify Ansible binary location (should be /usr/local/bin/ansible)


ansible --version
# Verify Ansible installation and version


sudo su -
# Switch to root user to check global availability


ansible --version
# Verify Ansible is accessible for another user (root)


echo $PATH
# Confirm /usr/local/bin is present in global PATH

```
