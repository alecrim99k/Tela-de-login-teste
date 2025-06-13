<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Tela de Login Avançada</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', sans-serif;
    }

    body {
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .login-container {
      background: #fff;
      padding: 40px;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.3);
      width: 100%;
      max-width: 400px;
    }

    .login-form h2 {
      text-align: center;
      margin-bottom: 25px;
      color: #333;
    }

    .input-group {
      margin-bottom: 20px;
    }

    .input-group label {
      display: block;
      margin-bottom: 5px;
      color: #555;
    }

    .input-group input {
      width: 100%;
      padding: 12px;
      border: 1px solid #ccc;
      border-radius: 8px;
      transition: 0.3s;
    }

    .input-group input:focus {
      border-color: #007bff;
      outline: none;
    }

    .password-wrapper {
      position: relative;
    }

    .password-wrapper span {
      position: absolute;
      right: 10px;
      top: 12px;
      cursor: pointer;
      user-select: none;
    }

    .remember {
      display: flex;
      justify-content: space-between;
      font-size: 0.9em;
      margin-bottom: 20px;
    }

    button {
      width: 100%;
      background-color: #007bff;
      color: white;
      border: none;
      padding: 12px;
      border-radius: 8px;
      font-size: 1em;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background-color: #0056b3;
    }

    .register {
      text-align: center;
      margin-top: 15px;
      font-size: 0.9em;
    }

    .register a {
      color: #007bff;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <div class="login-container">
    <form class="login-form" onsubmit="return validarLogin(event)">
      <h2>Bem-vindo</h2>

      <div class="input-group">
        <label for="email">Email</label>
        <input type="email" id="email" placeholder="Digite seu email" required />
      </div>

      <div class="input-group">
        <label for="senha">Senha</label>
        <div class="password-wrapper">
          <input type="password" id="senha" placeholder="Digite sua senha" required />
          <span id="toggleSenha" onclick="mostrarSenha()">👁️</span>
        </div>
      </div>

      <div class="remember">
        <label><input type="checkbox" /> Lembrar-me</label>
        <a href="#">Esqueceu a senha?</a>
      </div>

      <button type="submit">Entrar</button>
      <p class="register">Não tem conta? <a href="#">Crie uma</a></p>
    </form>
  </div>

  <script>
    function mostrarSenha() {
      const senha = document.getElementById("senha");
      const toggle = document.getElementById("toggleSenha");
      if (senha.type === "password") {
        senha.type = "text";
        toggle.textContent = "🙈";
      } else {
        senha.type = "password";
        toggle.textContent = "👁️";
      }
    }

    function validarLogin(event) {
      event.preventDefault();
      const email = document.getElementById("email").value.trim();
      const senha = document.getElementById("senha").value.trim();

      if (email === "" || senha === "") {
        alert("Por favor, preencha todos os campos.");
        return false;
      }

      // Aqui pode-se integrar com sistema real (ex: API)
      alert("Login realizado com sucesso!");
      return true;
    }
  </script>
</body>
</html>
