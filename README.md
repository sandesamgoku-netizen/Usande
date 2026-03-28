<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Calculadora de Troco</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
      width: 300px;
    }
    input {
      width: 100%;
      padding: 8px;
      margin: 8px 0;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      width: 100%;
      padding: 10px;
      background: #28a745;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background: #218838;
    }
    .resultado {
      margin-top: 15px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Calculadora de Troco</h2>
    <label>Preço do Produto (R$):</label>
    <input type="number" id="preco" step="0.01">
    
    <label>Valor Pago (R$):</label>
    <input type="number" id="pago" step="0.01">
    
    <button onclick="calcular()">Calcular</button>
    
    <div class="resultado" id="resultado"></div>
  </div>

  <script>
    function calcular() {
      let preco = parseFloat(document.getElementById("preco").value);
      let pago = parseFloat(document.getElementById("pago").value);
      let resultado = document.getElementById("resultado");

      if (isNaN(preco) || isNaN(pago)) {
        resultado.innerHTML = "Por favor, insira valores válidos.";
        return;
      }

      let troco = pago - preco;
      if (troco < 0) {
        resultado.innerHTML = "Valor insuficiente! Faltam R$ " + Math.abs(troco).toFixed(2);
      } else {
        resultado.innerHTML = "Troco: R$ " + troco.toFixed(2);
      }
    }
  </script>
</body>
</html>
def calcular_troco(preco, pago):
    troco = pago - preco
    if troco < 0:
        return f"Valor insuficiente! Faltam R$ {abs(troco):.2f}"
    else:
        return f"Troco: R$ {troco:.2f}"

# Exemplo de uso
preco = float(input("Digite o preço do produto (R$): "))
pago = float(input("Digite o valor pago (R$): "))

print(calcular_troco(preco, pago  
          
      
