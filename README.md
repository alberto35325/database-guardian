# 🏛️ Database Guardian Pro: Enterprise Async Sentinel

![License](https://img.shields.io/badge/License-Proprietary-red)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Architecture](https://img.shields.io/badge/Architecture-AsyncIO--Grade%20A-brightgreen)
![Maintenance](https://img.shields.io/badge/Code%20Duplication-0%25-brightgreen)
![Performance](https://img.shields.io/badge/Memory-%3C50MB-brightgreen)

**Database Guardian Pro** es un orquestador de monitoreo de alto rendimiento diseñado para entornos donde la disponibilidad no es negociable. A diferencia de scripts básicos, este Sentinel utiliza una **Arquitectura de Plugins Extensible** y un motor asíncrono para vigilar toda tu infraestructura con una eficiencia de recursos extrema.

---

## 🏗️ Ingeniería de Grado A: El Sistema de Plugins

El corazón de Guardian Pro es su **DatabasePluginRegistry**. Gracias a una implementación estricta de clases abstractas (`BaseDatabaseDriver`), el sistema garantiza:

* **Abstracción Total:** Cada driver implementa su propia lógica de conexión (`aiomysql`, `asyncpg`, `motor`, etc.), pero todos retornan un formato estandarizado de resultados.
* **Carga Dinámica:** El sistema escanea el directorio `/plugins` e integra nuevos drivers en tiempo de ejecución mediante `importlib`.
* **Future-Proof:** Si tu infraestructura cambia de motor, el Guardián se adapta sin tocar el código core.

---

## 🔌 Compatibilidad Universal (Out-of-the-box)

Monitorea múltiples instancias en paralelo con drivers asíncronos nativos:

* **Relacionales:** MySQL 8.0+, MariaDB, PostgreSQL, SQLite.
* **NoSQL:** MongoDB (vía Motor/Async).
* **Caching & Colas:** Redis (monitoreo de disponibilidad y latencia).
* **Extensibilidad:** Sistema de plugins listo para añadir cualquier DB (ej. SQL Server, Oracle) en minutos.

---

## 🚨 Sistema de Alertas Inteligente (Anti-Fatiga)

Guardian Pro incluye un **Sistema de Semáforo** diseñado para proteger tu salud mental y evitar el spam de notificaciones:

* 🔴 **Alertas ROJAS (Crítico):** Fallos totales de conexión. Notificación inmediata a Discord/Slack/Telegram con mención `@everyone`.
* 🟡 **Alertas AMARILLAS (Warning):** Advertencias de alta latencia o degradación de rendimiento. Alertas silenciosas para seguimiento técnico.
* 🔵 **Alertas AZULES (Info):** Logs informativos de recuperación de servicio y cambios de estado.
* 🔄 **Deduplicación & Cooldown:** Algoritmo que solo notifica cuando el estado **cambia**, evitando recibir 100 mensajes por el mismo error.

---

## 📡 Dashboard & API Gateway

* **WebSocket Live Stream:** Interfaz web responsive que recibe actualizaciones vivas del Sentinel sin necesidad de refrescar (Zero Polling).
* **API RESTful:** Endpoints protegidos (`/health`, `/status`, `/metrics`) para integrar con otros sistemas internos.
* **Prometheus Ready:** Exportación nativa de métricas para alimentar tus tableros profesionales en **Grafana**.

---

## 🛡️ Seguridad y Resiliencia Senior

* **Enmascaramiento de Datos:** Las credenciales y logs sensibles se filtran automáticamente antes de ser enviados a las plataformas de chat.
* **Rate Limiting:** Protección integrada en la API para evitar abusos o ataques DoS internos.
* **Zero-Footprint:** Optimizado para consumir **menos de 50MB de RAM**.
* **Instalador Automatizado:** Script `install.sh` que gestiona entornos virtuales, dependencias y permisos de forma segura.

---

## 🚀 Despliegue en Producción (5 min)

```bash
# 1. Preparar el entorno
cd database-guardian-pro
cp .env.example .env  # Configura tus Webhooks y API Keys

# 2. Despliegue con Docker (Recomendado)
docker-compose up -d

# 3. O instalación nativa
chmod +x scripts/install.sh && ./scripts/install.sh
python src/main.py
🏛️ Por qué elegir Database Guardian Pro
Este software se entrega como un activo de software profesional ("Source-Included"):

Privacidad Total: Tus datos y credenciales nunca salen de tu servidor. No hay telemetría ni dependencias externas ocultas.

Código Auditado: Arquitectura limpia, sin deuda técnica y lista para ser extendida por tu equipo.

Soporte Directo: Al adquirir la licencia, obtienes el compromiso de mantenimiento y estabilidad de una herramienta de pago.

🛒 Obtener Acceso Completo
Consigue tu licencia profesional y el código fuente completo instantáneamente:

👉 Consigue Database Guardian Pro en Gumroad:https://operao.gumroad.com/l/ytuyep
