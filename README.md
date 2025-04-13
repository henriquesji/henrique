<!DOCTYPE html>
<html>
<head>
    <meta http-equiv="CONTENT-TYPE" content="text/html; charset=UTF-8">
    <link rel="stylesheet" href="styles/style.css"/>
    <title>MAP Valinhos </title>
</head>

<body>
    <h1>Mundo à parte Valinhos</h1>
    <table>
        <tr>
            <th>Dia/Mes</th>
            <th>Janeiro</th>
            <th>Fevereiro</th>
            <th>Março</th>
            <th>Abril</th>
            <th>Maio</th>
            <th>Junho</th>
            <th>Julho</th>
            <th>Agosto</th>
            <th>Setembro</th>
            <th>Outubro</th>
            <th>Novembro</th>
            <th>Dezembro</th>
            <th>Total</th>
        </tr>
        <tr>
            <th>Total</th>
            <td>19.665</td>
            <td>15.939</td>
            <td>36.408</td>
            <td>6.884</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td id="total"></td>
        </tr>
        <tr>
            <th>Avaliações</th>
            <td>08</td>
            <td>03</td>
            <td>11</td>
            <td>04</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td>0</td>
            <td></td>
            <td></td>
            <td></td>
            <td id="total-avaliacao"></td>
        </tr>
        <tr>
            <th>Visitas</th>
            <td>08</td>
            <td>07</td>
            <td>00</td>
            <td>03</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td id="total-visita"></td>
        </tr>
    </table>
    <script>
        function calcularSomaDeLinha(tabela, linhaIndex, idTotal) {
            const linha = tabela.rows[linhaIndex];
            let soma = 0;
            for (let i = 1; i <= 12; i++) {
                const valor = linha.cells[i].textContent.trim();
                if (valor !== "") {
                    const numero = parseInt(valor.replace(/\./g, ""));
                    if (!isNaN(numero)) {
                        soma += numero;
                    }
                }
            }
            const celulaTotal = document.getElementById(idTotal);
            if (celulaTotal) {
                celulaTotal.textContent = soma.toLocaleString('pt-BR');
            } else {
                console.error(`Célula com id ${idTotal} não encontrada!`);
            }
        }

        const tabela = document.querySelector('table');
        calcularSomaDeLinha(tabela, 1, 'total');
        calcularSomaDeLinha(tabela, 2, 'total-avaliacao');
        calcularSomaDeLinha(tabela, 3, 'total-visita');
    </script>
    <style>
    h1{
        text-align:center;
        color:green;
    }
    table {
  width: 100%; /* Largura total da tabela */
  border-collapse: collapse; /* Colapsa as bordas das células */
  font-family: sans-serif; /* Fonte mais comum */
}

th, td {
  border: 1px solid #ccc; /* Borda cinza para células e cabeçalho */
  padding: 8px; /* Espaçamento interno das células */
  text-align: left; /* Alinhamento do texto à esquerda */
}

th {
  background-color: #f2f2f2; /* Fundo cinza claro para o cabeçalho */
  font-weight: bold; /* Texto do cabeçalho em negrito */
}

tr:nth-child(even) {
  background-color: #f9f9f9; /* Fundo levemente diferente para linhas pares */
}

#total, #total-finalizados, #total-cancelados {
  font-weight: bold; /* Destaca a célula de total */
  text-align: right; /* Alinha o total à direita */
}

    
    </style>
</body>
</html>