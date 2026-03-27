<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Calculadora de Troco</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; margin-top: 50px; }
    input { margin: 5px; padding: 10px; width: 150px; }
    button { margin: 5px; padding: 10px 20px; }
    #resultado { margin-top: 20px; font-size: 18px; font-weight: bold; }
  </style>
</head>
<body>
  <h2>Calculadora de Troco</h2>
  
  <input type="number" id="produto" placeholder="Preço do produto">
  <br>
  <input type="number" id="valorPago" placeholder="Valor pago">
  <br>
  
  <button onclick="somar()">Somar</button>
  <button onclick="troco()">Calcular Troco</button>
  
  <div id="resultado"></div>
  
  <script>
    function somar() {
      let produto = parseFloat(document.getElementById("produto").value) || 0;
      let valorPago = parseFloat(document.getElementById("valorPago").value) || 0;
      let soma = produto + valorPago;
      document.getElementById("resultado").innerText = "Soma: R$ " + soma.toFixed(2);
    }
    
    function troco() {
      let produto = parseFloat(document.getElementById("produto").value) || 0;
      let valorPago = parseFloat(document.getElementById("valorPago").value) || 0;
      let troco = valorPago - produto;
      if (troco < 0) {
        document.getElementById("resultado").innerText = "Falta pagar R$ " + Math.abs(troco).toFixed(2);
      } else {
        document.getElementById("resultado").innerText = "Troco: R$ " + troco.toFixed(2);
      }
    }
  </script>
</body>
</html>
