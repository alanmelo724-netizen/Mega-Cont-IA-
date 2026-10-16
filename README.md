MegaCont IA
MegaCont IA es un proyecto de software contable y administrativo asistido por inteligencia artificial, orientado inicialmente a Colombia y diseñado para evolucionar hacia una plataforma internacional, multidioma y configurable por país.
Estado del proyecto: este README describe los objetivos y requisitos que deben implementarse y verificarse en el código. No significa que todas las funciones estén terminadas, que la integración con la DIAN esté certificada ni que la aplicación esté lista para producción.
Objetivo principal
Consolidar en una sola aplicación las funciones contables, administrativas y de apoyo con IA, manteniendo la integridad de los datos, trazabilidad de las operaciones, controles de acceso, capacidad de respaldo y una experiencia de uso clara tanto en móvil como en escritorio.
Instrucción principal para quien desarrolle el proyecto
Revisa el repositorio completo de GitHub y el ZIP definitivo de MegaCont IA, si está disponible en los archivos del proyecto. Compara el código existente con todos los archivos, pantallas, componentes, módulos y funcionalidades del ZIP. No te limites a cambiar el diseño ni a crear pantallas de demostración. Identifica las funciones ausentes, incompletas, desconectadas o que solo usan datos ficticios, y completa su implementación en el proyecto actual.
Antes de modificar:
Inspecciona la estructura del repositorio, dependencias, rutas, componentes, esquema de base de datos y configuración existente.
Conserva y mejora lo que ya funciona; evita duplicar módulos o sobrescribir trabajo válido.
Elabora una lista de diferencias entre el repositorio y el ZIP definitivo.
Implementa las diferencias por módulos, conectando interfaz, validaciones, persistencia y permisos.
Ejecuta pruebas y corrige errores de compilación, navegación, formularios, persistencia y visualización móvil.
Documenta qué quedó implementado, qué pruebas pasaron y qué requisitos siguen pendientes. No declares una función terminada si no funciona de extremo a extremo.
Si el ZIP no está adjunto ni disponible en el repositorio, indícalo expresamente y trabaja con los requisitos de este README sin afirmar que comparaste archivos que no pudiste inspeccionar.
Módulos funcionales requeridos
Implementa y conecta, según corresponda al proyecto y a los archivos de referencia:
Panel principal: resumen de actividad, indicadores contables, alertas y accesos a las tareas frecuentes.
Empresas y configuración: datos de la organización, periodo contable, país, moneda, idioma, zona horaria y preferencias.
Usuarios y permisos: autenticación segura, perfiles y permisos por rol; aislamiento de los datos de cada empresa o usuario según el modelo de acceso.
Plan de cuentas y catálogos contables: consulta, creación, edición, importación y exportación de cuentas, subcuentas, auxiliares y subauxiliares, con validación de códigos y jerarquías.
Transacciones y comprobantes: registro, edición controlada, consulta, clasificación y trazabilidad de operaciones.
Asientos contables: débitos y créditos, validación de partida doble, balance del comprobante, periodo contable y referencias a los documentos de origen.
Facturación y documentos: gestión de documentos emitidos y recibidos, estados, consecutivos y datos requeridos por la normativa del país seleccionado.
Inventario: productos, movimientos, existencias y valoración, con integración contable cuando corresponda.
Nómina: estructura para empleados, novedades, liquidaciones y reportes, respetando la normativa aplicable al país y el acceso restringido a datos sensibles.
Informes y reportes: libro diario, mayor, balance de prueba, estado de resultados, balance general y otros reportes disponibles en el proyecto; filtros por empresa, periodo, cuenta y demás dimensiones pertinentes.
Importación y exportación: plantillas, carga desde Excel/CSV cuando esté implementada, validación previa, resumen de errores y exportación de datos permitidos.
Auditoría y trazabilidad: registro de acciones relevantes, usuario, fecha, entidad afectada y resultado, evitando guardar secretos o información innecesaria.
Ayuda y aprendizaje: tutoriales escritos y audiovisuales, instrucciones dentro de cada módulo, preguntas frecuentes y mensajes claros de error y éxito.
Copias de seguridad: creación y descarga de respaldos en formatos apropiados, indicación de fecha y contenido, y procedimiento documentado de restauración. No exponer respaldos a usuarios no autorizados.
Inteligencia artificial contable
La IA debe apoyar al usuario sin sustituir los controles contables ni ejecutar acciones críticas de forma silenciosa.
Permitir sugerencias de clasificación, cuentas contables, asientos, detección de inconsistencias y explicación de reportes, según las capacidades reales integradas.
Mostrar la información utilizada para la sugerencia, las cuentas propuestas, los importes y una explicación comprensible.
Solicitar aprobación humana antes de contabilizar, emitir documentos, modificar información sensible o realizar operaciones irreversibles.
Diferenciar claramente entre una sugerencia de IA y una operación efectivamente guardada o contabilizada.
Guardar trazabilidad de las sugerencias y aprobaciones cuando corresponda.
Manejar errores y falta de certeza sin inventar cifras, normas ni resultados.
No enviar datos financieros o personales a proveedores externos sin una integración autorizada, controles de seguridad y aviso apropiado.
Plan Único de Cuentas y catálogos de Colombia
El sistema debe permitir administrar el plan de cuentas y los catálogos contables aplicables a la organización, con especial atención a Colombia.
Preparar la estructura para los tres planes/catálogos oficiales referenciados por el proyecto, incluido el correspondiente a educación superior, solo después de verificar sus fuentes, vigencia y aplicabilidad.
No mezclar planes de cuentas de sectores distintos ni asignar automáticamente uno sin confirmar el tipo de entidad.
Permitir alta y edición manual de cuentas, subcuentas, auxiliares y subauxiliares, con código, nombre, nivel, cuenta padre, naturaleza, estado y demás campos que requiera el esquema.
Ofrecer importación desde Excel/CSV con vista previa, validación de duplicados, códigos, niveles, jerarquías y campos obligatorios.
Informar errores por fila y permitir descargar el reporte de validación; no guardar parcialmente una importación inválida sin avisar.
Validar JSON de catálogos antes de importarlo: estructura, tipos, campos requeridos, códigos únicos y relaciones padre-hijo.
Conservar la fuente, versión, fecha de actualización y entidad/sector al que aplica cada catálogo.
No presentar un catálogo como “oficial 2026” hasta contrastarlo con documentos oficiales vigentes y documentar su procedencia.
Internacionalización (i18n) y localización (l10n)
La internacionalización debe diseñarse desde la base, no limitarse a traducir algunos botones. La aplicación debe poder cambiar de idioma sin perder datos ni alterar los cálculos contables.
Idiomas
Implementar un selector de idioma visible en la configuración del usuario y, si procede, en el acceso inicial.
Incluir español como idioma inicial y preparar la arquitectura para añadir inglés y otros idiomas sin reescribir los módulos.
Centralizar todas las cadenas de interfaz en archivos de traducción por idioma; evitar textos de interfaz escritos directamente dentro de componentes.
Traducir menús, botones, formularios, validaciones, estados, notificaciones, tablas, filtros, informes, pantallas vacías, errores, tutoriales y ayudas.
Mantener traducciones completas y consistentes; si falta una traducción, aplicar una regla de respaldo definida sin dejar claves técnicas visibles al usuario.
Respetar pluralización, variables interpoladas, fechas, números y accesibilidad en cada idioma.
Guardar la preferencia del idioma del usuario y recuperarla en futuras sesiones; definir un idioma predeterminado para cada empresa cuando sea necesario.
Permitir cambiar de idioma en cualquier momento, sin cerrar la sesión ni perder formularios o datos guardados.
Formatos regionales y separación de conceptos
Separar idioma, país/región, moneda, zona horaria y configuración fiscal: no deben tratarse como una sola preferencia.
Localizar fechas, horas, separadores decimales y de miles, porcentajes, moneda y mensajes de validación.
Mostrar las monedas con código ISO cuando sea necesario para evitar ambigüedad.
No convertir valores monetarios ni alterar datos contables solo porque cambie el idioma o el formato de visualización.
Guardar fechas, horas y cantidades con tipos y reglas consistentes en la base de datos; convertirlas a formatos regionales solo al presentarlas.
Preparar configuraciones por país para impuestos, documentos, cuentas y reglas contables. No aplicar automáticamente las reglas colombianas a una empresa de otro país.
Verificar la interfaz en móvil y escritorio con textos largos, distintos idiomas y formatos regionales.
Pruebas de internacionalización
Confirmar que el selector cambia toda la interfaz, no solo el menú.
Revisar que no queden cadenas sin traducir, claves internas o textos cortados.
Comprobar que cambiar idioma/región no modifica importes, asientos, fechas almacenadas ni saldos.
Probar pluralización, fechas, moneda, números, formularios, errores y reportes en cada idioma habilitado.
Integración con Supabase y persistencia
El proyecto utiliza Supabase como backend, con una instancia que debe configurarse mediante variables de entorno. La URL de proyecto conocida durante la configuración es https://qduvrwgboaacqikbciki.supabase.co; verifica que siga siendo la correcta antes de desplegar.
Usar variables de entorno para la URL y la clave pública de Supabase; documentar los nombres necesarios en .env.example sin incluir valores secretos.
Nunca incluir claves service_role, contraseñas, tokens privados ni credenciales de producción en el código del cliente o en GitHub.
Crear o actualizar migraciones SQL versionadas para tablas, índices, restricciones y políticas de acceso.
Configurar Row Level Security (RLS) en tablas con datos de usuario/empresa y probar que un usuario no pueda consultar o modificar datos de otra empresa.
Validar los datos tanto en la interfaz como en el backend; no confiar únicamente en controles del navegador.
Conectar todos los formularios a operaciones reales de lectura/escritura. Evitar datos de ejemplo como sustituto silencioso de persistencia.
Gestionar estados de carga, errores, reintentos y confirmación de guardado; evitar dobles envíos.
No asumir que una tabla existente está completa: revisar esquema, permisos y comportamiento real antes de modificarla.
Ejemplo de variables para .env.example (sin credenciales reales):
VITE_SUPABASE_URL=https://TU-PROYECTO.supabase.co
VITE_SUPABASE_ANON_KEY=TU_CLAVE_PUBLICABLE
Ajusta los nombres al framework y al código que realmente utilice el repositorio. Una clave publicable no sustituye las políticas RLS ni la validación de permisos.
DIAN y cumplimiento normativo colombiano
La integración con la DIAN es un requisito de desarrollo futuro o pendiente hasta que el repositorio demuestre lo contrario.
Inspeccionar las funciones existentes y documentar exactamente qué está implementado.
Diseñar la integración con las especificaciones oficiales vigentes para el servicio correspondiente (por ejemplo, facturación electrónica, nómina electrónica u otros documentos, según el alcance aprobado).
Separar ambientes de pruebas y producción; gestionar certificados, credenciales y secretos en servidor seguro.
Validar esquemas, numeración, estados, respuestas, rechazos, reintentos y trazabilidad de cada envío.
Proporcionar una configuración clara para que el usuario pueda completar los requisitos legales y técnicos.
No afirmar que se envían documentos a la DIAN, que existe habilitación o que el sistema cumple legalmente hasta verificarlo mediante pruebas y evidencias oficiales.
Seguridad, privacidad y confiabilidad
Aplicar autenticación, autorización por roles y mínimo privilegio.
Proteger datos contables, tributarios, laborales y personales.
Validar entradas y evitar exposición de información en logs o mensajes de error.
No eliminar ni sobrescribir información contable sin confirmación y reglas de auditoría adecuadas.
Utilizar transacciones y restricciones de base de datos para mantener la integridad de asientos y operaciones relacionadas.
Proteger exportaciones, importaciones y copias de seguridad mediante permisos.
No introducir secretos, datos reales de clientes ni copias de bases de datos en el repositorio.
Experiencia de usuario y accesibilidad
Interfaz clara, consistente y adaptable a móviles, tabletas y escritorio.
Menús y rutas funcionales, formularios con etiquetas, validaciones comprensibles y mensajes en el idioma elegido.
Estados de carga, guardado, error, éxito y ausencia de resultados.
Navegación por teclado, contraste legible y etiquetas accesibles donde corresponda.
Evitar botones decorativos o pantallas que aparenten ejecutar acciones sin hacerlo.
Criterios de aceptación
Una función se considera terminada cuando:
La pantalla está conectada al flujo de navegación real.
Los formularios validan los campos obligatorios y muestran errores comprensibles.
Los datos se guardan y recuperan del backend cuando corresponde.
Los permisos se aplican en servidor/base de datos, no solo en la interfaz.
Los casos de éxito, error, carga y datos vacíos están tratados.
La interfaz funciona en móvil y escritorio y respeta el idioma seleccionado.
Hay pruebas o pasos reproducibles para verificar el comportamiento.
La documentación refleja el estado real, incluidas las limitaciones pendientes.
Flujo de trabajo solicitado
Inspeccionar el proyecto existente y el ZIP definitivo disponible.
Crear una lista de brechas por módulo y priorizarlas según dependencias.
Implementar primero los cimientos: configuración, autenticación, permisos, esquema de datos e internacionalización.
Completar cada módulo de punta a punta, evitando datos ficticios y funciones simuladas.
Añadir pruebas de lógica contable, permisos, persistencia, importación/exportación e idiomas.
Ejecutar lint, pruebas y build disponibles en el repositorio; resolver fallos antes de concluir.
Actualizar este README y documentar variables de entorno, migraciones, instalación y despliegue.
Entregar un resumen de cambios, archivos afectados, pruebas realizadas y pendientes reales.
Instalación y ejecución
Los comandos exactos dependen del package.json y del framework del repositorio. Inspecciona primero esos archivos y documenta los comandos correctos. Como guía, muchos proyectos JavaScript utilizan:
npm install
npm run dev
npm run build
No añadas scripts que no existan sin implementarlos y verificarlos. Mantén un .env.example actualizado y excluye .env del control de versiones.
Estado de implementación
Mantén esta sección actualizada con evidencia del código y pruebas:
[ ]
Comparación completa del repositorio con el ZIP definitivo.
[ ]
Inventario de funciones existentes, faltantes y parciales.
[ ]
Supabase configurado con RLS y permisos verificados.
[ ]
Módulos contables conectados a persistencia real.
[ ]
Catálogos/PUC verificados y con importación validada.
[ ]
Internacionalización completa y selector de idioma persistente.
[ ]
Copias de seguridad y exportaciones protegidas.
[ ]
IA con explicación y aprobación humana para acciones críticas.
[ ]
Tutoriales y ayuda contextual.
[ ]
Pruebas automatizadas y build satisfactorio.
[ ]
Integración DIAN verificada, si forma parte del alcance de la entrega.
[ ]
Documentación de despliegue y seguridad actualizada.
Instrucción final
No entregues solo una propuesta, una maqueta visual ni una lista de tareas. Implementa las funciones que falten en el código real, conserva las que funcionen, conecta cada módulo a su persistencia y permisos, prueba los flujos principales y explica con honestidad qué está terminado y qué no. No inventes funcionalidades ya implementadas ni declares cumplimiento normativo, catálogos oficiales o integración DIAN sin evidencia verificable.
