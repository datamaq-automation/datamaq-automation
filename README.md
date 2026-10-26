# ⚡ DataMaq Automation

**Monitoreo de energía eléctrica y automatización para PyMEs industriales — Zona Norte del GBA, Argentina.**

Hola, soy Agustín. Diseño y mantengo DataMaq: medidores de energía instalados en planta, un backend propio que recibe la telemetría en tiempo real y las aplicaciones que le permiten a una pyme entender (y bajar) su consumo y las penalizaciones de la distribuidora.

🌐 [datamaq.com.ar](https://datamaq.com.ar) · 📊 [app.datamaq.com.ar](https://app.datamaq.com.ar) · ✉️ agustin@datamaq.com.ar

---

## 🔌 Qué hago

**Telemetría y gestión de la energía**
- Medidores *Powermeter* (ESP32) que reportan por MQTT a un servidor propio.
- Dashboard en tiempo real, unifilar, alertas, curvas de potencia y facturación.
- Análisis de factor de potencia, penalizaciones por bajo cos φ y dimensionamiento de bancos de capacitores.
- Datos maestros declarativos (empresa → planta → proceso, estilo ISA-95) alineados con un Sistema de Gestión de la Energía (ISO 50001).

**Sitios y portales web**
- Sitios institucionales y de servicios renderizados en servidor (FastAPI + Jinja2 + Tailwind), con el contenido versionado en YAML.

**Desarrollo asistido por IA**
- Trabajo con *Spec-Driven Development*, Clean Architecture / DDD y agentes de código (Claude Code), con herramientas y plantillas propias para que el flujo sea reproducible.
- Un servidor MCP para consultar la telemetría de las plantas desde un asistente.

## 🧰 Stack

| Capa | Tecnologías |
|------|-------------|
| Backend | Python · FastAPI · MQTT (Mosquitto) · MySQL · WebSocket |
| Frontend | Vue 3 · TypeScript · Vite · Tailwind CSS v4 · Pinia |
| Embebido | ESP32 · Arduino |
| Infra | Linux (Debian) · VPS · Tailscale · CI/CD por push a `main` |
| Herramientas | Claude Code · Ollama · MCP · GitHub Actions |

## 📂 Repositorios públicos

| Repositorio | Descripción |
|-------------|-------------|
| [`spec`](https://github.com/datamaq-automation/spec) | Plantillas de SRS y especificaciones técnicas (SSOT + *Constraint Gauntlet*) para backend y frontend, con validador de arquitectura sin dependencias. |
| [`datamaq-skill-cliente`](https://github.com/datamaq-automation/datamaq-skill-cliente) | Skill pública para asesorar en un Sistema de Gestión de la Energía e inversiones de bajo riesgo. |
| [`promts`](https://github.com/datamaq-automation/promts) | Prompts reutilizables para coordinar varias sesiones de Claude Code (orquestadores y agentes). |
| [`agy-token-optimizer`](https://github.com/datamaq-automation/agy-token-optimizer) | Reducción del consumo de tokens con poda AST, caché semántico y modelos locales. |
| [`camino_critico_pert`](https://github.com/datamaq-automation/camino_critico_pert) | App web de Camino Crítico (CPM) y PERT: FastAPI, NetworkX y visualización de grafos. |
| [`dotfiles`](https://github.com/datamaq-automation/dotfiles) | Mi configuración de entorno. |

El producto (plataforma de telemetría, aplicación web y sitios) vive en repositorios privados.

---

## 🤝 Contacto

- **Web:** [datamaq.com.ar](https://datamaq.com.ar)
- **Email:** agustin@datamaq.com.ar
