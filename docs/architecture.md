# Azazel System Architecture

## Overview
The **Azazel System** is a portable deception-based security gateway designed to delay, deceive, and log intruders on compromised or vulnerable networks. It is intended to be deployed on a Raspberry Pi 5 with a lightweight yet modular architecture for flexible defense.

## Directory Structure

```plaintext
/opt/azazel/
├── bin/                         # Automation scripts (e.g., log backup)
│   └── backup_logs.sh
├── config/                      # Configuration files for services
│   ├── fluentbit.conf
│   ├── vector.toml
│   └── opencanary.conf
├── containers/                 # Docker Compose and container configs
│   └── docker-compose.yml
├── data/                        # Persistent data (PostgreSQL volumes, etc.)
│   └── postgres/
├── logs/                        # Log storage for Suricata, OpenCanary, etc.
│   └── install_errors.log

/opt/mattermost/
├── bin/                         # Mattermost binaries
├── config/                      # Mattermost configuration
└── data/                        # Mattermost persistent data
```

## Git Exclusion Rules

To prevent unwanted data from being committed to the repository, the following paths are excluded in `.gitignore`:

```gitignore
/opt/azazel/logs/
/opt/azazel/data/
```

These directories are created during installation and store runtime and sensitive operational data.

## Services Overview

- **Suricata**: Intrusion detection and network monitoring
- **OpenCanary**: Honeypot for deception-based intrusion activity
- **Fluent Bit**: Lightweight log shipper
- **Vector**: Log transformation and storage
- **Mattermost**: Notification and alerting platform
- **iptables** & **tc**: Traffic control and attacker delay
- **backup_logs.sh**: Log synchronization via rsync

## Bootstrapping

The full setup is done in three stages:

1. `1_install_azazel.sh` – base packages, system setup, and directory creation
2. `2_setup_containers.sh` – Docker services (PostgreSQL, Vector, OpenCanary)
3. `3_configure_services.sh` – Configuration and enabling of services

## Notes

- All runtime directories are located in `/opt/azazel` for modularity.
- External monitoring or backup systems should read from `/opt/azazel/logs`.

---

© 2025 Azazel Development Team