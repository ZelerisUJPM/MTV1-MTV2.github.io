                                          Manual de Usuario – MTV 1/MTV 2

1. Introducción

El sistema MTV 1/MTV 2 es una aplicación web diseñada para la gestión de incidencias y seguimiento de servicios. Permite a los usuarios seleccionar productos o servicios, consultar y editar descripciones predefinidas, alternar entre modo claro y modo oscuro, enviar comentarios y registrar estadísticas de copias de texto. Este manual brinda instrucciones detalladas para el uso óptimo de la aplicación.

2. Requisitos del Sistema
-Navegador Web Moderno: Se recomienda utilizar la última versión de navegadores como Google Chrome, Firefox, Edge o Safari.
-JavaScript Habilitado: La aplicación requiere que JavaScript esté activado para el correcto funcionamiento de las funcionalidades interactivas.
-Conexión a Internet: Necesaria para cargar recursos externos (hojas de estilo, fuentes y librerías como EmailJS).

3. Acceso a la Aplicación

3.1. Pantalla de Inicio de Sesión

Al cargar la aplicación se mostrará la pantalla de inicio de sesión.

Campos Requeridos:
Nombre de usuario
Contraseña

-Acceso Rápido:

El sistema contiene credenciales predefinidas (por ejemplo, usuario: 0 y contraseña: 0) para pruebas, aunque también es posible iniciar sesión con usuarios registrados en el sistema.

-Interacción:

Introduce tus credenciales y haz clic en “Iniciar Sesión”.
En caso de error, aparecerá un mensaje indicando que los datos son incorrectos.

3.2. Registro de Usuario

Si aún no cuentas con una cuenta, puedes registrarte:

-Proceso de Registro:

Haz clic en el enlace “¿No tienes cuenta? Regístrate” en la pantalla de inicio.
Completa los campos: Nombre de usuario, Contraseña y Confirmar contraseña.
Presiona el botón “Registrarse”.
Si el registro es exitoso, se mostrará un mensaje informativo y se redirigirá al formulario de inicio de sesión.

4. Funcionalidades Principales

4.1. Panel de Control y Navegación

Una vez iniciada la sesión, se mostrará el panel principal que incluye:

Barra de Botones:
En la parte superior se encuentran botones con diferentes productos/servicios:
DESCO 4K
IMATV
IMATV-VD
IMATV-VDT
AFR
MTV 2
ASOS
HGUW6-P

Cada botón está asociado a un conjunto de incidencias o estados.

4.2. Selección de Productos/Servicios

Cambio de Lista:

Al pulsar un botón (por ejemplo, “DESCO 4K”), se ejecuta la función changeList(opcionX), que Carga en un desplegable (select) la lista de incidencias asociadas al producto seleccionado. Actualiza la imagen correspondiente en el contenedor de imágenes. Guarda la opción seleccionada en el navegador para restaurarla en visitas futuras.

4.3. Visualización y Edición de Descripciones

Desplegable de Incidencias:

Una vez cargada la lista, selecciona una incidencia del menú desplegable.

Campo de Descripción:

Al seleccionar una incidencia, se carga automáticamente una descripción predefinida en un área de texto. Puedes editar la descripción manualmente si es necesario. Existe un botón para limpiar la descripción y restaurar el valor predefinido.

4.4. Modo Oscuro

Activación del Modo Oscuro:
En la esquina superior izquierda se encuentra un botón con el ícono “Modo Oscuro”.
Al pulsarlo, la aplicación alterna entre el modo claro y el modo oscuro.
La configuración se guarda en el navegador para que la próxima vez que inicies sesión se mantenga la preferencia.

5. Funcionalidades Adicionales

5.1. Seguimiento de Estadísticas de Copia

La aplicación monitorea las veces que se copia el contenido del área de descripción:

Registro Automático:
Cada vez que el usuario copia texto, se incrementan contadores por:
Producto/Servicio (botón seleccionado).
Incidencia (opción del desplegable).
Guardado de Estadísticas: Al cerrar sesión, se genera un archivo de texto que contiene un resumen de las estadísticas de copias realizadas durante la sesión.

5.2. Envío de Comentarios y Sugerencias
Botón de Feedback: En la esquina inferior derecha se encuentra el botón “Comentarios/Sugerencias”.

Formulario de Comentarios:

Al hacer clic, se despliega un formulario donde deberás:
Ingresar tu nombre.
Indicar el “Nombre Completo Walkie”.
Escribir tu comentario o sugerencia.
Envío del Formulario:
Al pulsar “Enviar”, el sistema utiliza EmailJS para enviar tu mensaje.

6. Cierre de Sesión y Guardado de Estadísticas
Cerrar Sesión:
Haz clic en el botón de “Cerrar Sesión” (ícono de logout ubicado en la esquina superior derecha).

Proceso de Cierre:

Se oculta el panel principal y se muestra nuevamente la pantalla de inicio de sesión.
Se ejecuta una función que guarda las estadísticas de copias en un archivo de texto descargable automáticamente.

7. Configuración y Personalización

Restauración de Preferencias:
La aplicación utiliza el almacenamiento local (localStorage) para recordar:
La última opción de producto seleccionada.
El último texto de descripción introducido.
El modo (oscuro o claro) preferido.
Ordenación de Listas:
Las incidencias de cada producto se ordenan alfabéticamente para facilitar su búsqueda.
8. Soporte Técnico y Contacto
Para cualquier duda o incidencia en el uso de la aplicación, puedes contactar al administrador o equipo de soporte. Consulta al responsable del sistema o al Ing. Javier Mastrangelo (según lo indicado en el pie de página) para mayor asistencia.Manual de Usuario – MTV 1/MTV 2
