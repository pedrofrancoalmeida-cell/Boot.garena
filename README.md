<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Minha Página</title>

    <!-- GOOGLE FONTS -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">

    <!-- CSS PRINCIPAL -->
    <link rel="stylesheet" href="style.css">
</head>

<body>

    <!-- NAVBAR -->
    <nav class="navbar">

        <div class="logo">
            Minha Página
        </div>

        <ul class="menu">
            <li><a href="#">Início</a></li>
            <li><a href="#">Sobre</a></li>
            <li><a href="#">Serviços</a></li>
            <li><a href="#">Contato</a></li>
        </ul>

        <button id="botaoTema">
            🌙 Modo escuro
        </button>

    </nav>

    <!-- CONTEÚDO PRINCIPAL -->
    <main>

        <h1>Minha página</h1>

        <p>
            Esta página possui modo claro e modo escuro.
        </p>

        <button id="botaoMensagem">
            Alterar texto
        </button>

        <p id="mensagem">
            Texto original
        </p>

    </main>

    <!-- JAVASCRIPT -->
    <script src="script.js"></script>

</body>

</html>/*
================================
CONFIGURAÇÃO GERAL
================================
*/

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: "Poppins", sans-serif;
    background-color: white;
    color: #222;
    transition: 0.3s;
}

/*
================================
NAVBAR
================================
*/

.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 50px;
    background-color: #222;
    color: white;
}

/*
================================
LOGO
================================
*/

.logo {
    font-size: 24px;
    font-weight: 700;
}

/*
================================
MENU
================================
*/

.menu {
    display: flex;
    gap: 30px;
    list-style: none;
}

.menu a {
    color: white;
    font-size: 16px;
    font-weight: 500;
    text-decoration: none;
    transition: 0.3s;
}

.menu a:hover {
    opacity: 0.7;
}

/*
================================
BOTÕES
================================
*/

button {
    padding: 10px 18px;
    border-radius: 8px;
    border: none;
    background-color: #eee;
    color: #222;
    transition: 0.3s;
    cursor: pointer;
}

button:hover {
    transform: scale(1.05);
}

/*
================================
CONTEÚDO
================================
*/

main {
    text-align: center;
    padding: 100px 20px;
}

h1 {
    font-size: 40px;
    margin-bottom: 20px;
}

p {
    margin-bottom: 30px;
}

/*
================================
MODO ESCURO
================================
*/

body.escuro {
    background-color: #222;
    color: white;
}

.escuro .navbar {
    background-color: #111;
}

.escuro button {
    background-color: #444;
    color: white;
}// ========================================
// MODO ESCURO
// ========================================

const botaoTema = document.getElementById("botaoTema");

function alternarTema() {

    document.body.classList.toggle("escuro");

    if (document.body.classList.contains("escuro")) {
        botaoTema.textContent = "☀️ Modo claro";
    } else {
        botaoTema.textContent = "🌙 Modo escuro";
    }
}

botaoTema.addEventListener("click", alternarTema);


// ========================================
// ALTERAR TEXTO
// ========================================

const botaoMensagem = document.getElementById("botaoMensagem");
const mensagem = document.getElementById("mensagem");

function alterarTexto() {
    mensagem.textContent = "O texto foi alterado pelo JavaScript!";
}

botaoMensagem.addEventListener("click", alterarTexto);
