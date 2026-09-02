<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BancoVital - Benefícios e Serviços</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.1/dist/chart.umd.min.js"></script>
  <style>
    :root { --green:#15803d; --dark:#14532d; --light:#f0fdf4; }
    * { box-sizing:border-box; }
    html { scroll-behavior:smooth; }
    body { font-family:Arial,Helvetica,sans-serif; background:#f8fafc; color:#17202a; }
    .page { display:none; min-height:calc(100vh - 90px); }
    .page-active { display:block; animation:fade .25s ease; }
    @keyframes fade { from{opacity:0;transform:translateY(6px)} to{opacity:1;transform:none} }
    .nav-active { color:var(--green)!important; font-weight:700; border-bottom:3px solid var(--green); }
    .card { background:#fff; padding:24px; border-radius:18px; box-shadow:0 5px 20px rgba(15,23,42,.08); }
    .hero { background:linear-gradient(135deg,rgba(20,83,45,.92),rgba(21,128,61,.72)),url('https://picsum.photos/id/1015/1400/650') center/cover; min-height:430px; border-radius:22px; }
    .clickable { transition:.18s ease; }
    .clickable:hover { transform:translateY(-2px); }
    .clickable:active { transform:scale(.98); }
    table { width:100%; border-collapse:collapse; }
    th,td { padding:13px 12px; text-align:left; border-bottom:1px solid #e5e7eb; }
    th { background:#f8fafc; color:#166534; }
    .stars { font-size:2.5rem; letter-spacing:5px; cursor:pointer; user-select:none; }
    .star { color:#d1d5db; }
    .star.filled { color:#fbbf24; }
    .toast { position:fixed; right:20px; bottom:20px; z-index:100; display:none; }
    .toast.show { display:block; animation:fade .2s ease; }
    @media(max-width:900px){
      .desktop-nav { display:none; }
      .mobile-nav { display:grid!important; }
    }
    .mobile-nav { display:none; }
  
  .accessibility-speaking { outline:3px solid #2563eb !important; outline-offset:3px; }
</style>
</head>
<body>

<nav class="bg-white shadow-md sticky top-0 z-50">
  <div class="max-w-7xl mx-auto px-4 py-4 flex items-center justify-between gap-4">
    <button onclick="navigate(1)" class="text-3xl font-extrabold text-green-700 clickable">BancoVital</button>
    <div class="desktop-nav flex flex-wrap justify-center gap-5 text-sm lg:text-base font-bold">
      <a onclick="navigate(1)" id="nav1" class="cursor-pointer nav-active clickable">Início</a>
      <a onclick="navigate(3)" id="nav3" class="cursor-pointer clickable">Gráficos</a>
      <a onclick="navigate(4)" id="nav4" class="cursor-pointer clickable">Benefícios</a>
      <a onclick="navigate(5)" id="nav5" class="cursor-pointer clickable">Estaduais</a>
      <a onclick="navigate(6)" id="nav6" class="cursor-pointer clickable">Tabelas</a>
      <a onclick="navigate(7)" id="nav7" class="cursor-pointer clickable">Saldo</a>
      <a onclick="navigate(9)" id="nav9" class="cursor-pointer clickable">Simulador</a>
      <a onclick="navigate(10)" id="nav10" class="cursor-pointer clickable">Calendário</a>
      <a onclick="navigate(11)" id="nav11" class="cursor-pointer clickable">Ajuda</a>
      <a onclick="navigate(12)" id="nav12" class="cursor-pointer clickable">Segurança</a>
      <a onclick="navigate(8)" id="nav8" class="cursor-pointer clickable">Feedback</a>
      <a onclick="navigate(13)" id="nav13" class="cursor-pointer clickable">Sobre Nós</a>
    </div>
    <button onclick="navigate(2)" id="btnMinhaConta" class="bg-green-700 text-white px-5 py-3 rounded-xl hover:bg-green-800 clickable">Minha Conta</button>
  </div>
  <div class="mobile-nav grid grid-cols-4 gap-2 p-2 border-t bg-gray-50">
    <button onclick="navigate(1)" class="text-xs py-2">Início</button>
    <button onclick="navigate(4)" class="text-xs py-2">Benefícios</button>
    <button onclick="navigate(9)" class="text-xs py-2">Simulador</button>
    <button onclick="navigate(11)" class="text-xs py-2">Ajuda</button>
  </div>
</nav>

<!-- BLOQUEIO DE LOGIN -->
<section id="loginRequiredPage" class="page p-5 md:p-8">
  <div class="min-h-[70vh] flex items-center justify-center">
    <div class="text-center max-w-xl mx-auto">
      <div class="text-7xl mb-6">🔐</div>
      <h2 class="text-3xl md:text-4xl font-extrabold text-green-700">
        Faça o login para acessar sua conta!🔐
      </h2>
    </div>
  </div>
</section>

<!-- 1 INÍCIO -->
<section id="page1" class="page page-active p-5 md:p-8">
  <div class="max-w-7xl mx-auto">
    <div class="hero flex items-center justify-center text-center text-white p-8 mb-10">
      <div class="max-w-3xl">
        <span class="inline-block bg-white/15 px-4 py-2 rounded-full mb-5">Seu painel de benefícios</span>
        <h1 class="text-4xl md:text-6xl font-extrabold mb-5">Tudo mais simples no BancoVital</h1>
        <p class="text-xl md:text-2xl mb-8">Consulte benefícios, organize recebimentos e encontre informações em um só lugar.</p>
        <div class="flex flex-wrap justify-center gap-3">
          <button onclick="navigate(4)" class="bg-white text-green-800 px-6 py-3 rounded-xl font-bold clickable">Explorar benefícios</button>
          <button onclick="navigate(9)" class="bg-green-900/70 px-6 py-3 rounded-xl font-bold clickable">Usar simulador</button>
        </div>
      </div>
    </div>

    <div class="grid md:grid-cols-4 gap-5 mb-10">
      <div class="card"><p class="text-gray-500">Benefícios disponíveis</p><strong class="text-3xl text-green-700">12+</strong></div>
      <div class="card"><p class="text-gray-500">Ferramentas</p><strong class="text-3xl text-green-700">4</strong></div>
      <div class="card"><p class="text-gray-500">Acesso ao painel</p><strong class="text-3xl text-green-700">24h</strong></div>
      <div class="card"><p class="text-gray-500">Central de ajuda</p><strong class="text-3xl text-green-700">Online</strong></div>
    </div>

    <div class="grid md:grid-cols-3 gap-6">
      <div class="card clickable cursor-pointer" onclick="navigate(3)">
        <div class="text-4xl mb-4">📊</div><h3 class="text-xl font-bold text-green-700">Acompanhe</h3>
        <p class="mt-2 text-gray-600">Veja gráficos e indicadores para entender seus recebimentos.</p>
      </div>
      <div class="card clickable cursor-pointer" onclick="navigate(10)">
        <div class="text-4xl mb-4">📅</div><h3 class="text-xl font-bold text-green-700">Organize</h3>
        <p class="mt-2 text-gray-600">Consulte um calendário demonstrativo de pagamentos e tarefas.</p>
      </div>
      <div class="card clickable cursor-pointer" onclick="navigate(12)">
        <div class="text-4xl mb-4">🛡️</div><h3 class="text-xl font-bold text-green-700">Proteja-se</h3>
        <p class="mt-2 text-gray-600">Aprenda boas práticas para manter sua conta mais segura.</p>
      </div>
    </div>
  </div>
</section>

<!-- 2 CONTA -->
<section id="page2" class="page p-5 md:p-8">
  <div class="max-w-lg mx-auto card">
    <h2 class="text-3xl font-bold text-center mb-8">Acessar Conta</h2>
    <div class="flex border-b mb-8">
      <button onclick="toggleAuth(1)" id="tab1" class="flex-1 pb-4 border-b-4 border-green-700 font-medium">Login</button>
      <button onclick="toggleAuth(2)" id="tab2" class="flex-1 pb-4 text-gray-500 font-medium">Cadastrar</button>
    </div>
    <div id="loginForm">
      <input type="text" id="loginUsuario" placeholder="Usuário ou e-mail" class="w-full p-4 border rounded-lg mb-4">
      <input type="password" id="loginSenha" placeholder="Senha" class="w-full p-4 border rounded-lg mb-6">
      <button onclick="fazerLogin()" class="w-full bg-green-700 text-white py-4 rounded-lg text-lg">Entrar</button>
      <p class="text-xs text-gray-500 mt-4">Demonstração local: os dados ficam somente no navegador.</p>
    </div>
    <div id="cadastroForm" class="hidden">
      <input type="text" id="nome" placeholder="Nome completo" class="w-full p-4 border rounded-lg mb-4">
      <input type="text" id="usuario" placeholder="Nome de usuário" class="w-full p-4 border rounded-lg mb-4">
      <input type="text" id="cpf" placeholder="CPF (apenas números)" maxlength="11" class="w-full p-4 border rounded-lg mb-4">
      <input type="number" id="idadeInput" placeholder="Idade" class="w-full p-4 border rounded-lg mb-4">
      <input type="email" id="email" placeholder="E-mail" class="w-full p-4 border rounded-lg mb-4">
      <input type="password" id="cadastroSenha" placeholder="Crie uma senha" class="w-full p-4 border rounded-lg mb-6">
      <button onclick="fazerCadastro()" class="w-full bg-green-700 text-white py-4 rounded-lg text-lg">Criar Conta</button>
    </div>
  </div>
</section>

<!-- 3 GRÁFICOS -->
<section id="page3" class="page p-5 md:p-8">
  <div class="max-w-7xl mx-auto">
    <h2 class="text-3xl font-bold text-center mb-8 text-blue-700">Painel de Recebimentos</h2>
    <div class="grid lg:grid-cols-2 gap-7">
      <div class="card"><h3 class="font-bold text-lg mb-4">Recebimentos mensais</h3><canvas id="barChart"></canvas></div>
      <div class="card"><h3 class="font-bold text-lg mb-4">Evolução acumulada</h3><canvas id="lineChart"></canvas></div>
    </div>
    <div class="grid md:grid-cols-4 gap-5 mt-8">
      <div class="card text-center"><p class="text-gray-500">Este mês</p><b class="text-3xl text-green-700">R$ 2.147</b></div>
      <div class="card text-center"><p class="text-gray-500">Benefícios ativos</p><b class="text-3xl text-green-700">5</b></div>
      <div class="card text-center"><p class="text-gray-500">Próximo pagamento</p><b class="text-xl">12/09/2026</b></div>
      <div class="card text-center"><p class="text-gray-500">Disponível</p><b class="text-3xl text-green-700">R$ 22.500</b></div>
    </div>
  </div>
</section>

<!-- 4 BENEFÍCIOS -->
<section id="page4" class="page p-5 md:p-8">
  <div class="max-w-7xl mx-auto">
    <h2 class="text-3xl font-bold text-center mb-10">Benefícios por perfil</h2>
    <div class="grid md:grid-cols-3 gap-7">
      <div class="card"><span class="text-4xl">🚀</span><h3 class="text-2xl font-bold text-green-700 mt-4">18 a 30 anos</h3><ul class="mt-5 space-y-3 text-gray-700"><li>✓ Conta digital sem tarifa</li><li>✓ Cashback demonstrativo</li><li>✓ Cartão sem anuidade</li><li>✓ Educação financeira</li><li>✓ Investimentos iniciais</li></ul></div>
      <div class="card"><span class="text-4xl">💼</span><h3 class="text-2xl font-bold text-green-700 mt-4">31 a 59 anos</h3><ul class="mt-5 space-y-3 text-gray-700"><li>✓ Opções de crédito</li><li>✓ Organização financeira</li><li>✓ Seguros e proteção</li><li>✓ Descontos parceiros</li><li>✓ Planejamento familiar</li></ul></div>
      <div class="card"><span class="text-4xl">🌿</span><h3 class="text-2xl font-bold text-green-700 mt-4">60+ anos</h3><ul class="mt-5 space-y-3 text-gray-700"><li>✓ Atendimento prioritário</li><li>✓ Informações sobre INSS</li><li>✓ Organização de pagamentos</li><li>✓ Conteúdo de segurança</li><li>✓ Serviços digitais</li></ul></div>
    </div>
    <div class="card mt-8 bg-green-50 border border-green-100">
      <h3 class="text-2xl font-bold text-green-800">🎓 Pé de Meia</h3>
      <p class="mt-3 text-gray-700">Área informativa para estudantes sobre o programa, com destaque para matrícula, frequência e conclusão. Consulte sempre os canais oficiais para regras e valores atualizados.</p>
      <button onclick="navigate(10)" class="mt-5 bg-green-700 text-white px-5 py-3 rounded-lg">Ver calendário demonstrativo</button>
    </div>
  </div>
</section>

<!-- 5 ESTADUAIS -->
<section id="page5" class="page p-5 md:p-8">
  <div class="max-w-6xl mx-auto">
    <h2 class="text-3xl font-bold text-center mb-8">Benefícios Estaduais e Municipais</h2>
    <div class="grid md:grid-cols-2 gap-7">
      <div class="card"><h3 class="text-2xl font-bold mb-5 text-green-700">🏛️ Estaduais</h3><div class="space-y-4"><div class="p-4 bg-gray-50 rounded-xl"><b>Transporte</b><p class="text-gray-600">Possíveis gratuidades ou descontos conforme regras locais.</p></div><div class="p-4 bg-gray-50 rounded-xl"><b>Educação</b><p class="text-gray-600">Programas de apoio e bolsas podem variar por estado.</p></div><div class="p-4 bg-gray-50 rounded-xl"><b>Habitação</b><p class="text-gray-600">Programas habitacionais e subsídios conforme critérios.</p></div></div></div>
      <div class="card"><h3 class="text-2xl font-bold mb-5 text-green-700">🏙️ Municipais</h3><div class="space-y-4"><div class="p-4 bg-gray-50 rounded-xl"><b>Restaurante Popular</b><p class="text-gray-600">Serviço alimentar com regras definidas pelo município.</p></div><div class="p-4 bg-gray-50 rounded-xl"><b>Capacitação</b><p class="text-gray-600">Cursos e programas de preparação profissional.</p></div><div class="p-4 bg-gray-50 rounded-xl"><b>Assistência</b><p class="text-gray-600">Auxílios e serviços sociais sujeitos a critérios locais.</p></div></div></div>
    </div>
    <div class="mt-8 card text-center"><p class="text-gray-600">Os benefícios estaduais e municipais mudam conforme a cidade e o estado.</p><button onclick="navigate(11)" class="mt-4 text-green-700 font-bold">Precisa de ajuda para encontrar uma informação?</button></div>
  </div>
</section>

<!-- 6 TABELAS -->
<section id="page6" class="page p-5 md:p-8">
  <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-7">
    <div class="card overflow-auto"><h3 class="font-bold text-xl mb-5">Tabela informativa — INSS</h3><table><thead><tr><th>Benefício</th><th>Descrição</th><th>Valor</th></tr></thead><tbody><tr><td>Aposentadoria</td><td>Conforme regras previdenciárias</td><td>Variável</td></tr><tr><td>Pensão por morte</td><td>Dependentes elegíveis</td><td>Variável</td></tr><tr><td>Auxílio por incapacidade</td><td>Sujeito à avaliação</td><td>Variável</td></tr><tr><td>BPC</td><td>Critérios legais específicos</td><td>Consultar regra</td></tr></tbody></table></div>
    <div class="card overflow-auto"><h3 class="font-bold text-xl mb-5">Comparativo de recursos</h3><table><thead><tr><th>Área</th><th>Recurso</th><th>Ação</th></tr></thead><tbody><tr><td>Conta</td><td>Saldo e histórico</td><td>Ver saldo</td></tr><tr><td>Benefícios</td><td>Por perfil</td><td>Explorar</td></tr><tr><td>Planejamento</td><td>Simulador</td><td>Calcular</td></tr><tr><td>Suporte</td><td>Central de ajuda</td><td>Consultar</td></tr></tbody></table></div>
  </div>
</section>

<!-- 7 SALDO -->
<section id="page7" class="page p-5 md:p-8">
  <div class="max-w-3xl mx-auto" id="conteudoSaldo"></div>
</section>

<!-- 8 FEEDBACK -->
<section id="page8" class="page p-5 md:p-8">
  <div class="max-w-3xl mx-auto">
    <h2 class="text-3xl font-bold text-center text-green-700 mb-8">Seu feedback</h2>
    <div class="card text-center mb-7"><h3 class="text-xl font-semibold">Como você avalia a experiência?</h3><div class="stars mt-3" id="estrelasAvaliacao"><span class="star" data-value="1">★</span><span class="star" data-value="2">★</span><span class="star" data-value="3">★</span><span class="star" data-value="4">★</span><span class="star" data-value="5">★</span></div><p id="textoAvaliacao" class="text-gray-600">Clique nas estrelas</p></div>
    <div class="card"><label class="block font-medium mb-2">O que você mais gostou?</label><textarea id="feedback1" rows="3" class="w-full p-4 border rounded-lg mb-5" placeholder="Escreva aqui..."></textarea><label class="block font-medium mb-2">O que podemos melhorar?</label><textarea id="feedback2" rows="3" class="w-full p-4 border rounded-lg mb-5" placeholder="Sua sugestão..."></textarea><button onclick="enviarFeedback()" class="w-full bg-green-700 text-white py-4 rounded-lg">Enviar feedback</button></div>
  </div>
</section>

<!-- 9 NOVA: SIMULADOR -->
<section id="page9" class="page p-5 md:p-8">
  <div class="max-w-5xl mx-auto">
    <div class="text-center mb-8"><span class="text-5xl">🧮</span><h2 class="text-3xl font-bold mt-3">Simulador financeiro</h2><p class="text-gray-600 mt-2">Faça uma simulação educativa para entender como pequenas decisões alteram seu orçamento.</p></div>
    <div class="grid lg:grid-cols-2 gap-7">
      <div class="card">
        <label class="font-medium">Renda mensal</label><input id="simRenda" type="number" value="2500" class="w-full p-4 border rounded-lg mt-2 mb-5">
        <label class="font-medium">Despesas mensais</label><input id="simDespesas" type="number" value="1700" class="w-full p-4 border rounded-lg mt-2 mb-5">
        <label class="font-medium">Valor que deseja guardar</label><input id="simGuardar" type="number" value="300" class="w-full p-4 border rounded-lg mt-2 mb-5">
        <button onclick="simular()" class="w-full bg-green-700 text-white py-4 rounded-xl font-bold">Calcular</button>
      </div>
      <div class="card" id="resultadoSimulador"><h3 class="text-xl font-bold">Resultado</h3><p class="text-gray-600 mt-3">Preencha os valores e clique em calcular.</p></div>
    </div>
  </div>
</section>

<!-- 10 NOVA: CALENDÁRIO -->
<section id="page10" class="page p-5 md:p-8">
  <div class="max-w-6xl mx-auto">
    <div class="text-center mb-8"><span class="text-5xl">📅</span><h2 class="text-3xl font-bold mt-3">Calendário e organização</h2><p class="text-gray-600">Uma visão simples para organizar compromissos financeiros.</p></div>
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-5" id="calendarioCards"></div>
    <div class="card mt-7 bg-yellow-50 border border-yellow-200"><b>Importante:</b> este calendário é demonstrativo. Datas oficiais de benefícios devem ser conferidas nos canais do órgão responsável.</div>
  </div>
</section>

<!-- 11 NOVA: AJUDA -->
<section id="page11" class="page p-5 md:p-8">
  <div class="max-w-5xl mx-auto">
    <div class="text-center mb-8"><span class="text-5xl">💬</span><h2 class="text-3xl font-bold mt-3">Central de ajuda</h2><p class="text-gray-600">Respostas rápidas para as principais dúvidas sobre o site.</p></div>
    <div class="space-y-4">
      <details class="card cursor-pointer"><summary class="font-bold text-lg">Como crio uma conta?</summary><p class="mt-3 text-gray-600">Abra “Minha Conta”, escolha “Cadastrar” e preencha os campos solicitados.</p></details>
      <details class="card cursor-pointer"><summary class="font-bold text-lg">Por que o saldo é demonstrativo?</summary><p class="mt-3 text-gray-600">Este projeto é uma interface de demonstração. Ele não se conecta a uma instituição financeira real.</p></details>
      <details class="card cursor-pointer"><summary class="font-bold text-lg">Onde vejo meus benefícios?</summary><p class="mt-3 text-gray-600">A página Benefícios reúne exemplos organizados por perfil, enquanto Tabelas apresenta uma visão resumida.</p></details>
      <details class="card cursor-pointer"><summary class="font-bold text-lg">Onde encontro informações oficiais?</summary><p class="mt-3 text-gray-600">Use os portais oficiais do órgão responsável pelo benefício antes de tomar decisões financeiras.</p></details>
    </div>
    <div class="card mt-7"><h3 class="text-xl font-bold mb-3">Ainda precisa de ajuda?</h3><input id="buscaAjuda" oninput="buscarAjuda()" placeholder="Digite uma palavra, como saldo, conta ou benefício..." class="w-full p-4 border rounded-xl"><p id="resultadoAjuda" class="mt-4 text-gray-600"></p></div>
  </div>
</section>

<!-- 13 NOVA: SOBRE NÓS -->
<section id="page13" class="page p-5 md:p-8">
  <div class="max-w-6xl mx-auto">
    <div class="text-center mb-10">
      <span class="text-5xl">👨‍💻</span>
      <h2 class="text-4xl font-bold text-green-700 mt-4">Sobre Nós</h2>
      <p class="text-gray-600 text-lg mt-3">Conheça os estudantes por trás do projeto BancoVital.</p>
    </div>
    <div class="card mb-8 text-center">
      <h3 class="text-2xl font-bold text-green-800 mb-4">Quem somos?</h3>
      <p class="text-gray-700 text-lg leading-relaxed">Somos programadores do <strong>2° ano do curso técnico</strong> e desenvolvemos o BancoVital como um projeto para colocar em prática nossos conhecimentos de programação, desenvolvimento web, organização de informações e criação de interfaces.</p>
      <p class="text-gray-700 text-lg leading-relaxed mt-4">A ideia do BancoVital é reunir, em uma única plataforma, informações e ferramentas relacionadas a benefícios, organização financeira e serviços digitais, criando uma experiência simples e fácil de utilizar.</p>
    </div>
    <div class="grid md:grid-cols-3 gap-6">
      <div class="card text-center clickable"><div class="text-5xl mb-4">👨‍💻</div><h3 class="text-2xl font-bold text-green-700">Pedro Oliveira</h3><p class="text-gray-600 mt-3">Programador e estudante do 2° ano técnico.</p></div>
      <div class="card text-center clickable"><div class="text-5xl mb-4">👨‍💻</div><h3 class="text-2xl font-bold text-green-700">Pedro Lima</h3><p class="text-gray-600 mt-3">Programador e estudante do 2° ano técnico.</p></div>
      <div class="card text-center clickable"><div class="text-5xl mb-4">👨‍💻</div><h3 class="text-2xl font-bold text-green-700">Wellinton</h3><p class="text-gray-600 mt-3">Programador e estudante do 2° ano técnico.</p></div>
    </div>
    <div class="card mt-8 bg-green-50 border border-green-100"><h3 class="text-2xl font-bold text-green-800 mb-3">🎯 Nosso objetivo</h3><p class="text-gray-700 leading-relaxed">Aprender, desenvolver e transformar o conhecimento adquirido no curso técnico em um projeto funcional, moderno e intuitivo. O BancoVital representa nosso trabalho em equipe e nossa evolução como programadores.</p></div>
    <div class="text-center mt-8"><button onclick="navigate(1)" class="bg-green-700 text-white px-7 py-3 rounded-xl font-bold clickable">Voltar ao início</button></div>
  </div>
</section>

<!-- 12 NOVA: SEGURANÇA -->
<section id="page12" class="page p-5 md:p-8">
  <div class="max-w-6xl mx-auto">
    <div class="text-center mb-8"><span class="text-5xl">🛡️</span><h2 class="text-3xl font-bold mt-3">Segurança digital</h2><p class="text-gray-600">Boas práticas para proteger seus dados e sua conta.</p></div>
    <div class="grid md:grid-cols-2 gap-6">
      <div class="card"><h3 class="text-xl font-bold text-green-700">🔑 Senhas</h3><ul class="mt-4 space-y-3 text-gray-700"><li>✓ Use senhas longas e únicas.</li><li>✓ Não compartilhe sua senha.</li><li>✓ Evite dados fáceis de adivinhar.</li></ul></div>
      <div class="card"><h3 class="text-xl font-bold text-green-700">📱 Dispositivo</h3><ul class="mt-4 space-y-3 text-gray-700"><li>✓ Mantenha sistema e aplicativos atualizados.</li><li>✓ Use bloqueio de tela.</li><li>✓ Evite acessar contas em computadores públicos.</li></ul></div>
      <div class="card"><h3 class="text-xl font-bold text-green-700">🎣 Golpes</h3><ul class="mt-4 space-y-3 text-gray-700"><li>✓ Desconfie de links inesperados.</li><li>✓ Confirme pedidos de pagamento.</li><li>✓ Nunca informe códigos de autenticação a terceiros.</li></ul></div>
      <div class="card"><h3 class="text-xl font-bold text-green-700">🚨 Suspeita</h3><ul class="mt-4 space-y-3 text-gray-700"><li>✓ Pare a operação se algo parecer estranho.</li><li>✓ Procure o canal oficial da instituição.</li><li>✓ Não tente resolver um golpe por meio do próprio contato suspeito.</li></ul></div>
    </div>
  </div>
</section>

<div id="toast" class="toast bg-gray-900 text-white px-5 py-4 rounded-xl shadow-xl"></div>

<script>
let audioContext, usuarioLogado = null, saldo = 2847.50;
let historico = JSON.parse(localStorage.getItem('historicoSaldo')) || [
  '12/08/2026 - Recebimento demonstrativo R$ 1.412,00',
  '05/08/2026 - Recebimento demonstrativo R$ 780,00'
];
let notaSelecionada = 0;

function playClickSound(){
  // Som antigo removido. A interface permanece silenciosa.
}
function playClickSound(){
  try{
    if(!audioContext) audioContext = new (window.AudioContext||window.webkitAudioContext)();
    const now = audioContext.currentTime;

    const gain = audioContext.createGain();
    gain.gain.setValueAtTime(0.0001, now);
    gain.gain.exponentialRampToValueAtTime(0.055, now + 0.015);
    gain.gain.exponentialRampToValueAtTime(0.0001, now + 0.16);
    gain.connect(audioContext.destination);

    const osc = audioContext.createOscillator();
    osc.type = 'sine';
    osc.frequency.setValueAtTime(520, now);
    osc.frequency.exponentialRampToValueAtTime(760, now + 0.09);
    osc.connect(gain);
    osc.start(now);
    osc.stop(now + 0.17);
  }catch(e){}
}

function toast(msg){
  const t=document.getElementById('toast'); t.textContent=msg; t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),2600);
}
function mostrarBloqueioLogin(){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('page-active'));
  const bloqueio=document.getElementById('loginRequiredPage');
  if(bloqueio) bloqueio.classList.add('page-active');
  document.querySelectorAll('nav a').forEach(a=>a.classList.remove('nav-active'));
  window.scrollTo({top:0,behavior:'smooth'});
}

function navigate(n){
  // Todas as páginas ficam bloqueadas até o usuário fazer login.
  // A página 2 (Minha Conta) continua sempre acessível para entrar/cadastrar.
  if(n!==2 && !usuarioLogado){
    mostrarBloqueioLogin();
    return;
  }

  document.querySelectorAll('.page').forEach(p=>p.classList.remove('page-active'));
  const page=document.getElementById('page'+n); if(page) page.classList.add('page-active');
  document.querySelectorAll('nav a').forEach(a=>a.classList.remove('nav-active'));
  const nav=document.getElementById('nav'+n); if(nav) nav.classList.add('nav-active');
  if(n===3) criarGraficos();
  if(n===7) verificarAcessoSaldo();
  if(n===10) criarCalendario();
  playClickSound();
  window.scrollTo({top:0,behavior:'smooth'});
}
function toggleAuth(tab){
  document.getElementById('loginForm').classList.toggle('hidden',tab===2);
  document.getElementById('cadastroForm').classList.toggle('hidden',tab===1);
  document.getElementById('tab1').className=tab===1?'flex-1 pb-4 border-b-4 border-green-700 font-medium':'flex-1 pb-4 text-gray-500 font-medium';
  document.getElementById('tab2').className=tab===2?'flex-1 pb-4 border-b-4 border-green-700 font-medium':'flex-1 pb-4 text-gray-500 font-medium';
}
function fazerCadastro(){
  const nome=document.getElementById('nome').value.trim(), usuario=document.getElementById('usuario').value.trim(),
        cpf=document.getElementById('cpf').value.trim(), idade=Number(document.getElementById('idadeInput').value),
        email=document.getElementById('email').value.trim(), senha=document.getElementById('cadastroSenha').value;
  if(!nome||!usuario||!cpf||!idade||!email||!senha) return toast('Preencha todos os campos.');
  if(!/^\d{11}$/.test(cpf)) return toast('CPF deve conter 11 números.');
  if(idade<18||idade>120) return toast('Idade inválida.');
  if(!email.includes('@')) return toast('E-mail inválido.');
  localStorage.setItem('usuarioBancoVital',JSON.stringify({nome,usuario,cpf,idade,email,senha}));
  toast('Conta criada! Agora faça login.');
  toggleAuth(1);
}
function fazerLogin(){
  const login=document.getElementById('loginUsuario').value.trim(), senha=document.getElementById('loginSenha').value;
  const u=JSON.parse(localStorage.getItem('usuarioBancoVital'));
  if(!u) return toast('Nenhuma conta cadastrada. Faça seu cadastro.');
  if((login.toLowerCase()===u.usuario.toLowerCase()||login.toLowerCase()===u.email.toLowerCase())&&senha===u.senha){
    usuarioLogado=u; atualizarBotaoConta(); toast('Login realizado com sucesso!'); navigate(1);
  }else toast('Usuário ou senha incorretos.');
}
function atualizarBotaoConta(){
  document.getElementById('btnMinhaConta').textContent=usuarioLogado?'Olá, '+usuarioLogado.nome.split(' ')[0]:'Minha Conta';
}
function criarGraficos(){
  if(window.barChartInstance) window.barChartInstance.destroy();
  if(window.lineChartInstance) window.lineChartInstance.destroy();
  window.barChartInstance=new Chart(document.getElementById('barChart'),{
    type:'bar',data:{labels:['Mar','Abr','Mai','Jun','Jul','Ago'],datasets:[{label:'Recebimentos',data:[1190,1650,2147,1890,2310,2640],borderRadius:8}]},
    options:{responsive:true,plugins:{legend:{display:false}},scales:{y:{beginAtZero:true}}}
  });
  window.lineChartInstance=new Chart(document.getElementById('lineChart'),{
    type:'line',data:{labels:['Mar','Abr','Mai','Jun','Jul','Ago'],datasets:[{label:'Acumulado',data:[1190,2840,4987,6877,9187,11827],tension:.35,borderWidth:3,fill:true}]},
    options:{responsive:true}
  });
}
function verificarAcessoSaldo(){
  const c=document.getElementById('conteudoSaldo');
  if(!usuarioLogado){
    c.innerHTML=`<div class="card text-center py-16"><div class="text-6xl">🔒</div><h2 class="text-3xl font-bold mt-5">Acesso restrito</h2><p class="text-gray-600 mt-3 mb-7">Faça login para visualizar o painel demonstrativo de saldo.</p><button onclick="navigate(2)" class="bg-green-700 text-white px-8 py-4 rounded-xl">Ir para minha conta</button></div>`;
    return;
  }
  c.innerHTML=`<div class="card text-center mb-6"><p class="text-gray-500">Saldo demonstrativo</p><p id="saldoValor" class="text-5xl font-extrabold text-green-700 my-4"></p><div class="flex flex-col md:flex-row gap-3"><button onclick="enviarPix()" class="flex-1 bg-green-700 text-white py-4 rounded-xl">📤 Simular PIX</button><button onclick="gerarQRCode()" class="flex-1 bg-blue-600 text-white py-4 rounded-xl">📱 Simular QR Code</button></div></div><div class="card mb-6"><h3 class="text-xl font-bold mb-4">Próximos recebimentos</h3><div class="space-y-4"><div class="flex justify-between border-b pb-3"><span>Benefício demonstrativo<br><small class="text-gray-500">12/09/2026</small></span><b class="text-green-700">R$ 1.412,00</b></div><div class="flex justify-between border-b pb-3"><span>Crédito demonstrativo<br><small class="text-gray-500">15/09/2026</small></span><b class="text-green-700">R$ 780,00</b></div></div></div><div class="card"><h3 class="font-bold text-xl mb-4">Histórico</h3><ul id="historicoSaldo" class="space-y-2 text-sm"></ul></div>`;
  atualizarSaldoTela();
}
function atualizarSaldoTela(){
  const s=document.getElementById('saldoValor'); if(s) s.textContent=saldo.toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
  const l=document.getElementById('historicoSaldo');
  if(l) l.innerHTML=historico.map(x=>`<li class="py-2 border-b">${x}</li>`).join('');
}
function enviarPix(){
  if(!usuarioLogado) return toast('Faça login primeiro.');
  const v=prompt('Valor do PIX (simulação):');
  if(v===null) return;
  const valor=Number(v.replace(',','.'));
  if(!Number.isFinite(valor)||valor<=0) return toast('Valor inválido.');
  if(valor>saldo) return toast('Saldo insuficiente.');
  const destino=prompt('Destinatário (simulação):','Contato');
  saldo-=valor; historico.unshift(`${new Date().toLocaleDateString('pt-BR')} - PIX simulado para ${destino||'destinatário'} - ${valor.toLocaleString('pt-BR',{style:'currency',currency:'BRL'})}`);
  localStorage.setItem('historicoSaldo',JSON.stringify(historico)); atualizarSaldoTela(); toast('PIX simulado com sucesso.');
}
function gerarQRCode(){
  if(!usuarioLogado) return toast('Faça login primeiro.');
  const v=prompt('Valor do QR Code (simulação):');
  if(v===null) return;
  const valor=Number(v.replace(',','.'));
  if(!Number.isFinite(valor)||valor<=0) return toast('Valor inválido.');
  toast('QR Code demonstrativo criado para R$ '+valor.toFixed(2).replace('.',',')+'.');
}
function simular(){
  const renda=Number(document.getElementById('simRenda').value), despesas=Number(document.getElementById('simDespesas').value), guardar=Number(document.getElementById('simGuardar').value);
  const sobra=renda-despesas, depois=sobra-guardar;
  const status=depois>=0?'Seu objetivo cabe no orçamento demonstrativo.':'O valor planejado supera a sobra mensal.';
  document.getElementById('resultadoSimulador').innerHTML=`<h3 class="text-xl font-bold">Resultado</h3><div class="mt-5 space-y-4"><div><span class="text-gray-500">Sobra antes de guardar</span><p class="text-3xl font-bold text-green-700">${sobra.toLocaleString('pt-BR',{style:'currency',currency:'BRL'})}</p></div><div><span class="text-gray-500">Sobra depois da meta</span><p class="text-3xl font-bold">${depois.toLocaleString('pt-BR',{style:'currency',currency:'BRL'})}</p></div><p class="p-4 rounded-xl bg-green-50 text-green-800">${status}</p><p class="text-xs text-gray-500">Simulação educativa; não representa recomendação financeira.</p></div>`;
}
function criarCalendario(){
  const itens=[
    ['05/09','Organizar contas','Revise despesas recorrentes.','📌'],
    ['12/09','Pagamento demonstrativo','Confira o histórico do painel.','💰'],
    ['15/09','Revisar orçamento','Compare renda e despesas.','📊'],
    ['20/09','Meta de economia','Registre quanto pretende guardar.','🎯'],
    ['25/09','Segurança','Revise senhas e acessos.','🛡️'],
    ['30/09','Fechamento do mês','Confira seus lançamentos.','🗂️']
  ];
  document.getElementById('calendarioCards').innerHTML=itens.map(i=>`<div class="card"><span class="text-3xl">${i[3]}</span><p class="text-green-700 font-bold mt-3">${i[0]}</p><h3 class="text-xl font-bold mt-1">${i[1]}</h3><p class="text-gray-600 mt-2">${i[2]}</p></div>`).join('');
}
function buscarAjuda(){
  const q=document.getElementById('buscaAjuda').value.toLowerCase(), out=document.getElementById('resultadoAjuda');
  if(!q) return out.textContent='';
  const mapa={saldo:'Você pode consultar o saldo na página Saldo após fazer login.',conta:'Use Minha Conta para cadastrar ou entrar.',benefício:'A página Benefícios organiza informações por perfil.',pix:'O PIX disponível neste projeto é apenas uma simulação.'};
  const chave=Object.keys(mapa).find(k=>q.includes(k));
  out.textContent=chave?mapa[chave]:'Não encontrei uma resposta rápida. Tente “saldo”, “conta”, “benefício” ou “pix”.';
}
function inicializarEstrelas(){
  document.querySelectorAll('.star').forEach(s=>{
    s.onclick=()=>{notaSelecionada=Number(s.dataset.value); atualizarEstrelas(notaSelecionada);document.getElementById('textoAvaliacao').textContent=`Você deu ${notaSelecionada} estrela${notaSelecionada>1?'s':''}.`;};
    s.onmouseover=()=>atualizarEstrelas(Number(s.dataset.value));
    s.onmouseout=()=>atualizarEstrelas(notaSelecionada);
  });
}
function atualizarEstrelas(n){
  document.querySelectorAll('.star').forEach(s=>s.classList.toggle('filled',Number(s.dataset.value)<=n));
}
function enviarFeedback(){
  if(!usuarioLogado) return toast('Faça login para enviar seu feedback.');
  const a=document.getElementById('feedback1').value.trim(), b=document.getElementById('feedback2').value.trim();
  if(!a&&!b&&!notaSelecionada) return toast('Preencha algo antes de enviar.');
  localStorage.setItem('feedbackBancoVital',JSON.stringify({nota:notaSelecionada,gostou:a,melhoria:b}));
  document.getElementById('feedback1').value='';document.getElementById('feedback2').value='';
  toast('Obrigado pelo feedback!');
}
window.onload=()=>{
  atualizarBotaoConta();
  inicializarEstrelas();
  criarCalendario();
  mostrarBloqueioLogin();
};

function falarAcessibilidade(texto){
  if(!('speechSynthesis' in window) || !texto) return;
  window.speechSynthesis.cancel();
  const fala = new SpeechSynthesisUtterance(texto);
  fala.lang='pt-BR';
  fala.rate=1.15;
  fala.pitch=1;
  fala.volume=.85;
  window.speechSynthesis.speak(fala);
}

function configurarAcessibilidade(){
  const elementos=document.querySelectorAll('nav a, nav button, button, h1, h2, h3, input, textarea, summary, .card');
  elementos.forEach(el=>{
    if(el.dataset.falaConfigurada) return;
    let texto=el.getAttribute('aria-label') || el.innerText || el.placeholder || '';
    texto=texto.replace(/\s+/g,' ').trim();
    if(!texto) return;
    if(texto.length>55) texto=texto.substring(0,55).trim()+'.';
    el.dataset.falaConfigurada='true';
    el.dataset.falaTexto=texto;
    el.addEventListener('mouseenter',()=>{
      el.classList.add('accessibility-speaking');
      falarAcessibilidade(el.dataset.falaTexto);
    });
    el.addEventListener('mouseleave',()=>el.classList.remove('accessibility-speaking'));
    el.addEventListener('focus',()=>falarAcessibilidade(el.dataset.falaTexto));
  });
}

const navigateComAcessibilidade = navigate;
navigate = function(n){
  navigateComAcessibilidade(n);
  setTimeout(configurarAcessibilidade,100);
};

window.addEventListener('load',()=>setTimeout(configurarAcessibilidade,200));

</script>
</body>
</html>
