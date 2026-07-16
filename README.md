# Nominativa · Cotizador (Sizing)

Cotizador interactivo del SaaS de nómina y cumplimiento fiscal-laboral de Nominativa.
Sitio 100% estático: todo el motor de cálculo corre en el navegador (`index.html`).

## Versión actual: v15.4 (16-jul-2026)

Cambios acumulados sobre v15.1:
- Tarifa escalonada marginal por colaborador ($23 primeros 300 · $22 de 301–600 · $21 de 601+), sin inversiones de precio.
- Configuración base incluye los esquemas: Sueldos y Salarios (ID 1), Finiquito (ID 4), Aguinaldo Sueldos y Salarios (ID 21) y PTU (ID 60).
- Resto de esquemas cotizados individualmente vía `SCH_COST` (promedio $15,000 MXN; REPSE/Maquila premium $22,000).
- Semanas de integraciones sumadas a la duración estimada (`intWks`).
- Copy de integraciones alineado (tarifas estándar por complejidad, alcance en diagnóstico).
- Firma como intención de avance, no aceptación de condiciones.
- Validación real de email; sin dependencias de Cloudflare email-decode.

## Deploy

Cloudflare Pages conectado a este repositorio:
- Build command: (ninguno)
- Output directory: `/`
- Cada push a `main` publica automáticamente.

## Pendiente

- Blindar el Worker de correo (purple-mountain): from/to fijos server-side,
  allowlist de orígenes (agregar el dominio del cotizador) y rate limiting.
