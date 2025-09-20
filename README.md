# mecom
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Корпорация МЕКОМ — МЭКОМ чемпионат</title>
<meta name="description" content="МЭКОМ — экономические игры между классами (7–11). Правила, сетка, регистрация." />
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#f7fbff;
    --blue:#005BFF;
    --blue-2:#2b7bff;
    --soft:#A7D8FF;
    --muted:#6b7280;
    --card:#ffffff;
    --glass: rgba(255,255,255,0.8);
    --radius:14px;
    --maxwidth:980px;
  }
  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0;
    font-family:'Poppins',system-ui,-apple-system,Segoe UI,Roboto,'Helvetica Neue',Arial;
    background: linear-gradient(180deg,var(--bg),#ffffff);
    color:#0b1220;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    line-height:1.45;
    -webkit-tap-highlight-color:transparent;
  }
  a{color:inherit;text-decoration:none}
  img{max-width:100%;height:auto;display:block}
  .wrap{max-width:var(--maxwidth);margin:0 auto;padding:18px}

  /* ---------- HERO ---------- */
  header.hero{
    position:relative;
    overflow:hidden;
    border-radius:18px;
    padding:18px;
    background:
      radial-gradient(600px 120px at -10% 0%, rgba(37,98,255,0.06), transparent 6%),
      linear-gradient(180deg, rgba(8,36,102,0.04), rgba(255,255,255,0.9));
    box-shadow:0 8px 30px rgba(12,24,60,0.06);
  }
  .hero-row{display:flex;gap:12px;align-items:center}
  .logo{
    width:72px;height:72px;border-radius:14px;background:linear-gradient(135deg,var(--blue),var(--blue-2));
    display:flex;align-items:center;justify-content:center;color:white;font-weight:800;font-size:20px;
    flex-shrink:0;box-shadow:0 6px 18px rgba(41,82,255,0.16);
    transform-origin:center; animation:logo-bob 3s ease-in-out infinite;
  }
  @keyframes logo-bob{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}
  .hero h1{font-size:18px;margin:0;color:var(--blue);letter-spacing:-0.2px}
  .hero .tag{margin-top:6px;color:var(--muted);font-size:13px}
  .hero .ctas{display:flex;gap:10px;margin-top:10px}
  .btn{
    display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;font-weight:700;font-size:14px;
    cursor:pointer;border:0;box-shadow:0 8px 24px rgba(10,30,120,0.06);
  }
  .btn-primary{background:linear-gradient(90deg,var(--blue),var(--blue-2));color:white; animation:btn-glow 2.4s infinite;}
  @keyframes btn-glow{0%{box-shadow:0 8px 20px rgba(0,91,255,0.14)}50%{box-shadow:0 14px 30px rgba(0,91,255,0.22)}100%{box-shadow:0 8px 20px rgba(0,91,255,0.14)}}
  .btn-ghost{background:#fff;border:1px solid rgba(10,40,120,0.06);color:var(--muted)}

  /* floating riff icons on hero */
  .floaters{position:absolute;inset:0;pointer-events:none;overflow:hidden}
  .riff {
    position:absolute;width:48px;height:48px;border-radius:50%;display:flex;align-items:center;justify-content:center;
    background:linear-gradient(180deg,var(--soft),#e6f3ff);color:var(--blue);opacity:0.95;box-shadow:0 6px 18px rgba(10,30,100,0.08);
    transform-origin:center;
    will-change:transform;
  }
  .riff.small{width:34px;height:34px}
  @keyframes riff-float {0%{transform:translateY(0) rotate(0)}50%{transform:translateY(-12px) rotate(8deg)}100%{transform:translateY(0) rotate(0)}}

  /* ---------- SECTIONS ---------- */
  section{margin-top:18px;padding:16px;border-radius:14px;background:var(--card);box-shadow:0 8px 26px rgba(12,24,56,0.04)}
  h2{margin:0 0 8px 0;font-size:16px;color:var(--blue)}
  p.muted{color:var(--muted);font-size:13px;margin:0}
  .cols{display:grid;grid-template-columns:1fr;gap:12px}
  @media(min-width:720px){ .cols{grid-template-columns:1fr 360px} }

  /* ---------- HOW TO PLAY (cards) ---------- */
  .steps{display:grid;grid-template-columns:repeat(2,1fr);gap:10px}
  @media(max-width:480px){ .steps{grid-template-columns:1fr} }
  .card{
    background:linear-gradient(180deg,#fff,#fbfdff);
    padding:12px;border-radius:12px;border:1px solid rgba(10,40,120,0.04);
    display:flex;gap:10px;align-items:flex-start;transition:transform .28s ease, box-shadow .28s ease;
  }
  .card:hover{transform:translateY(-6px);box-shadow:0 18px 40px rgba(30,60,140,0.08)}
  .icon{
    width:48px;height:48px;border-radius:10px;background:linear-gradient(135deg,var(--blue),var(--soft));display:flex;align-items:center;justify-content:center;color:white;font-weight:700;
    box-shadow:0 10px 24px rgba(10,60,200,0.08);flex-shrink:0;
  }
  .card h3{margin:0;font-size:15px;color:#0b234d}
  .card p{margin:6px 0 0 0;color:var(--muted);font-size:13px}

  /* nested list in step 3 */
  .strategy{margin-top:8px;padding-left:12px}
  .strategy li{margin:6px 0;color:var(--muted);font-size:13px;line-height:1.4}

  /* ---------- PRIZES TABLE ---------- */
  table{width:100%;border-collapse:collapse;font-size:14px}
  thead td{background:linear-gradient(90deg,var(--blue),var(--blue-2));color:white;padding:10px;border-radius:8px 8px 0 0;font-weight:700}
  tbody td{padding:12px;border-bottom:1px dashed rgba(10,30,80,0.04)}
  .amount{font-weight:800;text-align:right;color:var(--blue-2);font-variant-numeric:tabular-nums}

  /* ---------- PRIZES SECTION (styling taken from "каша") ---------- */
  .prizes-section{
    background: linear-gradient(90deg,var(--blue),var(--blue-2));
    color: #fff;
    border-radius:12px;
    padding:12px;
    box-shadow:0 12px 34px rgba(10,30,80,0.08);
    margin-top:12px;
  }
  .prizes-section .section-title{
    font-weight:800;
    margin:6px 0 10px 0;
    font-size:15px;
    display:flex;
    align-items:center;
    gap:10px;
    animation:prizesFadeIn 520ms cubic-bezier(.2,.9,.2,1);
  }
  .prizes-table{
    display:flex;
    flex-direction:column;
    gap:10px;
    margin-top:6px;
  }
  .prize-row{
    display:flex;justify-content:space-between;align-items:center;
    padding:10px 12px;border-radius:10px;background:rgba(255,255,255,0.06);
    font-weight:700;
    animation:prizeRowIn 420ms ease;
  }
  .prize-row .label{font-weight:700}
  .prize-row .value{font-variant-numeric:tabular-nums}
  .prize-row.highlight{
    background:linear-gradient(90deg,#fff5cc,#ffe680);
    color:#533f00;
    box-shadow:0 10px 30px rgba(255,193,7,0.06);
  }
  @keyframes prizesFadeIn { from{opacity:0;transform:translateY(-6px)} to{opacity:1;transform:none} }
  @keyframes prizeRowIn { from{opacity:0;transform:translateY(6px)} to{opacity:1;transform:none} }

  /* ---------- WHY MEKOM ---------- */
  .why{display:flex;gap:12px;align-items:center}
  .why .text{flex:1}
  .badge{background:linear-gradient(90deg,var(--soft),#cfeaff);padding:8px 10px;border-radius:10px;color:var(--blue);font-weight:700}

  /* ---------- FORM ---------- */
  form input, form select, form textarea{width:100%;padding:10px;margin-top:8px;border-radius:10px;border:1px solid rgba(10,30,80,0.06);font-size:14px}
  .submit{margin-top:10px;width:100%}
  .small{font-size:13px;color:var(--muted)}

  /* make t.me links clearly clickable */
  a[href^="https://t.me"]{color:var(--blue);font-weight:700;text-decoration:none}
  a[href^="https://t.me"]:hover{ text-decoration:underline }

  /* ---------- FOOTER ---------- */
  footer{margin-top:14px;text-align:center;color:var(--muted);font-size:13px;padding:14px}

  /* ---------- Animations ---------- */
  .fade-in{opacity:0;transform:translateY(12px);transition:all 560ms cubic-bezier(.2,.9,.2,1)}
  .fade-in.show{opacity:1;transform:none}
  .typing{display:inline-block;white-space:nowrap;overflow:hidden;border-right:2px solid rgba(0,0,0,0.12)}
  @keyframes pulse-blue{0%{transform:scale(1)}50%{transform:scale(1.03)}100%{transform:scale(1)}}
  .pulse{animation:pulse-blue 2400ms infinite}

  /* small helpers */
  .flex{display:flex;gap:8px;align-items:center}
  .muted-2{color:#4b5563;font-size:13px}

  /* ===========================================================
     MECOM BRACKET — заменённый блок стилей (улучшенная версия)
     =========================================================== */
  .mecom-bracket{--me-blue:#005BFF;--me-blue-2:#2b7bff;--me-soft:#A7D8FF;background: linear-gradient(90deg,rgba(7,48,159,0.03),rgba(0,91,255,0.02));border-radius:12px;padding:10px;box-sizing:border-box;color:#0b1220;font-family:'Poppins',system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;}
  .mecom-rounds-nav{display:flex;gap:6px;position:sticky;top:8px;z-index:5;margin-bottom:8px;overflow-x:auto;-webkit-overflow-scrolling:touch;scrollbar-width:none;}
  .mecom-rounds-nav::-webkit-scrollbar{display:none;}
  .mecom-rounds-nav .mecom-chip{background:rgba(0,91,255,0.06);color:var(--me-blue);padding:8px 10px;border-radius:999px;font-weight:700;cursor:pointer;border:0;font-size:12px;white-space:nowrap;}
  .mecom-rounds-nav .mecom-chip.is-active{background:linear-gradient(90deg,var(--me-blue),var(--me-blue-2));color:#fff;}

  /* important layout tweak: top-align slides so short slides don't force big container space */
  .mecom-swiper{position:relative;overflow:hidden;border-radius:10px;background:linear-gradient(180deg,#fff,#f7fbff);border:1px solid rgba(10,30,80,0.04);transition:height .26s ease;}
  .mecom-swiper-track{display:flex;width:100%;will-change:transform;transform:translate3d(0,0,0);transition:transform .26s ease;touch-action:pan-y;align-items:flex-start;}
  .mecom-slide{min-width:100%;padding:10px;align-self:flex-start;display:flex;flex-direction:column;}
  .mecom-round-title{font-weight:800;margin-bottom:8px;color:#0b234d;display:flex;justify-content:space-between;align-items:center}

  /* PACK & TEAM: layout (class/branch on left; team name on right) */
  .pack{border-radius:12px;padding:10px;background:linear-gradient(180deg,#fff,#fbfdff);border:1px solid rgba(10,40,120,0.04);margin-bottom:12px}
  .pack-title{font-weight:800;color:#0b234d;margin-bottom:8px;display:flex;align-items:center;gap:8px}
  .pack-contents{display:flex;flex-direction:column;gap:8px}
  .mecom-team{display:flex;justify-content:space-between;align-items:center;padding:12px;border-radius:10px;background:rgba(0,0,0,0.03);transition:transform .18s ease, box-shadow .18s ease}
  .mecom-team:hover{transform:translateY(-3px);box-shadow:0 10px 24px rgba(10,30,80,0.06)}
  .mecom-team .left{display:flex;flex-direction:column;gap:6px;min-width:95px}
  .mecom-team .name-wrap{display:flex;flex-direction:column;align-items:flex-end;gap:4px}
  .mecom-team .team-name{font-weight:800;font-size:15px;color:#0b234d;white-space:nowrap}
  .mecom-team.empty-slot{opacity:0.6;font-style:italic;color:var(--muted);padding:6px 12px;height:28px;display:flex;align-items:center;justify-content:flex-end;}
  .mecom-team.placeholder{background:transparent;border:1px dashed rgba(0,0,0,0.03)}

  /* TAGS: класс и филиал — цветные пиллы */
  .mecom-tag{font-size:11px;font-weight:800;padding:4px 6px;border-radius:999px;line-height:1;display:inline-block}
  .mecom-tag-grade{background:rgba(0,0,0,0.06);color:#111}
  .mecom-tag-north{background:rgba(10,92,255,0.09);color:var(--blue)}
  .mecom-tag-south{background:rgba(255,59,59,0.10);color:#c0392b}
  .mecom-tag-east{background:rgba(255,160,60,0.10);color:#d35400}
  .mecom-tag-west{background:rgba(88,165,90,0.10);color:#1e9b4a}

  /* WINNERS */
  .mecom-team.winner{background:linear-gradient(90deg,var(--me-soft),#dff4ff);box-shadow:0 10px 30px rgba(0,110,255,0.06)}
  .mecom-team.winner .team-name{color:var(--blue)}
  .mecom-team.winner .team-name::after{content:" 🏅";margin-left:8px}

  /* CHAMPION style */
  .mecom-team.champion{background: linear-gradient(90deg,#fff5cc,#ffe680);color:#533f00;border:1px solid rgba(255,193,7,0.12);box-shadow:0 12px 30px rgba(255,193,7,0.08)}
  .mecom-team.champion .team-name{ color:#533f00 }
  .mecom-team.champion .team-name::after{ content: " 👑"; margin-left:8px; }

  .promoted-note{font-size:12px;color:var(--muted);margin-top:6px}

  .mecom-dots{display:flex;justify-content:center;gap:6px;padding:10px 0 2px 0}
  .mecom-dot{width:8px;height:8px;border-radius:50%;background:rgba(0,0,0,0.15)}
  .mecom-dot.is-active{background:var(--me-blue)}

  @media(min-width:960px){ .mecom-swiper{ border-radius:12px } }
  @media (max-width:560px){ .mecom-team .team-name{ font-size:14px } }
</style>
</head>
<body>
  <div class="wrap">
    <!-- HERO -->
    <header class="hero">
      <div class="floaters" aria-hidden="true">
        <div class="riff" style="left:6%;top:10%"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><circle cx="12" cy="12" r="10" fill="white" opacity="0.06"/><path d="M6 12c2-5 10-5 10 0-2 5-10 5-10 0z" fill="#005BFF" opacity="0.18"/></svg></div>
        <div class="riff small" style="right:6%;top:22%"><svg width="18" height="18" viewBox="0 0 24 24"><path d="M6 12c2-5 10-5 10 0-2 5-10 5-10 0z" fill="#2b7bff"/></svg></div>
        <div class="riff" style="left:8%;bottom:10%"><svg width="24" height="24" viewBox="0 0 24 24"><path d="M12 3c5 0 9 4 9 9s-4 9-9 9S3 17 3 12 7 3 12 3z" fill="#A7D8FF"/></svg></div>
      </div>

      <div class="hero-row">
        <div class="logo" aria-hidden="true">МЕМ</div>
        <div style="flex:1">
          <h1 id="hero-title">МЭКОМ — экономика, азарт и риф</h1>
          <div class="tag muted"> Корпорация МЕКОМ — экономические игры между старшими классами (с 7 по 11, Южного и Северного филиала) школы Взмах </div>
          <div class="ctas">
            <button class="btn btn-primary" onclick="scrollToId('how')">Как играть</button>
            <button class="btn btn-ghost" onclick="scrollToId('reg')">Регистрация</button>
          </div>
        </div>
      </div>
    </header>

    <!-- ABOUT / WHAT IS MEKOM -->
    <section id="about" class="fade-in">
      <h2>Что такое МЭКОМ?</h2>
      <p class="muted">МЭКОМ — внутренняя школьная экономическая игра: команды из разных классов соревнуются в сериях раундов, принимают бизнес-решения и «зарабатывают» наивысший <strong>риф</strong> — рейтинговый индекс фирмы. Чем лучше стратегия и командная игра, тем выше шанс пройти в финал.</p>
      <div style="margin-top:12px" class="cols">
        <div>
          <div class="card" style="align-items:flex-start">
            <div class="icon" aria-hidden="true">Р</div>
            <div>
              <h3>Для кого?</h3>
              <p class="muted">Команды классов 7–11 из Южного и Северного филиалов. Каждый раунд — новая возможность показать смекалку.</p>
            </div>
          </div>

          <div class="card" style="margin-top:10px">
            <div class="icon" aria-hidden="true">⚖</div>
            <div>
              <h3>Цель</h3>
              <p class="muted">Набирать наибольший риф в играх и пройти через турнирную сетку до финала — там решается всё.</p>
            </div>
          </div>
        </div>

        <aside class="bracket-info fade-in" style="padding:8px">
          <div class="chip highlight">Ближайший чемпионат — южный филиал</div>
          <p class="muted" style="margin-top:8px">Следите за обновлениями в телеграме МЕКОМ (<a href="https://t.me/mekom_info" target="_blank" rel="noopener">@mekom_info</a>)</p>
          <div style="margin-top:12px" class="small muted-2">Организаторы: Ян · Егор · Артемий</div>
        </aside>
      </div>
    </section>

    <!-- HOW TO WIN -->
    <section id="how" class="fade-in">
      <h2>Как выиграть ВСЁ</h2>
      <div class="steps" style="margin-top:12px">
        <div class="card">
          <div class="icon">👥</div>
          <div>
            <h3>1. Собери команду</h3>
            <p class="muted">2–5 человек из класса, распределите роли: пусть хотя бы один игрок полностью изучит правила и формулы игры)</p>
          </div>
        </div>

        <div class="card">
          <div class="icon">📥</div>
          <div>
            <h3>2. Регистрация и старт</h3>
            <p class="muted">Регистрируйтесь у организаторов или через форму — получите отчёт по фирме за нулевой период и разбор показателей.</p>
          </div>
        </div>

        <div class="card">
          <div class="icon">⚙️</div>
          <div>
            <h3>3. Игра в раунде — стратегия важнее азарта</h3>
            <p class="muted">В каждом раунде вы принимаете решения: докупать станки, вкладывать в рекламу, повышать качество продукции и т. п.</p>
            <ul class="strategy">
              <li><strong>Разберите свои показатели и придумайте стратегию.</strong></li>
              <li><strong>Не бойтесь продуманных решений.</strong> Смелость + расчёт = преимущество.</li>
            </ul>
          </div>
        </div>

        <div class="card">
          <div class="icon">🎯</div>
          <div>
            <h3>4. Прохождение стадий</h3>
            <p class="muted">Отборочные → Вторая стадия → Полуфинал → Финал → Победитель.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- HOW TO PLAY (decisions) -->
    <section id="how-play" class="fade-in">
      <h2>Как играть — суть и решения</h2>
      <p class="muted">В каждом периоде вы принимаете 5 ключевых решений, которые формируют результаты фирмы и влияют на РИФ.</p>

      <div class="steps" style="margin-top:12px">
        <div class="card small">
          <div class="icon">1</div>
          <div>
            <h3>Установить цену</h3>
            <p class="muted">Цена влияет на спрос, маржу и конкурентоспособность.</p>
          </div>
        </div>

        <div class="card small">
          <div class="icon">2</div>
          <div>
            <h3>Производство</h3>
            <p class="muted">Определите количество товара и учитывайте загрузку фабрики.</p>
          </div>
        </div>

        <div class="card small">
          <div class="icon">3</div>
          <div>
            <h3>Маркетинг</h3>
            <p class="muted">Вложения в рекламу повышают потенциал спроса.</p>
          </div>
        </div>

        <div class="card small">
          <div class="icon">4</div>
          <div>
            <h3>Инвестиции</h3>
            <p class="muted">Амортизация и капвложения влияют на мощности и эффективность.</p>
          </div>
        </div>

        <div class="card small">
          <div class="icon">5</div>
          <div>
            <h3>НИОКР</h3>
            <p class="muted">Повышают качество и долгосрочную конкурентоспособность.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- PRIZES -->
    <section id="prizes" class="prizes-section fade-in" aria-label="Призовые">
      <div class="section-title">🏆 Призовые на Чемпионат</div>
      <div class="prizes-table" role="list" aria-hidden="false">
        <div class="prize-row highlight" role="listitem">
          <div class="label">1 место</div>
          <div class="value"><span class="counter" data-target="1140000">0</span> экси</div>
        </div>

        <div class="prize-row" role="listitem">
          <div class="label">2 место</div>
          <div class="value"><span class="counter" data-target="390000">0</span> экси</div>
        </div>

        <div class="prize-row" role="listitem">
          <div class="label">Команды вне финала</div>
          <div class="value"><span class="counter" data-target="90000">0</span> экси</div>
        </div>

        <div class="prize-row" role="listitem">
          <div class="label">Не прошли 3 стадию</div>
          <div class="value"><span class="counter" data-target="25000">0</span> экси</div>
        </div>

        <div class="prize-row" role="listitem">
          <div class="label">Не прошли отборочные</div>
          <div class="value"><span class="counter" data-target="5000">0</span> экси</div>
        </div>
      </div>
    </section>

    <!-- ========================= TOURNAMENT (REPLACED BLOCK) ========================= -->
    <section id="tournament" class="fade-in" aria-label="Турнирная сетка">
      <h2>Турнирная сетка — этапы</h2>

      <div id="mecom-bracket" class="mecom-bracket" data-storage-key="mecom_bracket_state_v4" data-auto-seed="true">
        <div class="mecom-rounds-nav" id="mecomRoundsNav"></div>

        <div class="mecom-swiper" id="mecomSwiper">
          <div class="mecom-swiper-track" id="mecomSwiperTrack"></div>
        </div>

        <div class="mecom-dots" id="mecomDots"></div>
      </div>
    </section>
    <!-- ======================= / TOURNAMENT ======================= -->

    <!-- WHY MEKOM -->
    <section id="why" class="fade-in">
      <h2>Почему мы — МЕКОМ?</h2>
      <div class="why" style="margin-top:8px">
        <div class="badge">Легенда</div>
        <div class="text">
          <p class="muted">Когда мы создавали корпорацию, решили сделать лёгкий реверанс в сторону нашего учителя Марии Егоровны — взяли её «МЕ» и просто докрутили название. Оставили знакомое звучание, но слегка поменяли букву, чтобы получилось уникально. Теперь МЕКОМ — это и про нас, и про игру, и про то, что в жизни всегда есть место креативу и хитрости (а так же подхалимству).</p>
        </div>
      </div>
    </section>

    <!-- REGISTRATION -->
    <section id="reg" class="fade-in">
      <h2>Как принять участие</h2>
      <p class="muted">Соберите команду, зарегистрируйтесь и готовьтесь к раундам. Заполнив форму, вы спустя какое-то время получите подтверждение/отказ в регистрации. В случае подтверждения регистрации команды, название вашей команды отобразиться на самом сайте в таблице, а именно в разделе отборочные! </p>

      <button class="btn btn-primary submit" type="submit"><a href="https://forms.gle/Zo1daNJ5sn5e5AcJ6" target="_blank" rel="noopener" style="color:inherit">Подать заявку на участие</a></button>
    </section>

    <!-- CONTACTS -->
    <section class="fade-in">
      <h2>Контакты</h2>
      <p class="muted">
        Телеграм-канал: <a href="https://t.me/mekom_info" target="_blank" rel="noopener">@mekom_info</a><br/>
        Техподдержка: <a href="https://t.me/mekom_chat" target="_blank" rel="noopener">@mekom_chat</a>
      </p>
    </section>

    <footer class="fade-in">
      <div style="font-weight:700">Корпорация МЕКОМ</div>
      <div class="muted" style="margin-top:6px">Сделано в школе, но на мировом уровне, с хитростью и дерзостью.</div>
    </footer>
  </div>

<script>
  "use strict";

  /* --------------------
     Основные общие утилиты и эффекты (scroll, fade-in, counters, floaters, title-typing)
     Оставлены из твоего оригинального лендинга — работают вместе с новой сеткой.
     -------------------- */

  // ----- smooth scroll to id -----
  function scrollToId(id){
    const el = document.getElementById(id);
    if(!el) return;
    el.scrollIntoView({behavior:'smooth',block:'start'});
  }

  // ----- fade-in on scroll -----
  (function initFadeIn(){
    const fades = document.querySelectorAll('.fade-in');
    if(!fades) return;
    const io = new IntersectionObserver((entries)=>{
      entries.forEach(e=>{
        if(e.isIntersecting){
          e.target.classList.add('show');
          io.unobserve(e.target);
        }
      });
    }, {threshold: 0.12});
    fades.forEach(f=>io.observe(f));
  })();

  // ----- format number helper -----
  function formatNumber(n){
    return n.toString().replace(/\B(?=(\d{3})+(?!\d))/g," ");
  }

  // ----- animateCounter (only define if not present) -----
  if(typeof window.animateCounter !== 'function'){
    window.animateCounter = function(el, target, duration=1200){
      const startTime = performance.now();
      const from = 0;
      function step(now){
        const t = Math.min((now - startTime) / duration, 1);
        const value = Math.floor(from + (target - from) * t);
        el.textContent = formatNumber(value);
        if(t < 1) requestAnimationFrame(step);
        else el.textContent = formatNumber(target);
      }
      requestAnimationFrame(step);
    };
  }

  // ----- initialize prize counters when visible -----
  (function initPrizeCounters(){
    const counters = document.querySelectorAll('.counter');
    if(!counters || counters.length === 0) return;
    const cIO = new IntersectionObserver((entries, obs)=>{
      entries.forEach(en=>{
        if(en.isIntersecting){
          const el = en.target;
          const tgt = parseInt(el.dataset.target, 10) || 0;
          animateCounter(el, tgt, 1300);
          obs.unobserve(el);
        }
      });
    }, {threshold: 0.4});
    counters.forEach(c=> cIO.observe(c));
  })();

  // ----- floating riff animations (randomized) -----
  (function initFloaters(){
    const floaters = document.querySelectorAll('.riff');
    floaters.forEach((el, i)=>{
      el.style.animation = `riff-float ${4 + (i%3)}s ${i*0.3}s ease-in-out infinite`;
    });
    window.addEventListener('scroll', ()=>{
      const sc = window.scrollY;
      floaters.forEach((el, idx)=>{
        const speed = (idx % 2 === 0) ? 0.08 : 0.04;
        el.style.transform = `translateY(${sc * speed}px)`;
      });
    }, {passive:true});
  })();

  // ----- tiny typing for hero title -----
  (function typeTitle(){
    const el = document.getElementById('hero-title');
    if(!el) return;
    const text = el.textContent.trim();
    el.textContent = '';
    let idx = 0;
    function tick(){
      if(idx <= text.length){
        el.textContent = text.slice(0, idx);
        idx++;
        setTimeout(tick, 25);
      } else {
        el.style.borderRight = 'none';
      }
    }
    tick();
  })();

  // ----- form stub (kept simple) -----
  function submitForm(e){
    if(e && e.preventDefault) e.preventDefault();
    const team = (document.querySelector('input[name="team"]') || {}).value || '';
    alert('Заявка принята: ' + (team ? team : 'команда без имени') + '. Организаторы свяжутся в телеграме.');
  }

  /* ===========================================================
     MECOM BRACKET — полностью изолированная реализация турнирной сетки
     Вставлена отдельно, чтобы заменить старую сетку. Всё, что нужно —
     правь переменную TOURNAMENT_DATA ниже.
     =========================================================== */
  (function(){
    // локальные короткие селекторы
    const qs = (s, r=document) => r.querySelector(s);
    const qsa = (s, r=document) => Array.from((r||document).querySelectorAll(s));

    // Рендер-опции
    const RENDER_OPTIONS = { keepEmptySlots: false };

    // -----------------------
    // ДАННЫЕ: правь только эту переменную (TOURNAMENT_DATA)
    // Пример структуры: массив раундов -> packs -> teams (team: {name, grade, branch, noDescription, _promotedFrom, _showPromoted})
    // Подсветка победителей: pack.winnerIndex (число) или pack.winnerIndex = [i,j]
    // Пометка чемпиона: round.winnerchamp = { pack: pIndex, index: tIndex } или pack.winnerchampIndex
    // -----------------------
    const TOURNAMENT_DATA = [
      {
        name: "Отборочные",
        packs: [
          {
            title: "Пачка A — 7 класс",
            teams: [
              { name: "Альфа", grade: "7", branch: "Север" },
              { name: "Бета",  grade: "7", branch: "Юг" },
              { name: "Гамма", grade: "7", branch: "Север" },
              { name: "Дельта", grade: "7", branch: "Юг" },
              { name: "Эпсилон", grade: "7", branch: "Север" },
              { name: "Зета", grade: "7", branch: "Юг" }
            ],
            winnerIndex: [0,1]
          },
          {
            title: "Пачка B — 8 класс",
            teams: [
              { name: "Икс", grade: "8", branch: "Север" },
              { name: "Йота", grade: "8", branch: "Юг" },
              { name: "Каппа", grade: "8", branch: "Север" },
              { name: "Лямбда", grade: "8", branch: "Юг" },
              { name: "Мю", grade: "8", branch: "Север" },
              { name: "Ню", grade: "8", branch: "Юг" }
            ],
            winnerIndex: [0,2]
          },
          {
            title: "Пачка C — смешанная",
            teams: [
              { name: "Омега", grade: "9", branch: "Север" },
              { name: "Пси", grade: "9", branch: "Юг" },
              { name: "Ро", grade: "10", branch: "Север" },
              { name: "Сигма", grade: "10", branch: "Юг" },
              { name: "Тау", grade: "11", branch: "Север" },
              { name: "Упсилон", grade: "11", branch: "Юг" }
            ],
            winnerIndex: [4,5]
          }
        ]
      },
      {
        name: "Вторая стадия",
        packs: [
          {
            title: "Пачка D",
            teams: [
              { name: null, grade: null, branch: null },
              { name: null, grade: null, branch: null },
              { name: null, grade: null, branch: null }
            ]
          },
          {
            title: "Пачка E",
            teams: [
              { name: null, grade: null, branch: null },
              { name: null, grade: null, branch: null },
              { name: null, grade: null, branch: null }
            ]
          }
        ]
      },
      {
        name: "Полуфинал",
        packs: [
          { title: "Пачка F1", teams: [ {name:null,grade:null,branch:null}, {name:null,grade:null,branch:null} ] },
          { title: "Пачка F2", teams: [ {name:null,grade:null,branch:null}, {name:null,grade:null,branch:null} ] }
        ]
      },
      {
        name: "Финал",
        winnerchamp: { pack: 0, index: 0 }, // пример: первый слот первой пачки — чемпион
        packs: [
          {
            title: "Финальная пачка",
            teams: [
              { name: "Титул", grade: "11", branch: "Север" },
              { name: "Претендент", grade: "11", branch: "Юг" }
            ]
          }
        ]
      }
    ];

    // -----------------------
    // Внутренние методы рендера
    // -----------------------
    function deepCopy(obj){ return JSON.parse(JSON.stringify(obj)); }
    function prepareRenderData(src){ return deepCopy(src); }

    // DOM references for this bracket
    const ROOT = qs('#mecom-bracket');
    if(!ROOT){
      console.warn('[MECOM] #mecom-bracket not found — сетка не инициализирована');
      return;
    }
    const navEl = qs('#mecomRoundsNav', ROOT);
    const swiper = qs('#mecomSwiper', ROOT);
    const track = qs('#mecomSwiperTrack', ROOT);
    const dotsEl = qs('#mecomDots', ROOT);

    // load/save using data-storage-key if provided
    const STORAGE_KEY = ROOT.getAttribute('data-storage-key') || 'mecom_bracket_state_vX';
    const AUTO_SEED = (ROOT.getAttribute('data-auto-seed') || 'true') === 'true';

    let renderData = prepareRenderData(TOURNAMENT_DATA);

    // Render navigation (round chips)
    function renderNav(activeIdx=0){
      navEl.innerHTML = '';
      renderData.forEach((r, idx)=>{
        const btn = document.createElement('button');
        btn.type = 'button';
        btn.className = 'mecom-chip' + (idx === activeIdx ? ' is-active' : '');
        btn.textContent = r.name || `Раунд ${idx+1}`;
        btn.addEventListener('click', ()=> goTo(idx));
        navEl.appendChild(btn);
      });
    }

    // Render dots (pager)
    function renderDots(activeIdx=0){
      dotsEl.innerHTML = '';
      renderData.forEach((_, idx)=>{
        const d = document.createElement('div');
        d.className = 'mecom-dot' + (idx === activeIdx ? ' is-active' : '');
        d.addEventListener('click', ()=> goTo(idx));
        dotsEl.appendChild(d);
      });
    }

    // Render slides (each round)
    function renderSlides(){
      track.innerHTML = '';
      renderData.forEach((round, rIndex)=>{
        const slide = document.createElement('div');
        slide.className = 'mecom-slide fade-in';

        // title
        const title = document.createElement('div');
        title.className = 'mecom-round-title';
        const left = document.createElement('div'); left.textContent = round.name || `Раунд ${rIndex+1}`;
        title.appendChild(left);
        slide.appendChild(title);

        // Iterate packs
        (round.packs || []).forEach((pack, pIndex)=>{
          const packEl = document.createElement('div');
          packEl.className = 'pack';

          const packTitle = document.createElement('div');
          packTitle.className = 'pack-title';
          packTitle.textContent = pack.title || `Пачка ${pIndex+1}`;
          packEl.appendChild(packTitle);

          const contents = document.createElement('div'); contents.className = 'pack-contents';

          (pack.teams || []).forEach((team, tIndex)=>{
            // Empty/team placeholder handling
            if(!team || !team.name){
              if(RENDER_OPTIONS.keepEmptySlots){
                const teamEl = document.createElement('div');
                teamEl.className = 'mecom-team empty-slot placeholder';
                const leftBlock = document.createElement('div'); leftBlock.className = 'left';
                const rightBlock = document.createElement('div'); rightBlock.className = 'name-wrap';
                const nameDiv = document.createElement('div'); nameDiv.className = 'team-name';
                nameDiv.textContent = '(пусто)';
                rightBlock.appendChild(nameDiv);
                teamEl.appendChild(leftBlock);
                teamEl.appendChild(rightBlock);
                contents.appendChild(teamEl);
              }
              return;
            }

            const teamEl = document.createElement('div');
            teamEl.className = 'mecom-team';

            // winner highlighting (pack-level)
            if(typeof pack.winnerIndex === 'number' && pack.winnerIndex === tIndex) teamEl.classList.add('winner');
            else if(Array.isArray(pack.winnerIndex) && pack.winnerIndex.includes(tIndex)) teamEl.classList.add('winner');

            // champion detection (pack-level or round-level)
            const isChampion =
              (typeof pack.winnerchampIndex === 'number' && pack.winnerchampIndex === tIndex)
              || (round && round.winnerchamp && round.winnerchamp.pack === pIndex && round.winnerchamp.index === tIndex);

            if(isChampion){
              teamEl.classList.add('champion');
              teamEl.classList.remove('winner'); // champion visual takes precedence
            }

            // left block (grade + branch) unless explicitly hidden
            const leftBlock = document.createElement('div'); leftBlock.className = 'left';
            if(!(team && team.noDescription)){
              const cls = document.createElement('span'); cls.className = 'mecom-tag mecom-tag-grade';
              cls.textContent = team && team.grade ? `${team.grade} класс` : '';
              const br = document.createElement('span');
              let branchClass = '';
              if(team && team.branch){
                const b = String(team.branch).toLowerCase();
                if(b.includes('север')) branchClass = 'mecom-tag-north';
                else if(b.includes('юг')) branchClass = 'mecom-tag-south';
                else if(b.includes('вост')) branchClass = 'mecom-tag-east';
                else if(b.includes('зап')) branchClass = 'mecom-tag-west';
                else branchClass = 'mecom-tag-north';
              }
              br.className = 'mecom-tag ' + branchClass;
              br.textContent = team && team.branch ? team.branch : '';
              leftBlock.appendChild(cls);
              leftBlock.appendChild(br);
            }

            // right block (name)
            const rightBlock = document.createElement('div'); rightBlock.className = 'name-wrap';
            const nameDiv = document.createElement('div'); nameDiv.className = 'team-name';
            nameDiv.textContent = team && team.name ? team.name : '(пусто)';
            rightBlock.appendChild(nameDiv);

            // optionally show promoted-note if present and flagged
            if(team && team._promotedFrom && team._showPromoted && !(team.noDescription)){
              const note = document.createElement('div');
              note.className = 'promoted-note';
              note.textContent = `проходит из: ${team._promotedFrom.roundName} · ${team._promotedFrom.packTitle}`;
              rightBlock.appendChild(note);
            }

            teamEl.appendChild(leftBlock);
            teamEl.appendChild(rightBlock);
            contents.appendChild(teamEl);
          });

          packEl.appendChild(contents);
          slide.appendChild(packEl);
        });

        track.appendChild(slide);
      });

      // trigger fade-ins (after DOM insert)
      requestAnimationFrame(()=> {
        qsa('.mecom-slide.fade-in', track).forEach(el => el.classList.add('show'));
        setTimeout(()=> updateHeightForSlide(current), 30);
      });
    }

    // -----------------------
    // Swiper: touch + mouse drag
    // -----------------------
    let current = 0;
    let startX = 0, startY = 0, curX = 0;
    let dragging = false;
    let width = 0;
    let lastMoveAt = 0;

    function setTranslate(px, withAnim=true){
      track.style.transition = withAnim ? 'transform .26s ease' : 'none';
      track.style.transform = `translate3d(${px}px,0,0)`;
    }

    function updateWidth(){ width = swiper.clientWidth || 1; }
    window.addEventListener('resize', ()=>{ updateWidth(); setTranslate(-current*width, false); updateHeightForSlide(current); });

    function updateHeightForSlide(i){
      const slide = track.children[i];
      if(!slide){
        swiper.style.height = '120px';
        return;
      }
      const rect = slide.getBoundingClientRect();
      const h = Math.ceil(rect.height);
      const minH = 80;
      swiper.style.height = (Math.max(h, minH)) + 'px';
    }

    function goTo(i){
      current = Math.max(0, Math.min(i, renderData.length-1));
      setTranslate(-current*width, true);
      setTimeout(()=> updateHeightForSlide(current), 120);
      // update chips and dots
      const chips = navEl.querySelectorAll('.mecom-chip');
      chips.forEach((c, idx)=> c.classList.toggle('is-active', idx===current));
      const dots = dotsEl.querySelectorAll('.mecom-dot');
      dots.forEach((d, idx)=> d.classList.toggle('is-active', idx===current));
    }

    function onStart(e){
      const touch = e.touches ? e.touches[0] : e;
      startX = touch.clientX;
      startY = touch.clientY;
      curX = startX;
      dragging = true;
      lastMoveAt = performance.now();
      track.style.transition = 'none';
    }
    function onMove(e){
      if(!dragging) return;
      const touch = e.touches ? e.touches[0] : e;
      const dx = touch.clientX - startX;
      const dy = touch.clientY - startY;
      if(Math.abs(dy) > Math.abs(dx)){ dragging = false; setTranslate(-current*width, false); return; }
      e.preventDefault();
      curX = touch.clientX;
      const base = -current * width;
      setTranslate(base + dx, false);
      lastMoveAt = performance.now();
    }
    function onEnd(){
      if(!dragging) return;
      dragging = false;
      const dx = (curX || startX) - startX;
      const dt = Math.max(1, performance.now() - lastMoveAt);
      const velocity = Math.abs(dx)/dt;
      const threshold = width * 0.18;
      if(dx < -threshold || (dx < -10 && velocity > 0.6)) goTo(current + 1);
      else if(dx > threshold || (dx > 10 && velocity > 0.6)) goTo(current - 1);
      else goTo(current);
    }

    function attachSwipe(){
      updateWidth();
      updateHeightForSlide(current);
      // touch
      swiper.addEventListener('touchstart', onStart, {passive:true});
      swiper.addEventListener('touchmove',  onMove,  {passive:false});
      swiper.addEventListener('touchend',   onEnd,   {passive:true});
      // mouse desktop
      swiper.addEventListener('mousedown', (e)=>{ e.preventDefault(); onStart(e); });
      window.addEventListener('mousemove', onMove);
      window.addEventListener('mouseup', onEnd);
    }

    // -----------------------
    // Persistence: load/save (localStorage)
    // -----------------------
    function saveState(obj){
      try{ localStorage.setItem(STORAGE_KEY, JSON.stringify(obj)); }catch(e){}
    }
    function loadState(){
      try{
        const raw = localStorage.getItem(STORAGE_KEY);
        if(!raw) return null;
        return JSON.parse(raw);
      }catch(e){ return null; }
    }

    // -----------------------
    // Render wrapper + helpers: initialize, render nav/dots/slides
    // -----------------------
    function renderAll(){
      renderSlides();
      renderNav(current);
      renderDots(current);
      // set initial position
      setTranslate(-current*width, false);
      updateHeightForSlide(current);
    }

    function init(){
      // Attempt to load persisted state (but do not auto-promote winners)
      const saved = loadState();
      if(saved && Array.isArray(saved)){
        renderData = saved;
      }else if(saved && saved.rounds){
        // support older format (rounds) — convert
        renderData = Array.isArray(saved.rounds) ? saved.rounds.map(r=>{
          return { name: r.name, packs: [ { title: 'Слоты', teams: (r.teams||[]).map(t=>({name:t})) } ] };
        }) : prepareRenderData(TOURNAMENT_DATA);
      } else {
        // no saved state — use default
        renderData = prepareRenderData(TOURNAMENT_DATA);
      }

      // Render and wire interactions
      renderAll();
      attachSwipe();

      // expose small API for debugging from console
      window.MECOM_BRACKET_V2 = {
        getState: ()=> deepCopy(renderData),
        setState: (obj)=>{ if(Array.isArray(obj)){ renderData = deepCopy(obj); saveState(renderData); renderAll(); } },
        resetDefaults: ()=> { renderData = prepareRenderData(TOURNAMENT_DATA); saveState(renderData); renderAll(); }
      };
    }

    init();

  })(); // end bracket IIFE
</script>
</body>
</html>




