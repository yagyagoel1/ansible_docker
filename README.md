# ansible with docker

A hands‑on Ansible playbook for installing and managing Docker on remote hosts. Perfect for anyone learning how to automate server provisioning, container setup, and infrastructure as code.

[![MIT License](https://img.shields.io/badge/license-MIT-green.svg)](#license) [![TypeScript](https://img.shields.io/badge/lang-TypeScript-blue.svg)](#tech-stack) [![Docker](https://img.shields.io/badge/container-Docker-blue.svg)](#prerequisites) 
---

## Why this repo matters

Modern backend teams rely on automation and reproducible infrastructure. This repo shows you:

- **Infrastructure as Code**  
  Define server setup in a version‑controlled playbook instead of manual SSH commands.
- **Configuration Management**  
  Use Ansible to ensure every host ends up with the same Docker version and service state.
- **Containerization**  
  Get Docker up and running in minutes, laying the groundwork for building, shipping, and running containers in development or production.

---

## What it does

1. **Targets a host group** named `dbservers` in your inventory.  
2. **Installs Docker** (`docker.io`) via the system package manager.
3. **Enables and starts** the Docker service so containers can launch automatically on boot.

All of this happens over SSH—no manual steps on each machine.

---

## How to use

1. **Clone the repo**  
   ```bash
   git clone https://github.com/yagyagoel1/ansible_docker.git
   cd ansible_docker
   ```

2. **Edit your `inventory`**  
   Replace the dummy IP with one (or more) hosts under your control:
   ```ini
   [dbservers]
   13.232.32.38   # replace with your server’s public or private address
   ```

3. **Run the playbook**  
   ```bash
   ansible-playbook -i inventory playbook.yaml --ask-become-pass
   ```
   – or configure passwordless sudo for a smoother run.

4. **Verify**  
   SSH into your server and run:
   ```bash
   docker version
   sudo systemctl status docker
   ```
   You should see Docker installed, enabled, and running.

---

## Key concepts & keywords

- **Ansible**: agentless automation, YAML playbooks, SSH orchestration  
- **Docker**: container runtime, images, services  
- **Infrastructure as Code**: reproducible builds, Git‑backed configuration  
- **Continuous Deployment**: integrate into CI/CD pipelines to spin up Docker hosts on demand  
- **Remote Provisioning**: manage servers at scale, avoid manual drift  

---

## Who this is for

- **Backend Engineer candidates**  
  Show your understanding of provisioning and immutable infrastructure.
- **DevOps Engineers**  
  Demonstrate basic Ansible + Docker synergy for day‑to‑day ops work.
- **Site Reliability / Infrastructure Engineers**  
  Lay the foundation for container orchestration and horizontal scaling.
- **Anyone learning IaC**  
  A clear, minimal example to build on for more complex multi‑tier deployments.

---

## Next steps

- Split tasks into reusable **Ansible roles** (`roles/docker/tasks/main.yml`)  
- Add **handlers** to restart Docker only when it’s newly installed or updated  
- Integrate with **CI pipelines** (GitHub Actions, GitLab CI) to trigger playbook runs  
- Expand inventory to multiple environments: `dev`, `staging`, `production`  

---

## Got feedback or questions?

Feel free to open an issue or reach out via my blog:  
https://blogs.yagyagoel.dev/getting-started-with-ansible-a-quick-guide

---

> This repo is a live tutorial—fork it, tweak it, and make it your own as you grow your backend and DevOps skill set.  
```
