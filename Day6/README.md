# Day 6 – Linux Cron Job Scheduling (cronie)

## 📌 Overview
This task demonstrates how to automate recurring system tasks in Linux using **cron jobs**. The objective is to install and configure the cron service (`cronie`) and schedule a sample job to validate functionality across Nautilus application servers.

---

## 🎯 Task Objective
- Install the **cronie** package
- Ensure the **crond** service is running and enabled
- Schedule a cron job for the **root user** that executes every 5 minutes

---

## 🖥️ Server Details
| Parameter | Value |
|--------|-------|
| Server Type | Application Servers |
| Servers | stapp01, stapp02, stapp03 |
| Datacenter | Stratos Datacenter |
| Project | Nautilus |
| Cron Schedule | */5 * * * * |
| Output File | /tmp/cron_text |

---

## 🛠️ Commands Executed

### 🔹 Step 1: Connect to the server
```bash
ssh steve@stapp02.stratos.xfusioncorp.com
# Connect to App Server 2

sudo yum install -y cronie
# Install cron service

sudo systemctl start crond
# Start cron daemon

sudo systemctl enable crond
# Enable cron service at boot

systemctl status crond
# Verify cron service status

sudo crontab -e
# Edit root user's crontab

*/5 * * * * echo hello > /tmp/cron_text
# Schedule cron job to run every 5 minutes

sudo crontab -l
# Verify cron job entry
```
