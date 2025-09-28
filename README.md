# AcmeSearch Agent (acmesearchd)

**AcmeSearch Agent** is a small, lightweight search/diagnostics agent intended for internal use on server fleets.
It exposes a simple TCP control interface (plain-text CLI) for ad-hoc log searching and basic network diagnostics.

> Project: AcmeSearch Agent  
> Daemon: `acmesearchd`  
> Banner: `AcmeSearch Agent v1.3 (acmesearchd)`  
> Default port: **24444**

---

## Overview

AcmeSearch Agent was designed to make it quick for operators to query logs and run basic checks on remote hosts without requiring SSH. The agent supports a tiny interactive CLI (version check, help, and `ping <term>` search). It was written for internal tooling and performance-constrained environments.

> **Note:** This repository contains the upstream userland component only. The agent is intended to be installed and run under supervision in private networks. Do not expose to untrusted networks.

---

## Key features

- Plain-text TCP CLI (banner + simple commands)
- Lightweight: single-file Python implementation
- Log search across configured system logs
- Fake-friendly ping/diagnostics for quick checks
- Pluggable architecture for custom parsers (future)

---

## Installation (quick)

```bash
# clone
git clone https://github.com/acme/acmesearch.git
cd acmesearch

# run locally
python3 acme_searchd.py
