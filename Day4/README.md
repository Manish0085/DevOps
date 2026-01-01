# Day 2 – Linux User Management (Temporary User Account)

## 📌 Overview
This task focuses on managing Linux file permissions by granting executable access to a shell script, ensuring it can be executed by all users while maintaining secure ownership control.

---

## 🎯 Task Objective
Grant executable permissions to a backup script so that all users can execute it as required by system operations.

---

## 🖥️ Server Details
| Parameter | Value |
|--------|-------|
| Server Name | App Server 2 |
| Hostname | stapp02.stratos.xfusioncorp.com |
| Datacenter | Stratos Datacenter |
| Project | Nautilus |
| Script Name | xfusioncorp.sh |
| Script Location | /tmp/xfusioncorp.sh |

---

## 🛠️ Commands Executed

```bash
ssh steve@stapp02.stratos.xfusioncorp.com
# Connect to App Server 2

ls -l /tmp/xfusioncorp.sh
# Check existing permissions

sudo chmod 755 /tmp/xfusioncorp.sh
# Grant executable permission to all users
# Owner: read, write, execute | Group/Others: read, execute

ls -l /tmp/xfusioncorp.sh
# Verify updated permissions
```
