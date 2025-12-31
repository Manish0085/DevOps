# Day 3 – Linux Security (Disable Direct Root SSH Login)

## 📌 Overview
This task focuses on improving server security by disabling direct SSH access for the root user, following updated security protocols implemented after recent security audits.

---

## 🎯 Task Objective
Disable direct SSH root login on all application servers within the Stratos Datacenter.

---

## 🖥️ Server Details
| Parameter | Value |
|--------|-------|
| Server Type | Application Servers |
| Hostnames | stapp01, stapp02, stapp03 |
| Datacenter | Stratos Datacenter |
| Project | Nautilus |

---

## 🛠️ Commands Executed

### For Application Server stapp01
```bash
ssh tony@stapp01.stratos.xfusioncorp.com
# Connect to App Server 1

sudo vi /etc/ssh/sshd_config
# Set: PermitRootLogin no

sudo systemctl restart sshd
# Restart SSH service
```


### For Application Server stapp02
```bash
ssh steve@stapp02.stratos.xfusioncorp.com
# Connect to App Server 2

sudo vi /etc/ssh/sshd_config
# Set: PermitRootLogin no

sudo systemctl restart sshd
# Restart SSH service
```


### For Application Server stapp03
```bash
ssh banner@stapp03.stratos.xfusioncorp.com
# Connect to App Server 3

sudo vi /etc/ssh/sshd_config
# Set: PermitRootLogin no

sudo systemctl restart sshd
# Restart SSH service
```
---

## 📘 Learning of the Day

```text
Direct root SSH login is a security risk and should be disabled

SSH access should be granted to normal users with sudo privileges

Security hardening must be applied consistently across all app servers

Restarting sshd is required for configuration changes to take effect
```
