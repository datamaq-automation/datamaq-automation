## 🦞 Agente Tenazas - Detalles Técnicos

Este documento contiene la configuración técnica de la capa de agentes de **DataMaq Automation**.

### 🛠️ Stack Tecnológico

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

### 📡 MCPs activos

| Servidor | Propósito |
|----------|-----------|
| `filesystem` | Lectura/escritura de archivos locales |
| `github` | Gestión de repos, issues, PRs y código |

### 🔧 Optimizaciones Recientes
- **VM**: limpieza de 5+ GB en residuos Docker, cachés y backups; swap de 2 GB; límite de memoria en gateway (`MemoryMax=700M`).
- **Contexto**: optimizado a ~1.650 tokens fijos por interacción (-62% vs. config base).
- **Logs**: rate-limit en systemd para reducir ruido de reconexiones WS.
