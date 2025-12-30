# Day 2 – Linux User Management (Temporary User Account)

## 📌 Overview
This task focuses on creating a temporary Linux user account with a defined expiry date to allow time-bound access, ensuring better security and access control.

---

## 🎯 Task Objective
Create a temporary user account for a developer with an expiry date as per project requirements.

---

## 🖥️ Server Details
| Parameter | Value |
|--------|-------|
| Server Name | App Server 2 |
| Hostname | stapp02.stratos.xfusioncorp.com |
| Datacenter | Stratos Datacenter |
| Project | Nautilus |
| User to Create | yousuf |
| Expiry Date | 2024-01-28 |

---

## 🛠️ Commands Executed

```bash
ssh banner@stapp02
# Connect to App Server 2

sudo useradd -e 2024-01-28 yousuf
# Create user with account expiry date (YYYY-MM-DD)

sudo chage -l yousuf
# Verify account expiration details
```
