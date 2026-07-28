# 01 - Producto: Visión, Modelo de Negocio y MVP

## 1. Público Objetivo y Propuesta de Valor

El producto tiene dos públicos, pero el foco principal es el vendedor (el cliente que paga). 
*   **El Vendedor:** Es un emprendedor o micro-negocio de Nicaragua y Centroamérica, muchas veces de un solo dueño y sin personal técnico. Actualmente vende por WhatsApp o redes sociales y necesita herramientas de gestión operativas (inventario, ventas, facturación). Es sensible al precio, con un ticket objetivo de $5 a $10 al mes.
*   **El Comprador:** Es el consumidor local acostumbrado a comprar por WhatsApp. Recorrerá el marketplace unificado para encontrar productos de varios negocios en un solo lugar, dándole visibilidad cruzada a las tiendas.

**Propuesta de Valor:**
El valor real del SaaS está en las **herramientas de gestión**, no solo en el marketplace. Aunque el marketplace será unificado y compartido para todos, es un criterio de diseño no negociable que las herramientas operativas deben valer por sí solas el costo de suscripción. El centro de administración de cada negocio será completamente personalizable con sus propios logos, colores y branding.

## 2. Modelo de Negocio y Planes

El SaaS operará mediante un modelo de tarifa plana mensual, donde cada negocio paga por el acceso a las herramientas de gestión. La plataforma NO cobrará comisiones por venta y NO manejará el dinero de las ventas de terceros.

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

## 3. Alcance del MVP (Producto Mínimo Viable / Fase Beta)

El objetivo central del MVP es lanzar un **programa beta con 10 usuarios** (emprendimientos pequeños). La tienda original (Gyro Store) no formará parte de esta plataforma y mantendrá su sistema actual independiente.

**Funcionalidades INCLUIDAS (Must-haves para la Beta):**
*   Modelo de aislamiento de datos: Cada uno de los 10 negocios beta tendrá su información completamente separada.
*   Herramientas core adaptadas: inventario, ventas, POS y reportes por negocio.
*   Panel de administración customizable: Cada negocio configura su branding, logos, moneda y número de WhatsApp para recibir pedidos.
*   Onboarding self-service y enrutamiento: Los usuarios beta podrán registrarse solos, y el sistema les asignará una URL única (ej. `gyrocommerce.com/tiendabeta`).
*   Marketplace Unificado (Fase 1): Estructura base para que todos los productos convivan en la misma plataforma general.

**Funcionalidades EXCLUIDAS del MVP (Para futuras versiones post-beta):**
*   **Checkout centralizado:** No se procesarán pagos de productos con tarjeta en la plataforma; el cliente enviará el pedido al WhatsApp del vendedor para coordinar el pago directo.
*   **Panel de super-admin avanzado:** No habrá métricas globales complejas, solo lo necesario para administrar a los usuarios beta.
*   **Dominios propios por negocio:** En la beta usarán las URLs generadas por la plataforma, no dominios personalizados (ej. `www.mitienda.com`).
*   **Asistencia por Inteligencia Artificial:** Las respuestas automáticas de WhatsApp con LLM quedan para una fase posterior.
*   Dominios propios por tenant y conversaciones de WhatsApp asistidas por LLM.
