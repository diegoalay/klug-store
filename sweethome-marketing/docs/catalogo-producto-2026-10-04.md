# Cómo se almacena el catálogo hoy — 2026-10-04

Repaso del repo `klugstore` (confirmado por el usuario: es el sitio de SweetHome) para responder la pregunta de cómo mejorar el almacenamiento de productos, dado que el equipo reporta que "les cuesta" mantenerlo.

## Qué hay hoy

`klugstore` es un catálogo digital whitelabel (Vue 3 + Quasar), y **SweetHome es literalmente la primera tienda en producción** del proyecto (`docs/architecture.md` del repo lo dice explícito). No hay base de datos propia: la fuente activa del catálogo es un **Google Sheet público** con 2 pestañas (`products`, `categories`) que el sitio lee en vivo vía el endpoint `gviz/tq`, con un JSON empaquetado como respaldo. No es técnicamente "Excel", pero funciona igual de manual — por eso seguramente se describe así de palabra.

Hay un panel `/admin/catalogo` pero es un MVP: edita en memoria del navegador y **no persiste** — solo sirve para exportar CSV que después alguien pega a mano en el Sheet.

## Por qué cuesta, específicamente

No es una impresión vaga — la guía del editor (`docs/editor-guide.md`) documenta el proceso real y deja ver los puntos de fricción concretos:

1. **Subir fotos no es autoservicio.** Las imágenes se suben a un bucket S3 aparte, y la guía dice textualmente: *"pídele a tu programador que te dé acceso o que las suba por ti"*. Cualquier producto nuevo depende de un programador para la parte visual, que es la más frecuente (cada publicación nueva es, en la práctica, producto nuevo).
2. **Formato rígido y sin validación.** Nombres de pestaña exactos, orden de columnas exacto, slugs de categoría que deben coincidir letra por letra entre dos pestañas distintas, sin acentos ni espacios. Un error no avisa — el producto simplemente no aparece, y hay que adivinar cuál de 3 posibles errores fue.
3. **Delay de 1-5 minutos + cache de navegador**, así que no hay confirmación inmediata de que el cambio quedó bien.
4. **No hay campo de inventario/stock**, solo `visible` (TRUE/FALSE). Esto conecta directo con lo que ya se vio en las conversaciones reales: la falta de inventario sin lista de espera fue la segunda causa de ventas perdidas más común ([diagnóstico de conversaciones](mensajes/diagnostico-2026-10-04.md)), y el catálogo no tiene ningún lugar donde reflejar "quedan 2" o "agotado, vuelve el 15".

## Opciones (sin decidir todavía)

**A. Arreglar solo el cuello de botella real: subir fotos.** Mantener el Google Sheet como está, pero dar acceso de autoservicio para imágenes (un formulario simple que suba a S3 y devuelva la URL para pegar en el Sheet, o aceptar una carpeta de Google Drive/Fotos como fuente). Es el cambio más barato y resuelve la dependencia del programador para lo que más se repite. No resuelve inventario ni el formato rígido.

**B. Admin real que escriba al Sheet (o a una base propia chica) en vez de exportar CSV.** Terminar el panel `/admin/catalogo` para que persista de verdad — subida de fotos incluida, con validación de slugs/categoría en el formulario en vez de en una hoja de cálculo. Resuelve autoservicio completo y formato, se puede agregar un campo de stock ahí mismo. Esfuerzo medio, no requiere backend nuevo (puede seguir escribiendo al mismo Sheet vía API, o migrar a SQLite/Firestore propio del repo).

**C. Terminar la migración a `klugstore-v2`,** que ya existe como repo aparte y está diseñado exactamente para esto: backend real en `klugsystem` (multi-tenant, `sweethome` es el tenant de ejemplo en su propia documentación), con endpoints reales de productos/categorías/stock en vez de un Sheet. Es la solución "correcta" a largo plazo y además sirve para más tiendas si `klugstore` se vuelve un producto para varios clientes, no solo SweetHome — pero **el backend (`Store::` / endpoints `/api/v1/stores/:code/products` en klugsystem) todavía no existe**, así que es la opción de más esfuerzo.

## Mi recomendación

Si la urgencia es solo "que el equipo de SweetHome pueda subir productos sin depender de un programador", la opción **A es la más rápida de rentabilizar** (días, no semanas) y resuelve el dolor que describiste. La opción C es la correcta si `klugstore` va a ser un producto para más tiendas además de SweetHome — en ese caso vale la pena invertir ahí en vez de parchar el Sheet dos veces. No es una decisión que deba tomar yo: depende de si `klugstore` es solo para SweetHome o un producto más amplio, y de cuánto tiempo de desarrollo hay disponible ahora.

Ver tarea relacionada en [`pendientes.md`](pendientes.md).

## Decisión (2026-10-04): seguir con `klugstore`, reemplazar el Sheet por Firestore + Storage

El usuario decidió no migrar a `klugstore-v2`/`klugsystem` por ahora — seguir con `klugstore` y resolver el dolor real (fotos sin autoservicio, sin stock) conectándolo a **Firebase Firestore + Storage**, reutilizando el proyecto `sweet-home-gt` que ya existe (Hosting + Analytics ya están ahí; el SDK de `firebase` ya es dependencia del repo).

**Confirmado:**
- Modo Firestore: **Native** (Datastore mode no es compatible con el SDK que usa el proyecto).
- Región: pendiente de crear la base — preferencia `us-south1` (Dallas, la más cercana a Guatemala), con `us-central1` como respaldo si no está disponible. No hay precedente de otros proyectos Firebase del portafolio (ninguno tiene Firestore habilitado todavía). **No se puede cambiar después de crear la base.**
- WhatsApp del botón "Comprar": corregido en `.env` a +502 3974-2544 (estaba apuntando al número viejo +502 5870-5804).
- Requisito de producto nuevo: cada producto debe soportar **múltiples imágenes con orden elegible y una marcada como portada/por defecto** (hoy es un campo de texto con URLs separadas por coma, sin orden explícito ni default).

**Bloqueado temporalmente:** Google Cloud exige verificación en 2 pasos (MFA) en la cuenta `diego.alay.dev@gmail.com` desde mayo 2025 para poder habilitar APIs nuevas (Firestore, Storage) — hay que activarla antes de poder seguir. Ver [`pendientes.md`](pendientes.md).
