# Linux SOC Incident Response Lab (Wazuh SIEM)

A home lab that simulates an SSH brute-force attack against an Ubuntu server, detects it with a Wazuh SIEM, and responds automatically by blocking the attacker's IP.

## Goal

Practice the core SOC workflow end to end: attack, log, detect, alert, respond.

## Architecture

```
Attacker (Windows host / WSL2, Hydra)  --SSH attempts-->  Ubuntu VM (VirtualBox)
                                                          - Wazuh manager + dashboard
                                                          - Wazuh agent reads /var/log/auth.log
                                                          - Active response blocks attacker IP
```

## Tools

Wazuh, Ubuntu, VirtualBox, Hydra, UFW, Bash

## MITRE ATT&CK mapping

- T1110 Brute Force

## Plan and progress

- [ ] Ubuntu VM running with bridged networking
- [ ] Wazuh installed, dashboard reachable from host
- [ ] Baseline: failed SSH logins visible in `/var/log/auth.log` and the dashboard
- [ ] Attack simulated with Hydra (own VM only, small wordlist)
- [ ] Custom rule written in `local_rules.xml`
- [ ] Active response configured, with a short block timeout
- [ ] False-positive test (legitimate user mistypes a password)
- [ ] Screenshots and final write-up

## Findings

_Add results here as you complete each step (screenshots, rule IDs, alert levels)._

## Problems I hit and how I fixed them

_Add real issues from your build here. Troubleshooting notes are valuable._

## Safety note

All attacks were run only against my own virtual machine in an isolated lab.
