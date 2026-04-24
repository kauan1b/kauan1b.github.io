<html>
<head>
    <meta charset="UTF-8">
    <title>Portal de Investimentos</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            background-color: #f0f0f0;
        }

        header {
            background-color: #475569;
            color: white;
            padding: 20px;
            text-align: center;
        }

        h1 {
            text-align: center;
            margin: 20px 0;
            color: #475569;
        }

        section {
            width: 100%;
            flex: 1;
            display: flex;
            min-height: 500px;
        }

        #primeiro {
            width: 20%;
            background-color: #eff6ff;
            padding: 20px;
            border-right: 1px solid #ccc;
        }

        #segundo {
            width: 60%;
            background-color: white;
            padding: 30px;
        }

        #terceiro {
            width: 20%;
            background-color: #eff6ff;
            padding: 20px;
            border-left: 1px solid #ccc;
        }

        footer {
            background-color: #475569;
            color: white;
            text-align: center;
            padding: 15px;
            margin-top: 20px;
        }

        .acao {
            background-color: #3b82f6;
            color: white;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            text-align: center;
            cursor: pointer;
        }

        .acao:hover {
            background-color: #2563eb;
        }

        .calculadora {
            background-color: #f3f4f6;
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
        }

        input, select, button {
            padding: 12px;
            margin: 10px 0;
            width: 100%;
            font-size: 16px;
        }

        button {
            background-color: #16a34a;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #15803d;
        }

        .resultado {
            background-color: #d1fae5;
            padding: 15px;
            border-radius: 5px;
            margin-top: 15px;
            text-align: center;
            display: none;
        }

        .dica {
            background-color: #fef3c7;
            padding: 10px;
            border-radius: 5px;
            margin: 10px 0;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <header>
        <h2>📈 Portal de Investimentos</h2>
        <p>Aprenda a investir no mercado de ações brasileiro</p>
    </header>

    <h1>💰 Investimento em Ações</h1>

    <section>
        <div id="primeiro">
            <h3>💡 Curiosidades</h3>
            <div class="dica">
                <strong>Petrobras (PETR4)</strong><br>
                Uma das maiores empresas de energia do mundo.
            </div>
            <div class="dica">
                <strong>Vale (VALE3)</strong><br>
                Maior produtora de minério de ferro do mundo.
            </div>
        </div>

        <div id="segundo">
            <h5>📊 O que são ações?</h5>
            <p>Ações são pequenas partes de uma empresa...</p>

            <div class="calculadora">
                <h3>🧮 Calculadora de Investimento</h3>
                <input type="number" id="valorInvestimento" placeholder="Valor em R$">
                <select id="acaoSelecionada">
                    <option value="petr4">🛢️ PETR4 - R$ 38,50</option>
                    <option value="vale3">⛏️ VALE3 - R$ 62,80</option>
                </select>
                <button onclick="calcularAcoes()">Calcular</button>
                <div id="resultado" class="resultado"></div>
            </div>
        </div>

        <div id="terceiro">
            <h3>📊 Cotações</h3>
            <div class="acao" onclick="alert('PETR4: R$ 38,50')">
                🛢️ PETR4 → R$ 38,50
            </div>
        </div>
    </section>

    <footer>
        <p>Projeto educacional sobre ações</p>
    </footer>

    <script>
        const acoes = {
            petr4: { preco: 38.50 },
            vale3: { preco: 62.80 }
        };

        function calcularAcoes() {
            const valor = parseFloat(document.getElementById('valorInvestimento').value);
            const codigo = document.getElementById('acaoSelecionada').value;
            const acao = acoes[codigo];
            const quantidade = Math.floor(valor / acao.preco);
            document.getElementById('resultado').innerHTML = `Você pode comprar ${quantidade} ações`;
            document.getElementById('resultado').style.display = 'block';
        }
    </script>
</body>
</html>
