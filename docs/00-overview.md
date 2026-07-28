# Gyro Commerce — Documentación (Overview)

Bienvenido a la documentación oficial de Gyro Commerce. Este repositorio centraliza tanto el código como las decisiones estratégicas y técnicas del proyecto SaaS.

## 1. Visión General y Problema a Resolver
Los emprendedores pequeños de Nicaragua y Centroamérica manejan su operación de forma fragmentada, dependiendo de cuadernos, Excel y WhatsApp de manera desconectada. Tienen una vitrina, pero les falta la operación y herramientas para administrar el inventario, facturación y clientes.

**La Solución:** Gyro Commerce es un SaaS multi-tenant que le da a cada negocio un back-office completo y una tienda pública propia, manteniendo todos los datos estrictamente aislados por negocio. El sistema nace del código probado de Gyro Store, el cual se convertirá en el primer cliente de la plataforma (tenant #0)[cite: 2].

## 2. Índice de Documentación
Esta documentación está dividida modularmente para que el mantenimiento y la lectura por parte de asistentes de IA sea óptima. 

*   **[01-producto.md](./01-producto.md):** Modelo de negocio, planes de suscripción, propuesta de valor y alcance del MVP.
*   **[02-arquitectura.md](./02-arquitectura.md):** Stack tecnológico, base de datos (PostgreSQL + Supabase + RLS) y estrategia de aislamiento multi-tenant.
*   **[03-frontend.md](./03-frontend.md):** Guías de diseño, identidad de marca configurable y flujos principales de usuario.
*   **[04-modulos.md](./04-modulos.md):** Diagnóstico actual y desglose de los 25 módulos del sistema organizados por bloques de prioridad.
*   **[05-roadmap.md](./05-roadmap.md):** Integraciones (WhatsApp Cloud API) y el roadmap de desarrollo por fases (F0 a F5).
