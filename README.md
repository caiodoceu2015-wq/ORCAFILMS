index.html🐬 ORCA FILMS
[🔐 Admin ]
🔍 Pesquisar filmes, séries ou novelas...
{🐬FILMES🐬}
(Nenhum filme adicionado ainda)

{🐬SÉRIES🐬}
(Nenhum serie adicionado ainda)


{🐬curtas🐬}
(nenhum curtas adicionado ainda)

 <script> function verificarSenha() { const senhaInserida = document.getElementById('senha').value; const senhaCorreta = 'tonito20'; if (senhaInserida === senhaCorreta) { document.getElementById('login-box').style.display = 'none'; document.getElementById('painel-box').style.display = 'block'; } else { alert('Senha incorreta! Use a senha tonito20 que está na tela.'); } } function deslogar() { document.getElementById('senha').value = ''; document.getElementById('login-box').style.display = 'block'; document.getElementById('painel-box').style.display = 'none'html<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ORCA FILMS</title>
    <style>
        body {
            background-color: #000000;
            color: #000000;
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
        }

        /* Borda preta por fora (body) e fundo Oval Branco por dentro */
        .painel-oval {
            background-color: #ffffff;
            border-radius: 50% / 30%; /* Cria o formato oval perfeito */
            box-shadow: 0 0 20px rgba(255,255,255,0.2);
            padding: 60px 40px;
            width: 100%;
            max-width: 500px;
            text-align: center;
            box-sizing: border-box;
        }

        h1 {
            margin: 0 0 15px 0;
            font-size: 28px;
            letter-spacing: 2px;
        }

        .btn-admin {
            background: none;
            border: 1px solid #000000;
            color: #000000;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 4px;
            font-size: 12px;
            margin-bottom: 20px;
        }

        .btn-admin:hover {
            background-color: #000000;
            color: #ffffff;
        }

        .search-bar {
            width: 80%;
            padding: 8px;
            border: 1px solid #000000;
            border-radius: 20px;
            text-align: center;
            margin-bottom: 25px;
            outline: none;
        }

        .secao {
            margin-bottom: 20px;
        }

        .titulo-secao {
            font-weight: bold;
            text-transform: uppercase;
            font-size: 14px;
            margin-bottom: 5px;
        }

        .vazio {
            font-size: 13px;
            color: #555555;
            font-style: italic;
            margin-bottom: 15px;
        }

        /* Estilos do Formulário Oculto de Login */
        .login-inputs {
            display: none;
            margin-top: 15px;
        }

        .login-inputs input {
            display: block;
            width: 70%;
            margin: 8px auto;
            padding: 8px;
            border: 1px solid #000000;
            border-radius: 4px;
            text-align: center;
        }

        .btn-entrar {
            background-color: #000000;
            color: #ffffff;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
        }

        /* Painel do Administrador Logado */
        .painel-adm-logado {
            display: none;
        }

        textarea {
            width: 80%;
            height: 60px;
            border: 1px solid #000000;
            padding: 8px;
            margin-top: 10px;
            resize: none;
        }
    </style>
</head>
<body>

<div class="painel-oval" id="tela-principal">
    
    <!-- Cabeçalho do Site -->
    <h1>🐬 ORCA FILMS</h1>
    
    <!-- Botão de Trocar para Admin / Sair -->
    <button class="btn-admin" id="btn-acao-admin" onclick="mostrarLogin()">🔐 Admin</button>

    <!-- Formulário Secreto de Login (Aparece ao clicar em Admin) -->
    <div class="login-inputs" id="caixa-login">
        <input type="email" id="email" placeholder="E-mail do Administrador">
        <input type="password" id="senha" placeholder="Senha do Administrador">
        <button class="btn-entrar" onclick="verificarAcesso()">Entrar</button>
    </div>

    <!-- Área de Gerenciamento do Admin (Apenas após o Login Correto) -->
    <div class="painel-adm-logado" id="caixa-adm-logado">
        <p><strong>Painel de Controle Ativo!</strong></p>
        <textarea placeholder="Adicionar novo filme ou série..."></textarea>
        <br>
        <button class="btn-entrar" onclick="alert('Item enviado para aprovação (Simulação)!')">Postar Conteúdo</button>
    </div>

    <hr style="border: 0; border-top: 1px dashed #000000; margin: 20px 0;" id="linha-divisoria">

    <!-- Catálogo de Exibição Público -->
    <div id="catalogo-publico">
        <input type="text" class="search-bar" placeholder="🔍 Pesquisar filmes, séries ou novelas...">

        <div class="secao">
            <div class="titulo-secao">{🐬 FILMES 🐬}</div>
            <div class="vazio">(Nenhum filme adicionado ainda)</div>
        </div>

        <div class="secao">
            <div class="titulo-secao">{🐬 SÉRIES 🐬}</div>
            <div class="vazio">(Nenhum serie adicionado ainda)</div>
        </div>

        <div class="secao">
            <div class="titulo-secao">{🐬 CURTAS 🐬}</div>
            <div class="vazio">(Nenhum curtas adicionado ainda)</div>
        </div>
    </div>

</div>

<script>
    // Abre e fecha os campos de e-mail e senha na tela
    function mostrarLogin() {
        const caixaLogin = document.getElementById('caixa-login');
        const btnAcao = document.getElementById('btn-acao-admin');
        
        if (btnAcao.innerText === "🔐 Admin") {
            if (caixaLogin.style.display === 'block') {
                caixaLogin.style.display = 'none';
            } else {
                caixaLogin.style.display = 'block';
            }
        } else {
            // Se o botão estiver como "Sair", faz o logout
            deslogar();
        }
    }

    // Validação estrita e protegida dos dados de login
    function verificarAcesso() {
        const emailInserido = document.getElementById('email').value.trim();
        const senhaInserida = document.getElementById('senha').value;

        // Dados obrigatórios escondidos aqui dentro do script
        const emailCorreto = 'caiodoceu@gmail.com';
        const senhaCorreta = 'tonito20';

        if (emailInserido === emailCorreto && senhaInserida === senhaCorreta) {
            // Oculta o formulário de login e o catálogo público
            document.getElementById('caixa-login').style.display = 'none';
            document.getElementById('catalogo-publico').style.display = 'none';
            document.getElementById('linha-divisoria').style.display = 'none';
            
            // Exibe as funções de Administrador
            document.getElementById('caixa-adm-logado').style.display = 'block';
            
            // Altera o botão superior para permitir a saída
            const btnAcao = document.getElementById('btn-acao-admin');
            btnAcao.innerText = "❌ Sair do Painel";
        } else {
            alert('Acesso Negado! Dados de administrador incorretos.');
        }
    }

    // Reseta o site de volta para o modo visitante comum
    function deslogar() {
        document.getElementById('email').value = '';
        document.getElementById('senha').value = '';
        document.getElementById('caixa-adm-logado').style.display = 'none';
        
        document.getElementById('catalogo-publico').style.display = 'block';
        document.getElementById('linha-divisoria').style.display = 'block';
        
        const btnAcao = document.getElementById('btn-acao-admin');
        btnAcao.innerText = "🔐 Admin";
    }
</script>

</body>
</html>
<script> // Abre e fecha os campos de e-mail e senha na tela function mostrarLogin() { const caixaLogin = document.getElementById('caixa-login'); const btnAcao = document.getElementById('btn-acao-admin'); if (btnAcao.innerText === "🔐 Admin") { if (caixaLogin.style.display === 'block') { caixaLogin.style.display = 'none'; } else { caixaLogin.style.display = 'block'; } } else { // Se o botão estiver como "Sair", faz o logout deslogar(); } } // Validação estrita e protegida dos dados de login function verificarAcesso() { const emailInserido = document.getElementById('email').value.trim(); const senhaInserida = document.getElementById('senha').value; // Dados obrigatórios escondidos aqui dentro do script const emailCorreto = 'caiodoceu@gmail.com'; const senhaCorreta = 'tonito20'; if (emailInserido === emailCorreto && senhaInserida === senhaCorreta) { // Oculta o formulário de login e o catálogo público document.getElementById('caixa-login').style.display = 'none'; document.getElementById('catalogo-publico').style.display = 'none'; document.getElementById('linha-divisoria').style.display = 'none'; // Exibe as funções de Administrador document.getElementById('caixa-adm-logado').style.display = 'block'; // Altera o botão superior para permitir a saída const btnAcao = document.getElementById('btn-acao-admin'); btnAcao.innerText = "❌ Sair do Painel"; } else { alert('Acesso Negado! Dados de administrador incorretos.'); } } // Reseta o site de volta para o modo visitante comum function deslogar() { document.getElementById('email').value = ''; document.getElementById('senha').value = ''; document.getElementById('caixa-adm-logado').style.display = 'none'; document.getElementById('catalogo-publico').style.display = 'block'; document.getElementById('linha-divisoria').style.display = 'block'; const btnAcao = document.getElementById('btn-acao-admin'); btnAcao.innerText = "🔐 Admin"; } </script>

