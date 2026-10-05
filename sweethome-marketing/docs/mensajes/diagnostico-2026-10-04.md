# Diagnóstico de conversaciones — 2026-10-04

Revisión del inbox completo de Meta Business Suite (Messenger + Instagram DM; WhatsApp Business no está conectado, ver [pendientes](../pendientes.md)). Se hicieron dos pasadas: una primera de ~65 conversaciones y una segunda que recorrió **las 6 páginas completas del centro de clientes potenciales (103 registros)**, cubriendo todo el histórico real de la cuenta desde el primer contacto en **septiembre 2024** hasta hoy. De esos 103, se excluyen 2 por no ser clientes reales (la cuenta del equipo y un registro de demostración de Meta) y **4 no se pudieron abrir** por un problema de carga de la propia tabla de Meta Business Suite (Marta Gaitan, Sindy Sanchez, Sagaz Bren, Gladis Valdez). El resto — prácticamente la totalidad — se revisó a fondo.

## Cuántas campañas de pauta hubo realmente

El [diagnóstico general](../diagnostico-2026-10-04.md) y la [pauta documentada](pautas/2026-08-reel-catalogo.md) solo cubrían un anuncio ("Reel Catálogo", ago–sep 2026). Revisando los `ad_id` en las conversaciones reales aparecen **al menos tres campañas pagadas distintas en 2026**, no solo una:

- `ad_id...7910247` — mediados de mayo a julio 2026 (varios contactos del 16 al 20 de mayo, más sueltos en junio y julio).
- `ad_id...190504` — alrededor de finales de julio/agosto 2026 (incluye la venta de Yohana R. De Castro, Q185).
- `ad_id...640504` — la "Reel Catálogo" ya documentada (14 ago–12 sep 2026).

Esto no estaba visible en el resumen de "Anuncios" de Business Suite porque ese resumen solo mostraba los últimos 60 días. **Pendiente:** documentar estas campañas anteriores igual que la de agosto, si todavía hay datos de gasto disponibles en el Administrador de anuncios.

## Tasa de conversión real: mejor de lo que parecía en la primera muestra

La primera revisión (8 conversaciones de un solo fin de semana) encontró solo una venta. Con la cobertura casi completa aparecen **8 ventas confirmadas con flujo completo** (dirección/recolección → pago → entrega → confirmación), más 4 relaciones de cliente recurrente con ventas previas fuera del rango de la pauta:

| Cliente | Producto | Monto | Pago | Fecha |
|---|---|---|---|---|
| Heidy Caballeros de Solares | Set decoración plateada | Q630 | Transferencia | 7–8 sep 2026 |
| Beatriz Hdc (Castillo) | — | Q230 | Transferencia | 8 sep 2026 |
| LRS81 (Leslie Rodríguez) | Servilletero + envío | Q165 | Transferencia | 20–21 sep 2026 |
| Jaquelinne Argueta | — | — | Transferencia | 1–2 sep 2026 (envío a Retalhuleu) |
| Kathya Mariané | 2 sets de jarrones + envío | Q500 | Efectivo al recoger en agencia Forza | 31 ago–3 sep 2026 |
| Ivonne Meneses (Gladys Ivonne Meneses) | — | — | Transferencia | 28–29 ago 2026 |
| Yohana R. De Castro | — | Q185 | Transferencia | 28–31 ago 2026 (campaña de mayo-julio) |
| Cinthya Escobar | — | — | Transferencia, entregado por mensajero propio | 18–22 may 2026 (campaña de mayo-julio) |

**Caso nuevo — Cinthya Escobar:** tuvo la misma fricción que Monik Gabriela (pidió reprogramar el envío a mitad del proceso), pero a diferencia de ella, el negocio sí recuperó la venta y la cerró con confirmación de entrega. Es la prueba de que la fricción de reprogramación no es necesariamente fatal si se le da seguimiento.

