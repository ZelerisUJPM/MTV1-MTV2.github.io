<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MTV 1/MTV 2</title>
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" rel="stylesheet">
    <link rel="icon" href="img/logo.ico" type="image/x-icon">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap">
    <style>
        body {
            font-family: 'Roboto', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #e0e7ec;
        }

        .container {
            text-align: center;
            background-color: #ffffff;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
            padding: 30px;
            display: none;
        }

        .buttons button {
            margin: 5px;
            background-color: #54eb36;
            color: #000;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.1s ease-in-out; /* Transición y escala para feedback visual */
        }

        .buttons button:hover {
            background-color: #4cd831;
        }

        /* NUEVO: Feedback visual al presionar los botones de producto */
        .buttons button:active {
            transform: scale(0.95); /* Ligeramente más pequeño al presionar */
        }


        #lista {
            margin: 20px 0;
            border-color: #ced4da;
            color: #495057;
            border-radius: 8px;
            padding: 10px;
        }

        footer {
            text-align: center;
            padding: 20px;
            background-color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        #descripcion {
            margin-top: 20px;
            background-color: #ffffff;
            border: 1px solid #ced4da;
            border-radius: 8px;
            padding: 15px;
            text-align: left;
            min-height: 100px;
            box-sizing: border-box;
            overflow-wrap: break-word;
            font-family: 'Roboto', sans-serif;
            color: #495057;
            font-size: 1em;
            line-height: 1.6;
            overflow: hidden;
            resize: none;
            outline: none;
            box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
            transition: box-shadow 0.3s ease;
        }

        .image-container {
            margin-top: 30px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .image-container img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
            box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.2);
        }

        .login-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #e0e7ec;
        }

        .login-form {
            padding: 30px;
            border: none;
            background-color: #ffffff;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
        }

        .login-form h2 {
            color: #495057;
            margin-bottom: 20px;
        }

        .login-form input {
            display: block;
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            border-radius: 8px;
            border: 1px solid #ced4da;
        }

        .login-form button {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: none;
            background-color: #54eb36;
            color: #ffffff;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .login-form button:hover {
            background-color: #4cd831;
        }

        .logout-button {
            background-color: transparent;
            position: absolute;
            top: 20px;
            right: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            padding: 0;
            color: #ffffff;
            font-size: 16px;
            cursor: pointer;
            background-color: rgba(0, 0, 0, 0.2);
            transition: background-color 0.3s ease, box-shadow 0.3s ease;
            overflow: hidden;
        }

        .logout-button:hover {
            background-color: rgba(0, 0, 0, 0.4);
            box-shadow: 0 0 10px #ff4d4d;
        }

        .logout-button img {
            display: block;
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            border: 2px solid #ffffff;
            box-sizing: border-box;
        }

        .error-message {
            color: #ff4d4d;
            margin-top: 10px;
            display: none;
            font-size: 0.9em;
        }

        #loadingIndicator {
            text-align: center;
            margin-top: 15px;
            color: #6c757d;
            display: none;
        }

        .dark-mode-button {
            background-color: transparent;
            position: absolute;
            top: 20px;
            left: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            padding: 0;
            color: #ffffff;
            font-size: 16px;
            cursor: pointer;
            background-color: rgba(0, 0, 0, 0.2);
            transition: background-color 0.3s ease, box-shadow 0.3s ease;
            overflow: hidden;
            box-shadow: 0 0 10px #000000; /* Sombra negra por defecto (modo oscuro desactivado) */
        }

        .dark-mode-button:hover {
           background-color: rgba(0, 0, 0, 0.4);
           box-shadow: 0 0 10px #cccccc;
        }

        .dark-mode-button img {
            display: block;
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            border: 2px solid #ffffff;
            box-sizing: border-box;
            transition: transform 0.5s ease-in-out;
        }

        .dark-mode-button img.rotated {
            transform: rotate(180deg);
        }

        body.dark-mode {
            background-color: #333;
            color: #f0f0f0;
        }

        .container.dark-mode{
           background-color: #333;
       }
        .login-container.dark-mode,
        .login-form.dark-mode,
        footer.dark-mode,
        #descripcion.dark-mode {
            background-color: #333;
            color: #f0f0f0;
            border-color: #666;
        }

        .buttons.dark-mode button {
            background-color: #666;
            color: #ffffff;
        }

        .buttons.dark-mode button:hover {
            background-color: #777;
        }

        #lista.dark-mode {
            background-color: #555;
            color: #f0f0f0;
            border-color: #777;
        }

        .login-form.dark-mode h2,
        footer.dark-mode p {
            color: #f0f0f0;
        }

        .login-form.dark-mode input {
            background-color: #555;
            color: #f0f0f0;
            border-color: #777;
        }

        .login-form.dark-mode button {
            background-color: #666;
            color: #ffffff;
        }

        .login-form.dark-mode button:hover {
            background-color: #777;
        }

        .logout-button.dark-mode:hover {
            box-shadow: 0 0 10px #a0a0a0;
        }

        #descripcion.dark-mode {
           background-color: #444;
           border: 1px solid #666;
           color: #f0f0f0;
           box-shadow: 0 0 5px rgba(100, 100, 100, 0.5);
        }

        body.dark-mode .dark-mode-button {
            box-shadow: 0 0 10px #ffffff;
        }
        /* NUEVO: Estilo para el botón de limpiar descripción */
        .clear-description-button {
            background-color: transparent; /* Fondo transparente */
            border: none; /* Sin borde */
            color: #777; /* Color grisáceo */
            cursor: pointer; /* Cursor de mano */
            font-size: 0.9em; /* Tamaño de fuente más pequeño */
            margin-left: 10px; /* Separación del textarea */
            vertical-align: top; /* Alineación vertical con la parte superior del textarea */
            opacity: 0.7; /* Ligeramente transparente */
            transition: opacity 0.3s ease; /* Transición suave para hover */
        }
	.clear-description-button img {
	    width: 30px; /* Ajusta el ancho si es necesario */
	    height: 30px; /* Ajusta la altura si es necesario */
	    vertical-align: top; /* Ajusta la alineación vertical si es necesario */
	}

        .clear-description-button:hover {
            opacity: 1; /* Opacidad total en hover */
            color: #555; /* Gris más oscuro en hover */
        }
        body.dark-mode .clear-description-button {
            color: #bbb; /* Color grisáceo claro en modo oscuro */
        }

        body.dark-mode .clear-description-button:hover {
            color: #ddd; /* Color más claro en hover en modo oscuro */
        }
	.register-form {
	padding: 30px;
	border: none;
	background-color: #ffffff;
	border-radius: 15px;
	box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
	}
	.register-form h2 {
	color: #495057;
	margin-bottom: 20px;
	}
	.register-form input {
	display: block;
	width: 100%;
	padding: 12px;
	margin-bottom: 20px;
	border-radius: 8px;
	border: 1px solid #ced4da;
	}
	.register-form button {
	width: 100%;
	padding: 12px;
	border-radius: 8px;
	border: none;
	background-color: #54eb36;
	color: #ffffff;
	font-size: 16px;
	cursor: pointer;
	transition: background-color 0.3s ease;
	}
	.register-form button:hover {
	background-color: #4cd831;
	}
	body.dark-mode .register-form {
	background-color: #333;
	color: #f0f0f0;
	border-color: #666;
	}
	body.dark-mode .register-form input {
	background-color: #555;
	color: #f0f0f0;
	border-color: #777;
	}
	body.dark-mode .register-form button {
	background-color: #666;
	color: #ffffff;
	}
	body.dark-mode .register-form button:hover {
	background-color: #777;
	}
