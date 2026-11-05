# Pasión Lencería

Tienda estática de presentación, desplegada en https://pasion-lenceria.vercel.app.

## Navegación

Inicio, Lencería, Pijamas, Bikinis, Regalos y Sex Shop son destinos del menú. Las cuatro secciones de producto tienen portada editorial, familias propias, asesoramiento y una selección local con búsqueda, orden, disponibilidad y carga de más productos. El catálogo completo sigue separado para la búsqueda avanzada. Las rutas existentes se mantienen.

## Funcionalidad

- Catálogo local de 314 productos, con categorías, subcategorías, búsqueda, precio, talle, disponibilidad, orden y paginación.
- Fichas con variantes, precio por variante, galería y productos relacionados.
- Carrito y favoritos persistidos en el navegador; diseño claro original.
- Pedido con envío o retiro, resumen y mensaje preparado para WhatsApp. No procesa cobros ni confirma pedidos automáticamente.
- Páginas locales de regalos, contacto, envíos, cambios, privacidad y guías.

## Datos y despliegue

`data/catalog.json` es una copia del catálogo público de Pasión del 5 de noviembre de 2026. No es una sincronización de inventario. Stock, pago y entrega se confirman con la tienda por WhatsApp. Las fotos principales y las fuentes se sirven localmente; algunas fotos adicionales de las fichas se cargan desde el CDN de la tienda.

No requiere compilación ni dependencias de ejecución. Vercel sirve los archivos estáticos y las rutas de `vercel.json` reutilizan `shop.html`. `app.js` renderiza cada sección. La portada conserva el rediseño inicial en `index.html`.

La web lleva `noindex` porque es una propuesta para presentar a la dueña. Las condiciones de entrega y cambios se basan en las páginas públicas de la tienda; la guía de talles remite a las medidas de cada modelo y al asesoramiento, sin inventar una tabla universal.

## Verificación

Se probó con Chromium a 390, 768, 1280 y 1440 px: búsqueda, filtros, orden, variantes, carrito persistente, favoritos, formulario de entrega y generación del mensaje de WhatsApp (interceptado, sin enviar). Se revisaron las páginas de ayuda y los estados vacíos. Las páginas revisadas no presentaron errores de JavaScript ni desbordes horizontales.

Se verificó además el recorrido desde el menú hacia los cuatro departamentos, sus filtros de estilos, la vuelta a Inicio, la selección de un producto y el carrito. Se corrigieron cinco artículos íntimos que estaban mezclados en Lencería.

Se ejecutó axe para WCAG A/AA en las pantallas principales y en ambos temas. El catálogo también se revisó con Lighthouse.
