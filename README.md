<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Apu GPS</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 10px 0;
            text-align: center;
        }
        section {
            margin: 20px;
        }
        h1 {
            font-size: 24px;
        }
        #map {
            height: 400px;
            width: 100%;
        }
        .chapatucho-container {
            margin-top: 20px;
        }
        .chapatucho-container h2 {
            font-size: 20px;
            color: #4CAF50;
        }
        .chapatucho-container form {
            display: flex;
            flex-direction: column;
        }
        .chapatucho-container input, .chapatucho-container textarea {
            margin-bottom: 10px;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ddd;
        }
        .chapatucho-container button {
            padding: 10px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
        .chapatucho-container button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <header>
        <h1>Apu GPS</h1>
    </header>
    <section>
        <h1>Localización del Camión Basurero</h1>
        <div id="map"></div>
    </section>
    <section class="chapatucho-container">
        <h2>CHAPAATUCOCHINO</h2>
        <form id="reportForm">
            <label for="description">Descripción:</label>
            <textarea id="description" name="description" rows="4" placeholder="Describa el incidente..."></textarea>
            <label for="media">Subir Foto o Video:</label>
            <input type="file" id="media" name="media" accept="image/*,video/*">
            <button type="submit">Enviar</button>
        </form>
    </section>

    <script>
        // Función para inicializar el mapa
        function initMap() {
            var mapOptions = {
                zoom: 12,
                center: { lat: -12.046374, lng: -77.042793 }
            };
            var map = new google.maps.Map(document.getElementById('map'), mapOptions);

            // Añadir marcador de ejemplo para el camión basurero
            var marker = new google.maps.Marker({
                position: { lat: -12.046374, lng: -77.042793 },
                map: map,
                title: 'Camión Basurero'
            });
        }

        // Cargar el mapa al cargar la página
        window.onload = function() {
            initMap();
        };

        // Manejar el envío del formulario CHAPAATUCOCHINO
        document.getElementById('reportForm').addEventListener('submit', function(event) {
            event.preventDefault();
            alert('Reporte enviado. ¡Gracias por su colaboración!');
            document.getElementById('reportForm').reset();
        });
    </script>
    <script async defer src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap"></script>
</body>
</html>
