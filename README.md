# Physio

*Correcting your cloud’s posture.*

Physio is an **open source, agentless Cloud Security Posture Management (CSPM)** tool focused on **Azure**.
It scans your subscriptions for misconfigurations using read-only Azure APIs and helps teams improve their security posture.
Self-hosted. Easy to deploy. Built with **Python (backend)** and **React (frontend)**.

---

## Features (MVP)

* 🔍 Agentless scans of Azure subscriptions (via Service Principal)
* 🧩 Pluggable rule engine for misconfiguration checks
* 📊 Outputs in table, JSON, and CSV
* 🌐 REST API + lightweight React UI to browse findings
* 🐳 Self-host with Docker (docker-compose for local, Helm chart later)

---

## Quick Start

### Prerequisites

* Python 3.11+
* Node 20+
* Docker / Docker Compose
* Azure Service Principal with **Reader** role on target subscriptions


### Run a Scan (CLI)

```bash
git clone https://github.com/<your-username>/physio.git
cd physio/backend

python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

export AZ_TENANT_ID=...
export AZ_CLIENT_ID=...
export AZ_CLIENT_SECRET=...
export AZ_SUBSCRIPTION_ID=...

python -m engine.scan --subscriptions $AZ_SUBSCRIPTION_ID --format table
```


---

## Project Structure

```
physio/
 ├── backend/      # Python collector, rules, engine, API
 ├── frontend/     # React app for viewing findings
 ├── deploy/       # docker-compose, Helm (later)
 ├── docs/         # guides, architecture, design notes
 └── README.md
```

---

## Roadmap

* [ ] Collector for Azure Resource Graph & ARM
* [ ] Rule engine with core rules (Storage, KeyVault, Network, Identity)
* [ ] CLI interface with JSON/CSV exports
* [ ] REST API with FastAPI
* [ ] React UI to view findings
* [ ] Self-host deployment via Docker
* [ ] v1.0 release with \~30 Azure rules

---

## Contributing

PRs and issues are welcome. Check out `docs/` for guidance on writing rules and contributing code.

---

## License

MIT License. See [LICENSE](./LICENSE).