**Corrección sobre la primera versión de este diagnóstico:** Monik Gabriela se había contado como venta confirmada; al releer el hilo completo, **no lo fue**. Pidió una bandeja de brazo de quesos, el pedido llegó a salir a ruta más de una vez, pero ella fue reprogramando la entrega por falta de efectivo ("Es que el día de hoy no tengo para pagarlo en efectivo") y terminó cerrando con "mejor dejémoslo para la otra semana fijo" (11 sep) sin retomarlo. Nunca se confirmó precio ni pago. Se mueve a la sección de fricción por falta de cierre firme, no es un caso de inventario agotado.

A esto se suma **Gabrielly**, clienta recurrente con una compra confirmada en octubre 2025 y contacto repetido en abril y septiembre 2026; **Grace López** y **Noe💕**, contactos repetidos desde febrero 2024 y julio 2025 respectivamente (sin compra confirmada en esos casos, pero sí interés repetido a lo largo de casi 2 años); e **Ivannita**, que contactó por dos campañas distintas sin comprar ninguna de las dos veces.

**Lectura:** de las conversaciones genuinas (excluyendo contactos vacíos o accidentales, ver abajo), la conversión real ronda **1 de cada 8 a 9 conversaciones** sobre el universo casi completo — se mantiene en el mismo orden de magnitud que con la primera muestra ampliada, lo que da más confianza al número. El negocio sí sabe cerrar cuando el prospecto llega hasta el final, pero también pierde pedidos ya encaminados por falta de un segundo o tercer intento de cobro (ver casos Monik y, en contraste, Cinthya Escobar que sí se recuperó).

Detalle de direcciones, teléfonos y ticket promedio en [`clientes-2026-10-04.md`](clientes-2026-10-04.md).

## El guion de cierre ya existe, solo no está escrito

Con 8 ventas confirmadas, el patrón es consistente en todas:

1. Preguntar producto de interés concreto (si no se dio ya).
2. Dar precio y medida exactos.
3. Pedir dirección completa.
4. Ofrecer método de pago: **transferencia** (cuenta a nombre de Paola Alay) o **pago contra entrega**; para fuera de la capital, también recoger en **agencia Forza** y pagar ahí.
5. Confirmar el total (incluye envío cuando aplica).
6. Pedir la boleta si fue transferencia.
7. Avisar cuando el pedido sale a ruta.
8. Dar seguimiento el mismo día o al día siguiente para confirmar que llegó bien.

Esto ya está en [pendientes.md](../pendientes.md) como tarea de documentarlo como respuesta estándar.

## Lo que sigue matando conversaciones

**Pregunta genérica → link al catálogo → silencio.** Sigue siendo el patrón más común (40+ casos vistos en la cobertura casi completa, en las tres campañas). "¿Cuáles son las últimas tendencias?", "¿catálogo disponible?", "¿dónde puedo ver más?" terminan casi siempre en el link a `sweethome.com.gt/catalog` y ahí se corta.

**Faltante de inventario sin lista de espera.** Es la segunda causa de pérdida más común, y con la cobertura ampliada aparece en al menos 9 conversaciones distintas: bandejas giratorias doradas, calabazas grandes naranjas, accesorios de hierro forjado color dorado, un estilo de alfombra/tapete específico, colores específicos de reloj de arena, entre otros. La respuesta casi siempre es "esperamos pronto ingreso" sin comprometerse a avisar proactivamente — salvo dos excepciones puntuales (Stu San y Alexandra RO) donde el negocio sí ofreció avisar cuando hubiera reingreso. Ninguna de estas conversaciones tiene seguimiento real cuando el producto vuelve a estar disponible.

**"¿Dónde están ubicados?" / "¿tienen tienda física?" sigue sin resolverse del todo.** Apareció en al menos 6 conversaciones distintas a lo largo de los meses (Carol Vasquez, Anabella Ho, Chiqui Chacón, Maria Vera, Maureen Cruz Chang, entre otras), siempre con la misma respuesta ("de momento únicamente en línea"). **Dato nuevo:** en junio de 2025 el negocio sí tuvo presencia física temporal — un stand en "Top Market, Oakland Place" con horario de fin de semana — así que la respuesta actual no es del todo precisa; podría ofrecerse como alternativa ("no tenemos tienda fija, pero participamos en ferias") en vez de una negación seca.

