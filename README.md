  <!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Calculadora Completa</title>
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
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      width: 320px;
    }
    h2 {
      text-align: center;
    }
    .display {
      width: 100%;
      height: 50px;
      font-size: 20px;
      text-align: right;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      margin-bottom: 10px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      padding: 15px;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      background: #007bff;
      color: white;
      cursor: pointer;
    }
    button:hover {
      background: #0056b3;
    }
    .resultado {
      margin-top: 15px;
      font-weight: bold;
      white-space: pre-line;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Calculadora Completa</h2>
    <input type="text" id="display" class="display" disabled>

    <div class="buttons">
      <button onclick="press('7')">7</button>
      <button onclick="press('8')">8</button>
      <button onclick="press('9')">9</button>
      <button onclick="press('/')">÷</button>

      <button onclick="press('4')">4</button>
      <button onclick="press('5')">5</button>
      <button onclick="press('6')">6</button>
      <button onclick="press('*')">×</button>

      <button onclick="press('1')">1</button>
      <button onclick="press('2')">2</button>
      <button onclick="press('3')">3</button>
      <button onclick="press('-')">−</button>

      <button onclick="press('0')">0</button>
      <button onclick="press('.')">.</button>
      <button onclick="calculate()">=</button>
      <button onclick="press('+')">+</button>

      <button onclick="clearDisplay()" style="grid-column: span 4; background:#dc3545;">C</button>
    </div>

    <label>Valor do Produto:</label>
    <input type="number" id="valor" placeholder="Ex: 50">

    <label>Valor Pago:</label>
    <input type="number" id="pago" placeholder="Ex: 100">

    <button style="background:#28a745;" onclick="calcularTroco()">Calcular Troco/Soma</button>

    <div class="resultado" id="resultado"></div>
  </div>

  <script>
    let display = document.getElementById('display');

    function press(num) {
      display.value += num;
    }

    function clearDisplay() {
      display.value = '';
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Erro";
      }
    }

    function calcularTroco() {
      let valor = parseFloat(document.getElementById('valor').value);
      let pago = parseFloat(document.getElementById('pago').value);

      if (isNaN(valor) || isNaN(pago)) {
        document.getElementById('resultado').innerText = "Preencha todos os campos!";
        return;
      }

      let soma = valor + pago;
      let troco = pago - valor;

      let mensagem = "Soma: R$ " + soma.toFixed(2) + "\n";
      if (troco < 0) {
        mensagem += "Falta: R$ " + Math.abs(troco).toFixed(2);
      } else {
        mensagem += "Troco: R$ " + troco.toFixed(2);
      }

      document.getElementById('resultado').innerText = mensagem;
    }
  </script>
</body>
</html>
