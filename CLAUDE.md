# CTI Homelab — Project Memory

## Identity
Goal: CTI analyst who knows DFIR. Core forever: CTI.
DFIR: learn on the job. Do not over-engineer this now.

## Hardware
Windows: Dell i5-1035G1, 8GB RAM, Win11 Pro, PS7
  IP: 192.168.100.4
  Docker limit: 3 containers MAX simultaneously
  C: 234GB (82GB free) | D: 463GB | E: 467GB

Linux: Dell E7250 i5-5300U, 8GB RAM, Linux Mint 22.1
  IP: [run ip a on Linux and fill in]
  No Docker. Native installs only. Always on, plugged in.

## Always-On Docker (Windows)
  MISP:          https://localhost:443
  Elasticsearch: http://localhost:9200
  Grafana:       http://localhost:3000

## On-Demand Docker (Windows)
  TheHive: http://localhost:9000
  Stop Grafana first. Restart Grafana after.

## Linux Services
  Suricata: monitoring wlp2s0
  Zeek: monitoring wlp2s0
  Filebeat: shipping to Windows Elasticsearch
  Feed scripts: ~/cti-lab/feeds/ via cron every 6h
  SpiderFoot: http://localhost:5001 (on demand)

## Current Phase
  Phase 0 — Foundation

## What Is Working
  - Git installed (2.53.0)
  - Node.js installed (v24.14.0)
  - Claude Code installed (2.1.52)
  - GitHub repo created: https://github.com/farrukhCTI/cti-homelab
  - Folder structure created on D:\cti-homelab
  - Static IP set: 192.168.100.4 (permanent)
  - WSL memory capped at 5GB via .wslconfig
  - Docker Desktop installed and running (v29.2.1)
  - Docker data root on D:\docker data\DockerDesktopWSL
  - Bitwarden installed with 2FA
  - ProtonMail research identity created
  - Discord CTI Lab server created (5 channels)
  - Sysmon v15.15 installed with SwiftOnSecurity config
  - Sysmon logs verified (Event ID 1, 4, 16 confirmed)
  - Config committed to GitHub: windows/sysmon/sysmonconfig.xml
  - Elasticsearch v8.13.0 running in Docker on localhost:9200
  - Winlogbeat v8.13.0 installed as Windows service
  - Winlogbeat shipping Sysmon, Security, System, PowerShell logs to Elasticsearch
  - Pipeline verified: 730+ events indexed
  - Config committed to GitHub: windows/winlogbeat/winlogbeat.yml

## Known Issues
  None yet.

## Decisions Log
  See decisions.md

## Next Steps
  - Get Linux IP and update this file
  - Phase 0 complete, begin Phase 1 (MISP)