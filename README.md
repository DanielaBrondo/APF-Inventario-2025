# C-lculo-de-Tolerancia
Material contado en Báscula y Reel Counter tiene el 5% de tolerancia
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Calculadora de Rango ±5%</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    body { font-family: sans-serif; padding: 20px; max-width: 400px; margin: auto; }
    input, button { width: 100%; padding: 10px; margin-top: 10px; font-size: 16px; }
    p { font-size: 18px; margin-top: 20px; }
  </style>
</head>
<body>
  <h2>Calculadora de Rango (±5%)</h2>
  <label>Ingresa un número:
    <input type="number" id="numero" placeholder="Ej. 100" />
  </label>
  <button onclick="calcular()">Calcular</button>
  <p id="resultado"></p>

  <script>
    function calcular() {
      const n = parseFloat(document.getElementById('numero').value);
      if (isNaN(n)) {
        document.getElementById('resultado').innerText = "Por favor, ingresa un número válido.";
        return;
      }
      const tolerancia = n * 0.05;
      const minimo = n - tolerancia;
      const maximo = n + tolerancia;
      document.getElementById('resultado').innerText = 
        `Mínimo: ${minimo.toFixed(2)} | Máximo: ${maximo.toFixed(2)} (±5%)`;
    }
  </script>
</body>
</html>
