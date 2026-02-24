# Decisions Log

## 2026-02-25 — Initial Architecture

### Windows as Intelligence Core
Windows node (i5-1035G1, 8GB) is stronger than Linux node (i5-5300U, 8GB).
Docker runs here. MISP, Elasticsearch, Grafana, TheHive all on Windows.
Hard rule: maximum 3 Docker containers simultaneously.

### Linux as Sensor Node
Linux node stays always-on, plugged in permanently.
No Docker on Linux. Native installs only.
Runs Suricata, Zeek, Filebeat, and feed scripts.

### No RAM upgrade
Budget constraint. Working within 8GB on both nodes.
Architecture designed around this ceiling — not ignoring it.

### Claude Code on Windows
All active work happens on Windows. Claude Code lives where the work is.
Reads CLAUDE.md automatically for persistent context.

### Discord for alerting
Telegram banned in Pakistan. Discord is free, reliable, webhook native in Grafana.