/* Nuevos estilos para el botón de comentarios y el formulario */
        .feedback-button {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #54eb36;
            color: #000;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            z-index: 1000;
        }

        .feedback-button:hover {
            background-color: #4cd831;
        }

        .feedback-form {
            display: none;
            position: fixed;
            bottom: 80px;
            right: 20px;
            background-color: #ffffff;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
            padding: 20px;
            width: 300px;
            z-index: 1000;
        }

        .feedback-form input,
        .feedback-form textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 8px;
            border: 1px solid #ced4da;
        }

        .feedback-form button {
            width: 100%;
            padding: 10px;
            border-radius: 8px;
            border: none;
            background-color: #54eb36;
            color: #000;
            cursor: pointer;
        }

        .feedback-form button:hover {
            background-color: #4cd831;
        }
    </style>
</head>
<body>
    <button title="Modo Oscuro" id="darkModeButton" class="dark-mode-button">
        <img src="img/oscuro.ico" alt="Modo Oscuro">
    </button>
    <div class="container">
        <div class="buttons">
            <button data-imagen="opcion1" class="btn btn-primary" onclick="changeList('opcion1')">DESCO 4K</button>
            <button data-imagen="opcion2" class="btn btn-primary" onclick="changeList('opcion2')">IMATV</button>
            <button data-imagen="opcion3" class="btn btn-primary" onclick="changeList('opcion3')">IMATV-VD</button>
            <button data-imagen="opcion4" class="btn btn-primary" onclick="changeList('opcion4')">IMATV-VDT</button>
            <button data-imagen="opcion5" class="btn btn-primary" onclick="changeList('opcion5')">AFR</button>
            <button data-imagen="opcion6" class="btn btn-primary" onclick="changeList('opcion6')">MTV 2</button>
            <button data-imagen="opcion7" class="btn btn-primary" onclick="changeList('opcion7')">ASOS</button>
            <button data-imagen="opcion8" class="btn btn-primary" onclick="changeList('opcion8')">HGUW6-P</button>
        </div>
        <select id="lista" class="form-control mt-3" onchange="showDescription()">
        </select>
        <div style="display:flex; align-items: center;">  <textarea id="descripcion" class="form-control mt-3" rows="4" placeholder="Descripción..."></textarea>
            <button type="button" id="clearDescriptionButton" class="clear-description-button" title="Limpiar descripción">
    		<img src="img/borrar.ico" alt="Limpiar descripción">
	    </button>
        </div>

        <div id="image-container" class="image-container">
        </div>
        <footer>
            <br><p>&copy; <span id="currentYear"></span> Ing. Javier Mastrangelo. Todos los derechos reservados.</p>
        </footer>
	<button class="feedback-button" onclick="toggleFeedbackForm()">Comentarios/Sugerencias</button>

         <!-- Formulario de comentarios -->
      <div class="feedback-form" id="feedbackForm">
        <h3>Envíanos tus comentarios</h3>
        <input type="text" id="from_name" placeholder="Tu nombre" required>
        <input type="email" id="email_id" placeholder="Tu correo electrónico" required>
        <textarea id="message" placeholder="Tu comentario o sugerencia" rows="4" required></textarea>
        <button onclick="sendFeedback()">Enviar</button>
    </div>
        <button title="Cerrar Sesión" id="logoutButton" class="logout-button">
            <img src="img/logout.ico" alt="Cerrar Sesión">
        </button>

    </div>
    <div class="login-container">
    <div class="logo-container">
        <img src="img/empresa.png" alt="Logo de la Empresa">
    </div>
    <form class="login-form">
        <h2>Iniciar Sesión</h2>
        <input type="text" id="username" placeholder="Nombre de usuario" required>
        <input type="password" id="password" placeholder="Contraseña" required>
        <button type="button" id="loginButton">Iniciar Sesión</button>
        <div id="errorMessage" class="error-message"></div>
 <div class="form-options">
                <br><a href="#" id="showRegisterButton">¿No tienes cuenta? Regístrate</a>
            </div>
    </form>
    <form class="register-form" style="display: none;">
        <h2>Registrarse</h2>
	<a href="#" id="showLoginButton">¿Ya tienes cuenta? Inicia Sesión</a>
        <input type="text" id="registerUsername" placeholder="Nombre de usuario" required>
        <input type="password" id="registerPassword" placeholder="Contraseña" required>
        <input type="password" id="confirmPassword" placeholder="Confirmar contraseña" required>
        <button type="button" id="registerButton">Registrarse</button>
        <div id="registerErrorMessage" class="error-message"></div>
    </form>
