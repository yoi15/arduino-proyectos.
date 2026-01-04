# arduino-proyectos.
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Repositorio Arduino - Calmago</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f4f4f4; }
    header { background: #004080; color: white; padding: 20px; text-align: center; }
    nav a { margin: 0 15px; color: white; text-decoration: none; }
    section { padding: 20px; }
    .card { background: white; padding: 20px; margin: 20px auto; max-width: 600px; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
    pre { background: #272822; color: #f8f8f2; padding: 15px; border-radius: 5px; overflow-x: auto; }
    footer { background: #eee; text-align: center; padding: 20px; margin-top: 40px; }
    @media (max-width: 600px) {
      nav { display: block; }
      nav a { display: block; margin: 10px 0; }
    }
    input[type="text"] { width: 100%; padding: 10px; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; }
  </style>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/themes/prism.min.css" rel="stylesheet" />
  <script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/prism.min.js"></script>
</head>
<body>
  <header>
    <h1>Repositorio de Proyectos Arduino</h1>
    <nav>
      <a href="#proyectos">Proyectos</a>
      <a href="#contacto">Contacto</a>
    </nav>
  </header>

  <section id="buscador">
    <h2>Buscar proyectos</h2>
    <input type="text" id="search" placeholder="Escribe para buscar..." onkeyup="filtrar()">
  </section>

  <section id="proyectos">
    <h2>Proyectos disponibles</h2>

    <!-- Proyecto 1 -->
    <div class="card proyecto">
      <h3>Blink LED</h3>
      <p>Enciende y apaga un LED cada segundo.</p>
      <pre><code class="language-cpp">
// Código Arduino: Blink
void setup() {
  pinMode(13, OUTPUT); // LED en pin 13
}

void loop() {
  digitalWrite(13, HIGH); // Enciende LED
  delay(1000);            // Espera 1 segundo
  digitalWrite(13, LOW);  // Apaga LED
  delay(1000);            // Espera 1 segundo
}
      </code></pre>
      <p><a href="blink.ino" download>📥 Descargar código</a></p>
    </div>

    <!-- Proyecto 2 -->
    <div class="card proyecto">
      <h3>Sensor de Temperatura</h3>
      <p>Lee datos de un sensor LM35 y los muestra en el monitor serial.</p>
      <pre><code class="language-cpp">
// Código Arduino: Sensor LM35
int sensorPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int valor = analogRead(sensorPin);
  float temperatura = (valor * 5.0 * 100.0) / 1024.0;
  Serial.println(temperatura);
  delay(1000);
}
      </code></pre>
      <p><a href="sensor.ino" download>📥 Descargar código</a></p>
    </div>

  </section>

  <section id="contacto">
    <h2>Contacto</h2>
    <p>Correo: info@calmago.com</p>
  </section>

  <footer>
    <p>&copy; 2026 Calmago, S.R.L.</p>
  </footer>

  <script>
    function filtrar() {
      let input = document.getElementById("search").value.toLowerCase();
      let proyectos = document.getElementsByClassName("proyecto");
      for (let i = 0; i < proyectos.length; i++) {
        let titulo = proyectos[i].getElementsByTagName("h3")[0].innerText.toLowerCase();
        proyectos[i].style.display = titulo.includes(input) ? "block" : "none";
      }
    }
  </script>
</body>
</html>
// Proyecto Blink LED
void setup() {
  pinMode(13, OUTPUT); // LED en pin 13
}

void loop() {
  digitalWrite(13, HIGH); // Enciende LED
  delay(1000);            // Espera 1 segundo
  digitalWrite(13, LOW);  // Apaga LED
  delay(1000);            // Espera 1 segundo
}
// Proyecto Sensor LM35
int sensorPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int valor = analogRead(sensorPin);
  float temperatura = (valor * 5.0 * 100.0) / 1024.0;
  Serial.println(temperatura);
  delay(1000);
}
