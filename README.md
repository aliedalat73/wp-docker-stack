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
   git clone https://github.com/aliedalat73/wp-docker-stack.git
   cd wp-docker-stack
   ```
2.Configure environment variables:
   cp .env.example .env
   nano .env
   (Fill in your desired secure database passwords and domain name)
   
  3.Provide SSL Certificates:
  Create an ssl directory and put your certificates inside:
  mkdir ssl
  # Place your cert.pem and key.pem inside ./ssl/

   4.Launch the stack:
   docker compose up -d
راهنمای فارسی (نحوه راه‌اندازی و استفاده)
برای راه‌اندازی سریع، امن و پایدار وردپرس با بالاترین کارایی بهینه شده است. همچنین تمام ابزارهای مانیتورینگ برای پایش سخت‌افزار، ترافیک وب‌سرور و کش به صورت خودکار متصل شده‌اند.

قابلیت‌های اصلی
سرعت لود زیر ثانیه: بهینه‌سازی شده برای حفظ پایداری بدون وابستگی به CDNهای خارجی با لود مستقیم استاتیک‌ها.

مسیردهی امن مانیتورینگ: دسترسی به داشبوردهای گرافانا روی مسیر /grafana/ با پشتیبانی کامل از وب‌سوکت.

دیده‌بانی کامل سرور: پایش مداوم منابع سرور (Node Exporter)، اتصالات Nginx و سلامت کش ردیس در داشبوردهای گرافانا.

امنیت کامل: عدم افشای رمزها در سورس‌کد با بهره‌گیری از .env.

مراحل دانلود و اجرا
   ۱. کلون کردن و دریافت پروژه:
git clone https://github.com/aliedalat73/wp-docker-stack.git
cd wp-docker-stack

۲. تنظیم پسوردها و مشخصات:
cp .env.example .env
nano .env
(رمزهای دلخواه خود را داخل فایل وارد کرده و ذخیره کنید).

۳. قرار دادن کلیدهای امنیتی SSL:
پوشه ssl را ساخته و فایل‌های سرتیفیکیت دامنه را داخل آن بگذارید
mkdir ssl
# فایل‌های cert.pem و key.pem را در این پوشه قرار دهید

۴.اجرای سرویس‌ها
docker compose up -d