</div>
<script src="https://cdn.jsdelivr.net/npm/emailjs-com@3.2.0/dist/email.min.js"></script>
    <script>
        const listas = {
            opcion1: ["No desea el servicio", "Cliente necesita cable HDMI", "Cliente no necesita cable HDMI", "Cliente INSISTE querer ayuda técnica para la instalación", "Cliente desea cambiar dirección de instalación.", "Aplazamiento de llamada", "Cliente no contesta", "Contestador automático", "Número equivocado, cliente si conoce el producto y  el destinatario.", "Número equivocado, cliente no conoce ni el producto, ni el destinatario.", "Cliente extranjero", "Actualización de numero telefonico", "Abandono"],
            opcion2: ["No desea el servicio", "Cliente no tiene cerca el router de la TV (Acepta amplificador).", "Cliente no tiene cerca el router de la TV (No acepta amplificador).", "Cliente no cuenta con conexión HDMI", "Cliente INSISTE querer ayuda técnica para la instalación", "Cliente desea el servicio.", "Cliente no puede recibir el producto dentro de los tiempos establecidos (RETENCIÓN)", "Aplazamiento de llamada", "Cliente no contesta", "Contestador automático", "Número equivocado, cliente si conoce el producto y  el destinatario.", "Número equivocado, cliente no conoce ni el producto, ni el destinatario.", "Cliente extranjero", "Actualización de numero telefonico", "Abandono"],
            opcion3: ["No desea el servicio", "Cliente no cuenta con roseta o clavija de fibra óptica","No sabe si tiene roseta en el domicilio","No desea conectar terminal fijo","Cliente INSISTE querer ayuda técnica para la instalación","Cliente no puede recibir el producto dentro de los tiempos establecidos (RETENCIÓN)","Cliente desea el servicio.","Cliente desea cambiar dirección de instalación.","Cliente no contesta","Contestador automático","Número equivocado, cliente si conoce el producto y  el destinatario.","Número equivocado, cliente no conoce ni el producto, ni el destinatario.","Aplazamiento de llamada","Cliente extranjero","Actualización de numero telefonico","Abandono"],
            opcion4: ["No desea el servicio","Cliente INSISTE querer ayuda técnica para la instalación","Cliente no cuenta con roseta o clavija de fibra óptica","No sabe si tiene roseta en el domicilio","Cliente no tiene cerca el router de la TV (Acepta amplificador).","Cliente no tiene cerca el router de la TV (No acepta amplificador).","Cliente desea el servicio.","Cliente desea cambiar dirección de instalación.","No desea conectar terminal fijo","Cliente no tiene roseta pero acepta amplificador.","Cliente no cuenta con conexión HDMI","Cliente no puede recibir el producto dentro de los tiempos establecidos (RETENCIÓN)","Cliente no contesta","Contestador automático","Número equivocado, cliente si conoce el producto y  el destinatario.","Número equivocado, cliente no conoce ni el producto, ni el destinatario.","Aplazamiento de llamada","Cliente extranjero","Actualización de numero telefonico","Abandono"],
            opcion5: ["No desea el servicio","Cliente desea el servicio.","Cliente tiene servicio incompatible","Cliente desea cambiar dirección de instalación.","Cliente INSISTE querer ayuda técnica para la instalación","Cliente no puede recibir el producto dentro de los tiempos establecidos (RETENCIÓN)","Cliente no contesta","Contestador automático","Número equivocado, cliente si conoce el producto y  el destinatario.","Número equivocado, cliente no conoce ni el producto, ni el destinatario.","Aplazamiento de llamada","Cliente extranjero","Actualización de numero telefonico","Abandono"],
            opcion6: ["Cliente asegura que no recibio el paquete (reportar a tu lider)","Ya instalo y realizo configuración del equipo nuevo.","Cliente INSISTE querer ayuda técnica para la instalación","(AFR)Phonebox-migración: Cliente cuenta con servicio incompatible con tecnologia radio.","Material averiado o roto.","Se realizamos varios intentos de instalación y/o configuración, pero no se pudo completar el proceso","Cliente rechaza el servicio de instalación y configuración (devolver)","Aplazamiento de llamada","Cliente no puede recibir el producto dentro de los tiempos establecidos (RETENCIÓN)","Contestador automático","Cliente no contesta","Número equivocado, cliente si conoce el producto y  el destinatario.", "Número equivocado, cliente no conoce ni el producto, ni el destinatario.","Cliente extranjero","Cliente no cuenta con roseta o clavija de fibra óptica","Abandono"],
            opcion7: ["No desea el servicio", "Cliente no cuenta con roseta o clavija de fibra óptica", "No sabe si tiene roseta en el domicilio", "No desea conectar terminal fijo", "Cliente INSISTE querer ayuda técnica para la instalación", "Cliente no puede recibir el producto dentro de los tiempos establecidos (RETENCIÓN)", "Cliente desea el servicio.", "Cliente desea cambiar dirección de instalación.", "Cliente no contesta", "Contestador automático", "Número equivocado, cliente sí conoce el producto y el destinatario.", "Número equivocado, cliente no conoce ni el producto ni el destinatario.", "Aplazamiento de llamada", "Cliente extranjero", "Actualización de número telefónico", "Abandono", "Cliente no tiene cerca el router de la TV (Acepta amplificador).", "Cliente no tiene cerca el router de la TV (No acepta amplificador).", "Cliente no tiene roseta pero acepta amplificador.", "Cliente no cuenta con conexión HDMI"],
            opcion8: ["No desea el servicio","Cliente INSISTE querer ayuda técnica para la instalación", "Cliente desea el servicio.", "Cliente no contesta", "Número equivocado, cliente sí conoce el producto y el destinatario.", "Número equivocado, cliente no conoce ni el producto ni el destinatario.", "Aplazamiento de llamada", "Cliente extranjero", "Actualización de número telefónico", "Abandono"]
        };

        const descripciones = {
        "No desea el servicio": "Cliente no desea el servicio, se remite a la linea 1004. Hablo con ",
            "Cliente necesita cable HDMI": "Cliente necesita cable hdmi, confirmo envio. Hablo con ",
            "Cliente no necesita cable HDMI": "Cliente no necesita cable hdmi, confirmo envio. Hablo con ",
            "Cliente INSISTE querer ayuda técnica para la instalación": "Cliente insiste en tener ayuda técnica, se deriva a servicio técnico. Hablo con ",
            "Cliente desea cambiar dirección de instalación.": "Cliente desea cambiar dirección de instalación, se brinda linea 1004. Hablo con ",
            "Aplazamiento de llamada": "Cliente solicita nueva comunicación, aplazamiento de llamada. Hablo con ",
            "Cliente no contesta": "Cliente no contesta.",
            "Contestador automático": "Contestador automático, cliente no contesta.",
            "Número equivocado, cliente si conoce el producto y  el destinatario.": "Número equivocado, se actualiza información.",
            "Número equivocado, cliente no conoce ni el producto, ni el destinatario.": "Número equivocado, se brinda línea 1004.",
            "Cliente extranjero": "Cliente no habla español, se brinda línea 1004.",
            "Actualización de numero telefonico": "Cliente actualiza teléfono, se genera aplazamiento de llamada. Hablo con ",
            "Abandono": "Llamada cortada, cliente abandonó la comunicación. Hablo con ",
        "Cliente no tiene cerca el router de la TV (Acepta amplificador).": "Router no está cerca de la TV, cliente acepta amplificador, se confirma envío. Hablo con ",
            "Cliente no tiene cerca el router de la TV (No acepta amplificador).": "Router no está cerca de la TV, cliente no acepta amplificador, se deriva a servicio técnico. Hablo con ",
            "Cliente no cuenta con conexión HDMI": "Cliente no tiene conexión HDMI, brindo la línea 1004. Hablo con ",
            "Cliente desea el servicio.": "Cliente autoinstalable, confirmo envío. Hablo con ",
            "Cliente no puede recibir el producto dentro de los tiempos establecidos (RETENCIÓN)": "Cliente manifiesta xxx, se genera retención. Hablo con ",
            "Cliente no cuenta con roseta o clavija de fibra óptica": "Cliente no cuenta con roseta de fibra óptica, se deriva a servicio técnico. Hablo con ",
            "No sabe si tiene roseta en el domicilio": "Se aplaza llamada porque cliente no sabe si tiene roseta. Hablo con ",
            "No desea conectar terminal fijo": "Cliente no conectará terminal fijo, se confirma envío. Hablo con ",
            "Cliente no tiene roseta pero acepta amplificador.": "Cliente no tiene roseta pero acepta amplificador, se deriva a servicio técnico. Hablo con ",
            "Cliente tiene servicio incompatible":"Cliente tiene servicio incompatible, se brinda línea 1004.Hablo con ",
            "Cliente asegura que no recibio el paquete (reportar a tu lider)":"Cliente asegura que no recibió el paquete, se brinda línea 1004.Hablo con ",
            "Ya instalo y realizo configuración del equipo nuevo.":"Equipo instalado y configurado, se espera comprobación de Arce y Magia.Hablo con ",
            "(AFR)Phonebox-migración: Cliente cuenta con servicio incompatible con tecnologia radio.":"Cliente tiene servicio incompatible con tecnología radio, se brinda línea 1004. Hablo con ",
            "Material averiado o roto.":"Cliente tiene el equipo dañado y/o roto. Hablo con ",
            "Se realizamos varios intentos de instalación y/o configuración, pero no se pudo completar el proceso":"No se puede generar instalación y configuración por xxx, se deriva a servicio técnico.Hablo con ",
            "Cliente rechaza el servicio de instalación y configuración (devolver)":"Cliente rechaza el servicio por xxx, se brinda línea 1002.Hablo con ",


        };

        const imagenes = {
            opcion1: "<img src='img/DESCO4K.png' alt='DESCO4K'>",
            opcion2: "<img src='img/IMATV.png' alt='IMATV'>",
            opcion3: "<img src='img/IMATV-VD.png' alt='IMATV-VD'>",
            opcion4: "<img src='img/IMATV-VDT.png' alt='IMATV-VDT'>",
            opcion5: "<div class='imagenes-paralelas'><img src='img/AFR-MIGRACION.png' alt='AFR-MIGRACION'><img src='img/AFR-V.png' alt='AFR-V'></div>",
            opcion6: "<a href='https://padlet.com/NICO333/multiconsulta-formaci-n-25ks0qamr4j4vhy6/wish/dMA1W8X3bJY1W4OV'><img src='img/MTV-2.png' alt='MTV-2'></a>",
            opcion7: "<div class='imagenes-paralelas'><img src='img/ASOS-VD.png' alt='ASOS-VD'><img src='img/ASOS-VDT.png' alt='ASOS-VDT'></div>",
            opcion8: "<img src='img/WIFI-6.png' alt='WIFI-6'>",


        };

        document.querySelectorAll('button[data-imagen]').forEach(button => {
            button.addEventListener('click', function() {
                const opcion = this.getAttribute('data-imagen');
                const imagenSeleccionada = imagenes[opcion];
                document.getElementById('image-container').innerHTML = imagenSeleccionada;
            });
        });

        function changeList(opcion) {
            const lista = document.getElementById('lista');
            lista.innerHTML = '';
            listas[opcion].forEach(item => {
                const option = document.createElement('option');
                option.value = item;
                option.textContent = item;
                lista.appendChild(option);
            });
            document.getElementById('descripcion').value = '';

            lista.selectedIndex = 0; // Selecciona la primera opción por defecto
            showDescription();        // Carga la descripción de la primera opción

            showImage(opcion);

            // NUEVO: Guardar la última opción seleccionada en localStorage
            localStorage.setItem('lastSelectedOption', opcion);
        }

        function showDescription() {
            const lista = document.getElementById('lista');
            const item = lista.value;
            document.getElementById('descripcion').value = descripciones[item];

            // NUEVO: Guardar la descripción en localStorage al cambiarla
            localStorage.setItem('lastDescriptionText',  document.getElementById('descripcion').value);
        }

        function showImage(opcion) {
            const imageContainer = document.getElementById('image-container');
            imageContainer.innerHTML = imagenes[opcion] || ''; // Muestra la imagen o vacio si no hay imagen
        }

        document.getElementById('loginButton').addEventListener('click', function() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const errorMessageDiv = document.getElementById('errorMessage');

            if (username === '0' && password === '0') {
                document.querySelector('.container').style.display = 'block';
                document.querySelector('.login-container').style.display = 'none';
                errorMessageDiv.style.display = 'none';

            } else {
                errorMessageDiv.textContent = 'Nombre de usuario o contraseña incorrectos.';
                errorMessageDiv.style.display = 'block';
            }
        });

        document.getElementById('logoutButton').addEventListener('click', function() {
            document.querySelector('.container').style.display = 'none';
            document.querySelector('.login-container').style.display = 'flex';
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        });

        document.getElementById('password').addEventListener('keydown', function(event) {
            if (event.key === 'Enter') {
                document.getElementById('loginButton').click();
                event.preventDefault();
            }
        });

        const darkModeButton = document.getElementById('darkModeButton');
        const body = document.body;
        const container = document.querySelector('.container');
        const loginContainer = document.querySelector('.login-container');
        const loginForm = document.querySelector('.login-form');
        const footerElem = document.querySelector('footer');
        const buttonsContainer = document.querySelector('.buttons');
        const listaSelect = document.getElementById('lista');
        const descripcionTextarea = document.getElementById('descripcion');
        const logoutButtonElem = document.getElementById('logoutButton');
        const clearDescriptionButton = document.getElementById('clearDescriptionButton'); // NUEVO: Botón limpiar descripción


        function toggleDarkMode() {
            body.classList.toggle('dark-mode');
            container.classList.toggle('dark-mode');
            loginContainer.classList.toggle('dark-mode');
            loginForm.classList.toggle('dark-mode');
            footerElem.classList.toggle('dark-mode');
            buttonsContainer.classList.toggle('dark-mode');
            listaSelect.classList.toggle('dark-mode');
            descripcionTextarea.classList.toggle('dark-mode');
            logoutButtonElem.classList.toggle('dark-mode');

            const darkModeImage = darkModeButton.querySelector('img');
            darkModeImage.classList.toggle('rotated');


            if (body.classList.contains('dark-mode')) {
                localStorage.setItem('darkMode', 'enabled');
            } else {
                localStorage.setItem('darkMode', 'disabled');
            }
        }

        darkModeButton.addEventListener('click', toggleDarkMode);

        // NUEVO: Evento para el botón de limpiar descripción
        clearDescriptionButton.addEventListener('click', function() {
            descripcionTextarea.value = ''; // Limpiar el textarea
            localStorage.removeItem('lastDescriptionText'); // Opcional: limpiar también de localStorage
            showDescription(); // Actualizar la descripción (en este caso, estará vacía)
        });


        //  Carga inicial de la página:
        document.addEventListener('DOMContentLoaded', function() {
            // Restaurar el modo oscuro desde localStorage (si está guardado)
            if (localStorage.getItem('darkMode') === 'enabled') {
                toggleDarkMode();
            }

            // NUEVO: Restaurar la última opción de producto seleccionada desde localStorage
            const lastOption = localStorage.getItem('lastSelectedOption');
            if (lastOption) {
                changeList(lastOption);
                // Opcional:  Si quieres que el botón de producto se vea visualmente "activo" o seleccionado, podrías añadirle una clase aquí también.
            } else {
                changeList('opcion1'); // Establecer 'opcion1' como predeterminado si no hay opción guardada.
            }

            // NUEVO: Restaurar el texto del área de descripción desde localStorage
            const lastDescription = localStorage.getItem('lastDescriptionText');
            if (lastDescription) {
                descripcionTextarea.value = lastDescription;
                showDescription(); // Asegurar que la descripción se actualice (aunque ya debería estar actualizada con textarea.value = lastDescription;)
            }
        });

    document.addEventListener('DOMContentLoaded', function() {
    const loginForm = document.querySelector('.login-form');
    const registerForm = document.querySelector('.register-form');
    const showRegisterButton = document.getElementById('showRegisterButton');
    const showLoginButton = document.getElementById('showLoginButton');
    const loginButton = document.getElementById('loginButton');
    const registerButton = document.getElementById('registerButton');
    const errorMessageDiv = document.getElementById('errorMessage');
    const registerErrorMessageDiv = document.getElementById('registerErrorMessage');

    showRegisterButton.addEventListener('click', function() {
        loginForm.style.display = 'none';
        registerForm.style.display = 'block';
    });

    showLoginButton.addEventListener('click', function() {
        registerForm.style.display = 'none';
        loginForm.style.display = 'block';
    });

    loginButton.addEventListener('click', function() {
        const username = document.getElementById('username').value;
        const password = document.getElementById('password').value;

        const users = JSON.parse(localStorage.getItem('users')) || [];
        const user = users.find(u => u.username === username && u.password === password);

        if (user) {
            document.querySelector('.container').style.display = 'block';
            document.querySelector('.login-container').style.display = 'none';
            errorMessageDiv.style.display = 'none';
        } else {
            errorMessageDiv.textContent = 'Nombre de usuario o contraseña incorrectos.';
            errorMessageDiv.style.display = 'block';
        }
    });

    registerButton.addEventListener('click', function() {
        const username = document.getElementById('registerUsername').value;
        const password = document.getElementById('registerPassword').value;
        const confirmPassword = document.getElementById('confirmPassword').value;

        if (password !== confirmPassword) {
            registerErrorMessageDiv.textContent = 'Las contraseñas no coinciden.';
            registerErrorMessageDiv.style.display = 'block';
            return;
        }

        const users = JSON.parse(localStorage.getItem('users')) || [];
        const userExists = users.some(u => u.username === username);

        if (userExists) {
            registerErrorMessageDiv.textContent = 'El nombre de usuario ya existe.';
            registerErrorMessageDiv.style.display = 'block';
            return;
        }

        users.push({ username, password });
        localStorage.setItem('users', JSON.stringify(users));

        registerErrorMessageDiv.textContent = 'Registro exitoso. Por favor, inicie sesión.';
        registerErrorMessageDiv.style.display = 'block';

        registerForm.style.display = 'none';
        loginForm.style.display = 'block';
    });
});
document.getElementById("currentYear").innerHTML = new Date().getFullYear();

