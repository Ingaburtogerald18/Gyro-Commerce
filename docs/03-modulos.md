# 03 - Módulos del Sistema y Bloques de Desarrollo

La construcción de Gyro Commerce se divide en bloques lógicos para garantizar que la base sea sólida antes de agregar características complejas. (Nota: Se ha excluido el módulo original de migración de la tienda base, enfocando el desarrollo directamente en el programa beta).

## Bloque A: Fundación Multi-Tenant
Este bloque es el cimiento de la plataforma; sin él, no hay aislamiento de negocios.
*   **M1 — Modelo de Tenant y Aislamiento:** Creación del middleware que identifica el `tenant_id` a través del subdominio o subpath en cada petición web. Ninguna operación de datos puede ejecutarse sin este contexto.
*   **M2 — Identidad y Membresías:** Implementación de Supabase Auth para separar los roles de plataforma (super-admin) de los permisos operativos dentro de cada tienda beta.
*   **M3 — Onboarding Self-Service:** Flujo para que los 10 usuarios beta se registren por sí mismos, creen su negocio (generando un slug único) y reciban su configuración inicial por defecto.
*   **M4 — Enrutamiento y Dominios:** Resolución en el frontend Remix para saber qué tienda mostrar dependiendo de la URL visitada.

## Bloque B: Gobernanza de la Plataforma
Módulos para que el dueño del SaaS administre las cuentas beta y prepare la futura monetización.
*   **M5 — Planes y Suscripciones:** Estructura base de los planes (Free, Estándar, Pro) y control de estados (activo, suspendido) para futuras integraciones de cobro.
*   **M6 — Límites y Cuotas:** Lógica que evalúa constantemente los topes de productos, almacenamiento y reportes según el plan asignado al negocio.
*   **M7 — Panel de Plataforma Básico:** Centro de control independiente para dar de alta, pausar o gestionar las cuentas de los usuarios beta, sin métricas globales complejas por el momento.

## Bloque C: Marketplace Unificado y Superficie Pública
La cara visible para los compradores finales.
*   **M9 — Catálogo Unificado:** Estructura base para el marketplace compartido, permitiendo en un futuro la búsqueda centralizada de productos de todos los negocios inscritos.
*   **M10 — Storefront Individual:** La vitrina pública de cada tienda, parametrizada para mostrar el branding, logo y colores propios de cada negocio beta.
*   **M11 — Carrito y Checkout por WhatsApp:** Lógica de compras donde los pedidos no se cobran en la plataforma, sino que generan un mensaje directo al número de WhatsApp configurado por el vendedor.

## Bloque D: Herramientas Core de Gestión
La adaptación del back-office operativo para que funcione de manera aislada por negocio.
*   **M12 a M16 — Operaciones Centrales:** Catálogo, inventario, cotizador de ventas, facturación POS y reportes, todos con el alcance (scope) estrictamente limitado al `tenant_id` del usuario que los consulta.
*   **M20 — Configuración del Negocio:** Panel donde cada tienda beta ajusta sus reglas internas: marca, textos, moneda local y número oficial de contacto.

## Bloque E: Requisitos Transversales
*   **M21 — Almacenamiento Compartimentado:** Separación de carpetas por `tenant_id` dentro de Cloudflare R2 para aislar las imágenes subidas por cada usuario beta.
*   **M24 — Seguridad de Aislamiento:** Pruebas automatizadas (tests) que verifiquen activamente que un usuario del negocio A no pueda leer ni por accidente la información del negocio B.
