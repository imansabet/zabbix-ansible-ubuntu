# Production-Ready Zabbix Infrastructure Automation with Ansible

> Infrastructure as Code (IaC) project for deploying and managing a production-ready Zabbix environment using Ansible.

---

## Project Goal

The purpose of this repository is to build a complete Zabbix monitoring infrastructure from scratch while following Ansible best practices.

This project is not only focused on installing Zabbix, but also on learning Infrastructure as Code concepts such as:

- Idempotency
- Role-based architecture
- Configuration management
- Automation
- Reusability
- Verification
- Production-ready project structure

---

## Current Architecture

```text
Controller
    │
    │ SSH
    ▼
+--------------------+
|  Zabbix Server     |
| Ubuntu 24.04       |
+--------------------+

        │

        │ Monitoring

        ▼

+--------------------+
|  Zabbix Agent      |
| Ubuntu 24.04       |
+--------------------+
```

---

## Repository Structure

```

.
├── inventory/
│   └── inventory.ini
│
├── roles/
│   ├── common/
│   │   ├── tasks/
│   │   └── handlers/
│   │
│   ├── server/
│   ├── agent/
│   └── proxy/
│
├── playbooks/
│   ├── common.yml
│   └── site.yml
│
└── ansible.cfg

```

---

## Why this structure?

### inventory/

Stores target hosts and inventory variables.

Keeping the inventory separate allows managing multiple environments such as Development, Staging and Production.

---

### roles/

Each role has a single responsibility.

```

common → shared configuration

server → Zabbix Server installation

agent → Zabbix Agent installation

proxy → Zabbix Proxy installation

```

This approach follows the Single Responsibility Principle.

---

### playbooks/

Playbooks orchestrate roles.

Instead of containing implementation details, they simply define **what should run**.


