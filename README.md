[index (1).html](https://github.com/user-attachments/files/28477165/index.1.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Concursos Ceará 2026 | Painel Inteligente</title>
  <style>
    :root{
      --bg:#020814;
      --bg2:#06152c;
      --green:#19e36f;
      --green2:#75ff9d;
      --cyan:#2be7ff;
      --blue:#1c74ff;
      --yellow:#ffd34e;
      --text:#f6fbff;
      --muted:#b6c7dd;
      --panel:rgba(5,18,40,.70);
      --panel2:rgba(7,30,58,.84);
      --border:rgba(43,231,255,.22);
      --borderGreen:rgba(25,227,111,.35);
      --shadow:0 22px 60px rgba(0,0,0,.42);
      --radius:22px;
    }

    *{box-sizing:border-box;margin:0;padding:0}
    html{scroll-behavior:smooth}
    body{
      min-height:100vh;
      font-family:Inter, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color:var(--text);
      background:
        radial-gradient(circle at 18% 12%, rgba(25,227,111,.26), transparent 27%),
        radial-gradient(circle at 78% 4%, rgba(43,231,255,.22), transparent 26%),
        radial-gradient(circle at 82% 82%, rgba(28,116,255,.20), transparent 33%),
        linear-gradient(135deg, #010611 0%, #06142a 42%, #04271d 100%);
      overflow-x:hidden;
    }

    body::before,
    body::after{
      content:"";
      position:fixed;
      inset:0;
      pointer-events:none;
      z-index:-3;
    }

    body::before{
      background-image:
        linear-gradient(rgba(43,231,255,.055) 1px, transparent 1px),
        linear-gradient(90deg, rgba(43,231,255,.055) 1px, transparent 1px);
      background-size:52px 52px;
      mask-image:linear-gradient(to bottom, rgba(0,0,0,.95), rgba(0,0,0,.25));
      animation:gridMove 22s linear infinite;
    }

    body::after{
      background:
        linear-gradient(120deg, transparent 0 20%, rgba(25,227,111,.16) 21%, transparent 23% 54%, rgba(43,231,255,.12) 55%, transparent 58%),
        radial-gradient(circle at 50% 18%, rgba(255,255,255,.055), transparent 36%);
      filter:blur(.2px);
      animation:lightSweep 13s ease-in-out infinite alternate;
      z-index:-2;
    }

    @keyframes gridMove{
      from{background-position:0 0,0 0}
      to{background-position:52px 52px,52px 52px}
    }

    @keyframes lightSweep{
      from{transform:translateX(-4%) translateY(-1%);opacity:.55}
      to{transform:translateX(4%) translateY(2%);opacity:1}
    }

    .orb{
      position:fixed;
      border-radius:50%;
      filter:blur(28px);
      opacity:.50;
      z-index:-1;
      animation:float 10s ease-in-out infinite alternate;
    }
    .orb.one{width:300px;height:300px;background:rgba(25,227,111,.32);left:-90px;top:180px}
    .orb.two{width:360px;height:360px;background:rgba(43,231,255,.23);right:-120px;top:80px;animation-delay:1s}
    .orb.three{width:330px;height:330px;background:rgba(28,116,255,.20);left:45%;bottom:-120px;animation-delay:2s}

    @keyframes float{
      from{transform:translate3d(0,0,0) scale(1)}
      to{transform:translate3d(36px,-28px,0) scale(1.08)}
    }

    .page{max-width:1500px;margin:0 auto;padding:0 28px 54px}

    header{
      position:sticky;
      top:0;
      z-index:20;
      backdrop-filter:blur(20px);
      background:rgba(2,8,20,.72);
      border-bottom:1px solid rgba(43,231,255,.14);
    }

    .nav{
      max-width:1500px;
      margin:0 auto;
      padding:16px 28px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:22px;
    }

    .brand{display:flex;align-items:center;gap:12px;font-weight:900;letter-spacing:.2px}
    .badge-logo{
      width:48px;height:48px;border-radius:16px;
      display:grid;place-items:center;
      background:linear-gradient(145deg, rgba(25,227,111,.25), rgba(43,231,255,.18));
      border:1px solid var(--borderGreen);
      box-shadow:0 0 28px rgba(25,227,111,.22);
      font-size:26px;
    }
    .brand small{display:block;color:var(--green);letter-spacing:2px;font-weight:900;margin-top:2px}

    .search-top{
      flex:1;
      max-width:520px;
      position:relative;
    }
    .search-top input{
      width:100%;
      padding:15px 48px 15px 18px;
      border-radius:14px;
      border:1px solid rgba(255,255,255,.14);
      background:rgba(255,255,255,.055);
      color:var(--text);
      outline:none;
    }
    .search-top span{position:absolute;right:16px;top:12px;color:var(--muted);font-size:20px}

    nav a{
      color:#e9f5ff;
      text-decoration:none;
      margin-left:22px;
      font-weight:800;
      font-size:14px;
      opacity:.92;
    }
    nav a:hover{color:var(--green)}

    .hero{
      min-height:500px;
      display:grid;
      grid-template-columns:1.35fr .65fr;
      gap:28px;
      align-items:center;
      padding:46px 0 26px;
      position:relative;
    }

    .hero::before{
      content:"";
      position:absolute;
      inset:20px -28px 0;
      background:
        linear-gradient(90deg, rgba(2,8,20,.58), rgba(2,8,20,.10)),
        radial-gradient(circle at 54% 42%, rgba(25,227,111,.18), transparent 26%);
      border-radius:0 0 38px 38px;
      z-index:-1;
    }

    .hero-visual{
      position:absolute;
      left:42%;
      top:54px;
      width:430px;
      height:430px;
      opacity:.88;
      z-index:0;
      pointer-events:none;
    }

    .ceara-map{
      width:100%;
      height:100%;
      filter:drop-shadow(0 0 20px rgba(25,227,111,.65));
      animation:pulseMap 3.4s ease-in-out infinite alternate;
    }

    @keyframes pulseMap{
      from{opacity:.72;transform:scale(.985)}
      to{opacity:1;transform:scale(1.015)}
    }

    .hero-content{position:relative;z-index:2;max-width:660px}
    .kicker{
      color:var(--green2);
      font-weight:900;
      letter-spacing:3px;
      text-transform:uppercase;
      margin-bottom:14px;
    }

    h1{
      font-size:clamp(42px,6vw,78px);
      line-height:.95;
      letter-spacing:-2px;
      margin-bottom:20px;
    }
    h1 span{color:var(--green)}
    .lead{
      color:#d8e8f7;
      font-size:20px;
      line-height:1.55;
      max-width:650px;
      margin-bottom:24px;
    }

    .stats{
      display:grid;
      grid-template-columns:repeat(3, minmax(140px,1fr));
      gap:12px;
      margin:24px 0;
      max-width:640px;
    }
    .stat{
      background:rgba(5,18,40,.64);
      border:1px solid rgba(43,231,255,.18);
      border-radius:16px;
      padding:15px;
      box-shadow:0 12px 28px rgba(0,0,0,.20);
    }
    .stat strong{font-size:27px;display:block}
    .stat small{color:var(--muted)}

    .actions{display:flex;gap:14px;flex-wrap:wrap;margin-top:20px}
    .btn{
      border:0;
      cursor:pointer;
      color:white;
      padding:14px 22px;
      border-radius:14px;
      font-weight:900;
      background:linear-gradient(135deg, #08a843, #20dd69);
      box-shadow:0 0 28px rgba(25,227,111,.28);
      text-decoration:none;
      display:inline-flex;
      align-items:center;
      gap:9px;
    }
    .btn.secondary{
      background:rgba(255,255,255,.06);
      border:1px solid rgba(255,255,255,.16);
      box-shadow:none;
    }

    .monitor{
      position:relative;
      z-index:2;
      background:linear-gradient(180deg, rgba(7,30,58,.88), rgba(4,18,37,.72));
      border:1px solid var(--border);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
      padding:26px;
      overflow:hidden;
    }
    .monitor::before{
      content:"";
      position:absolute;
      width:220px;height:220px;border-radius:50%;
      background:rgba(25,227,111,.12);
      right:-80px;top:-80px;
      filter:blur(8px);
    }
    .status-row{display:flex;justify-content:space-between;gap:16px;align-items:center;margin-bottom:18px}
    .status{display:flex;gap:10px;align-items:center;font-weight:900}
    .dot{width:11px;height:11px;border-radius:50%;background:var(--green);box-shadow:0 0 15px var(--green)}
    .monitor p{color:var(--muted);line-height:1.65;margin-bottom:16px}
    .timer{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-top:18px}
    .timebox{
      background:rgba(0,0,0,.20);
      border:1px solid rgba(255,255,255,.10);
      border-radius:14px;
      padding:14px;
      text-align:center;
    }
    .timebox strong{font-size:30px;display:block}
    .timebox small{color:var(--muted)}

    .layout{
      display:grid;
      grid-template-columns:280px 1fr 360px;
      gap:22px;
      align-items:start;
      margin-top:10px;
    }

    .panel{
      background:var(--panel);
      border:1px solid var(--border);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
      backdrop-filter:blur(18px);
    }

    .filters{padding:20px;position:sticky;top:90px}
    .panel h2,.panel h3{font-size:20px;margin-bottom:15px}
    label{display:block;color:#dcecff;font-size:13px;font-weight:800;margin:14px 0 7px}
    input,select{
      width:100%;
      padding:13px 14px;
      border-radius:12px;
      border:1px solid rgba(255,255,255,.14);
      background:rgba(1,8,20,.55);
      color:white;
      outline:none;
    }

    .main{display:grid;gap:22px}
    .section-head{
      display:flex;justify-content:space-between;gap:12px;align-items:center;
      margin-bottom:16px;
    }
    .section-head a{color:var(--green);font-size:13px;text-decoration:none;font-weight:900}

    .cards{
      display:grid;
      grid-template-columns:repeat(3, minmax(0,1fr));
      gap:14px;
    }

    .card{
      position:relative;
      overflow:hidden;
      min-height:255px;
      border:1px solid rgba(43,231,255,.22);
      border-radius:18px;
      padding:18px;
      background:
        linear-gradient(145deg, rgba(8,34,65,.82), rgba(7,16,43,.72)),
        radial-gradient(circle at 20% 0%, rgba(25,227,111,.20), transparent 28%);
      box-shadow:0 18px 32px rgba(0,0,0,.28);
      transition:.25s ease;
    }
    .card:hover{transform:translateY(-6px);border-color:rgba(25,227,111,.60);box-shadow:0 26px 45px rgba(0,0,0,.36)}
    .card::after{
      content:"";
      position:absolute;inset:auto -60px -70px auto;
      width:170px;height:170px;border-radius:50%;
      background:rgba(43,231,255,.10);
      filter:blur(8px);
    }
    .tag{
      display:inline-flex;
      border-radius:999px;
      padding:7px 10px;
      background:rgba(25,227,111,.18);
      color:#baffcd;
      font-size:12px;
      font-weight:900;
      border:1px solid rgba(25,227,111,.28);
    }
    .org-icon{
      height:72px;
      display:grid;
      place-items:center;
      margin:10px 0;
      font-size:42px;
      filter:drop-shadow(0 0 12px rgba(25,227,111,.36));
    }
    .card h3{text-align:center;font-size:21px;margin-bottom:7px}
    .card p{text-align:center;color:var(--muted);min-height:46px;line-height:1.4}
    .meta{display:flex;gap:7px;justify-content:center;flex-wrap:wrap;margin:15px 0}
    .pill{background:rgba(255,255,255,.08);border:1px solid rgba(255,255,255,.10);border-radius:8px;padding:7px 9px;font-size:12px;color:#dcecff}
    .card-actions{display:flex;gap:8px;position:relative;z-index:2}
    .card-actions a,.card-actions button{
      flex:1;
      text-align:center;
      text-decoration:none;
      border:1px solid rgba(255,255,255,.13);
      color:white;
      background:rgba(255,255,255,.06);
      border-radius:11px;
      padding:11px 8px;
      font-weight:900;
      font-size:13px;
      cursor:pointer;
    }
    .card-actions a:last-child,.card-actions button.primary{background:linear-gradient(135deg,#08a843,#22dc68);border:0}

    .flow{
      padding:20px;
      position:relative;
      overflow:hidden;
    }
    .steps{
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:10px;
    }
    .step{
      background:rgba(255,255,255,.05);
      border:1px solid rgba(25,227,111,.18);
      border-radius:16px;
      padding:14px;
    }
    .step b{color:var(--green);display:block;margin-bottom:7px}
    .step p{color:var(--muted);font-size:13px;line-height:1.45}

    .right-col{display:grid;gap:18px}
    .side-panel{padding:20px}
    .material-item,.news-item{
      display:flex;align-items:center;gap:12px;
      background:rgba(255,255,255,.055);
      border:1px solid rgba(255,255,255,.08);
      border-radius:15px;
      padding:12px;
      margin-bottom:10px;
    }
    .material-item span:first-child,.news-thumb{
      width:42px;height:42px;border-radius:12px;
      display:grid;place-items:center;
      background:linear-gradient(135deg,rgba(43,231,255,.32),rgba(25,227,111,.22));
      flex:none;
    }
    .material-item strong,.news-item strong{display:block;font-size:14px}
    .material-item small,.news-item small{color:var(--muted)}

    .wide-features{
      margin:28px 0 0;
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:14px;
    }
    .feature{
      padding:22px;
      background:rgba(5,18,40,.62);
      border:1px solid rgba(25,227,111,.23);
      border-radius:20px;
    }
    .feature span{font-size:34px}
    .feature h3{margin:10px 0 6px}
    .feature p{color:var(--muted);line-height:1.5}

    .library{
      margin-top:24px;
      padding:24px;
    }
    .library-grid{
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:14px;
    }
    .book{
      background:rgba(255,255,255,.055);
      border:1px solid rgba(255,255,255,.09);
      border-radius:18px;
      padding:18px;
    }
    .book h3{font-size:16px;margin:8px 0}
    .book p{color:var(--muted);font-size:13px;line-height:1.45}
    .book a{display:inline-block;margin-top:12px;color:var(--green);font-weight:900;text-decoration:none}

    footer{
      margin-top:34px;
      color:var(--muted);
      text-align:center;
      padding:28px;
      border-top:1px solid rgba(255,255,255,.10);
    }

    .modal{
      position:fixed;inset:0;background:rgba(0,0,0,.62);
      display:none;place-items:center;z-index:40;padding:20px;
    }
    .modal.active{display:grid}
    .modal-box{
      max-width:820px;width:100%;
      max-height:88vh;overflow:auto;
      background:#06152c;
      border:1px solid var(--border);
      border-radius:24px;
      padding:26px;
      box-shadow:var(--shadow);
    }
    .close{float:right;background:rgba(255,255,255,.08);border:1px solid rgba(255,255,255,.14);color:white;border-radius:10px;padding:8px 12px;cursor:pointer}
    .modal-box h2{margin-bottom:10px}
    .modal-box p,.modal-box li{color:#d7e8f6;line-height:1.65}
    .modal-box ul{margin:14px 0 14px 20px}

    .toast{
      position:fixed;
      right:24px;bottom:24px;
      background:rgba(3,20,32,.92);
      border:1px solid rgba(25,227,111,.40);
      border-radius:16px;
      padding:14px 16px;
      box-shadow:var(--shadow);
      transform:translateY(110px);
      opacity:0;
      transition:.3s;
      z-index:50;
    }
    .toast.show{transform:translateY(0);opacity:1}

    @media(max-width:1180px){
      .hero{grid-template-columns:1fr}
      .hero-visual{right:0;left:auto;opacity:.38}
      .layout{grid-template-columns:1fr}
      .filters{position:relative;top:0}
      .cards{grid-template-columns:repeat(2,1fr)}
      .right-col{grid-template-columns:1fr 1fr}
      .wide-features,.library-grid{grid-template-columns:repeat(2,1fr)}
    }
    @media(max-width:760px){
      .page,.nav{padding-left:16px;padding-right:16px}
      nav{display:none}
      .search-top{display:none}
      .stats,.cards,.steps,.right-col,.wide-features,.library-grid{grid-template-columns:1fr}
      .hero{padding-top:28px}
      .hero-visual{width:300px;height:300px;top:120px}
      h1{font-size:46px}
      .lead{font-size:17px}
    }
  </style>
</head>
<body>
  <div class="orb one"></div>
  <div class="orb two"></div>
  <div class="orb three"></div>

  <header>
    <div class="nav">
      <div class="brand">
        <div class="badge-logo">🛡️</div>
        <div>
          <div>Concursos</div>
          <small>CEARÁ 2026</small>
        </div>
      </div>
      <div class="search-top">
        <input id="topSearch" placeholder="Buscar concurso, órgão ou cidade..." />
        <span>⌕</span>
      </div>
      <nav>
        <a href="#inicio">Início</a>
        <a href="#concursos">Concursos</a>
        <a href="#materiais">Estudos</a>
        <a href="#planos">Planos</a>
        <a href="#atualizacao">Atualização</a>
      </nav>
    </div>
  </header>

  <main class="page" id="inicio">
    <section class="hero">
      <div class="hero-visual" aria-hidden="true">
        <svg class="ceara-map" viewBox="0 0 500 500" fill="none">
          <path d="M169 84 L261 54 L352 87 L406 162 L389 242 L346 279 L356 359 L294 421 L215 392 L163 331 L106 312 L91 230 L123 170 Z"
            fill="rgba(25,227,111,.08)" stroke="rgba(117,255,157,.95)" stroke-width="4"/>
          <path d="M169 84 L261 54 L352 87 M123 170 L260 190 L406 162 M91 230 L260 190 L389 242 M106 312 L260 190 L356 359 M163 331 L260 190 L294 421 M215 392 L260 190"
            stroke="rgba(43,231,255,.36)" stroke-width="2"/>
          <g fill="rgba(117,255,157,.95)">
            <circle cx="169" cy="84" r="5"/><circle cx="261" cy="54" r="5"/><circle cx="352" cy="87" r="5"/><circle cx="406" cy="162" r="5"/>
            <circle cx="389" cy="242" r="5"/><circle cx="356" cy="359" r="5"/><circle cx="294" cy="421" r="5"/><circle cx="215" cy="392" r="5"/>
            <circle cx="163" cy="331" r="5"/><circle cx="106" cy="312" r="5"/><circle cx="91" cy="230" r="5"/><circle cx="123" cy="170" r="5"/><circle cx="260" cy="190" r="6"/>
          </g>
        </svg>
      </div>

      <div class="hero-content">
        <div class="kicker">Painel inteligente de editais</div>
        <h1>Seu futuro, nosso <span>compromisso.</span></h1>
        <p class="lead">
          Encontre concursos públicos do Ceará para 2026, veja editais, acompanhe inscrições,
          organize materiais de estudo e gere planos focados por área e banca.
        </p>
        <div class="stats">
          <div class="stat"><strong id="statConcursos">8</strong><small>Concursos monitorados</small></div>
          <div class="stat"><strong>25.430</strong><small>Vagas previstas/mapeadas</small></div>
          <div class="stat"><strong>54</strong><small>Órgãos e bancas no radar</small></div>
        </div>
        <div class="actions">
          <a class="btn" href="#concursos">Ver concursos ↗</a>
          <a class="btn secondary" href="#atualizacao">Como atualiza ⟳</a>
        </div>
      </div>

      <aside class="monitor">
        <div class="status-row">
          <div class="status"><span class="dot"></span> Monitoramento ativo</div>
          <small id="lastUpdate">Atualizado agora</small>
        </div>
        <p>
          O painel foi estruturado para consultar uma base atualizável. Em hospedagem real,
          um robô pode verificar bancas e portais oficiais e publicar novos editais automaticamente.
        </p>
        <button class="btn" style="width:100%;justify-content:center" onclick="simulateUpdate()">Atualizar agora ⟳</button>
        <div class="timer">
          <div class="timebox"><strong id="h">00</strong><small>Horas</small></div>
          <div class="timebox"><strong id="m">05</strong><small>Minutos</small></div>
          <div class="timebox"><strong id="s">00</strong><small>Segundos</small></div>
        </div>
      </aside>
    </section>

    <section class="layout" id="concursos">
      <aside class="panel filters">
        <h2>🔎 Encontre seu concurso</h2>
        <label>Busca</label>
        <input id="search" placeholder="Digite para buscar..." />
        <label>Área</label>
        <select id="area">
          <option value="">Todas as áreas</option>
          <option>Educação</option>
          <option>Saúde</option>
          <option>Segurança</option>
          <option>Administrativo</option>
          <option>Tribunais</option>
        </select>
        <label>Situação</label>
        <select id="status">
          <option value="">Todas as situações</option>
          <option>Inscrições abertas</option>
          <option>Edital publicado</option>
          <option>Previsto</option>
          <option>Atualizado</option>
        </select>
        <button class="btn" style="width:100%;justify-content:center;margin-top:18px" onclick="renderCards()">Filtrar resultados</button>
        <button class="btn secondary" style="width:100%;justify-content:center;margin-top:10px" onclick="clearFilters()">Limpar filtros</button>
      </aside>

      <div class="main">
        <section class="panel" style="padding:20px">
          <div class="section-head">
            <h2>Concursos em destaque</h2>
            <a href="#concursos">Ver todos ›</a>
          </div>
          <div class="cards" id="cards"></div>
        </section>

        <section class="panel flow" id="atualizacao">
          <div class="section-head">
            <h2>Como o site se mantém atualizado</h2>
            <a href="#" onclick="simulateUpdate();return false;">Testar atualização</a>
          </div>
          <div class="steps">
            <div class="step"><b>1. Monitoramento 24/7</b><p>Robô consulta páginas de bancas, diários oficiais e portais de concursos.</p></div>
            <div class="step"><b>2. Extração de dados</b><p>Captura edital, retificação, inscrições, cargos, banca, cidade e prazos.</p></div>
            <div class="step"><b>3. Validação</b><p>Confere mudanças e registra a última alteração monitorada.</p></div>
            <div class="step"><b>4. Publicação</b><p>Atualiza a base do site e exibe novos editais para o candidato.</p></div>
          </div>
        </section>
      </div>

      <aside class="right-col">
        <section class="panel side-panel" id="materiais">
          <div class="section-head"><h2>Materiais em destaque</h2><a href="#materiais">Ver todos ›</a></div>
          <div class="material-item"><span>📘</span><div><strong>Português</strong><small>Teoria + questões</small></div></div>
          <div class="material-item"><span>∑</span><div><strong>Matemática</strong><small>Raciocínio lógico</small></div></div>
          <div class="material-item"><span>⚖️</span><div><strong>Direito Constitucional</strong><small>Artigos essenciais</small></div></div>
          <div class="material-item"><span>💻</span><div><strong>Informática</strong><small>Conceitos e prática</small></div></div>
          <div class="material-item"><span>🏛️</span><div><strong>Legislação local</strong><small>Conforme o edital</small></div></div>
        </section>

        <section class="panel side-panel" id="planos" style="border-color:var(--borderGreen)">
          <h2>Plano de estudo personalizado</h2>
          <p style="color:var(--muted);line-height:1.6;margin-bottom:14px">
            Crie uma trilha focada no concurso selecionado, com prioridade para disciplinas de maior peso.
          </p>
          <button class="btn" style="width:100%;justify-content:center" onclick="openPlan()">Criar plano</button>
        </section>

        <section class="panel side-panel">
          <h2>Últimas movimentações</h2>
          <div class="news-item"><div class="news-thumb">🟢</div><div><strong>Novo edital detectado</strong><small>Base local de demonstração</small></div></div>
          <div class="news-item"><div class="news-thumb">🟣</div><div><strong>Retificação monitorada</strong><small>Atualize antes de se inscrever</small></div></div>
          <div class="news-item"><div class="news-thumb">🟡</div><div><strong>Inscrições próximas</strong><small>Configure alertas no backend</small></div></div>
        </section>
      </aside>
    </section>

    <section class="wide-features">
      <div class="feature"><span>🎯</span><h3>Tudo em um só lugar</h3><p>Editais, materiais, planos e inscrições centralizados para facilitar sua rotina.</p></div>
      <div class="feature"><span>📚</span><h3>Materiais completos</h3><p>Referências por disciplina, legislação e conteúdos cobrados em edital.</p></div>
      <div class="feature"><span>⏱️</span><h3>Planos inteligentes</h3><p>Estudos distribuídos por prazo, peso da disciplina e objetivo do candidato.</p></div>
      <div class="feature"><span>✍️</span><h3>Inscrição facilitada</h3><p>Acesso direto à página da banca responsável por cada concurso.</p></div>
    </section>

    <section class="panel library">
      <div class="section-head"><h2>Biblioteca de referências oficiais</h2><a href="#materiais">Atualizável por edital</a></div>
      <div class="library-grid">
        <div class="book"><span>⚖️</span><h3>Constituição Federal</h3><p>Base para Direito Constitucional e Administração Pública.</p><a href="https://www.planalto.gov.br/ccivil_03/constituicao/constituicao.htm" target="_blank">Acessar referência</a></div>
        <div class="book"><span>🏛️</span><h3>Lei 8.112/1990</h3><p>Regime jurídico federal usado como referência em muitos editais.</p><a href="https://www.planalto.gov.br/ccivil_03/leis/l8112cons.htm" target="_blank">Acessar referência</a></div>
        <div class="book"><span>📗</span><h3>BNCC / Educação</h3><p>Referência importante para cargos de professor e pedagogia.</p><a href="https://www.gov.br/mec/pt-br/escola-em-tempo-integral/BNCC_EI_EF_110518_versaofinal.pdf" target="_blank">Acessar referência</a></div>
        <div class="book"><span>🩺</span><h3>ACS e ACE</h3><p>Legislação de agentes comunitários e combate às endemias.</p><a href="https://www.planalto.gov.br/ccivil_03/_ato2004-2006/2006/lei/l11350.htm" target="_blank">Acessar referência</a></div>
      </div>
    </section>

    <footer>
      <strong>Concursos Ceará 2026</strong><br>
      Protótipo funcional. Antes de se inscrever ou pagar taxa, confirme sempre no edital e no site oficial da banca.
    </footer>
  </main>

  <div class="modal" id="modal">
    <div class="modal-box">
      <button class="close" onclick="closeModal()">Fechar</button>
      <div id="modalContent"></div>
    </div>
  </div>
  <div class="toast" id="toast">Base atualizada com sucesso.</div>

  <script>
    const concursos = [
      {orgao:"SEPLAG CE", nome:"Secretaria do Planejamento e Gestão do Ceará", cidade:"Fortaleza", area:"Administrativo", status:"Previsto", nivel:"Superior", vagas:"123 vagas", data:"Previsão 2026", icon:"🛡️", link:"#", material:["Português", "Raciocínio Lógico", "Administração Pública", "Direito Constitucional"], plano:"Priorize Administração Pública, Direito Constitucional e questões de banca."},
      {orgao:"PMCE", nome:"Polícia Militar do Estado do Ceará", cidade:"Ceará", area:"Segurança", status:"Atualizado", nivel:"Médio", vagas:"1.000 vagas", data:"Acompanhar edital", icon:"👮", link:"#", material:["Português", "Direito Penal", "Direitos Humanos", "Atualidades"], plano:"Intercale legislação, condicionamento teórico e simulados semanais."},
      {orgao:"SEDUC CE", nome:"Secretaria da Educação do Ceará", cidade:"Ceará", area:"Educação", status:"Previsto", nivel:"Superior", vagas:"2.000 vagas", data:"Previsão 2026", icon:"📚", link:"#", material:["Didática", "LDB", "BNCC", "Conhecimentos específicos"], plano:"Reserve 50% da carga para disciplina específica e 30% para legislação educacional."},
      {orgao:"TJCE", nome:"Tribunal de Justiça do Estado do Ceará", cidade:"Fortaleza", area:"Tribunais", status:"Previsto", nivel:"Superior", vagas:"Cadastro reserva", data:"Radar 2026", icon:"⚖️", link:"#", material:["Direito Constitucional", "Direito Administrativo", "Português", "Informática"], plano:"Foco em lei seca, jurisprudência básica e questões de tribunais."},
      {orgao:"Coreáu CE", nome:"Prefeitura Municipal de Coreáu", cidade:"Coreáu", area:"Saúde", status:"Inscrições abertas", nivel:"Médio/Superior", vagas:"Diversos cargos", data:"Conferir banca", icon:"🏥", link:"https://www.consulpam.com.br/", material:["SUS", "Legislação municipal", "Português", "Conhecimentos específicos"], plano:"Estude SUS diariamente e revise legislação municipal a cada 48h."},
      {orgao:"Groaíras CE", nome:"Prefeitura Municipal de Groaíras", cidade:"Groaíras", area:"Administrativo", status:"Inscrições abertas", nivel:"Médio/Superior", vagas:"Diversos cargos", data:"Conferir banca", icon:"🏛️", link:"https://www.consulpam.com.br/", material:["Português", "Matemática", "Noções de Informática", "Conhecimentos específicos"], plano:"Comece por matérias comuns e avance para conhecimentos específicos do cargo."},
      {orgao:"Alto Santo CE", nome:"Prefeitura Municipal de Alto Santo", cidade:"Alto Santo", area:"Educação", status:"Edital publicado", nivel:"Médio/Superior", vagas:"Diversos cargos", data:"Conferir banca", icon:"🏫", link:"https://www.consulpam.com.br/", material:["LDB", "BNCC", "Português", "Conhecimentos pedagógicos"], plano:"Faça ciclos de 2h para pedagogia, 1h para legislação e 1h para questões."},
      {orgao:"IDECAN", nome:"Concursos Ceará em banca IDECAN", cidade:"Ceará", area:"Administrativo", status:"Previsto", nivel:"Variado", vagas:"Conforme edital", data:"Monitoramento", icon:"🧾", link:"https://concursos.idecan.org.br/", material:["Português", "Raciocínio Lógico", "Direito Administrativo", "Informática"], plano:"Use provas anteriores da banca para calibrar dificuldade e tempo de prova."}
    ];

    const cards = document.getElementById("cards");
    const search = document.getElementById("search");
    const topSearch = document.getElementById("topSearch");
    const area = document.getElementById("area");
    const statusSel = document.getElementById("status");
    const modal = document.getElementById("modal");
    const modalContent = document.getElementById("modalContent");
    const toast = document.getElementById("toast");

    function normalize(t){return (t||"").toString().toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g,"");}

    function getFiltered(){
      const q = normalize(search.value || topSearch.value);
      const a = area.value;
      const st = statusSel.value;
      return concursos.filter(c=>{
        const text = normalize([c.orgao,c.nome,c.cidade,c.area,c.status].join(" "));
        return (!q || text.includes(q)) && (!a || c.area === a) && (!st || c.status === st);
      });
    }

    function renderCards(){
      const data = getFiltered();
      document.getElementById("statConcursos").textContent = concursos.length;
      cards.innerHTML = data.map((c,i)=>`
        <article class="card">
          <span class="tag">${c.status}</span>
          <div class="org-icon">${c.icon}</div>
          <h3>${c.orgao}</h3>
          <p>${c.nome}</p>
          <div class="meta">
            <span class="pill">${c.nivel}</span>
            <span class="pill">${c.vagas}</span>
            <span class="pill">${c.cidade}</span>
          </div>
          <p style="min-height:auto;font-size:13px">Última alteração: ${c.data}</p>
          <div class="card-actions">
            <button onclick="openDetails(${i})">Detalhes</button>
            <a href="${c.link}" target="_blank">Inscrever-se</a>
          </div>
        </article>
      `).join("") || `<p style="color:var(--muted);padding:20px">Nenhum concurso encontrado com os filtros atuais.</p>`;
    }

    function openDetails(i){
      const c = concursos[i];
      modalContent.innerHTML = `
        <h2>${c.orgao} — ${c.nome}</h2>
        <p><strong>Cidade/abrangência:</strong> ${c.cidade}</p>
        <p><strong>Área:</strong> ${c.area} | <strong>Situação:</strong> ${c.status} | <strong>Nível:</strong> ${c.nivel}</p>
        <p><strong>Vagas:</strong> ${c.vagas}</p>
        <h3>Material de estudo recomendado</h3>
        <ul>${c.material.map(m=>`<li>${m}</li>`).join("")}</ul>
        <h3>Plano de estudo focado</h3>
        <p>${c.plano}</p>
        <p><strong>Referência:</strong> sempre confirme edital, cronograma, taxa e requisitos no site oficial da banca antes da inscrição.</p>
        <p><a class="btn" href="${c.link}" target="_blank">Acessar banca / inscrição</a></p>
      `;
      modal.classList.add("active");
    }

    function openPlan(){
      modalContent.innerHTML = `
        <h2>Plano de estudo personalizado</h2>
        <p>Modelo inicial de 6 semanas para concursos do Ceará:</p>
        <ul>
          <li><strong>Segunda:</strong> Português + questões.</li>
          <li><strong>Terça:</strong> Raciocínio lógico ou matemática.</li>
          <li><strong>Quarta:</strong> Legislação específica do cargo.</li>
          <li><strong>Quinta:</strong> Conhecimentos específicos.</li>
          <li><strong>Sexta:</strong> Informática, atualidades ou legislação local.</li>
          <li><strong>Sábado:</strong> Simulado e correção dos erros.</li>
          <li><strong>Domingo:</strong> Revisão leve e leitura do edital.</li>
        </ul>
        <p>Quando um edital for importado com pesos e disciplinas, o plano pode ser recalculado automaticamente.</p>
      `;
      modal.classList.add("active");
    }

    function closeModal(){modal.classList.remove("active");}
    modal.addEventListener("click", e=>{if(e.target===modal) closeModal();});

    function clearFilters(){
      search.value="";
      topSearch.value="";
      area.value="";
      statusSel.value="";
      renderCards();
    }

    function showToast(msg){
      toast.textContent=msg;
      toast.classList.add("show");
      setTimeout(()=>toast.classList.remove("show"),2600);
    }

    function simulateUpdate(){
      const now = new Date();
      document.getElementById("lastUpdate").textContent = "Atualizado às " + now.toLocaleTimeString("pt-BR",{hour:"2-digit",minute:"2-digit"});
      showToast("Verificação concluída. Nenhuma falha de carregamento.");
    }

    let total = 300;
    setInterval(()=>{
      total--;
      if(total < 0){total = 300; simulateUpdate();}
      const h = Math.floor(total/3600);
      const m = Math.floor((total%3600)/60);
      const s = total%60;
      document.getElementById("h").textContent = String(h).padStart(2,"0");
      document.getElementById("m").textContent = String(m).padStart(2,"0");
      document.getElementById("s").textContent = String(s).padStart(2,"0");
    },1000);

    [search, topSearch, area, statusSel].forEach(el=>el.addEventListener("input", renderCards));
    renderCards();
  </script>
</body>
</html>
