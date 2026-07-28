# 01 - Producto: Visión, Modelo de Negocio y MVP

## 1. Público Objetivo y Propuesta de Valor

El producto tiene dos públicos, pero el foco principal es el vendedor (el cliente que paga). 
*   **El Vendedor:** Es un emprendedor o micro-negocio de Nicaragua y Centroamérica, muchas veces de un solo dueño y sin personal técnico. Actualmente vende por WhatsApp o redes sociales y necesita herramientas de gestión operativas (inventario, ventas, facturación). Es sensible al precio, con un ticket objetivo de $5 a $10 al mes.
*   **El Comprador:** Es el consumidor local acostumbrado a comprar por WhatsApp. A futuro, recorrerá el marketplace para encontrar productos de varios negocios, dándole visibilidad a las tiendas.

**Propuesta de Valor:**
El valor real del SaaS está en las **herramientas de gestión**, no en el marketplace. El directorio público es un gancho de adquisición. Es un criterio de diseño no negociable que las herramientas operativas deben valer por sí solas el costo de suscripción, incluso si el negocio nunca recibe tráfico de la vitrina compartid.

## 2. Modelo de Negocio y Planes

El SaaS operará mediante un modelo de tarifa plana mensual, donde cada negocio paga por el acceso a las herramientas de gestión. La plataforma NO cobrará comisiones por venta y NO manejará el dinero de las ventas de terceros en la primera versión.

### Filosofía de los límites
El plan gratuito funciona como gancho de entrada y limita fuertemente los costos de infraestructura (productos y fotos), pero es generoso con las características que generan enganche en el usuario (registro de ventas).

### Tabla de Planes

| Característica | Free | Estándar ($5/mes) | Pro ($10/mes) |
| :--- | :--- | :--- | :--- |
| **Productos** | 20 | 250 | Ilimitado (tope storage) |
| **Fotos por producto** | 4 | 8 | 12 |
| **Ventas / mes** | 100 | Ilimitado | Ilimitado |
| **Usuarios** | 2 | 5 | 10 |
| **Almacenamiento (R2)** | 100 MB | 2 GB | 10 GB |
| **Marca Gyro en storefront** | Visible | Removible | Removible |

> *Nota sobre las ventas en el plan Free: Al superar las 100 ventas, NO se bloquea el registro para no interrumpir el negocio, pero se limita el acceso al historial y a reportes detallados, invitando a subir de plan.*

## 3. Alcance del MVP (Producto Mínimo Viable)

El objetivo central del MVP es lograr migrar exitosamente el tenant #0 (la tienda base original) y permitir que un segundo negocio real pueda registrarse, operar y pagar sus suscripciones de forma independiente[cite: 2]. 

**Funcionalidades INCLUIDAS (Must-haves):**
*   Modelo de tenant y middleware de resolución en cada request (base del aislamiento).
*   Tests activos de aislamiento de datos entre negocios.
*   Migración de los datos actuales al tenant #0 sin downtime.
*   Herramientas core adaptadas: catálogo, inventario, ventas, POS y reportes.
*   Configuración individual por negocio: branding, moneda, WhatsApp y comisiones internas.
*   Onboarding self-service mínimo y enrutamiento por subdominio o subpath.

**Funcionalidades EXCLUIDAS (Para la versión 2):**
*   Vitrina compartida (discovery cross-tenant con búsqueda global).
*   Checkout centralizado con pasarela de pago de productos.
*   Panel de super-admin avanzado con métricas globales.
*   Dominios propios por tenant y conversaciones de WhatsApp asistidas por LLM.
