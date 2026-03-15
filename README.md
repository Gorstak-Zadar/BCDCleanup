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

---

## Disclaimer

**NO WARRANTY.** THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY APPLICABLE LAW. EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM IS WITH YOU. SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.

**Limitation of Liability.** IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR CONVEYS THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.
