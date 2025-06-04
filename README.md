# Systems Engineer | DevSecOps | Cyberpunk

_Automating infrastructure, hardening systems, and building tools from the ground up._

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffffff)
![Bash](https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white)
![Puppet](https://img.shields.io/badge/Puppet-302B6D?style=for-the-badge&logo=puppet&logoColor=yellow)
![NGINX](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020.svg?style=for-the-badge&logo=Cloudflare&logoColor=white)
![XCP-ng](https://img.shields.io/badge/XCP--ng-003399.svg?style=for-the-badge&logo=rocket&logoColor=white)
![Tailscale](https://img.shields.io/badge/Tailscale-242424.svg?style=for-the-badge&logo=Tailscale&logoColor=white)
![WireGuard](https://img.shields.io/badge/WireGuard-88171A.svg?style=for-the-badge&logo=WireGuard&logoColor=white)
![GCP](https://img.shields.io/badge/Google%20Cloud-4285F4.svg?style=for-the-badge&logo=Google-Cloud&logoColor=white)
![GPG](https://img.shields.io/badge/GPG-26A269?style=for-the-badge&logo=gnuprivacyguard&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624.svg?style=for-the-badge&logo=linux&logoColor=black)
![Debian](https://img.shields.io/badge/Debian-A81D33.svg?style=for-the-badge&logo=Debian&logoColor=white)
![FreeBSD](https://img.shields.io/badge/FreeBSD-AB2B28.svg?style=for-the-badge&logo=FreeBSD&logoColor=white)
![TrueNas](https://img.shields.io/badge/TrueNAS-0095D5.svg?style=for-the-badge&logo=TrueNAS&logoColor=white)
![Zsh](https://img.shields.io/badge/Zsh-F15A24.svg?style=for-the-badge&logo=Zsh&logoColor=white)
![Vim](https://img.shields.io/badge/Vim-019733.svg?style=for-the-badge&logo=Vim&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032.svg?style=for-the-badge&logo=git&logoColor=white)
![tmux](https://img.shields.io/badge/tmux-1BB91F.svg?style=for-the-badge&logo=tmux&logoColor=white)
![asciinema](https://img.shields.io/badge/asciinema-000000.svg?style=for-the-badge&logo=asciinema&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000.svg?style=for-the-badge&logo=Markdown&logoColor=white)
![Obsidian](https://img.shields.io/badge/Obsidian-7C3AED.svg?style=for-the-badge&logo=Obsidian&logoColor=white)
![Homebrew](https://img.shields.io/badge/Homebrew-FBB040?style=for-the-badge&logo=homebrew&logoColor=white)
![Zed](https://img.shields.io/badge/Zed-084CCF.svg?style=for-the-badge&logo=Zed-Industries&logoColor=white)
![iTerm2](https://img.shields.io/badge/iTerm2-000000?style=for-the-badge&logo=iterm2&logoColor=white)
![Coursera](https://img.shields.io/badge/Coursera-0056D2.svg?style=for-the-badge&logo=Coursera&logoColor=white)
![Udemy](https://img.shields.io/badge/Udemy-A435F0.svg?style=for-the-badge&logo=Udemy&logoColor=white)


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

- **[gtop](https://github.com/0xjuang/gtop)** — Modular Python snapshot tool for CPU, memory, disk, and network stats. Designed for system introspection during provisioning and orchestration pipelines
- **[gg3utils](https://github.com/gg3-dev/gg3utils)** — Modular Bash/Python toolkit for health checks, UFW audits, and Nmap parsing.
- **[gg3-docs](https://github.com/gg3-dev/gg3-docs)** — Written architecture, firewall policies, SSH key logic, and system logs.
- **[gg3-admin-tools](https://github.com/gg3-dev/gg3-admin-tools)** — Scripts for provisioning new systems and managing dotfiles.
- **[vm-utils](https://github.com/gg3-dev/vm-utils)** — Automation for VM provisioning, rollback prep, and recovery.
- **[tech-crucible](https://github.com/0xjuang/tech-crucible)** — Personal roadmap and cert logs for DevOps/infra/security.
- **[3-iX-WSL-CC](https://github.com/0xjuang/3-iX-WSL-CC)** — Legacy job repo with burn-in scripts for TrueNAS & WSL servers.

---

## 🧰 Roles I Fit

These roles summarize the functions I currently fulfill within my infrastructure practice.

- **Linux Systems Administrator** — Hardened Debian systems with UFW, SSH key auth, and Puppet-managed config. No GUI, no guesswork — just clean shells and tight permissions.
- **Infrastructure Engineer** — Self-hosted hypervisor lab (XCP-ng) with segmented IP/DNS zones, static routes, and CLI-based lifecycle management. Logs, nodes, and services all tracked in version control.
- **Junior DevOps Engineer** — Bash/Python automation for provisioning, firewall audits, service checks, and backups. Git-based workflows with clear commits, preflight scripts, and reproducible results.
- **Security-Focused Operator** — Systems built locked-down: passphrase-protected keys, SSH-only ingress, TLS-enforced endpoints, and plaintext change logs. Operate with zero trust by default.

---

## 📫 Let's Connect

- 📧 Email: [juan@gg3.dev](mailto:juan@gg3.dev)  
- 🧑‍💻 Portfolio: [about.gg3.dev](https://about.gg3.dev/)  
- 🐙 Org: [github.com/gg3-dev](https://github.com/gg3-dev)

---

## 📄 About This README

This README was written and maintained by Juan Garcia (@0xjuang) to reflect real infrastructure, tooling, and practices as of **May 2025**.

Signed: `0x1G`  
GPG Fingerprint: `E5F5 811F 0BED A8C1 ABEE  8161 708C BC98 E7D3 9F79`  
Public key: [https://keys.openpgp.org/vks/v1/by-fingerprint/E5F5811F0BEDA8C1ABEE8161708CBC98E7D39F79](https://keys.openpgp.org/vks/v1/by-fingerprint/E5F5811F0BEDA8C1ABEE8161708CBC98E7D39F79)

_Last updated: May 27, 2025_
