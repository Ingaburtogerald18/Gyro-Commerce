# 01 - Producto: Visión, Modelo de Negocio y MVP

## 1. Público Objetivo y Propuesta de Valor

El producto tiene dos públicos, pero el foco principal es el vendedor (el cliente que paga)[cite: 2]. 
*   **El Vendedor:** Es un emprendedor o micro-negocio de Nicaragua y Centroamérica, muchas veces de un solo dueño y sin personal técnico[cite: 2]. Actualmente vende por WhatsApp o redes sociales y necesita herramientas de gestión operativas (inventario, ventas, facturación)[cite: 2]. Es sensible al precio, con un ticket objetivo de $5 a $10 al mes[cite: 2].
*   **El Comprador:** Es el consumidor local acostumbrado a comprar por WhatsApp[cite: 2]. A futuro, recorrerá el marketplace para encontrar productos de varios negocios, dándole visibilidad a las tiendas[cite: 2].

**Propuesta de Valor:**
El valor real del SaaS está en las **herramientas de gestión**, no en el marketplace[cite: 2]. El directorio público es un gancho de adquisición[cite: 2]. Es un criterio de diseño no negociable que las herramientas operativas deben valer por sí solas el costo de suscripción, incluso si el negocio nunca recibe tráfico de la vitrina compartida[cite: 2].

## 2. Modelo de Negocio y Planes

El SaaS operará mediante un modelo de tarifa plana mensual, donde cada negocio paga por el acceso a las herramientas de gestión[cite: 2]. La plataforma NO cobrará comisiones por venta y NO manejará el dinero de las ventas de terceros en la primera versión[cite: 2].

### Filosofía de los límites
El plan gratuito funciona como gancho de entrada y limita fuertemente los costos de infraestructura (productos y fotos), pero es generoso con las características que generan enganche en el usuario (registro de ventas)[cite: 2].

### Tabla de Planes

| Característica | Free | Estándar ($5/mes) | Pro ($10/mes) |
| :--- | :--- | :--- | :--- |
| **Productos** | 20[cite: 2] | 250[cite: 2] | Ilimitado (tope storage)[cite: 2] |
| **Fotos por producto** | 4[cite: 2] | 8[cite: 2] | 12[cite: 2] |
| **Ventas / mes** | 100[cite: 2] | Ilimitado[cite: 2] | Ilimitado[cite: 2] |
| **Usuarios** | 2[cite: 2] | 5[cite: 2] | 10[cite: 2] |
| **Almacenamiento (R2)** | 100 MB[cite: 2] | 2 GB[cite: 2] | 10 GB[cite: 2] |
| **Marca Gyro en storefront** | Visible[cite: 2] | Removible[cite: 2] | Removible[cite: 2] |

> *Nota sobre las ventas en el plan Free: Al superar las 100 ventas, NO se bloquea el registro para no interrumpir el negocio, pero se limita el acceso al historial y a reportes detallados, invitando a subir de plan[cite: 2].*

## 3. Alcance del MVP (Producto Mínimo Viable)

El objetivo central del MVP es lograr migrar exitosamente el tenant #0 (la tienda base original) y permitir que un segundo negocio real pueda registrarse, operar y pagar sus suscripciones de forma independiente[cite: 2]. 

**Funcionalidades INCLUIDAS (Must-haves):**
*   Modelo de tenant y middleware de resolución en cada request (base del aislamiento)[cite: 2].
*   Tests activos de aislamiento de datos entre negocios[cite: 2].
*   Migración de los datos actuales al tenant #0 sin downtime[cite: 2].
*   Herramientas core adaptadas: catálogo, inventario, ventas, POS y reportes[cite: 2].
*   Configuración individual por negocio: branding, moneda, WhatsApp y comisiones internas[cite: 2].
*   Onboarding self-service mínimo y enrutamiento por subdominio o subpath[cite: 2].

**Funcionalidades EXCLUIDAS (Para la versión 2):**
*   Vitrina compartida (discovery cross-tenant con búsqueda global)[cite: 2].
*   Checkout centralizado con pasarela de pago de productos[cite: 2].
*   Panel de super-admin avanzado con métricas globales[cite: 2].
*   Dominios propios por tenant y conversaciones de WhatsApp asistidas por LLM[cite: 2].
