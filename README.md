<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cube Box Mystery</title>

  <!-- Etiquetas para la vista previa al compartir el link -->
  <meta property="og:title" content="🎁 Cube Box Mystery">
  <meta property="og:description" content="Hay algo guardado acá adentro, pero solo una persona puede abrirlo...">
  <meta property="og:image" content="https://netlify.app">
  <meta property="og:url" content="https://netlify.app">
  <meta property="og:type" content="website">

  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      /* Degradado de crema pastel a rosa suave */
      background: linear-gradient(135deg, #fff5f7, #fce1e4, #e8dff5);
      color: #5c4b51;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 20px;
      text-align: center;
    }
    .caja {
      background: rgba(255, 255, 255, 0.85);
      padding: 35px 25px;
      border-radius: 24px;
      max-width: 440px;
      width: 100%;
      box-shadow: 0 10px 30px rgba(214, 162, 173, 0.25);
      border: 2px solid #ffd6e0;
    }
    h1 {
      font-size: 1.6rem;
      margin-bottom: 10px;
      color: #d96b8a;
    }
    p {
      line-height: 1.6;
      font-size: 1.05rem;
    }
    .pista {
      background-color: #fcf4dd;
      color: #7f6a4d;
      padding: 8px 14px;
      border-radius: 12px;
      display: inline-block;
      font-size: 0.9rem;
      margin-top: 5px;
    }
    input {
      width: 80%;
      padding: 12px;
      margin: 18px 0 12px 0;
      border: 2px solid #f7cad0;
      background-color: #fffafb;
      color: #5c4b51;
      border-radius: 12px;
      font-size: 1rem;
      text-align: center;
      outline: none;
      transition: border-color 0.3s;
    }
    input:focus {
      border-color: #e07a96;
    }
    button {
      background-color: #f2849e;
      color: white;
      border: none;
      padding: 12px 30px;
      font-size: 1rem;
      font-weight: bold;
      border-radius: 12px;
      cursor: pointer;
      box-shadow: 0 4px 12px rgba(242, 132, 158, 0.35);
      transition: background 0.3s, transform 0.2s;
    }
    button:hover {
      background-color: #e06d88;
      transform: translateY(-1px);
    }
    .error {
      color: #d9534f;
      font-size: 0.9rem;
      margin-top: 12px;
      display: none;
    }
    /* Ocultamos la segunda pantalla al principio */
    #pantalla-poema {
      display: none;
      text-align: left;
    }
    .poema {
      background: #fff9fb;
      border: 1px dashed #f4acb7;
      padding: 22px;
      border-radius: 16px;
      margin: 20px 0;
      font-style: italic;
      line-height: 1.8;
      color: #6d595f;
    }
    .mision-final {
      text-align: center;
      background: #e2ece9;
      border: 1px solid #bee1e6;
      color: #4a635d;
      padding: 16px;
      border-radius: 16px;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <!-- PANTALLA 1: CONTRASEÑA -->
  <div class="caja" id="pantalla-login">
    <h1>🧁 Cube Box Mystery</h1>
    <p>Hay algo guardado acá adentro, pero solo una persona puede abrirlo.</p>
    <div class="pista">Pista: ???</div>
    <br>
    <input type="text" id="clave" placeholder="Escribí la contraseña...">
    <br>
    <button onclick="verificarClave()">Abrir cajita</button>
    <p class="error" id="mensaje-error">Esa no es la clave. Probá de nuevo.</p>
  </div>

  <!-- PANTALLA 2: POEMA Y MENSAJE -->
  <div class="caja" id="pantalla-poema">
    <h1 style="text-align: center;">✨ Lo lograste ✨</h1>
    <p style="text-align: center; font-size: 0.95rem;">Hay una palabra escondida en estas líneas. Si prestás atención, la vas a encontrar...</p>
    
    <!-- POEMA DE EJEMPLO (La palabra escondida en la 1ra letra de cada estrofa es: S - O - L) -->
    <div class="poema">
      <p>
        Siempre que hablamos el tiempo pasa distinto,<br>
        como si todo alrededor se volviera más simple<br>
        y tuviera mucho más sentido.
      </p>
      <p>
        Ojalá supieras lo linda que sos para mí,<br>
        la persona más hermosa que llegó a mi vida<br>
        y a quien más quiero ver sonreír.
      </p>
      <p>
        Lo que siento ya no me entra en un simple mensaje,<br>
        por eso armé este pequeño juego para vos,<br>
        esperando que te anime a dar el siguiente paso.
      </p>
    </div>

    <div class="mision-final">
      <p style="margin: 0 0 8px 0;"><strong>Último paso del juego:</strong></p>
      <p style="margin: 0; font-size: 0.95rem;">Cuando descubras cuál es la palabra escondida en el texto, andá a nuestro chat privado y mandámela.</p>
    </div>
  </div>

  <script>
    function verificarClave() {
      // Cambiá "???" por la contraseña real cuando la decidas (en minúsculas)
      const contrasenaCorrecta = "???"; 
      
      const ingreso = document.getElementById("clave").value.trim().toLowerCase();
      const error = document.getElementById("mensaje-error");

      if (ingreso === contrasenaCorrecta) {
        document.getElementById("pantalla-login").style.display = "none";
        document.getElementById("pantalla-poema").style.display = "block";
      } else {
        error.style.display = "block";
      }
    }

    // Permite entrar apretando la tecla Enter
    document.getElementById("clave").addEventListener("keypress", function(event) {
      if (event.key === "Enter") {
        verificarClave();
      }
    });
  </script>

</body>
</html>
<img width="1408" height="768" alt="image_b4f7d9bb" src="https://github.com/user-attachments/assets/e23481b5-3a35-46d6-b6fc-c4e0b23177b8" />
