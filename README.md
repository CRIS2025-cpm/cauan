<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lojinha do Cauã</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #ff4500;
            color: white;
            text-align: center;
            padding: 1rem 0;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem;
        }
        .produto {
            background-color: white;
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 1rem;
            margin: 1rem 0;
            text-align: center;
        }
        .produto img {
            max-width: 100px;
            margin-bottom: 10px;
        }
        .botao-comprar, .botao-carrinho {
            background-color: #ff4500;
            color: white;
            padding: 0.5rem 1rem;
            text-decoration: none;
            border-radius: 5px;
            display: inline-block;
            margin-top: 1rem;
        }
        .botao-carrinho {
            background-color: #008000;
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1rem 0;
            margin-top: 2rem;
        }
    </style>
    <script>
        let carrinho = [];

        function adicionarAoCarrinho(produto, preco) {
            carrinho.push({ produto, preco });
            alert(`${produto} adicionado ao carrinho!`);
        }

        function finalizarCompra() {
            if (carrinho.length === 0) {
                alert("Seu carrinho está vazio!");
                return;
            }
            let mensagem = "Olá, gostaria de finalizar minha compra:\n\n";
            carrinho.forEach(item => {
                mensagem += `- ${item.produto}: R$ ${item.preco}\n`;
            });
            mensagem += "\nTotal: R$ " + carrinho.reduce((total, item) => total + item.preco, 0).toFixed(2);
            mensagem += "\n\nPor favor, confirme a compra!";
            window.open(`https://wa.me/5574999392169?text=${encodeURIComponent(mensagem)}`);
        }
    </script>
</head>
<body>
    <header>
        <h1>Lojinha do Cauã</h1>
        <p>Os melhores preços de Free Fire!</p>
    </header>
    <div class="container">
        <!-- Lista de Produtos -->
        <div class="produto">
            <h2>65 Dimas</h2>
            <p><strong>R$ 5,00</strong></p>
            <button class="botao-carrinho" onclick="adicionarAoCarrinho('65 Dimas', 5.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="produto">
            <h2>100 Dimas</h2>
            <p><strong>R$ 7,00</strong></p>
            <button class="botao-carrinho" onclick="adicionarAoCarrinho('100 Dimas', 7.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="produto">
            <h2>310 Dimas</h2>
            <p><strong>R$ 15,00</strong></p>
            <button class="botao-carrinho" onclick="adicionarAoCarrinho('310 Dimas', 15.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="produto">
            <h2>520 Dimas</h2>
            <p><strong>R$ 23,00</strong></p>
            <button class="botao-carrinho" onclick="adicionarAoCarrinho('520 Dimas', 23.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="produto">
            <h2>1.060 Dimas</h2>
            <p><strong>R$ 47,00</strong></p>
            <button class="botao-carrinho" onclick="adicionarAoCarrinho('1.060 Dimas', 47.00)">Adicionar ao Carrinho</button>
        </div>
        <div class="produto">
            <h2>Assinatura Semanal</h2>
            <p><strong>R$ 10,00</strong></p>
            <button class="botao-carrinho" onclick="adicionarAoCarrinho('Assinatura Semanal', 10.00)">Adicionar ao Carrinho</button>
        </div>
        <!-- Botão de Finalizar Compra -->
        <div style="text-align: center; margin-top: 2rem;">
            <button class="botao-comprar" onclick="finalizarCompra()">Finalizar Compra</button>
        </div>
    </div>
    <footer>
        <p>Lojinha do Cauã &copy; 2025 - Todos os direitos reservados</p>
    </footer>
</body>
</html>
