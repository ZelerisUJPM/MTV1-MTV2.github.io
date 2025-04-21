                                          Manual de Usuario – MTV 1/MTV 2
1. Introducción
“Zeleris” es una aplicación web diseñada para facilitar la gestión y visualización de contenidos interactivos. La interfaz está desarrollada en español y combina funcionalidades como inicio de sesión, registro de usuarios, secciones dinámicas (MTV 1, MTV 2 y CAC), registro de estadísticas y un modo oscuro personalizable. Además, la aplicación incluye un reloj que muestra la hora en España en tiempo real.

2. Requisitos del Sistema
Navegador Web Moderno: Se recomienda utilizar navegadores actualizados como Google Chrome, Mozilla Firefox, Microsoft Edge u otros compatibles con HTML5, CSS3 y JavaScript.

Conexión a Internet: Para cargar fuentes de Google, imágenes y asegurar el funcionamiento de algunos elementos dinámicos.

Soporte para IndexedDB: La aplicación utiliza IndexedDB para gestionar sesiones, usuarios y estadísticas, por lo que el navegador debe soportar esta tecnología.

3. Acceso y Configuración Inicial
3.1. Pantalla Principal
Al acceder a la aplicación, verás:

Logo de la Empresa: Posicionado en la parte superior.

Botón de Modo Oscuro: Ubicado en la esquina superior izquierda, que te permitirá alternar entre el tema claro y el tema oscuro.

Visualización de la Hora en España: Un reloj que actualiza la hora en tiempo real en formato “Hora en España: …”.

3.2. Navegación Principal
En la pantalla principal se muestran tres botones:

MTV 1

MTV 2

CAC

Estos botones sirven para acceder a diferentes secciones de la aplicación y a contenidos específicos para cada área.

4. Funcionalidades de la Aplicación
4.1. Inicio de Sesión y Registro
Inicio de Sesión:

Al hacer clic en cualquiera de los botones principales (por ejemplo, MTV 1, MTV 2 o CAC), la aplicación verifica si tienes una sesión activa.

Si no hay sesión, se mostrará un formulario donde deberás ingresar tu usuario y contraseña.

Una vez autenticado, se redirigirá al contenido seleccionado.

Registro de Usuario:

Si no tienes una cuenta, accede al formulario de registro haciendo clic en el enlace “¿No tienes cuenta? Regístrate”.

Introduce el usuario y la contraseña y confirma el registro.

4.2. Sección MTV 1 y MTV 2
Cada una de estas secciones cuenta con:

Botones Secundarios (Sub-botones):

Al hacer clic en uno de los sub-botones (por ejemplo, “Sub-botón 1.1”, “Sub-botón 1.2”, etc.), se muestra un selector y se carga una descripción y una imagen según la opción seleccionada.

Selector Dinámico:

Un desplegable que muestra una lista ordenada de opciones. Al cambiar la selección, se actualiza la descripción disponible en la sección correspondiente.

4.3. Sección CAC
La sección CAC está diseñada para ofrecer distintas funcionalidades específicas y cuenta con dos tipos de controles:

Selector (Drop-down):

Permite seleccionar entre opciones predefinidas (por ejemplo, “TME Fusion Sap”, “Automantenimiento”, etc.).

Al cambiar la selección, se muestra la imagen asociada a la opción elegida.

Botones Específicos: En la parte superior se encuentran varios botones horizontales que incluyen:

Buzón CAC: Muestra la imagen correspondiente al buzón.

Códigos: Muestra la imagen referida a códigos de gestión.

O2: Muestra la imagen que representa el servicio O2.

Abreviaturas (Nuevo):

Funcionalidad: Al hacer clic en el botón Abreviaturas, se mostrará una imagen (por ejemplo, img/Abreviaturas.png) en el área destinada para ello.

Ubicación: Este botón se encuentra integrado junto a los otros botones en la sección CAC.

