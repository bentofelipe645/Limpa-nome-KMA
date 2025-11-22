<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Limpa Nome KMA - Atendimento Online</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: radial-gradient(circle at top, #1a237e, #0b102f 45%, #050712 100%);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px 10px;
      color: #f5f5f5;
    }

    header {
      width: 100%;
      max-width: 520px;
      text-align: center;
      margin-bottom: 16px;
    }

    /* “Logo” visual */
    .logo-caixa {
      width: 210px;
      height: 70px;
      margin: 0 auto 12px auto;
      border-radius: 999px;
      background: linear-gradient(135deg, #0d47a1, #42a5f5);
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.7);
      position: relative;
      overflow: hidden;
    }

    .logo-caixa::before {
      content: "";
      position: absolute;
      width: 80px;
      height: 80px;
      background: radial-gradient(circle, rgba(255,255,255,0.35), transparent 60%);
      top: -20px;
      left: -10px;
      opacity: 0.9;
    }

    .logo-texto-principal {
      position: relative;
      font-weight: 800;
      letter-spacing: 1px;
      text-transform: uppercase;
      font-size: 16px;
      text-shadow: 0 0 6px rgba(0,0,0,0.6);
    }

    .logo-texto-principal span {
      display: block;
      line-height: 1.1;
    }

    .logo-texto-principal span:nth-child(1) {
      font-size: 13px;
      opacity: 0.9;
    }

    .logo-texto-principal span:nth-child(2) {
      font-size: 18px;
      color: #e3f2fd;
    }

    header h1 {
      font-size: 24px;
      font-weight: 700;
      margin-bottom: 4px;
    }

    header p {
      font-size: 13px;
      color: #c5cae9;
    }

    /* SCORE ANIMADO */
    .score-box {
      width: 100%;
      max-width: 520px;
      background: #0d1333;
      padding: 15px;
      border-radius: 14px;
      margin-bottom: 18px;
      border: 1px solid rgba(255,255,255,0.15);
      text-align: center;
      box-shadow: 0 10px 25px rgba(0,0,0,0.55);
    }

    .score-title {
      font-size: 14px;
      margin-bottom: 8px;
      color: #bcd0ff;
    }

    .score-bar {
      width: 100%;
      height: 22px;
      background: #1b224a;
      border-radius: 20px;
      overflow: hidden;
      border: 1px solid #4451a3;
      margin-bottom: 10px;
    }

    .score-fill {
      height: 100%;
      width: 0%;
      background: linear-gradient(90deg,#00e676,#00c853,#00bfa5);
      border-radius: 20px;
      animation: scoreAnim 5s forwards;
    }

    @keyframes scoreAnim {
      from { width: 10%; }
      to   { width: 92%; }
    }

    .score-value {
      font-size: 18px;
      font-weight: 700;
      color: #69f0ae;
    }

    /* TESTEMUNHOS */
    .testemunhos {
      width: 100%;
      max-width: 520px;
      margin-top: 8px;
      margin-bottom: 10px;
    }

    .testemunho-card {
      background: rgba(255,255,255,0.08);
      padding: 12px 14px;
      border-radius: 12px;
      margin-bottom: 8px;
      border: 1px solid rgba(255,255,255,0.12);
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
    }

    .testemunho-card h4 {
      font-size: 14px;
      margin-bottom: 4px;
      color: #ffffff;
    }

    .testemunho-card p {
      font-size: 12px;
      color: #d0d4ff;
    }

    /* FORMULÁRIO */
    .container {
      width: 100%;
      max-width: 520px;
      background: linear-gradient(145deg, rgba(255,255,255,0.15), rgba(255,255,255,0.04));
      border-radius: 18px;
      padding: 18px 16px 20px;
      box-shadow: 0 18px 40px rgba(0,0,0,0.55);
      backdrop-filter: blur(16px);
      border: 1px solid rgba(255,255,255,0.15);
      margin-top: 4px;
    }

    .container h2 {
      font-size: 18px;
      margin-bottom: 4px;
    }

    .container .subtitle {
      font-size: 12px;
      color: #d1d5ff;
      margin-bottom: 10px;
    }

    label {
      font-weight: 600;
      display: block;
      margin-top: 10px;
      margin-bottom: 4px;
      font-size: 13px;
    }

    input, textarea {
      width: 100%;
      padding: 10px 11px;
      border-radius: 10px;
      border: 1px solid rgba(255,255,255,0.28);
      font-size: 14px;
      background: rgba(3,7,30,0.8);
      color: #e8eaf6;
      outline: none;
    }

    input::placeholder,
    textarea::placeholder {
      color: #9fa8da;
      font-size: 13px;
    }

    textarea {
      resize: vertical;
      min-height: 80px;
    }

    .form-row {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .field {
      flex: 1;
    }

    @media (min-width: 460px) {
      .form-row {
        flex-direction: row;
      }
    }

    button {
      width: 100%;
      padding: 13px;
      margin-top: 16px;
      background: linear-gradient(135deg,#25d366,#128c7e);
      color: white;
      font-size: 16px;
      font-weight: 600;
      border: none;
      border-radius: 999px;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.45);
    }

    button:hover {
      filter: brightness(1.05);
    }

    .footer-info {
      width: 100%;
      max-width: 520px;
      text-align: center;
      margin-top: 14px;
      font-size: 11px;
      color: #c5cae9;
    }
  </style>
</head>
<body>

  <header>
    <div class="logo-caixa">
      <div class="logo-texto-principal">
        <span>Sistema</span>
        <span>LIMPA NOME KMA</span>
      </div>
    </div>

    <h1>Limpa Nome KMA</h1>
    <p>Atendimento rápido • Consulta e negociação via WhatsApp</p>
  </header>

  <!-- SCORE -->
  <div class="score-box">
    <div class="score-title">Score estimado após a limpeza (simulação)</div>
    <div class="score-bar">
      <div class="score-fill"></div>
    </div>
    <div class="score-value">Score: 920+</div>
  </div>

  <!-- TESTEMUNHOS -->
  <div class="testemunhos">
    <div class="testemunho-card">
      <h4>⭐ Marcos S. – São Paulo/SP</h4>
      <p>"Em 3 dias meu nome saiu do SPC e SERASA. Atendimento muito atencioso!"</p>
    </div>
    <div class="testemunho-card">
      <h4>⭐ Juliana R. – Salvador/BA</h4>
      <p>"Meu score passou de 300 para mais de 900 e consegui financiamento aprovado."</p>
    </div>
    <div class="testemunho-card">
      <h4>⭐ Renato M. – Belo Horizonte/MG</h4>
      <p>"Achei rápido demais, em menos de 48 horas já estava tudo limpo."</p>
    </div>
    <div class="testemunho-card">
      <h4>⭐ Patrícia V. – Rio de Janeiro/RJ</h4>
      <p>"Resolveram tudo pelo WhatsApp, sem burocracia. Super recomendo."</p>
    </div>
  </div>

  <!-- FORMULÁRIO -->
  <div class="container">
    <h2>Solicitação de Limpeza de Nome</h2>
    <p class="subtitle">Preencha seus dados que calculamos a taxa e enviamos direto para o atendimento oficial no WhatsApp.</p>

    <form onsubmit="enviarWhatsApp(event)">
      <label>Nome Completo</label>
      <input type="text" id="nome" placeholder="Digite seu nome completo" required>

      <div class="form-row">
        <div class="field">
          <label>CPF</label>
          <input type="text" id="cpf" placeholder="000.000.000-00" required>
        </div>
        <div class="field">
          <label>Telefone / WhatsApp</label>
          <input type="text" id="telefone" placeholder="(00) 00000-0000" required>
        </div>
      </div>

      <div class="form-row">
        <div class="field">
          <label>E-mail</label>
          <input type="email" id="email" placeholder="seuemail@exemplo.com" required>
        </div>
        <div class="field">
          <label>Data de Nascimento</label>
          <input type="date" id="nascimento" required>
        </div>
      </div>

      <label>Motivo da Restrição</label>
      <textarea id="motivo" placeholder="Explique sua situação (atraso em cartão, empréstimo, conta em aberto, etc.)" required></textarea>

      <label>Valor aproximado das dívidas (R$)</label>
      <input type="text" id="valor" placeholder="Ex.: 10.000" required>

      <button type="submit">📲 Enviar solicitação pelo WhatsApp</button>
    </form>
  </div>

  <div class="footer-info">
    Sua solicitação será encaminhada para o atendimento oficial da
    <strong>Limpa Nome KMA</strong> via WhatsApp.<br>
    Taxa de serviço: <strong>R$ 500,00 a cada R$ 10.000,00</strong> de dívida informada.
  </div>

  <script>
    function parseValorBR(v) {
      if (!v) return 0;
      v = v.replace(/\./g, "").replace(/,/g, ".");
      return parseFloat(v) || 0;
    }

    function formatBR(v) {
      return v.toLocaleString("pt-BR", {
        minimumFractionDigits: 2,
        maximumFractionDigits: 2
      });
    }

    function enviarWhatsApp(e) {
      e.preventDefault();

      var nome = document.getElementById("nome").value;
      var cpf = document.getElementById("cpf").value;
      var telefone = document.getElementById("telefone").value;
      var email = document.getElementById("email").value;
      var nasc = document.getElementById("nascimento").value;
      var motivo = document.getElementById("motivo").value;
      var valorStr = document.getElementById("valor").value;

      var divida = parseValorBR(valorStr);
      var taxa = (divida / 10000) * 500; // R$ 500,00 a cada 10.000 de dívida

      var msg =
        "SOLICITAÇÃO LIMPA NOME KMA%0A%0A" +
        "👤 Nome: " + nome + "%0A" +
        "📄 CPF: " + cpf + "%0A" +
        "📱 WhatsApp do cliente: " + telefone + "%0A" +
        "📧 E-mail: " + email + "%0A" +
        "🎂 Data de nascimento: " + nasc + "%0A" +
        "📝 Motivo da restrição: " + motivo + "%0A" +
        "💰 Valor aproximado das dívidas (informado pelo cliente): " + valorStr + "%0A%0A" +
        "📌 Taxa de serviço (R$ 500,00 a cada R$ 10.000,00 de dívida): R$ " + formatBR(taxa);

      // Seu número de atendimento (com DDI 55)
      var url = "https://wa.me/5598988548606?text=" + msg;
      window.open(url, "_blank");
    }
  </script>

</body>
</html>
