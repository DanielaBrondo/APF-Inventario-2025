<html lang="es">
<head>
  <meta charset="UTF-8" />
  <h2 style="color: green; text-align: center;">Outdoor</h2>

  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    body { font-family: sans-serif; padding: 20px; max-width: 400px; margin: auto; }
    input, button { width: 100%; padding: 10px; margin-top: 10px; font-size: 16px; }
    p { font-size: 18px; margin-top: 20px; }
    #mensaje {
      font-weight: bold;
      margin-top: 15px;
      font-size: 18px;
    }
    .dentro {
      color: green;
    }
    .fuera {
      color: red;
    }
  </style>
</head>
<body>
  <h2 style="color: green; style="text-align: center;">Calculo de Tolerancia ±5%</h2>
  <h4 style=" text-align: center;">Metodo de conteo en Bascula o Reel Counter</h4>
  <label>Ingresa la cantidad del TAG:
    <input type="number" id="numero1" placeholder="Ej. 100" />
  </label>

  <label>Ingresa la cantidad Auditada:
    <input type="number" id="numero2" placeholder="Ej. 104" />
  </label>

  <button onclick="calcular()">Calcular</button>

  <p id="resultado"></p>
  <p id="mensaje"></p>

  <script>
    function calcular() {
      const n1 = parseFloat(document.getElementById('numero1').value);
      const n2 = parseFloat(document.getElementById('numero2').value);

      if (isNaN(n1) || isNaN(n2)) {
        document.getElementById('resultado').innerText = "Por favor, ingresa números válidos.";
        document.getElementById('mensaje').innerText = "";
        return;
      }

      const tolerancia = n1 * 0.05;
      const minimo = Math.round(n1 - tolerancia);
      const maximo = Math.round(n1 + tolerancia);

      document.getElementById('resultado').innerHTML = 
        `Valor Mínimo: ${minimo} <br> Valor Máximo: ${maximo} <br>`;

      const mensaje = document.getElementById('mensaje');
      if (n2 >= minimo && n2 <= maximo) {
        mensaje.innerText = "Cantidad dentro de tolerancia, no debemos hacer ningun cambio 🙂";
        mensaje.className = "dentro";
      } else {
        mensaje.innerText = "Cantidad fuera de tolerancia, el TAG está equivocado 😞";
        mensaje.className = "fuera";
      }
    }
  </script>
</body>
</html>
