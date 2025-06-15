
# Systems Engineer | DevSecOps | Cyberpunk

_Automating infrastructure, hardening systems, and building tools from the ground up._

<!-- Languages -->
![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffffff)
![Bash](https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white)

<!-- Infrastructure & Tools -->
![Puppet](https://img.shields.io/badge/Puppet-302B6D?style=for-the-badge&logo=puppet&logoColor=yellow)
![NGINX](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white)
![XCP-ng](https://img.shields.io/badge/XCP--ng-003399?style=for-the-badge&logo=rocket&logoColor=white)
![Tailscale](https://img.shields.io/badge/Tailscale-242424?style=for-the-badge&logo=Tailscale&logoColor=white)
![WireGuard](https://img.shields.io/badge/WireGuard-88171A?style=for-the-badge&logo=WireGuard&logoColor=white)

<!-- Term & Editors -->
![Zsh](https://img.shields.io/badge/Zsh-F15A24?style=for-the-badge&logo=Zsh&logoColor=white)
![Vim](https://img.shields.io/badge/Vim-019733?style=for-the-badge&logo=Vim&logoColor=white)
![Zed](https://img.shields.io/badge/Zed-084CCF?style=for-the-badge&logo=Zed-Industries&logoColor=white)
![iTerm2](https://img.shields.io/badge/iTerm2-000000?style=for-the-badge&logo=iterm2&logoColor=white)

<!-- OS & Distros -->
![Debian](https://img.shields.io/badge/Debian-A81D33?style=for-the-badge&logo=Debian&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![FreeBSD](https://img.shields.io/badge/FreeBSD-AB2B28?style=for-the-badge&logo=FreeBSD&logoColor=white)
![TrueNAS](https://img.shields.io/badge/TrueNAS-0095D5?style=for-the-badge&logo=TrueNAS&logoColor=white)

<!-- Security & Git -->
![GPG](https://img.shields.io/badge/GPG-26A269?style=for-the-badge&logo=gnuprivacyguard&logoColor=white)
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
├── xcp-ng           # hypervisor
├── debian           # prod/dev VMs
├── puppet           # config management
├── nginx            # web server
└── tailscale        # encrypted fallback
```

- **XCP-ng** — Bare-metal hypervisor with static IPs and virtual switch segmentation.
- **Terraform** — VM provisioning and cloud-init injection via Xen Orchestra API.
- **Puppet** — Manages packages, dotfiles, users, and services like NGINX.
- **NGINX** — Hardened TLS web server with Certbot-managed HTTPS.
- **UFW** — Default-deny firewalls. SSH-only access allowed from fixed IPs.
- **Tailscale** — Zero-trust VPN for fallback management.
- **Bash/Python** — Scripting for health checks, port scans, backups, and automation.
- **MacBook + UTM** — Isolated testbed for staging changes and testing scripts.
- **Debian** — Uniform base OS for reliability, security, and config portability.

> This lab is my research ground — a space to test, break, and secure systems like an operator.

---

## 🔐 DevSecOps & Security Practices

My workflow prioritizes repeatability, observability, and least privilege.

```sh
# Audit current firewall config
sudo ufw status verbose

# Scan local subnet
nmap -sn 10.10.10.0/24

# Apply Puppet manifest to node
sudo puppet apply ./manifests/init.pp
```

- **SSH key auth only** — Namespaced key format (e.g. `key.gg3.git`, `key.gg3.lab.vm1`) with passphrase and rotation.
- **Firewall lockdowns** — SSH-only access. All other ports are denied at host level.
- **TLS enforcement** — Certbot + manual NGINX hardening: no autoindex, strict headers.
- **Dotfiles as code** — Reproducible system configs and deployment scripts.
- **Markdown + `.txt` logs** — Every change tracked in version-controlled documentation.
- **Minimal tooling, max clarity** — `nmap`, `ufw`, `journalctl`, `systemctl`, `puppet`, `bash`, `Python`.

---

## 📂 Public Projects

These are real tools, scripts, and documentation sets I’ve built and use daily.

- **[gtop](https://github.com/0xjuang/gtop)** — Modular Python snapshot tool for CPU, memory, disk, and network stats.
- **[gg3utils](https://github.com/gg3-dev/gg3utils)** — Bash/Python toolkit for audits, health checks, and automation.
- **[terraform-xo-vm](https://github.com/0xjuang/terraform-xo-vm)** — Deploys cloud-init VMs on XCP-ng via Terraform & XO API.
- **[gg3-docs](https://github.com/gg3-dev/gg3-docs)** — Architecture, firewall policies, SSH schemes, and logs.
- **[gg3-admin-tools](https://github.com/gg3-dev/gg3-admin-tools)** — Dotfile and service setup scripts.
- **[vm-utils](https://github.com/gg3-dev/vm-utils)** — VM provisioning, rollback prep, and CLI helpers.
- **[tech-crucible](https://github.com/0xjuang/tech-crucible)** — Personal cert/skill roadmap and logs.
- **[3-iX-WSL-CC](https://github.com/0xjuang/3-iX-WSL-CC)** — Legacy burn-in scripts for WSL/TrueNAS testing.

---

## 🧰 Roles I Fit

**🔐 Junior Security Engineer**  
- SSH key auth, UFW lockdowns, TLS-only endpoints  
- Zero-trust fallback access with WireGuard and Tailscale  

**🖥️ Linux System Administrator**  
- Debian environments, config-as-code with Puppet  
- CLI-based service management, recovery workflows  

**🏗️ Infrastructure Engineer**  
- VM lifecycle automation with Terraform and Xen Orchestra  
- Reproducible setups with static IPs and cloud-init  

**⚙️ Junior DevOps Engineer**  
- Shell scripting, config management, and Git workflows  
- Custom toolsets for audit, monitoring, and provisioning  

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