function ordenarListasAlfabeticamente(listas) {
    for (const opcion in listas) {
        if (Array.isArray(listas[opcion])) {
            listas[opcion].sort();
        }
    }
    return listas;
}

const listasOrdenadas = ordenarListasAlfabeticamente(listas);

console.log(listasOrdenadas);// Inicializa EmailJS con tu User ID
        (function() {
            emailjs.init("y-HHCtNBV2WfEoijB"); // Reemplaza con tu User ID de EmailJS
        })();

        // Función para mostrar/ocultar el formulario de comentarios
        function toggleFeedbackForm() {
            const form = document.getElementById("feedbackForm");
            form.style.display = form.style.display === "none" ? "block" : "none";
        }

        // Función para enviar el formulario usando EmailJS
        function sendFeedback() {
            const name = document.getElementById("from_name").value;
            const email = document.getElementById("email_id").value;
            const message = document.getElementById("message").value;

            if (!name || !email || !message) {
                alert("Por favor, completa todos los campos.");
                return;
            }

            // Parámetros para la plantilla de EmailJS
            const templateParams = {
                from_name: name,
                email_id: email,
                message: message,
            };

            // Envía el correo usando EmailJS
            emailjs.send("MTV1/MTV2", "Template_MTV", templateParams)
                .then(function(response) {
                    alert("¡Gracias por tus comentarios!");
                    toggleFeedbackForm(); // Oculta el formulario después de enviar
                }, function(error) {
                    alert("Hubo un error al enviar tu mensaje. Por favor, inténtalo de nuevo.");
                    console.error("Error al enviar el correo:", error);
                });
        }
