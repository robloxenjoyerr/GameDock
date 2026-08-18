# GameDock

> Open-source, self-hosted game server management platform.

GameDock is a self-hosted platform for managing dedicated game servers through a modern web interface.

The goal is to make deploying, configuring, monitoring and managing game servers simple while keeping the platform lightweight, modular and fully under the user's control.

> ⚠️ **GameDock is currently in early development.**
> Features, architecture and APIs are subject to change.

---

## ✨ Goals

GameDock aims to provide a central interface for managing game servers without relying on proprietary hosting platforms.

Planned capabilities include:

- 🎮 Create and manage game servers
- ▶️ Start, stop and restart servers
- 📋 View server status and logs
- 🖥️ Live server console
- 📦 Server templates
- 💾 Backups and restore
- 👥 User and permission management
- 🔐 Authentication and security
- 🐳 Docker-based server provisioning
- 🌐 Multi-node support
- 📊 Server resource monitoring

The initial development focus is a reliable single-node setup. More advanced infrastructure will be introduced incrementally.

---

## 🏗️ Architecture

GameDock is designed as a modular application consisting of a web frontend, API backend, database and container infrastructure.

```text
                         ┌─────────────────┐
                         │     Browser     │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │    Next.js      │
                         │ React / TS      │
                         └────────┬────────┘
                                  │
                           REST / WebSocket
                                  │
                                  ▼
                         ┌─────────────────┐
                         │     FastAPI     │
                         │     Python      │
                         └───────┬─────────┘
                                 │
                    ┌────────────┼────────────┐
                    │            │            │
                    ▼            ▼            ▼
              PostgreSQL      Docker       Services
                                │
                                ▼
                         Game Containers
