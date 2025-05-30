![Score](https://img.shields.io/badge/Score-125%2F100-lightgrey) ![Shell](https://img.shields.io/badge/Shell-100%25-lightgrey)

# Born2BeRoot

> *Intro to system administration & virtualization*
> *(Debian or Rocky on VirtualBox/UTM)*

---

## Table of Contents

* [About 📌](#about)
* [Setup 🛠️](#setup)
* [Security 🔒](#security)
* [Monitoring 📊](#monitoring)
* [Bonus 🏆](#bonus)
* [Submission 📮](#submission)
* [Inspired 🚀](#inspired)
* [Requirements ⚠️](#requirements)
* [License ©](#license)

---

## About 📌

Configure your first virtual server: partitioning (LVM+encryption), VM hardening, firewall, SSH, sudo policies, and a monitoring banner.
I compiled my study and setup details into a mind map: [View here](https://xmind.ai/share/xFYnNbIP)

---

## Setup 🛠️

1. **OS**: Latest stable Debian (recommended) or Rocky.
2. **VM**: Use VirtualBox or UTM (no snapshots).
3. **Partitioning**: Create ≥2 encrypted LVM partitions per subject diagrams.
4. **Hostname**: Set to `<your_login>42`.
5. **SSH**: Run on port `4242`, disable direct root login.

---

## Security 🔒

* **Firewall**: UFW (Debian) or firewalld (Rocky), only port `4242` open.
* **Users**: Create `<login>` in `user42` & `sudo` groups.
* **Password policy**:

  * Expire every 30 days; min 2 days between changes; warning at 7 days
  * ≥10 chars, mixed case, numbers, ≤3 identical consecutively
  * Root exception: last password rules relaxed
* **sudo**:

  * Limit to 3 attempts; custom error message
  * Log all I/O to `/var/log/sudo/`
  * Restrict secure\_path
  * Require TTY

---

## Monitoring 📊

Create `monitoring.sh` (bash) to broadcast every 10 min & at startup:

* OS architecture & kernel
* Physical & virtual CPU count
* RAM & disk usage
* CPU load
* Last reboot time
* LVM active
* TCP connections
* Active users
* IPv4 & MAC
* `sudo` command count

---

## Bonus 🏆

All bonus objectives have been implemented, including additional hardening tasks and automated backups.
I compiled my study and setup details into a mind map: [View here](https://xmind.ai/share/xFYnNbIP)

---

## Submission 📮

Include only `signature.txt` at repo root with your VM’s VDI/QCOW2 SHA1 hash. No VM files; snapshots forbidden.

---

## Inspired 🚀

Inspired by these community repos:

* [PedroZappa/42\_Born2beRoot](https://github.com/PedroZappa/42_Born2beRoot)
* [afmyhouse/4204-Born2BeRoot](https://github.com/afmyhouse/4204-Born2BeRoot)
* [ghenriqub/born2beroot](https://github.com/ghenriqub/born2beroot)

---

