# 02 - Arquitectura y Stack Tecnológico

## 1. Stack Tecnológico Elegido
El proyecto consolida su infraestructura en las siguientes herramientas principales:
*   **Frontend:** Construido con el framework Remix[cite: 2].
*   **Estilos y Componentes:** Utiliza Tailwind CSS y shadcn/ui para garantizar un diseño consistente y personalizable por cada negocio[cite: 2].
*   **Backend:** Servidor Node.js alojado en Render, responsable de la validación de datos con Zod y el control de tasa de peticiones (rate limiting)[cite: 2].
*   **Base de Datos:** Motor relacional PostgreSQL gestionado a través de Supabase (se requiere el plan Pro para backups y persistencia)[cite: 2].
*   **Almacenamiento de Archivos:** Las imágenes de los productos se alojarán en Cloudflare R2, asignando espacios separados por negocio[cite: 2].

## 2. Estrategia Multi-Tenant y Aislamiento de Datos
El riesgo principal del modelo SaaS es la fuga de datos entre los negocios registrados[cite: 2]. Para evitarlo, la plataforma implementa un aislamiento estricto:
*   **Regla de Oro del Backend:** Ninguna consulta a la base de datos se ejecuta sin antes haber resuelto el `tenant_id` (el identificador único del negocio) en cada petición[cite: 2].
*   **Row-Level Security (RLS):** PostgreSQL y Supabase proveen políticas RLS que actúan como una segunda capa de defensa[cite: 2]. Esto asegura desde la raíz de la base de datos que una consulta solo devuelva las filas de información que coincidan con el negocio autorizado[cite: 2].
*   **Acceso Centralizado:** El cliente (frontend web) NUNCA interactúa directamente con la base de datos[cite: 2]. Absolutamente toda transacción pasa por el backend en Node.js, que actúa como única puerta de entrada y validación[cite: 2].

## 3. Autenticación, Identidad y Roles
*   **Proveedor de Identidad:** Se abandona la lista blanca manual y se utilizará Supabase Auth para el registro y acceso self-service de los usuarios[cite: 2].
*   **Modelo de Membresías:** El sistema opera con un modelo de roles de dos niveles donde un usuario puede pertenecer a varios negocios (tenants) distintos[cite: 2]. 
*   **Jerarquía de Accesos:** Se separan por completo los permisos de "Plataforma" (el super-admin dueño del SaaS) de los permisos dentro de un "Tenant" (donde un usuario puede ser administrador, vendedor o cajero de una tienda específica)[cite: 2].