**El tiempo de respuesta varía de minutos a más de 24 horas**, y en al menos un caso (Sharon Madrid, 30 ago) **el negocio nunca respondió**. No es la mayoría de los casos, pero existe.

**Contactos vacíos o accidentales.** Una parte de los "103 clientes potenciales" no son conversaciones reales: algunos son solo "le gustó/comentó el anuncio" sin ningún mensaje (Dulcemaria, Cris_bdonis, Lupita), y otros son contactos accidentales reconocidos por el mismo prospecto ("fue dedazo", "apachó sin querer"). Esto infla el conteo de 103 — el número de conversaciones *genuinas* es menor.

**El cierre explícito ("¿gusta que le tome el pedido?") se pregunta más seguido de lo que parecía, pero casi nunca convierte solo.** Se encontraron 4 casos (Larrg Jesi, Liki Estrada, Gaby HV, Kelly) donde el negocio preguntó directamente algo como "¿Gusta que tome su pedido?" o "¿lo agrego a la ruta de hoy?" después de dar precio y costo de envío — y en los 4 el prospecto no volvió a escribir. Es buena práctica, pero sin un seguimiento posterior no cierra por sí sola.

**Pedidos que ya iban en camino y se cayeron por falta de un tercer intento concreto.** Caso Monik Gabriela: el pedido salió a ruta, ella no tenía efectivo ese día (era contra entrega), el negocio sí ofreció transferencia como alternativa y ella aceptó reprogramar para el viernes siguiente — pero ese viernes tampoco se concretó ("perdone que hasta ahorita le conteste, mejor dejémoslo para la otra semana fijo") y nadie volvió a proponer una fecha fija. Se perdió por falta de seguimiento con fecha concreta en el tercer intento, no por falta de alternativa de pago. **Contraste:** Cinthya Escobar pidió reprogramar en circunstancias similares y sí se recuperó — la diferencia fue que el negocio insistió con una fecha concreta en vez de dejarlo abierto.

## Dato confirmado: costo de envío

Ya se puede responder con precisión (pendiente resuelto parcialmente, falta decidir si se comunica de forma pública):

- **Capital:** Q30, estándar.
- **Departamentos:** Q35–55 aproximado, vía agencia **Forza** (recoger en agencia o entrega a domicilio según el caso).

## Centro de clientes potenciales: sigue sin trackear nada

Ninguna de las 8 ventas confirmadas, ni la relación de años con Gabrielly o Grace López, está marcada como "Convertido" en el pipeline. Todas quedan en "Registrado"/"Intake". Confirma lo ya visto en el [diagnóstico general](../diagnostico-2026-10-04.md).

## Lectura general (actualizada, cobertura casi completa)

- El negocio **sí cierra ventas de forma consistente** cuando el prospecto llega a compartir dirección — el cuello de botella no es la capacidad de vender, es la cantidad de conversaciones que nunca llegan a ese punto.
- Dos causas de pérdida dominan: (1) preguntas genéricas que se resuelven con un link sin personalización ni cierre, y (2) falta de inventario en estilos/colores específicos sin mecanismo de lista de espera (ahora con 9 casos documentados, no 2-3).
- La objeción de "tienda física" es recurrente a lo largo de año y medio; la respuesta actual ("únicamente en línea") no es del todo exacta, porque sí hubo al menos una feria/stand físico documentado (jun 2025, Top Market Oakland Place).
- Hubo más pauta de la que se había documentado (al menos 3 campañas en 2026, no 1).
- La tasa de conversión (≈1 de cada 8-9) se mantuvo estable al pasar de una muestra de 65 a la cobertura casi completa de 103 — da confianza de que el número no era un artefacto de la muestra chica.
- Reprogramar un envío no es necesariamente una venta perdida: de dos casos con el mismo patrón de fricción, uno se perdió (Monik) y otro se recuperó (Cinthya Escobar) — la diferencia fue el seguimiento con fecha concreta.

Ver tareas abiertas y nuevas en [`pendientes.md`](../pendientes.md).
