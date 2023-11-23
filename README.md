# calculadora-racao
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Ração</title>
    <script>
        function calcularQuantidade() {
            var quantidade = parseFloat(document.getElementById('quantidade').value);
            var kgPorBatida = getKgPorBatida();

            var resultado = quantidade / kgPorBatida;

            document.getElementById('resultadoQuantidade').innerHTML = "ESSA RAÇÃO TEM: " + resultado + " BATIDAS";
        }

        function calcularBatida() {
            var batidas = parseFloat(document.getElementById('batidas').value);
            var kgPorBatida = getKgPorBatida();

            var resultado = batidas * kgPorBatida;

            document.getElementById('resultadoBatida').innerHTML = "ESSA RAÇÃO TEM: " + resultado + " KG";
        }

        function getKgPorBatida() {
            var select = document.getElementById('tipoRacao');
            var tipoRacao = select.options[select.selectedIndex].value;

            switch (tipoRacao) {
                case 'postura':
                    return 900;
                case 'crescimento':
                    return 700;
                case 'macho':
                    return 700;
                case 'prepostura':
                    return 800;
                case 'iniciais':
                    return 800;
                default:
                    return 0;
            }
        }
    </script>
</head>
<body>
    <h1>Calculadora de Ração</h1>

    <h2>Calcular Quantidade</h2>
    <label for="quantidade">Digite a Quantidade:</label>
    <input type="number" id="quantidade" step="any">
    <br>
    <label for="tipoRacao">Selecione o Tipo:</label>
    <select id="tipoRacao">
        <option value="postura">Postura</option>
        <option value="crescimento">Crescimento</option>
        <option value="macho">Macho</option>
        <option value="prepostura">Pré Postura</option>
        <option value="iniciais">Iniciais</option>
    </select>
    <br>
    <button onclick="calcularQuantidade()">Calcular</button>
    <p id="resultadoQuantidade"></p>

    <h2>Calcular Batida</h2>
    <label for="batidas">Digite a Quantidade de Batidas:</label>
    <input type="number" id="batidas" step="any">
    <br>
    <label for="tipoRacaoBatida">Selecione o Tipo:</label>
    <select id="tipoRacaoBatida">
        <option value="postura">Postura</option>
        <option value="crescimento">Crescimento</option>
        <option value="macho">Macho</option>
        <option value="prepostura">Pré Postura</option>
        <option value="iniciais">Iniciais</option>
    </select>
    <br>
    <button onclick="calcularBatida()">Calcular</button>
    <p id="resultadoBatida"></p>
</body>
</html>
