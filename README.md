# 🚀 DevOps Journey

Tracking my hands-on DevOps learning using **KodeKloud labs**.

---

## 📌 Progress

# 📘 DevOps Learning Log

---

## ✅ Day 1 – Linux User Management

### 🔹 Learnings  
**Interactive vs Non-Interactive Terminals**

- An **interactive shell** allows users to log in and execute commands directly.  
- A **non-interactive shell** is typically used by service or system accounts and does not allow login,  
which helps improve **system security** by restricting direct user access.

---

## ✅ Day 2 – Linux User Management (Temporary Users)

### 🔹 Learnings  
**Creating temporary users with account expiry**

A **temporary user account** provides time-bound access by defining an  
**account expiry date**. Using `useradd -e`, the account is automatically  
disabled after the specified date, helping improve **security**,  
**access control**, and **user lifecycle management**.

---

## ✅ Day 3 – Linux Security (Disable Root SSH Login)

### 🔹 Learnings  
**Disabling direct root SSH access**

Allowing direct SSH login as the **root user** poses a serious security risk.  
By configuring SSH with `PermitRootLogin no`, administrative access is enforced  
through **sudo-enabled users**. This reduces the **attack surface**,  
improves **system security**, and aligns with **industry security best practices**.

---

## ✅ Day 4 – Linux File Permissions (Executable Scripts)

### 🔹 Learnings  
**Managing executable permissions for shell scripts**

Linux scripts require proper **read (`r`) and execute (`x`) permissions** to run correctly.  
Using `chmod 755` grants execution access to **all users**,  
while restricting modification rights to the **owner** only.  
This ensures scripts are **securely executable**, prevents unauthorized changes,  
and follows **Linux security best practices** for production environments.

---

---

- Day 5 ⏳
- Day 6 ⏳
---

## ✅ Day 7 – Alllowing Password-Less ssh Login

### 🔹 Learnings

- Learned how **SSH key-based authentication** works and why it is essential for automation.
- Understood the purpose of SSH files:
  - `id_rsa` → private key  
  - `id_rsa.pub` → public key  
  - `authorized_keys` → stores trusted public keys on remote servers
- Learned that `ssh-copy-id` fails if **no SSH identity exists** and requires a generated key.
- Gained hands-on experience generating **RSA 4096-bit SSH keys** using `ssh-keygen`.
- Learned the importance of **correct SSH permissions** to avoid authentication issues:
  - `.ssh` → `700`
  - `id_rsa` → `600`
  - `id_rsa.pub` → `644`
- Understood how password-less SSH enables **cron jobs, scripts, and DevOps automation**.
- Practiced real-world **Linux troubleshooting** by fixing SSH key location and permission issues.
- Reinforced DevOps best practices for **secure and automated server access**.



### 🧠 Key Takeaway
Password-less SSH is a foundational DevOps skill that enables secure, scalable, and fully automated system operations.

---

- Day 8 ⏳
---

## ✅ Day 9 - MariaDB Service Failure – Production Incident Resolution
  
## 📘 Today’s Learning

- Always **check service logs first** (`journalctl`) before attempting fixes
- An **exit-code = 1** without a crash usually indicates a **configuration-level issue**
- MariaDB fails fast when it encounters **invalid configuration directives**
- Avoid blind edits — use **non-destructive and reversible actions** (e.g., backing up config files)
- `systemctl reset-failed` is important when a service enters a failed state
- Isolating the root cause is safer than applying quick fixes under pressure
- Proper validation after restart ensures **service stability**, not just recovery

➡️ This incident reinforced the importance of **systematic debugging, log analysis, and safe recovery strategies** in production environments.


---

## 🛠 Tools
- Linux
- Git
- Docker
- Kubernetes
- CI/CD

---

## 🎯 Goal
Build strong DevOps fundamentals with real-world, hands-on practice.
