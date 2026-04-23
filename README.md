## 👋 datamaq-automation

Cuenta de automatización e infraestructura de **DataMaq**, servicios técnicos e industrial-digitales en AMBA.

Este perfil agrupa los repos, configs y experimentos de nuestra capa de **agentes AI autónomos** orientados a operaciones, decisión ejecutiva y gestión de riesgo.

---

### 🦞 Agente principal: Tenazas

CEO virtual construido sobre [OpenClaw](https://github.com/openclaw/openclaw) / KimiClaw.

- **Modelo**: `gemini-2.5-flash` vía Google Vertex AI (proxy local)
- **Canales**: Kimi (bridge nativo) + Telegram (bot)
- **Contexto optimizado**: ~1.650 tokens fijos por interacción (-62% vs. config base)
- **Infra**: VM Debian 12 en GCP, 2 vCPU, 3.8 GB RAM, systemd user services

**Repo**: [`datamaq-automation/kimiclaw`](https://github.com/datamaq-automation/kimiclaw)

---

### 🛠️ Stack

| Capa | Tecnología |
|------|-----------|
| Gateway | OpenClaw 2026.4.15 (Node.js 22, systemd) |
| LLM | Google Vertex AI → `gemini-2.5-flash` |
| Proxy local | Node.js (`vertex-proxy.js`) |
| CLI dev | Kimi Code CLI v1.37.0 |
| Plugins | TypeScript (custom MCP-like tools) |
| MCPs | `filesystem`, `github` |
| OS | Debian 12 (bookworm) |
| Infra | GCE `southamerica-west1-b` |

---

### 📡 MCPs activos

| Servidor | Propósito |
|----------|-----------|
| `filesystem` | Lectura/escritura de archivos locales (`/home/agustin`) |
| `github` | Gestión de repos, issues, PRs y código |

Configurados tanto en **Kimi Code CLI** como en el **gateway de OpenClaw**.

---

### 🔧 Optimizaciones recientes

- **VM**: limpieza de 5+ GB en residuos Docker, cachés y backups; swap de 2 GB; límite de memoria en gateway (`MemoryMax=700M`)
- **Agente**: fusión de `AGENTS.md` + `SOUL.md`, eliminación de contexto redundante, plugin `workspace_check` con cache
- **Bridge**: rate-limit de logs en systemd para reducir ruido de reconexiones WS

---

### 📂 Repos principales

| Repo | Descripción |
|------|-------------|
| [`kimiclaw`](https://github.com/datamaq-automation/kimiclaw) | Personalizaciones del agente Tenazas: identidad, plugins, configs, docs |

---

### 🤝 Contacto

- **Empresa**: [DataMaq](https://datamaq.com.ar)
- **Human behind the bot**: Agustín
