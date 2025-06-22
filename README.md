
# Systems Engineer | DevSecOps | Cyberpunk

_Automating infrastructure, hardening systems, and building tools from the ground up._

<!-- Languages -->
![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffffff)
![Bash](https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)

<!-- Infrastructure & Tools -->
![Puppet](https://img.shields.io/badge/Puppet-FFAE1A?style=for-the-badge&logo=puppet&logoColor=000000)
![NGINX](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white)
![XCP-ng](https://img.shields.io/badge/XCP--ng-CC584C?style=for-the-badge&logo=rocket&logoColor=white)
![Tailscale](https://img.shields.io/badge/Tailscale-242424?style=for-the-badge&logo=Tailscale&logoColor=white)
![WireGuard](https://img.shields.io/badge/WireGuard-88171A?style=for-the-badge&logo=WireGuard&logoColor=white)

<!-- Term & Editors -->
![Zsh](https://img.shields.io/badge/Zsh-89e051?style=for-the-badge&logo=Zsh&logoColor=white)
![Vim](https://img.shields.io/badge/Vim-019733?style=for-the-badge&logo=Vim&logoColor=white)
![Zed](https://img.shields.io/badge/Zed-084CCF?style=for-the-badge&logo=Zed-Industries&logoColor=white)
![iTerm2](https://img.shields.io/badge/iTerm2-000000?style=for-the-badge&logo=iterm2&logoColor=white)

<!-- OS & Distros -->
![Debian](https://img.shields.io/badge/Debian-A81D33?style=for-the-badge&logo=Debian&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![FreeBSD](https://img.shields.io/badge/FreeBSD-AB2B28?style=for-the-badge&logo=FreeBSD&logoColor=white)
![TrueNAS](https://img.shields.io/badge/TrueNAS-0095D5?style=for-the-badge&logo=TrueNAS&logoColor=white)

<!-- Security & Git -->
![GPG](https://img.shields.io/badge/GPG-0093DD?style=for-the-badge&logo=gnuprivacyguard&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

<!-- Workflow & Docs -->
![tmux](https://img.shields.io/badge/tmux-1BB91F?style=for-the-badge&logo=tmux&logoColor=white)
![asciinema](https://img.shields.io/badge/asciinema-000000?style=for-the-badge&logo=asciinema&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=Markdown&logoColor=white)
![Obsidian](https://img.shields.io/badge/Obsidian-7C3AED?style=for-the-badge&logo=Obsidian&logoColor=white)
![Homebrew](https://img.shields.io/badge/Homebrew-FBB040?style=for-the-badge&logo=homebrew&logoColor=white)

---

I'm an **Automation-Oriented Systems Engineer**, building terminal-native infrastructure with a DevSecOps mindset. My work focuses on infrastructure automation, secure scripting, system design, and hands-on experimentation in a purpose-built lab.  
While I don’t build frontend interfaces, I manage the full lifecycle of backend systems — from provisioning and orchestration to hardening and monitoring — giving me a comprehensive, operational view of real-world infrastructure.

---

## 🔧 Homelab Stack

My self-hosted lab ([GG3-DevNet](https://github.com/gg3-dev)) simulates a scaled-down enterprise environment:

```sh
~/GG3-DevNet
├── xcp-ng           # bare-metal hypervisor
│   └── terraform    # VM provisioning via XO API
├── debian           # base OS for prod/dev VMs
│   ├── puppet       # config management for VMs
│   └── nginx        # hardened web services
├── tailscale        # encrypted fallback access
└── bash/python      # scripting, monitoring, automation
```

- **XCP-ng** — Bare-metal hypervisor with static IPs and segmented virtual switches.  
  └── **Terraform** — Provisions Debian VMs via Xen Orchestra API with cloud-init injection.

- **Debian** — Uniform base OS across all nodes for security and portability.  
  ├── **Puppet** — Manages system state: users, dotfiles, packages, and services.  
  ├── **NGINX** — TLS-only web server with Certbot integration and hardened headers.  
  └── **UFW** — Default-deny firewall with SSH access restricted to trusted IPs.

- **Tailscale** — Zero-trust fallback VPN for remote management if SSH fails.

- **Bash / Python** — Custom scripts for auditing, snapshots, port scans, and automation.

- **MacBook + UTM** — Isolated staging environment for testing scripts and deployments before live use.

> This lab is my research ground — a space to test, break, and secure systems like an operator.

---

## 🔐 DevSecOps & Security Practices

My workflow prioritizes **repeatability**, **observability**, and **least privilege** — all driven through terminal-native tooling and version control.

```sh
# Audit UFW rules
sudo ufw status verbose

# Scan local subnet for live hosts
nmap -sn 10.10.10.0/24

# Apply configuration state to node
sudo puppet apply ./manifests/init.pp
```

- **SSH Key Authentication Only**  
  Namespaced key format (e.g. `key.gg3.git`, `key.gg3.lab.vm1`), always passphrase-protected and rotated regularly.

- **Firewall Lockdown by Default**  
  UFW configured to deny all except trusted SSH ingress. No open ports unless explicitly whitelisted.

- **TLS Enforcement**  
  Certbot for certificates + hardened NGINX config (no autoindex, HSTS, X-Frame-Options, and other strict headers).

- **Dotfiles as Code**  
  Managed through Git and deployed via Puppet or symlinked provisioning scripts.

- **Logged Infrastructure Changes**  
  Markdown (`.md`) and plaintext (`.txt`) logs tracked in Git for every configuration, deployment, and state change.

- **Minimal Tooling, Max Clarity**  
  Only essentials: `nmap`, `ufw`, `journalctl`, `systemctl`, `puppet`, `bash`, `python`.

---

## 📂 Public Projects

These are real tools, scripts, and documentation sets I’ve built and use daily.

- **[gtop](https://github.com/0xjuang/gtop)**  
  Modular Python snapshot tool for CPU, memory, disk, and network stats.

- **[citadel-33](https://github.com/0xjuang/citadel-33)**  
  Secure password generator using user-defined patterns and entropy.

- **[gg3utils](https://github.com/gg3-dev/gg3utils)**  
  Bash/Python toolkit for audits, health checks, and automation tasks.

- **[terraform-xo-vm](https://github.com/0xjuang/terraform-xo-vm)**  
  Deploys cloud-init Debian VMs on XCP-ng via Terraform + Xen Orchestra API.

- **[gg3-docs](https://github.com/gg3-dev/gg3-docs)**  
  Architecture blueprints, firewall policies, SSH key schemes, and operational logs.

- **[gg3-admin-tools](https://github.com/gg3-dev/gg3-admin-tools)**  
  System setup helpers — dotfiles, packages, service states, and recovery tools.

- **[vm-utils](https://github.com/gg3-dev/vm-utils)**  
  VM lifecycle helpers for provisioning, rollback snapshots, and CLI-driven automation.

- **[tech-crucible](https://github.com/0xjuang/tech-crucible)**  
  Certification roadmap, personal learning tracker, and daily log entries.

- **[3-iX-WSL-CC](https://github.com/0xjuang/3-iX-WSL-CC)**  
  Legacy burn-in suite for WSL/TrueNAS testing from previous lab iterations.

---

## 🧰 Roles I Fit

**🔐 Junior Security Engineer**  
- SSH key authentication, UFW lockdowns, and TLS-only service exposure  
- Zero-trust fallback access using WireGuard and Tailscale tunnels

**🖥️ Linux System Administrator**  
- Debian-based environments with config-as-code via Puppet  
- CLI-native workflows for service management, recovery, and troubleshooting

**🏗️ Infrastructure Engineer**  
- VM lifecycle automation using Terraform and the Xen Orchestra API  
- Cloud-init provisioning with reproducible network and storage configs

**⚙️ Junior DevOps Engineer**  
- Shell scripting, config management, and Git-driven workflows  
- Custom-built tooling for audits, monitoring, backups, and hardening

---

## 📫 Let's Connect

- 📧 Email: [juan@gg3.dev](mailto:juan@gg3.dev)  
- 🧑‍💻 Portfolio: [about.gg3.dev](https://about.gg3.dev/)  
- 🐙 Org: [github.com/gg3-dev](https://github.com/gg3-dev)

---

## 📄 About This README

This README reflects real infrastructure, workflows, and tools I build and maintain inside my lab.

Signed: `0x1G`  
GPG Fingerprint: `E5F5 811F 0BED A8C1 ABEE 8161 708C BC98 E7D3 9F79`  
Public key: [https://keys.openpgp.org/vks/v1/by-fingerprint/E5F5811F0BEDA8C1ABEE8161708CBC98E7D39F79](https://keys.openpgp.org/vks/v1/by-fingerprint/E5F5811F0BEDA8C1ABEE8161708CBC98E7D39F79)

_Last updated: June 15, 2025_