Área de Visualización de Imágenes:

Un contenedor centralizado donde se muestran las imágenes generadas al seleccionar cualquiera de los botones o al cambiar el selector.

4.4. Descarga de Estadísticas
Registro de Eventos de Copia:

Cada vez que el usuario copia contenido del área editable (por ejemplo, en las descripciones), la aplicación registra la acción guardando detalles como el sub-botón activo, la opción seleccionada y la hora exacta.

Descarga:

Hay un botón “Descargar Estadísticas” en la pantalla principal. Al hacer clic, se genera un archivo TXT con la información de las acciones registradas.

En caso de no haber estadísticas registradas, se muestra un mensaje indicándolo.

4.5. Modo Oscuro
Activación:

Utiliza el botón de modo oscuro (imagen de un ícono) que se encuentra en la esquina superior izquierda.

Al hacer clic, la clase dark-mode se activa o desactiva en la etiqueta <body>, modificando la paleta de colores de toda la aplicación.

4.6. Hora en Tiempo Real
Visualización:

Un contenedor dedicado muestra la hora actual en España, actualizándose cada segundo mediante la API Intl.DateTimeFormat, que toma en cuenta la zona horaria de Madrid.

5. Flujo de Trabajo y Ejecución
Acceso a la Aplicación:

Se inicia visualizando el logo, el reloj de España y los botones principales (MTV 1, MTV 2 y CAC).

Inicio de Sesión/Registro:

Selecciona una opción principal y, si no tienes sesión activa, ingresa tus credenciales o regístrate.

Navegación y Selección de Contenido:

En MTV 1 o MTV 2, selecciona uno de los sub-botones y utiliza el desplegable para ver diferentes descripciones e imágenes.

En la sección CAC, utiliza el selector o haz clic en alguno de los botones de servicios (Buzón CAC, Códigos, O2 o Abreviaturas) para ver la imagen correspondiente.

Descarga de Estadísticas:

Cuando necesites revisar las estadísticas de las acciones de copia, utiliza el botón “Descargar Estadísticas” que genera un archivo TXT con todos los registros.

Cambio de Modo y Navegación:

Puedes cambiar a modo oscuro en cualquier momento y, para cambiar de Skill (o sección), utiliza los botones “Cambiar de Skill” que restablecen la vista a la pantalla inicial.

6. Consideraciones de Seguridad y Sesión
Gestión de Sesión:

La aplicación utiliza IndexedDB para almacenar y gestionar de forma segura las sesiones de usuario.

Al seleccionar “Cambiar de Skill”, se elimina la sesión activa para permitir el cambio de usuario o de área.

Protección de Datos:

La validación básica de credenciales se realiza comparando el usuario y la contraseña almacenados en IndexedDB.

Se recomienda utilizar contraseñas seguras y gestionar adecuadamente los accesos.

7. Soporte y Resolución de Problemas
Errores Comunes:

Si tienes problemas para iniciar sesión, revisa que los datos ingresados sean correctos.

En caso de que no se visualice ninguna imagen o descripción, asegúrate de que el navegador soporte IndexedDB y que tu conexión a Internet esté activa (para cargar recursos externos).

Actualizaciones y Mantenimiento:

Este manual se actualizará a medida que se introduzcan nuevas funcionalidades. Mantente al tanto de las notificaciones de actualización de la aplicación.

Para reportar incidencias o sugerencias, contacta al equipo de soporte.

8. Conclusión
El uso de “Zeleris” está diseñado para ser intuitivo y amigable, combinando funciones de gestión de contenidos, estadísticas y configuraciones visuales (como el modo oscuro). Con este manual, se espera que puedas navegar y aprovechar todas las funcionalidades que ofrece la aplicación.

Si tienes cualquier duda adicional o encuentras algún inconveniente, no dudes en consultar el área de ayuda o contactar a soporte técnico para recibir asistencia personalizada.