// Objeto para almacenar las estadísticas
    const estadisticas = {
        totalCopias: 0, // Contador total de copias
        copiasConBoton: {}, // Contador de copias por botón
        copiasConLista: {}, // Contador de copias por lista
        detallesCopias: [] // Array para almacenar detalles de cada copia
    };

    // Variables para almacenar el botón y la lista seleccionada actualmente
    let botonSeleccionado = null;
    let listaSeleccionada = null;

    // Función para registrar el botón seleccionado
    document.querySelectorAll('.buttons button').forEach(button => {
        button.addEventListener('click', () => {
            botonSeleccionado = button.textContent.trim(); // Almacenar el texto del botón
        });
    });

    // Función para registrar la lista seleccionada
    const lista = document.getElementById('lista');
    lista.addEventListener('change', () => {
        listaSeleccionada = lista.options[lista.selectedIndex].text; // Almacenar el texto de la opción seleccionada
    });

    // Función para registrar copias de texto
    const textarea = document.getElementById('descripcion');
    textarea.addEventListener('copy', () => {
        // Incrementar el contador de copias
        estadisticas.totalCopias++;

        // Actualizar contador de copias por botón
        if (botonSeleccionado) {
            estadisticas.copiasConBoton[botonSeleccionado] = (estadisticas.copiasConBoton[botonSeleccionado] || 0) + 1;
        }

        // Actualizar contador de copias por lista
        if (listaSeleccionada) {
            estadisticas.copiasConLista[listaSeleccionada] = (estadisticas.copiasConLista[listaSeleccionada] || 0) + 1;
        }

        // Almacenar detalles de la copia
        estadisticas.detallesCopias.push({
            fechaHora: new Date().toLocaleString(),
            boton: botonSeleccionado || 'Ninguno',
            lista: listaSeleccionada || 'Ninguna'
        });

        console.log('Total de copias:', estadisticas.totalCopias);
        console.log('Copias por botón:', estadisticas.copiasConBoton);
        console.log('Copias por lista:', estadisticas.copiasConLista);
        console.log('Detalles de copias:', estadisticas.detallesCopias);
    });

    // Función para guardar las estadísticas en un archivo de texto
    function guardarEstadisticas() {
    const datos = [];
    datos.push("Estadísticas de copias de texto:\n");

    // Agregar el total de copias
    datos.push(`- Total de copias: ${estadisticas.totalCopias}`);

    // Agregar estadísticas por botón
    datos.push("\n- Copias por botón:");
    for (const boton in estadisticas.copiasConBoton) {
        datos.push(`  - ${boton}: ${estadisticas.copiasConBoton[boton]}`);
    }

    // Agregar estadísticas por lista
    datos.push("\n- Copias por lista:");
    for (const lista in estadisticas.copiasConLista) {
        datos.push(`  - ${lista}: ${estadisticas.copiasConLista[lista]}`);
    }

    // Agregar detalles de cada copia
    datos.push("\n- Detalles de copias:");
    estadisticas.detallesCopias.forEach(copia => {
        datos.push(`  - Fecha/Hora: ${copia.fechaHora}, Botón: ${copia.boton}, Lista: ${copia.lista}`);
    });

    // Convertir a texto
    const texto = datos.join("\n");

    // Obtener la fecha y hora actual en formato DD-MM-AAAA_HH-MM
    const fechaActual = new Date();
    const dia = String(fechaActual.getDate()).padStart(2, '0'); // Día con dos dígitos
    const mes = String(fechaActual.getMonth() + 1).padStart(2, '0'); // Mes con dos dígitos
    const año = fechaActual.getFullYear(); // Año con cuatro dígitos
    const horas = String(fechaActual.getHours()).padStart(2, '0'); // Horas con dos dígitos
    const minutos = String(fechaActual.getMinutes()).padStart(2, '0'); // Minutos con dos dígitos
    const fechaHoraFormateada = `${dia}-${mes}-${año}_${horas}-${minutos}`; // Formato DD-MM-AAAA_HH-MM

    // Crear un archivo de texto y permitir su descarga
    const blob = new Blob([texto], { type: 'text/plain' });
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = `${fechaHoraFormateada}.txt`; // Nombre del archivo con la fecha y hora en formato DD-MM-AAAA_HH-MM
    a.click();
    URL.revokeObjectURL(url);
}

    // Guardar estadísticas al cerrar sesión
    document.getElementById('logoutButton').addEventListener('click', () => {
        guardarEstadisticas(); // Guardar estadísticas en un archivo de texto
    });


</script>
</body>
</html>
