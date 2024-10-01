<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Acesso ao Lavbot</title>
    <style>
        /* Definindo as cores principais */
        :root {
            --cor-verde: #4CAF50;
            --cor-laranja: #FF9800;
            --cor-branca: #FFFFFF;
            --cor-cinza: #f4f4f4;
            --cor-preta: #333333;
        }

        /* Resetando os estilos padrões */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Estilos para o corpo da página */
        body {
            font-family: 'Arial', sans-serif;
            background-color: var(--cor-cinza);
            color: var(--cor-preta);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        /* Estilos para o contêiner principal */
        .login-container, .chatbot-container {
            background-color: var(--cor-branca);
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            padding: 40px;
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        /* Estilos para o título */
        h1 {
            color: var(--cor-verde);
            margin-bottom: 20px;
        }

        /* Estilos do input de senha */
        input[type="password"] {
            width: 100%;
            padding: 15px;
            margin: 10px 0;
            border: 1px solid var(--cor-cinza);
            border-radius: 5px;
            font-size: 16px;
        }

        /* Botão de login */
        .btn-login {
            background-color: var(--cor-laranja);
            color: var(--cor-branca);
            padding: 15px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
            margin-top: 20px;
            transition: background-color 0.3s;
        }

        /* Efeito hover no botão */
        .btn-login:hover {
            background-color: #e68900;
        }

        /* Container do chatbot */
        .chatbot-container {
            margin-top: 30px;
            display: none; /* Oculto até o login ser feito */
        }

        /* Estilos para o iframe do chatbot */
        iframe {
            width: 100%;
            height: 500px;
            border: 2px solid var(--cor-verde);
            border-radius: 10px;
        }

        /* Estilos para a logo */
        .logo {
            max-width: 200px;
            margin-bottom: 20px;
        }

    </style>
</head>
<body>

    <!-- Logo da Empresa (Visível sempre) -->
    <img src="https://1drv.ms/i/c/c46bee475153475c/IQRq7-iMUxJpS7UWA7PvA2v5ARHPaeFaVqylCnm7dZSXoxc?width=1024" alt="Logo da Empresa" class="logo" id="logoEmpresa">

    <!-- Contêiner de login -->
    <div class="login-container" id="loginContainer">
        <h1>Acessar Lavbot</h1>
        <p>Olá, funcionário! <br> Digite a senha para acessar nosso Assistente Virtual.</p>

        <!-- Input de senha -->
        <input type="password" id="senha" placeholder="Digite sua senha" onkeydown="if(event.key === 'Enter') verificarSenha()">

        <!-- Botão de login -->
        <button class="btn-login" onclick="verificarSenha()">Entrar</button>
    </div>

    <!-- Contêiner do chatbot -->
    <div class="chatbot-container" id="chatbotContainer">
        <iframe id="chatbotFrame" src=""></iframe>
    </div>

    <!-- Script para verificar a senha -->
    <script>
        // Defina a senha correta
        const senhaCorreta = "newlav2024";  // Substitua pela senha desejada

        // Função para verificar a senha
        function verificarSenha() {
            var senha = document.getElementById("senha").value;
            
            // Verifica se a senha está correta
            if (senha === senhaCorreta) {
                // Exibe o chatbot
                var chatbotContainer = document.getElementById("chatbotContainer");
                var iframe = document.getElementById("chatbotFrame");

                // Substitua pelo link do seu chatbot
                iframe.src = "https://lavbot.netlify.app"; 

                chatbotContainer.style.display = "block";

                // Esconde o campo de senha e o botão
                var loginContainer = document.getElementById("loginContainer");
                loginContainer.style.display = "none";
            } else {
                alert("Senha incorreta! Tente novamente.");
            }
        }
    </script>

</body>
</html>
