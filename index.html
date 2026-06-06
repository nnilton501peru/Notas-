<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mauricio Editor v2.2</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: sans-serif;
            background-color: #121212;
            color: white;
            display: flex;
            flex-direction: column;
            height: 100vh;
            padding: 15px;
            position: relative;
        }

        /* Botón de menú: un poco más grande y mejor ubicado */
        .boton-menu {
            position: absolute;
            top: 20px; /* Bajado un poco más */
            right: 20px;
            width: 44px; /* Un poco más grande para tocar mejor */
            height: 44px;
            border-radius: 8px;
            background-color: #222;
            color: white;
            border: none;
            font-size: 24px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 100;
            transition: all 0.15s ease;
        }

        .boton-menu:hover {
            background-color: #333;
        }

        .boton-menu:active {
            transform: scale(0.95); /* Efecto leve al presionar */
        }

        /* Menú desplegable con mejor espaciado */
        .menu-contenido {
            position: absolute;
            top: 75px;
            right: 20px;
            background-color: #1e1e1e;
            border: 1px solid #333;
            border-radius: 10px;
            padding: 14px;
            min-width: 200px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
            display: none;
            z-index: 99;
        }

        .menu-contenido.mostrar {
            display: block;
        }

        .menu-opcion {
            width: 100%;
            padding: 12px; /* Más cómodo */
            margin: 5px 0;
            border: none;
            border-radius: 7px;
            background-color: #2d2d2d;
            color: white;
            text-align: left;
            cursor: pointer;
            font-size: 14px;
            display: flex;
            align-items: center;
            gap: 9px;
            transition: background 0.15s ease;
        }

        .menu-opcion:hover {
            background-color: #3d3d3d;
        }

        .menu-opcion:active {
            background-color: #444;
        }

        .config-grupo {
            margin-top: 14px;
            padding-top: 14px;
            border-top: 1px solid #333;
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        .config-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 5px;
            font-size: 11px;
            color: #ccc;
        }

        input[type="color"] {
            width: 32px;
            height: 32px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background: #333;
        }

        input[type="number"] {
            width: 48px;
            background: #333;
            color: white;
            border: 1px solid #555;
            border-radius: 5px;
            text-align: center;
            padding: 5px;
        }

        /* Área de texto: borde más sutil y texto discreto */
        #main-textarea {
            flex-grow: 1;
            width: 100%;
            background-color: #1e1e1e;
            color: white;
            border: 1px solid #2a2a2a; /* Borde más suave */
            border-radius: 10px;
            padding: 22px;
            font-size: 18px;
            resize: none;
            outline: none;
            line-height: 1.55;
            margin: 12px 0;
        }

        /* Texto de ayuda más discreto */
        #main-textarea::placeholder {
            color: #444;
            opacity: 0.7;
        }

        /* Barra inferior: reloj ajustado */
        footer {
            padding: 11px 15px;
            background-color: #1e1e1e;
            border-radius: 8px;
            border: 1px solid #2a2a2a;
            text-align: center;
            font-size: 14px;
            color: #00ffcc;
        }

        #reloj {
            color: #f1c40f;
            margin-left: 12px;
            font-family: monospace;
            font-size: 1.1em; /* Tamaño equilibrado */
        }
    </style>
</head>
<body>

    <!-- Botón de menú -->
    <button class="boton-menu" id="menuBoton">⋮</button>

    <!-- Menú desplegable con todas las opciones -->
    <div class="menu-contenido" id="menuContenido">
        <button class="menu-opcion" onclick="copyText()">📋 Copiar</button>
        <button class="menu-opcion" onclick="pasteText()">📥 Pegar</button>
        <button class="menu-opcion" onclick="clearText()">🗑️ Borrar todo</button>
        <button class="menu-opcion" onclick="sendWhatsApp()">💬 Enviar a WhatsApp</button>
        <button class="menu-opcion" onclick="saveToFile()">💾 Guardar</button>
        <button class="menu-opcion" onclick="toggleFullScreen()">⛶ Pantalla completa</button>

        <div class="config-grupo">
            <div class="config-item">
                <label>Fondo</label>
                <input type="color" id="bgColor" value="#1e1e1e" oninput="updateStyle()">
            </div>
            <div class="config-item">
                <label>Letra</label>
                <input type="color" id="textColor" value="#ffffff" oninput="updateStyle()">
            </div>
            <div class="config-item">
                <label>Tamaño</label>
                <input type="number" id="fontSize" value="18" min="10" max="50" oninput="updateStyle()">
            </div>
        </div>
    </div>

    <!-- Área de escritura -->
    <textarea id="main-textarea" placeholder="..."></textarea>

    <!-- Barra inferior -->
    <footer>
        Mauricio v2.2 <span id="reloj">00:00 AM</span>
    </footer>

    <script>
        const textarea = document.getElementById('main-textarea');
        const menuBoton = document.getElementById('menuBoton');
        const menuContenido = document.getElementById('menuContenido');

        // Mostrar/ocultar menú
        menuBoton.addEventListener('click', () => {
            menuContenido.classList.toggle('mostrar');
        });

        // Cerrar menú al tocar fuera
        document.addEventListener('click', (e) => {
            if (!menuBoton.contains(e.target) && !menuContenido.contains(e.target)) {
                menuContenido.classList.remove('mostrar');
            }
        });

        // Reloj
        function actualizarReloj() {
            const ahora = new Date();
            let horas = ahora.getHours();
            const minutos = ahora.getMinutes().toString().padStart(2, '0');
            const ampm = horas >= 12 ? 'PM' : 'AM';
            horas = horas % 12 || 12;
            document.getElementById('reloj').innerText = `${horas}:${minutos} ${ampm}`;
        }
        setInterval(actualizarReloj, 1000);
        actualizarReloj();

        // Funciones
        function clearText() {
            if (confirm("¿Borrar todo el texto?")) {
                textarea.value = "";
            }
        }

        function updateStyle() {
            textarea.style.backgroundColor = document.getElementById('bgColor').value;
            textarea.style.color = document.getElementById('textColor').value;
            textarea.style.fontSize = document.getElementById('fontSize').value + "px";
        }

        async function copyText() {
            if (!textarea.value.trim()) return;
            try {
                await navigator.clipboard.writeText(textarea.value);
            } catch (err) {}
        }

        async function pasteText() {
            try {
                const text = await navigator.clipboard.readText();
                textarea.value += text;
            } catch (err) {}
        }

        function sendWhatsApp() {
            const text = encodeURIComponent(textarea.value);
            if (!text) return;
            window.open(`https://wa.me/?text=${text}`, '_blank');
        }

        // Guardado corregido
        function saveToFile() {
            if (!textarea.value.trim()) return;
            const blob = new Blob([textarea.value], { type: "text/plain;charset=utf-8" });
            const url = URL.createObjectURL(blob);
            const a = document.createElement("a");
            a.href = url;
            a.download = "mi_nota.txt";
            a.click();
            URL.revokeObjectURL(url);
        }

        function toggleFullScreen() {
            if (!document.fullscreenElement) {
                document.documentElement.requestFullscreen().catch(() => {});
            } else {
                document.exitFullscreen().catch(() => {});
            }
        }

        // Cerrar menú al escribir en móvil
        textarea.addEventListener('focus', () => {
            if (window.innerWidth < 768) {
                menuContenido.classList.remove('mostrar');
            }
        });
    </script>

</body>
</html>
