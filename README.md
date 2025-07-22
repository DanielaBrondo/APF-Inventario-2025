<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Inventario Fisico- Outdoor </title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    body { font-family: sans-serif; padding: 20px; max-width: 400px; margin: auto; }
    input, button { width: 100%; padding: 10px; margin-top: 10px; font-size: 16px; }
    p { font-size: 18px; margin-top: 20px; }
  </style>
</head>
<body>
 <h2 style="color: green;">Calculadora de Tolerancia ±5%</h2>
  <label>Ingresa la cantidad del TAG:
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
      const minimo = Math.round(n - tolerancia);
      const maximo = Math.round(n + tolerancia);
      document.getElementById('resultado').innerHTML = 
        `Valor Mínimo: ${minimo.toFixed(2)} <br> Valor Máximo: ${maximo.toFixed(2)} <br> Si la cantidad del TAG esta dentro de estos dos numeros, o es igual a alguno de ellos,no debemos hacer ningun cambio :)`;
    }
  </script>
</body>
</html>
