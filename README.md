# 🐳 Docker Microservice App & DB Integration

## 📖 Descrizione

Ho realizzato un progetto Docker in cui ho containerizzato una mini-app basata su Node.js e PostgreSQL, con l’obiettivo di dimostrare la mia capacità di costruire e gestire servizi Docker.
L’applicazione include endpoint di healthcheck, API REST, un pannello database "Adminer" e una pagina web che mostra lo stato del servizio e l’URL di accesso.

---

## 🎯 Obiettivi del progetto

Questo progetto serve per mostrare:

- 🧱 **Competenze pratiche in Docker e networking** (servizi su rete interna)  
- ⚙️ **Gestione di build multistadio o ottimizzate** (Node runtime vs deps)  
- 🔗 **Separazione tra applicazione e database**  
- 🧩 **Creazione di API REST semplici ma reali**  
- 🌐 **Integrazione front-end / back-end / DB** in un ambiente container

---

## 🧠 Architettura

Il progetto è composto da tre servizi:

| Servizio | Descrizione | Porta locale |
|-----------|-------------|---------------|
| **app** | Contiene l’applicazione Node.js / Express con API REST e pagina web | `8080` |
| **db** | Database PostgreSQL con tabella `users` di esempio | `5432` |
| **adminer** | Interfaccia web per esplorare il database | `8081` |

Tutti i servizi comunicano tra loro su una **rete Docker privata**, isolata dal resto del sistema.

---

## ⚙️ Endpoint principali

| Metodo | Endpoint | Descrizione |
|---------|-----------|-------------|
| `GET` | `/health` | Verifica lo stato dell’applicazione |
| `GET` | `/users` | Restituisce la lista degli utenti nel database |
| `POST` | `/users` | Crea un nuovo utente con JSON `{ "name": "Tizio" }` |
| `GET` | `/` | Mostra la pagina web principale (index.html) |

---

## 🧩 Avvio del progetto

Assicurati di avere **Docker** e **Docker Compose** installati.  
Poi esegui:

```bash
docker compose up -d --build
