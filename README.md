# High-Performance Production WordPress & Observability Stack (Dockerized)

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![WordPress](https://img.shields.io/badge/WordPress-21759B?style=for-the-badge&logo=wordpress&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)

معماری ایزوله و پرسرعت وردپرس به همراه پشته مانیتورینگ بلادرنگ (پرومتئوس و گرافانا) بر بستر داکر.

---

## English

A production-ready Docker Compose architecture providing an ultra-fast WordPress deployment backed by MariaDB and Redis Object Cache, served securely through Nginx with SSL, and monitored continuously using Prometheus, Exporters, and Grafana.

### Architecture Features
- **Sub-Second Latency**: Redis In-Memory object caching, tuned FastCGI buffers, and local static asset delivery.
- **Unified Reverse Proxy**: Nginx securely terminates SSL, routes WordPress requests, and reverse-proxies Grafana dashboards at `/grafana/` with full WebSocket support.
- **Full Observability**: Live metrics scrapers for host resources (Node Exporter), Nginx traffic (Nginx Exporter), and Redis operations (Redis Exporter).
- **Hardened & Zero Secrets**: Environment variable driven via `.env`, keeping sensitive credentials out of version control.

### How to Download & Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/aliedalat73/wp-docker-stack.git](https://github.com/aliedalat73/wp-docker-stack.git)
   cd wp-docker-stack
