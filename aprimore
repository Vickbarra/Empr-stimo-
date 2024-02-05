
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Formulário de Empréstimo</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/sweetalert2@10">
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #f4f4f4;
      color: #333;
      margin: 20px;
    }

    form {
      max-width: 600px;
      margin: 0 auto;
      background-color: #ffffff;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
    }

    label {
      display: block;
      margin-bottom: 10px;
      color: #333;
    }

    input, select {
      width: 100%;
      padding: 12px;
      margin-bottom: 20px;
      box-sizing: border-box;
      border: 1px solid #3498db;
      border-radius: 5px;
      transition: border-color 0.3s ease-in-out;
    }

    input:focus, select:focus {
      border-color: #2ecc71;
      outline: none;
    }

    .input-group {
      position: relative;
    }

    .input-group-addon {
      position: absolute;
      top: 50%;
      right: 15px;
      transform: translateY(-50%);
    }

    button {
      background-color: #2ecc71;
      color: #fff;
      padding: 15px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
      transition: background-color 0.3s ease-in-out;
    }

    button:hover {
      background-color: #27ae60;
    }

    .success-message {
      color: #2ecc71;
      margin-top: 15px;
    }

    #textCarousel {
      max-width: 100%;
      margin-top: 30px;
      color: #333;
    }

    #textCarousel .carousel-inner {
      text-align: center;
    }

    #textCarousel .carousel-inner p {
      font-size: 18px;
      margin: 20px;
    }
  </style>
</head>
<body>

<!-- Carrossel de Texto -->
<div id="textCarousel" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <p>CONQUISTE SEUS SONHOS . SEJA SÉRIO COM OS NOSSO SERVIÇO.</p>
    </div>
    <div class="carousel-item">
      <p>CONQUISTE SEUS SONHOS . SEJA SÉRIO COM OS NOSSO SERVIÇO.</p>
    </div>
    <div class="carousel-item">
      <p>CONQUISTE SEUS SONHOS . SEJA SÉRIO COM OS NOSSO SERVIÇO.</p>
    </div>
    <div class="carousel-item">
      <p>CONQUISTE SEUS SONHOS . SEJA SÉRIO COM OS NOSSO SERVIÇOS.</p>
    </div>
  </div>
</div>

<form id="loanForm">
  <label for="fullName">Nome Completo:</label>
  <input type="text" id="fullName" placeholder="Seu Nome Completo" required>

  <label for="idCard">Bilhete de Identidade:</label>
  <input type="text" id="idCard" placeholder="Número do Bilhete de Identidade" required>

  <label for="age">Idade:</label>
  <input type="number" id="age" placeholder="Sua Idade" required>

  <label for="phoneNumber">Número de Telefone:</label>
  <input type="tel" id="phoneNumber" placeholder="Seu Número de Telefone" required>

  <label for="neighborhood">Bairro:</label>
  <input type="text" id="neighborhood" placeholder="Seu Bairro" required>

  <label for="loanAmount">Valor do Empréstimo (MZN):</label>
  <div class="input-group">
    <span class="input-group-addon"><i class="fas fa-money-bill"></i></span>
    <input type="number" id="loanAmount" placeholder="Quantia Desejada" required>
  </div>

  <label for="collateral">Garantia em Caso de:</label>
  <input type="text" id="collateral" placeholder="Sua Garantia" required>

  <label for="repaymentDate">Data de Reembolso:</label>
  <input type="date" id="repaymentDate" required>

  <label for="signature">Assinatura:</label>
  <input type="text" id="signature" placeholder="Sua Assinatura" required>

  <button type="button" onclick="submitForm()">Enviar Solicitação</button>
  <p class="success-message" id="successMessage"></p>
</form>

<<script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-database.js"></script>
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@10"></script>

<script>
  // Configurar o Firebase com as suas informaçõesconst firebaseConfig = {
      apiKey: "AIzaSyB3giUQFfwMb4B66xdsVxZPA6g0TX7wQlg",
      authDomain: "folevila.firebaseapp.com",
      databaseURL: "https://folevila-default-rtdb.firebaseio.com",
      projectId: "folevila",
      storageBucket: "folevila.appspot.com",
      messagingSenderId: "424163311320",
      appId: "1:424163311320:web:85a7e99f738d32bccda1ad",
      measurementId: "G-V7E7WVY72R"
    };
    firebase.initializeApp(firebaseConfig);


  // Referência ao nó do banco de dados
  const database = firebase.database();

  function submitForm() {
    // Validar entrada...

    // Obter valores dos campos
    const fullName = document.getElementById('fullName').value;
    const idCard = document.getElementById('idCard').value;
    const age = document.getElementById('age').value;
    const phoneNumber = document.getElementById('phoneNumber').value;
    const neighborhood = document.getElementById('neighborhood').value;
    const loanAmount = document.getElementById('loanAmount').value;
    const collateral = document.getElementById('collateral').value;
    const repaymentDate = document.getElementById('repaymentDate').value;
    const signature = document.getElementById('signature').value;

    if (!fullName || !idCard || !age || !phoneNumber || !neighborhood || !loanAmount || !collateral || !repaymentDate || !signature) {
      Swal.fire({
        icon: 'error',
        title: 'Oops...',
        text: 'Por favor, preencha todos os campos!',
      });
      return;
    }

    // Criar objeto de dados
    const loanData = {
      fullName,
      idCard,
      age,
      phoneNumber,
      neighborhood,
      loanAmount,
      collateral,
      repaymentDate,
      signature,
    };

    // Enviar dados para o Firebase Realtime Database
    database.ref('pedidos_emprestimo').push(loanData)
      .then(() => {
        Swal.fire({
          icon: 'success',
          title: 'Sucesso!',
          text: 'Formulário enviado com sucesso!',
        });
        document.getElementById('successMessage').textContent = "Formulário enviado com sucesso!";
        
        // Limpar os campos após o envio
        document.getElementById('loanForm').reset();
      })
      .catch((error) => {
        console.error('Erro ao enviar dados para o Firebase:', error);
        Swal.fire({
          icon: 'error',
          title: 'Oops...',
          text: 'Erro ao enviar dados para o Firebase!',
        });
      });
  }
</script>

<script>
  // Ativar carrossel de texto
  $(document).ready(function(){
    $('#textCarousel').carousel({
      interval: 5000 // Trocar a cada 5 segundos
    });
  });
</script>

</body>
</html>
