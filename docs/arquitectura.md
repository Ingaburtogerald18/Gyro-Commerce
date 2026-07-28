# 02 - Arquitectura y Stack Tecnológico

## 1. Stack Tecnológico Elegido
El proyecto consolida su infraestructura en las siguientes herramientas principales para la fase beta:
*   **Frontend:** Construido con el framework web Remix[cite: 2].
*   **Estilos y Componentes:** Utiliza Tailwind CSS y la librería shadcn/ui para garantizar un diseño consistente y personalizable para cada uno de los negocios de prueba[cite: 2].
*   **Backend:** Servidor Node.js alojado en Render, responsable de la validación de entrada de datos con Zod y el control de tasa de peticiones (rate limiting)[cite: 2].
*   **Base de Datos:** Motor relacional PostgreSQL gestionado a través de Supabase[cite: 2]. Para la fase beta con 10 usuarios, se utilizará el plan **Gratuito (Free)**, el cual es suficiente para probar la viabilidad del sistema.
*   **Almacenamiento de Archivos:** Las imágenes del catálogo se alojarán en Cloudflare R2, asignando espacios separados por negocio[cite: 2].

## 2. Estrategia Multi-Tenant y Aislamiento de Datos
El riesgo principal del modelo SaaS es la fuga de datos, es decir, que un negocio vea las ventas o inventario de otro[cite: 2]. Para evitarlo, la plataforma implementa un aislamiento estricto:
*   **Regla de Oro del Backend:** Ninguna consulta a la base de datos se ejecuta sin antes haber resuelto el `tenant_id` (el identificador único del negocio) a través de un middleware en cada petición[cite: 2].
*   **Row-Level Security (RLS):** PostgreSQL y Supabase proveen políticas RLS que actúan como una segunda capa de seguridad a nivel del motor de base de datos[cite: 2]. Esto asegura que una consulta solo devuelva las filas de información que coincidan con el negocio autorizado[cite: 2].
*   **Acceso Centralizado:** El cliente web NUNCA lee ni escribe en la base de datos directamente[cite: 2]. Absolutamente toda transacción pasa por el backend en Node.js, que actúa como puerta única[cite: 2].

## 3. Autenticación, Identidad y Roles
*   **Proveedor de Identidad:** Se utilizará Supabase Auth para el registro, inicio de sesión y gestión de sesiones mediante JWT[cite: 2].
*   **Modelo de Membresías:** El sistema opera con un modelo donde un usuario puede tener una membresía asociada a uno o varios negocios distintos[cite: 2]. 
*   **Jerarquía de Accesos:** Se separan por completo los roles a nivel de "Plataforma" (el super-administrador del SaaS) de los roles a nivel de "Tenant" (los permisos operativos dentro de cada tienda)[cite: 2].
