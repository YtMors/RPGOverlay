<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Painel de Controle</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #111;
      color: #fff;
      padding: 20px;
    }

    input[type="number"], button {
      font-size: 18px;
      margin: 10px 0;
      padding: 5px;
    }

    label {
      display: block;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <h2>Painel de Controle do Mago</h2>

  <label>Vida:
    <input type="number" id="vida" min="0" max="12" value="12">
  </label>

  <label>Mana:
    <input type="number" id="mana" min="0" max="9" value="9">
  </label>

  <label>
    <input type="checkbox" id="armadura"> Armadura Mágica (+8 CA)
  </label>

  <br>
  <button onclick="atualizar()">Atualizar</button>

  <script>
    function atualizar() {
      localStorage.setItem("vida", document.getElementById("vida").value);
      localStorage.setItem("mana", document.getElementById("mana").value);
      localStorage.setItem("armaduraMagica", document.getElementById("armadura").checked);
    }

    // Carrega os valores atuais se existirem
    window.onload = () => {
      document.getElementById("vida").value = localStorage.getItem("vida") || 12;
      document.getElementById("mana").value = localStorage.getItem("mana") || 9;
      document.getElementById("armadura").checked = localStorage.getItem("armaduraMagica") === "true";
    };
  </script>
</body>
</html>
