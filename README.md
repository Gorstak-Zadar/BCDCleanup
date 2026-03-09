# 📋 BCDCleanup

> PowerShell script to enumerate and clean **suspicious Boot Configuration Data (BCD)** entries on Windows.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🛡️ **Automated** | No user input — runs fully unattended |
| 📋 **BCD Enumeration** | Parses all BCD entries and flags suspicious ones |
| 🔒 **Backup First** | Creates timestamped BCD backup before any changes |
| 📝 **Logging** | Logs all actions to `C:\BCD_Cleanup_Log_*.txt` |
| ⚠️ **Critical Protection** | Never removes `{bootmgr}`, `{current}`, or `{default}` |

---

## 📋 Requirements

| Requirement | Details |
|-------------|---------|
| **OS** | Windows 10/11, Server |
| **PowerShell** | 5.1+ |
| **Privileges** | Administrator |

---

## 🚀 Usage

```powershell
# Run as Administrator
.\BCDCleanup.ps1
```

---

## 🔧 What It Does

1. Creates BCD backup: `C:\BCD_Backup_<timestamp>.bcd`
2. Enumerates all BCD entries via `bcdedit /enum all`
3. Flags entries with non-Windows descriptions, odd paths, or suspicious characteristics
4. Removes suspicious entries (excluding critical boot identifiers)
5. Logs all actions for audit trail

---

## ⚠️ Warning

Always create a system restore point before running. Incorrect BCD changes can prevent boot.

---

<p align="center">
  <sub>🛡️ Gorstak Windows Security Tooling</sub>
</p>
