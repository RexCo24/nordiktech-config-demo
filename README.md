# nordiktech-config-demo

> [Demo] This is a portfolio/training scenario. NordikTech Solutions is a fictional company.

## Scenario
Junior DevOps Engineer task — configure a provisioned Azure VM for the NordikTech staging environment using Ansible.

## What this Playbook does
1. Installs and starts nginx
2. Deploys nginx as a Reverse Proxy (Port 80 → 5000)
3. Copies the Flask Inventory API to the server
4. Creates a Python virtual environment
5. Installs Flask dependencies
6. Deploys and starts the Flask app as a systemd service (auto-restart on boot)

## Architecture

User → Port 80 → nginx (Reverse Proxy) → Port 5000 → Flask Inventory API


## Files
| File | Purpose |
|---|---|
| `playbook.yml` | Main Ansible playbook |
| `inventory.ini` | Target host definition |
| `nginx.conf` | nginx Reverse Proxy configuration |
| `flask.service` | systemd service definition for Flask |
| `app.py` | Flask Inventory API |

## Usage
```bash
ansible-playbook -i inventory.ini playbook.yml --ask-become-pass
```

## Tech Stack
- Ansible
- nginx
- Flask (Python 3.12)
- systemd
- Ubuntu 24.04 LTS
