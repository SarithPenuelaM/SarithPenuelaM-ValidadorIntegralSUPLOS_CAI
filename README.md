# SarithPenuelaM-ValidadorIntegralSUPLOS_CAI
VALIDADOR INTEGRAL SUPLOS–CAI v1.7
=================================
1. Abre index.html en un navegador moderno. Para consumir APIs, recomendamos un servidor local: python -m http.server 8080 y abrir http://localhost:8080.
2. Selecciona la integración (17 disponibles) y JSON manual o Ejecutar API.
3. Carga un archivo .json, pega el JSON o carga el ejemplo original.
4. Valida y revisa los hallazgos. Exporta evidencia en JSON o CSV.
5. Para APIs, indica método, URL, credenciales temporales y headers; la ejecución es desde el navegador y depende de CORS, VPN y permisos del servicio.

LÍMITES Y PRECAUCIONES
- Basado en data.js del portal original v1.8; no modifica las fuentes.
- Valida tipos, obligatoriedad, longitudes, decimales, fechas de formato básico, estructuras contrastables, campos adicionales no documentados como ERRORES y opciones separadas por ; o | como advertencias.
- NO certifica reglas de negocio complejas, consistencia con bases de datos, homologaciones ni semántica externa sin especificaciones ejecutables.
- Los ejemplos JSON originales que son inválidos siguen siendo inválidos: se advierten, no se corrigen.
- Una misma clave en rutas distintas puede requerir revisión manual de contexto.
- Configuración HTTP y credenciales no se guardan en historial ni evidencia; no usar tokens reales en entornos no confiables.
- No hay proxy para eludir CORS ni autenticación de servidor.
- Los ejemplos y campos documentales pueden ser inconsistentes: revisar los hallazgos antes de reportar defectos.

VERSIÓN 1.1: informe de conformidad, hallazgos separados por severidad, esperado/recibido y acciones sugeridas. Los campos opcionales ausentes ya no generan alertas.

VERSIÓN 1.2 - RESULTADOS EN TABLA DE CASUÍSTICAS
- Cada hallazgo se visualiza en una fila de tabla con estado, campo, casuística, causa, esperado, recibido y acción.
- Filtrado de errores, advertencias e inconsistencias documentales.
- Exportación CSV con la misma estructura del reporte.
- No se cambiaron las reglas originales de validación ni la ejecución de APIs.

CAMBIO V1.3: Los campos recibidos que no existen en el mapeo original de la integración y dirección seleccionadas son ERRORES bloqueantes. Se eliminó la opción de ignorarlos o degradarlos a advertencia.


VERSIÓN 1.4: Comparador visual en dos columnas de JSON documental y probado con resaltado rojo para errores identificados por el validador, amarillo para advertencias y verde para campos revisados sin error. No compara igualdad literal de valores entre el ejemplo y el mensaje real. Botón para ver únicamente diferencias. Campos adicionales fuera del mapeo siempre son ERROR sin opción de ignorar.


VERSIÓN 1.5 - TIPOS Y CONTENIDO
- NOT NULL: null, cadena vacía y espacios son ERROR; campo ausente también ERROR.
- Validación ampliada para String, Number, Long/Entero, Date, DateTime, Boolean, Object y Array cuando el contrato defina esos tipos.
- Comprobación de fechas reales, longitudes, precisión decimal, Base64 y catálogos explícitos de códigos del mapeo.
- Catálogos sólo inferidos desde listas inequívocas; textos de ejemplo no se convierten en valores obligatorios.
- Valor distinto al ejemplo JSON NO significa error si cumple el contrato.
- No se infieren patrones, catálogos ni reglas intercampo no documentadas.
- Pendientes documentales y rutas ambiguas requieren confirmación funcional.

Versión 1.6: el comparador visual de JSON aparece antes de la tabla de casuísticas. Sin modificaciones de las reglas de validación.

VERSIÓN 1.7 - PUBLICACIÓN GITHUB PAGES
- Todos los archivos están en la raíz del ZIP, sin carpeta contenedora ni assets.
- Subir el contenido directamente a la raíz del repositorio (o a /docs si GitHub Pages se publica desde /docs).
- La página principal es index.html; las rutas de CSS, JS y logo son relativas a su misma carpeta.
