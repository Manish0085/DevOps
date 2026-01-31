# MariaDB Service Failure – Production Incident Resolution

## Overview

The Nautilus application in Stratos DC experienced a production outage due to a database connectivity issue. During investigation, it was found that the MariaDB service on the database server was not running. Because of this, the application was unable to connect to the database and its functionality was affected.

This document describes the problem statement, investigation process, root cause analysis, and the final resolution.

---

## Problem Statement

The Nautilus application was unable to connect to its database.  
Production support confirmed that the MariaDB service on the database server (stdb01) was down.  
This caused a complete outage for features that depended on the database.

---

## Investigation Approach

### Checking MariaDB Service Status

The first step was to verify the status of the MariaDB service.

```bash
sudo systemctl status mariadb
```

## 🔍 Observation

- The MariaDB service was either **inactive** or **failed**
- The process exited with **exit-code = 1**
- No crash or segmentation fault was observed

➡️ This indicated a **clean failure**, not a system-level crash.

---

## 2️⃣ Analyze Service Logs

To understand why the service was failing, detailed service logs were analyzed using:

```bash
sudo journalctl -xeu mariadb.service
```

### 🔑 Key Error Identified

```ngnix
Fatal error in defaults handling. Program aborted
```

➡️ This clearly indicated that MariaDB was failing while reading its configuration files, preventing the service from starting successfully.


## 🧠 Root Cause Analysis (RCA)

MariaDB reads configuration files in the following order:

1. `/etc/my.cnf`
2. `/etc/my.cnf.d/*.cnf`
3. `~/.my.cnf`

### 🔎 Root Cause Identified

- The file `/etc/my.cnf` contained an **invalid or incompatible configuration directive**

Due to this:

- MariaDB started briefly
- Failed during **configuration parsing**
- Exited with **status = 1**

➡️ As a result, the **database service never remained running**, causing the application to lose database connectivity.

## 🛠️ Solution Strategy

Instead of modifying the configuration blindly, a **safe and reversible approach** was used to restore service availability.

---

## 3️⃣ Isolate the Faulty Configuration

The problematic configuration file was temporarily moved out of the way:

```bash
sudo mv /etc/my.cnf /etc/my.cnf.bak
```

## 4️⃣ Reset and Restart MariaDB Service

After isolating the faulty configuration, the MariaDB service state was reset and restarted:

```bash
sudo systemctl reset-failed mariadb
sudo systemctl start mariadb
```

## ✅ Verification & Validation

```bash
sudo systemctl status mariadb
```
