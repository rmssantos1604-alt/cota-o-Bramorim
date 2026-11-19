
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bramorim | Dashboard de Cotações</title>

<style>
:root {
  --navy: #102b4e;
  --blue: #1769aa;
  --light: #f2f5f9;
  --white: #ffffff;
  --text: #263449;
  --muted: #748196;
  --border: #e3e9f0;
}
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: var(--light);
  color: var(--text);
}
.sidebar {
  position: fixed;
  inset: 0 auto 0 0;
  width: 245px;
  background: var(--navy);
  color: white;
  padding: 26px 16px;
}
.logo {
  font-size: 22px;
  font-weight: bold;
  padding: 0 12px 8px;
}
.subtitle {
  color: #b9c9dc;
  font-size: 12px;
  padding: 0 12px 28px;
}
.menu-label {
  color: #91a9c4;
  font-size: 11px;
  padding: 12px;
  text-transform: uppercase;
}
.menu button {
  width: 100%;
  padding: 13px 12px;
  border: 0;
  border-radius: 7px;
  background: transparent;
  color: white;
  text-align: left;
  cursor: pointer;
  font-size: 14px;
  margin-bottom: 4px;
}
.menu button:hover, .menu button.active {
  background: #24476d;
}
.main {
  margin-left: 245px;
  padding: 28px;
}
.topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
  margin-bottom: 28px;
}
h1 { font-size: 25px; margin: 0 0 7px; }
.description { color: var(--muted); font-size: 13px; }
.user {
  background: white;
  padding: 11px 16px;
  border-radius: 9px;
  font-size: 13px;
}
.notice {
  background: #fff6df;
  color: #805d13;
  padding: 12px 15px;
  border-radius: 8px;
  font-size: 13px;
  margin-bottom: 20px;
}
.cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
  margin-bottom: 22px;
}
.card {
  background: white;
  padding: 20px;
  border-radius: 11px;
  border: 1px solid var(--border);
}
.card small { color: var(--muted); }
.number {
  font-size: 28px;
  font-weight: bold;
  margin-top: 13px;
  color: var(--navy);
}
.panel {
  background: white;
  padding: 22px;
  border-radius: 11px;
  border: 1px solid var(--border);
  margin-bottom: 20px;
}
.panel h2 { font-size: 17px; margin-top: 0; }
table {
  width: 100%;
  border-collapse: collapse;
  font-size: 13px;
}
th, td {
  padding: 13px 10px;
  text-align: left;
  border-bottom: 1px solid var(--border);
}
th { color: var(--muted); font-weight: 600; }
.status {
  padding: 5px 9px;
  border-radius: 20px;
  font-size: 11px;
  background: #e8f5ec;
  color: #24733c;
}
.pending { background: #fff2d9; color: #95620b; }
.section { display: none; }
.section.active { display: block; }
.filters {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-bottom: 18px;
}
input, select {
  padding: 11px;
  border: 1px solid var(--border);
  border-radius: 7px;
  background: white;
}
button.primary {
  background: var(--blue);
  color: white;
  border: 0;
  padding: 11px 15px;
  border-radius: 7px;
  cursor: pointer;
}
@media(max-width:900px) {
  .sidebar { width: 190px; }
  .main { margin-left: 190px; padding: 18px; }
  .cards { grid-template-columns: repeat(2, 1fr); }
}
@media(max-width:600px) {
  .sidebar { position: relative; width: 100%; }
  .main { margin-left: 0; }
  .cards { grid-template-columns: 1fr 1fr; }
  .topbar { align-items: flex-start; flex-direction: column; }
  .panel { overflow-x: auto; }
}
</style>
</head>

<body>

<aside class="sidebar">
  <div class="logo">BRAMORIM</div>
  <div class="subtitle">DASHBOARD DE COTAÇÕES</div>

  <div class="menu-label">Menu principal</div>
  <nav class="menu">
    <button class="active" onclick="showSection('dashboard',this)">▦ Dashboard</button>
    <button onclick="showSection('emails',this)">✉ E-mails</button>
    <button onclick="showSection('historico',this)">◷ Histórico</button>
    <button onclick="showSection('pendencias',this)">◷ Pendências</button>
    <button onclick="showSection('clientes',this)">♙ Clientes</button>
    <button onclick="showSection('funcionarios',this)">♧ Funcionários</button>
    <button onclick="showSection('relatorios',this)">▤ Relatórios</button>
    <button onclick="showSection('configuracoes',this)">⚙ Configurações</button>
  </nav>
</aside>

<main class="main">
  <header class="topbar">
    <div>
      <h1 id="pageTitle">Dashboard</h1>
      <div class="description">Central de gestão de cotações • Pricing</div>
    </div>
    <div class="user">Gestão | Bramorim</div>
  </header>

  <div class="notice">
    Protótipo demonstrativo: os números e registros abaixo são fictícios.
    A conexão com o Outlook ainda precisa ser autorizada e desenvolvida.
  </div>

  <section id="dashboard" class="section active">
    <div class="cards">
      <div class="card"><small>Cotações enviadas</small><div class="number">248</div></div>
      <div class="card"><small>Cotações recebidas</small><div class="number">312</div></div>
      <div class="card"><small>Pendentes</small><div class="number">36</div></div>
      <div class="card"><small>Clientes atendidos</small><div class="number">87</div></div>
    </div>

    <div class="cards">
      <div class="card"><small>Tempo médio de resposta</small><div class="number">42 min</div></div>
      <div class="card"><small>Equipe de Pricing</small><div class="number">8</div></div>
      <div class="card"><small>Respondidas</small><div class="number">276</div></div>
      <div class="card"><small>Taxa de resposta</small><div class="number">88%</div></div>
    </div>

    <div class="panel">
      <h2>Últimas cotações</h2>
      <table>
        <thead><tr><th>Cliente</th><th>Responsável</th><th>Data</th><th>Status</th></tr></thead>
        <tbody>
          <tr><td>Cliente Exemplo A</td><td>Colaborador 1</td><td>19/11/2026</td><td><span class="status">Respondida</span></td></tr>
          <tr><td>Cliente Exemplo B</td><td>Colaborador 2</td><td>19/11/2026</td><td><span class="status pending">Pendente</span></td></tr>
          <tr><td>Cliente Exemplo C</td><td>Colaborador 3</td><td>18/11/2026</td><td><span class="status">Respondida</span></td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <section id="emails" class="section">
    <div class="panel">
      <h2>Controle de e-mails</h2>
      <p class="description">Área preparada para centralizar as caixas de entrada e saída da equipe de Pricing.</p>
      <div class="filters">
        <select><option>Todos os e-mails</option><option>Enviados</option><option>Recebidos</option></select>
        <input placeholder="Pesquisar cliente ou assunto">
      </div>
      <p>Nenhum e-mail real conectado.</p>
    </div>
  </section>

  <section id="historico" class="section">
    <div class="panel">
      <h2>Histórico de cotações</h2>
      <div class="filters">
        <input type="date">
        <input placeholder="Pesquisar cliente">
        <select><option>Todos os responsáveis</option></select>
      </div>
      <p>O histórico completo será exibido após a integração com o Outlook e o banco de dados.</p>
    </div>
  </section>

  <section id="pendencias" class="section">
    <div class="panel">
      <h2>Cotações pendentes</h2>
      <p>Área para acompanhar solicitações sem resposta e identificar responsáveis.</p>
      <span class="status pending">Aguardando integração de dados</span>
    </div>
  </section>

  <section id="clientes" class="section">
    <div class="panel">
      <h2>Clientes</h2>
      <input placeholder="Pesquisar cliente">
      <p>Cadastro e histórico de clientes serão alimentados pelos dados das cotações.</p>
    </div>
  </section>

  <section id="funcionarios" class="section">
    <div class="panel">
      <h2>Equipe de Pricing</h2>
      <table>
        <thead><tr><th>Funcionário</th><th>Caixa de e-mail</th><th>Status</th></tr></thead>
        <tbody>
          <tr><td>Colaborador 1</td><td>A configurar</td><td>Não conectado</td></tr>
          <tr><td>Colaborador 2</td><td>A configurar</td><td>Não conectado</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <section id="relatorios" class="section">
    <div class="panel">
      <h2>Relatórios gerenciais</h2>
      <p>Indicadores por período, cliente, funcionário, volume de cotações e tempo de resposta.</p>
      <button class="primary" onclick="window.print()">Imprimir relatório</button>
    </div>
  </section>

  <section id="configuracoes" class="section">
    <div class="panel">
      <h2>Configurações</h2>
      <p><b>Integração:</b> Microsoft Outlook / Microsoft Graph.</p>
      <p><b>Autorização:</b> pendente de aprovação da TI.</p>
      <p><b>Banco de dados:</b> ainda não conectado.</p>
      <p><b>Permissões previstas:</b> leitura das caixas autorizadas de Pricing.</p>
    </div>
  </section>
</main>

<script>
function showSection(id, button) {
  document.querySelectorAll('.section').forEach(section => {
    section.classList.remove('active');
  });

  document.getElementById(id).classList.add('active');

  document.querySelectorAll('.menu button').forEach(item => {
    item.classList.remove('active');
  });

  button.classList.add('active');

  const titles = {
    dashboard: 'Dashboard',
    emails: 'E-mails',
    historico: 'Histórico de Cotações',
    pendencias: 'Pendências',
    clientes: 'Clientes',
    funcionarios: 'Funcionários',
    relatorios: 'Relatórios',
    configuracoes: 'Configurações'
  };

  document.getElementById('pageTitle').textContent = titles[id];
}
</script>

</body>
</html>
