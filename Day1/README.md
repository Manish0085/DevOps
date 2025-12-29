# Day1 - Linux User Management

## Task 
Create a non-interactive user for a backup agent on App Server 3.

## Server Details
- Server Name: stapped03
- IP: 172.16.238.12
- Hostname: stapp03.stratos.xfusioncorp.com
- User: banner
- Password: *******
- Purpose: Nautilus App 3

## Commands used
```bash
sudo useradd -s /sbin/noLogin kirsty
getent kirsty
su - kirsty
```
