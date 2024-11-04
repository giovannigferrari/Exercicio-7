<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>6Determinação de Predominância na Liga</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
        }
        .result {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Calculadora de Predominância em uma Liga</h1>
    <label for="metalPercent">Informe o percentual de metal (%):</label>
    <input type="number" id="metalPercent" placeholder="Percentual de metal" step="0.01" />
    <br>
    <label for="ametalPercent">Informe o percentual de ametal (%):</label>
    <input type="number" id="ametalPercent" placeholder="Percentual de ametal" step="0.01" />
    <br>
    <button onclick="determinarPredominancia()">Determinar Predominância</button>
    <div class="result">
        <p><strong>Resultado:</strong> <span id="resultado"></span></p>
    </div>
    <script>
        function determinarPredominancia() {
            const metal = parseFloat(document.getElementById('metalPercent').value);
            const ametal = parseFloat(document.getElementById('ametalPercent').value);
            if (isNaN(metal) || isNaN(ametal)) {
                alert("Por favor, insira valores válidos para ambos os percentuais.");
                return;
            }
            const soma = metal + ametal;
            if (soma !== 100) {
                alert("A soma dos percentuais deve ser exatamente 100%.");
                return;
            }
            if (metal > ametal) {
                document.getElementById('resultado').textContent = "A liga é predominantemente metálica.";
            } else if (ametal > metal) {
                document.getElementById('resultado').textContent = "A liga é predominantemente ametálica.";
            } else {
                document.getElementById('resultado').textContent = "A liga tem partes iguais de metal e ametal.";
            }
        }
    </script>
</body>
</html>
