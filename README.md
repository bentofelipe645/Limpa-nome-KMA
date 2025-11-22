<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Limpa Nome KMA - Atendimento Online</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
* {box-sizing: border-box; margin:0; padding:0;}
body {
    font-family: Arial, Helvetica, sans-serif;
    background: radial-gradient(circle at top, #1a237e, #0b102f 45%, #050712 100%);
    min-height:100vh; display:flex; flex-direction:column;
    align-items:center; padding:20px 10px; color:#f5f5f5;
}
header {width:100%; max-width:520px; text-align:center; margin-bottom:15px;}
header h1 {font-size:22px; font-weight:700; margin-top:8px;}
header p {font-size:13px; color:#c5cae9;}

/* LOGO REAL */
.logo-real {
    width: 100%;
    max-width: 360px;
    margin: 0 auto 8px auto;
}
.logo-real img {
    width:100%;
    height:auto;
    border-radius:18px;
    box-shadow:0 10px 25px rgba(0,0,0,0.6);
}

/* SCORE ANIMADO */
.score-box {
    width:100%; max-width:520px;
    background:#0d1333;
    padding:15px;
    border-radius:14px;
    margin-bottom:20px;
    border:1px solid rgba(255,255,255,0.15);
    text-align:center;
}
.score-title {font-size:14px; margin-bottom:8px; color:#bcd0ff;}
.score-bar {
    width:100%; height:22px; background:#1b224a; border-radius:20px;
    overflow:hidden; border:1px solid #4451a3; margin-bottom:10px;
}
.score-fill {
    height:100%; width:0%;
    background:linear-gradient(90deg,#00e676,#00c853,#00bfa5);
    border-radius:20px;
    animation:scoreAnim 5s forwards;
}
@keyframes scoreAnim {from {width:10%;} to {width:92%;}}
.score-value {font-size:18px; font-weight:700; color:#69f0ae;}

/* TESTEMUNHOS */
.testemunhos {width:100%; max-width:520px; margin-top:10px;}
.testemunho-card {
    background:rgba(255,255,255,0.08);
    padding:16px; border-radius:12px; margin-bottom:12px;
    border:1px solid rgba(255,255,255,0.12);
    box-shadow:0 4px 12px rgba(0,0,0,0.4);
}
.testemunho-card h4 {font-size:15px; margin-bottom:6px; color:white;}
.testemunho-card p {font-size:13px; color:#d0d4ff;}

/* FORM */
.container {
    width:100%; max-width:520px;
    background:linear-gradient(145deg, rgba(255,255,255,0.15), rgba(255,255,255,0.04));
    border-radius:18px; padding:20px 18px 22px;
    box-shadow:0 18px 40px rgba(0,0,0,0.55);
    backdrop-filter:blur(16px);
    border:1px solid rgba(255,255,255,0.15);
    margin-top:12px;
}
label {font-weight:600; display:block; margin-top:10px; margin-bottom:4px; font-size:13px;}
input, textarea {
    width:100%; padding:10px 11px; border-radius:10px;
    border:1px solid rgba(255,255,255,0.28);
    background:rgba(3,7,30,0.8); color:#e8eaf6;
    font-size:14px;
}
input::placeholder, textarea::placeholder {color:#9fa8da; font-size:13px;}
textarea {resize:vertical; min-height:80px;}
.form-row {display:flex; flex-direction:column; gap:10px;}
@media (min-width:460px){
    .form-row {flex-direction:row;}
    .field {flex:1;}
}

button {
    width:100%; padding:13px; margin-top:16px;
    background:linear-gradient(135deg,#7c4dff,#536dfe);
    color:white; border:none; border-radius:999px; font-size:16px;
    font-weight:600; cursor:pointer;
}
button:hover {
    filter:brightness(1.05);
}
.footer-info {
    width:100%; max-width:520px;
    text-align:center;
    margin-top:14px;
    font-size:11px; color:#c5cae9;
}
</style>
</head>
<body>

<header>
    <div class="logo-real">
        <img src="https://i.imgur.com/OE28XwR.png" alt="Logo Limpa Nome KMA">
    </div>
    <h1>Limpeza de Nome SPC & SERASA</h1>
    <p>Confidencial, rápido e verificado.</p>
</header>

<div class="score-box">
    <div class="score-title">Seu score estimado após a limpeza</div>
    <div class="score-bar"><div class="score-fill"></div></div>
    <div class="score-value">Score: 920+</div>
</div>

<div class="testemunhos">
    <div class="testemunho-card"><h4>⭐ Marcos S. – SP</h4><p>"Meu nome estava preso há anos e resolveram tudo em 3 dias."</p></div>
    <div class="testemunho-card"><h4>⭐ Juliana R. – BA</h4><p>"Meu score subiu para 900 e consegui financiamento."</p></div>
    <div class="testemunho-card"><h4>⭐ Renato M. – MG</h4><p>"48h e estava limpo, inacreditável."</p></div>
    <div class="testemunho-card"><h4>⭐ Patrícia V. – RJ</h4><p>"Atendimento perfeito e rápido."</p></div>
</div>

<div class="container">
    <form onsubmit="sendWhatsApp(event)">
        <label>Nome Completo</label>
        <input type="text" id="nome" required>

        <div class="form-row">
            <div class="field"><label>CPF</label><input type="text" id="cpf" required></div>
            <div class="field"><label>Telefone / WhatsApp</label><input type="text" id="telefone" required></div>
        </div>

        <div class="form-row">
            <div class="field"><label>E-mail</label><input type="email" id="email" required></div>
            <div class="field"><label>Data de Nascimento</label><input type="date" id="nascimento" required></div>
        </div>

        <label>Motivo da Restrição</label>
        <textarea id="motivo" required></textarea>

        <label>Valor aproximado da dívida (R$)</label>
        <input type="text" id="valor" required>

        <button type="submit">📲 ENVIAR SOLICITAÇÃO PELO WHATSAPP</button>
    </form>
</div>

<div class="footer-info">
    Sua solicitação será enviada diretamente ao WhatsApp oficial da <strong>Limpa Nome KMA</strong>.<br>
    Taxa: R$ 500,00 a cada R$ 10.000,00 de dívida.
</div>

<script>
function parseValorBR(v){
    if(!v) return 0;
    v=v.replace(/\\./g,"").replace(/,/g,".");
    return parseFloat(v)||0;
}
function formatBR(v){
    return v.toLocaleString("pt-BR",{minimumFractionDigits:2,maximumFractionDigits:2});
}

function sendWhatsApp(event){
    event.preventDefault();

    var nome=document.getElementById('nome').value;
    var cpf=document.getElementById('cpf').value;
    var telefone=document.getElementById('telefone').value;
    var email=document.getElementById('email').value;
    var nasc=document.getElementById('nascimento').value;
    var motivo=document.getElementById('motivo').value;
    var valor=document.getElementById('valor').value;

    var taxa = (parseValorBR(valor)/10000)*500;

    var msg =
        "SOLICITAÇÃO LIMPA NOME KMA%0A%0A"+
        "Nome: "+nome+"%0A"+
        "CPF: "+cpf+"%0A"+
        "Telefone: "+telefone+"%0A"+
        "Email: "+email+"%0A"+
        "Nascimento: "+nasc+"%0A"+
        "Motivo: "+motivo+"%0A"+
        "Dívida informada: "+valor+"%0A"+
        "Taxa calculada: R$ "+formatBR(taxa);

    window.open("https://wa.me/5598988548606?text="+msg,"_blank");
}
</script>

</body>
</html>
