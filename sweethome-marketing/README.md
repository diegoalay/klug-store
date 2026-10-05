# sweethome-marketing

Contexto comercial y de marketing de SweetHome (`sweethome.gt_`): decisiones, oferta, diagnóstico de redes y pauta, y bitácora de pautas en Meta.

**Qué es SweetHome:** tienda de decoración del hogar, propia de Diego. Vende por Instagram (`@sweethome.gt_`) y WhatsApp (+502 3974-2544); el sitio está en migración de `sweethome.com.gt` a `sweethome.gt` (caído por ahora). No es un cliente de LealKlub ni de Klug: es un negocio de retail aparte.

**Qué no va aquí:** el código del catálogo vive en el repo `klugstore` (sitio whitelabel, SweetHome es su primera tienda en producción; fuente de productos hoy es un Google Sheet). Aquí solo va la estrategia comercial y de marketing, aunque hay una excepción puntual: [`docs/catalogo-producto-2026-10-04.md`](docs/catalogo-producto-2026-10-04.md) analiza cómo se almacena el catálogo porque afecta directo a la oferta y a las ventas perdidas por falta de inventario.

## Índice

| Documento | Qué contiene |
|---|---|
| [`docs/diagnostico-2026-10-04.md`](docs/diagnostico-2026-10-04.md) | Primer levantamiento: redes, contenido, pauta corrida y centro de clientes potenciales |
| [`docs/mensajes/diagnostico-2026-10-04.md`](docs/mensajes/diagnostico-2026-10-04.md) | Revisión de conversaciones reales en Messenger/Instagram: dónde se cortan, y el guion de cierre que ya funciona |
| [`docs/mensajes/clientes-2026-10-04.md`](docs/mensajes/clientes-2026-10-04.md) | Ventas confirmadas, lugares de envío, clientas recurrentes y ticket promedio (uso interno) |
| [`docs/catalogo-producto-2026-10-04.md`](docs/catalogo-producto-2026-10-04.md) | Cómo se arma hoy el catálogo (Google Sheet vía `klugstore`), por qué cuesta mantenerlo, y opciones |
| [`docs/decisiones.md`](docs/decisiones.md) | Decisiones comerciales vigentes, con fecha y por qué, y lo que falta decidir |
| [`docs/oferta.md`](docs/oferta.md) | Qué se vende, precios observados y condiciones de envío/pago |
| [`docs/pautas/README.md`](docs/pautas/README.md) | Cuenta de Meta, aprendizajes, índice de pautas, convención de nombres y plantilla |
| [`docs/pendientes.md`](docs/pendientes.md) | Tareas comerciales abiertas |

## Cómo alimentarlo

- **Pauta nueva:** copiar la plantilla de [`docs/pautas/README.md`](docs/pautas/README.md) a `docs/pautas/AAAA-MM-<nombre>.md`, agregarla al índice y, al cerrarla, llenar los resultados y los aprendizajes.
- **Decisión nueva:** agregar una fila con fecha en [`docs/decisiones.md`](docs/decisiones.md). Si reemplaza a otra, se mueve la anterior a "Decisiones reemplazadas".
- **Cambio de oferta o precio:** primero confirmarlo con el catálogo real, después actualizar [`docs/oferta.md`](docs/oferta.md).
- Convenciones: fechas absolutas (AAAA-MM-DD), dinero en GTQ (es el mercado y la moneda en que se vende), y referencias a secciones con `#`.
