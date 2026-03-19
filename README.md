# NetBox + Ansible Automation Lab

This project demonstrates how to use NetBox as a source of truth and Ansible as the automation engine.

## Project Overview
In this lab:
- NetBox is used to store infrastructure inventory
- Ansible uses NetBox dynamic inventory
- A real Linux VM is managed over SSH
- Ansible deploys and starts nginx
- The target host serves a custom web page

## Architecture
NetBox -> Ansible Dynamic Inventory -> SSH -> Managed Host

## Components
- NetBox (Docker-based deployment)
- Ansible
- Dynamic inventory plugin: `netbox.netbox.nb_inventory`
- Managed host: `web-01`
- Web server: nginx

## Achievements
- Installed and ran NetBox in Docker
- Created device records in NetBox
- Added interface and primary IP for `web-01`
- Configured SSH key-based access from Master to VM4
- Verified dynamic inventory from NetBox in Ansible
- Ran Ansible ad-hoc ping successfully
- Created and ran a playbook to install and start nginx
- Verified deployment with a custom web page

## Repository Structure
- `ansible/inventory.yml` - NetBox dynamic inventory configuration
- `ansible/playbooks/setup-nginx.yml` - nginx deployment playbook
- `docs/` - project notes and screenshots
- `netbox-docker/` - NetBox Docker deployment files

## Test Result
Successful Ansible connectivity test:

```bash
ansible all -i /root/netbox-ansible-lab/ansible/inventory.yml -m ping


