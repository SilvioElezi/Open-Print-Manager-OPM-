# Open Print Manager (OPM)

**Vision:**  
An open-source print management suite for mixed environments (Windows, macOS, Linux, iOS, Android). Built on top of [CUPS](https://openprinting.github.io/cups/) and [OpenPrinting](https://openprinting.github.io/), with features for quotas, reporting, and secure pull-printing — free from vendor lock-in.

---

## Why?
Commercial print management software is expensive, closed-source, and often tied to specific vendors.  
Our goal: **a fully open-source, sustainable alternative** that organizations (schools, NGOs, businesses) can deploy on standard Linux servers.

---

## Project Goals
- ✅ Centralized print server on **Ubuntu LTS** using **CUPS**  
- ✅ Support for **driverless printing (IPP Everywhere, AirPrint, Mopria)**  
- ✅ Legacy printer support via **Gutenprint** and **OpenPrinting Printer Applications**  
- 🚧 Quotas & accounting via **PyKota** (revived & modernized)  
- 🚧 Web UI for **pull-print / secure release**  
- 🚧 Integration with **LDAP / Active Directory** for authentication  
- 🚧 Reporting & monitoring (usage, costs, per-user stats)  

---

## Architecture Overview

```mermaid
flowchart TD
    Clients[Windows/macOS/Linux/iOS/Android] -->|IPP/SMB| CUPS[(CUPS Server)]
    Printers -->|IPP / USB / Legacy| CUPS
    CUPS --> PyKota[(PyKota DB)]
    CUPS --> WebUI[(Pull-Print Web Portal)]
    Auth[(LDAP/AD)] --> CUPS
    Auth --> WebUI
