<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Scheduled Maintenance — Resuming May 5, 2026</title>
  <meta name="robots" content="noindex, nofollow" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    :root {
      --navy:        #0b1f3a;
      --navy-mid:    #122d50;
      --gold:        #c9a84c;
      --gold-lite:   #e2c97e;
      --gold-pale:   rgba(201,168,76,0.12);
      --cream:       #f8f4ec;
      --white:       #ffffff;
      --green:       #0e5a37;
      --green-bg:    rgba(14,90,55,0.09);
      --green-bd:    rgba(14,90,55,0.26);
      --text-main:   #0b1f3a;
      --text-mute:   #456080;
      --text-lite:   #7d96ae;
      --border:      rgba(11,31,58,0.09);
      --border-gold: rgba(201,168,76,0.32);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--cream);
      color: var(--text-main);
      min-height: 100vh;
      overflow-x: hidden;
      -webkit-font-smoothing: antialiased;
    }

    /* Subtle grid */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 52px 52px;
      opacity: 0.5;
    }
    body::after {
      content: '';
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background:
        radial-gradient(ellipse 60% 44% at 0% 0%,   rgba(11,31,58,0.06) 0%, transparent 55%),
        radial-gradient(ellipse 50% 38% at 100% 100%, rgba(201,168,76,0.05) 0%, transparent 55%);
    }

    /* Gold top rule */
    .top-bar {
      position: fixed; top: 0; left: 0; right: 0; height: 3px; z-index: 200;
      background: linear-gradient(90deg, transparent 0%, var(--gold) 20%, var(--gold-lite) 65%, transparent 100%);
    }

    /* Page */
    .page {
      position: relative; z-index: 1;
      min-height: 100vh;
      display: flex; flex-direction: column;
      align-items: center; justify-content: center;
      padding: 68px 18px 50px;
    }

    /* Card */
    .card {
      width: 100%; max-width: 680px;
      background: var(--white);
      border: 1px solid rgba(11,31,58,0.09);
      border-top: 2px solid var(--gold);
      border-radius: 4px;
      box-shadow:
        0 2px 6px  rgba(11,31,58,0.05),
        0 18px 52px rgba(11,31,58,0.09);
      overflow: hidden;
    }

    /* ── Header ── */
    .card-header {
      background: var(--navy);
      padding: 36px 44px 32px;
      text-align: center;
      position: relative; overflow: hidden;
    }
    /* Inner grid on navy */
    .card-header::before {
      content: '';
      position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
      background-size: 36px 36px;
    }
    /* Gold underline */
    .card-header::after {
      content: '';
      position: absolute; bottom: 0; left: 50%; transform: translateX(-50%);
      width: 120px; height: 1px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
    }

    /* Logo */
    .logo-wrap {
      position: relative; z-index: 1;
      margin-bottom: 20px;
      animation: sd 0.6s ease both;
    }
    .logo-wrap img {
      height: 68px;
      width: auto;
      max-width: 210px;
      object-fit: contain;
      /* NO filter — show original colours */
      display: block;
      margin: 0 auto;
      border-radius: 4px;
    }

    /* Status pill */
    .status-pill {
      position: relative; z-index: 1;
      display: inline-flex; align-items: center; gap: 7px;
      background: rgba(201,168,76,0.13);
      border: 1px solid rgba(201,168,76,0.35);
      color: var(--gold-lite);
      font-size: 10px; font-weight: 500;
      letter-spacing: 0.12em; text-transform: uppercase;
      padding: 5px 15px; border-radius: 2px;
      margin-bottom: 16px;
      animation: sd 0.68s 0.08s ease both;
    }
    .pill-dot {
      width: 5px; height: 5px; border-radius: 50%;
      background: var(--gold);
      animation: blink 2.5s ease-in-out infinite;
    }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.18} }

    /* Main heading */
    .header-title {
      position: relative; z-index: 1;
      font-family: 'Playfair Display', serif;
      font-size: clamp(22px, 4.2vw, 34px);
      font-weight: 500; color: #fff; line-height: 1.22;
      margin-bottom: 12px;
      animation: sd 0.72s 0.14s ease both;
    }
    .header-title em { font-style: normal; color: var(--gold-lite); }

    /* Sub copy */
    .header-sub {
      position: relative; z-index: 1;
      font-size: 13.5px; color: rgba(255,255,255,0.5);
      line-height: 1.78; font-weight: 300;
      max-width: 440px; margin: 0 auto;
      animation: sd 0.76s 0.2s ease both;
    }
    .header-sub strong { color: rgba(255,255,255,0.78); font-weight: 400; }

    @keyframes sd { from{opacity:0;transform:translateY(-10px)} to{opacity:1;transform:translateY(0)} }

    /* ── Body ── */
    .card-body { padding: 34px 44px 30px; }

    /* Dates row */
    .dates-row {
      display: grid; grid-template-columns: 1fr auto 1fr;
      align-items: center; gap: 12px;
      margin-bottom: 30px;
      animation: ru 0.65s 0.26s ease both;
    }
    .date-block { text-align: center; }
    .date-label {
      font-size: 9px; font-weight: 500;
      letter-spacing: 0.13em; text-transform: uppercase;
      color: var(--text-lite); margin-bottom: 5px;
    }
    .date-val {
      font-family: 'Playfair Display', serif;
      font-size: clamp(13px, 2.4vw, 16px);
      font-weight: 500; color: var(--text-main);
    }
    .date-note { font-size: 11px; color: var(--text-lite); margin-top: 3px; }
    .arrow-area {
      display: flex; align-items: center;
      font-size: 13px; color: var(--gold);
    }
    .arrow-area::before, .arrow-area::after {
      content: ''; display: block; flex: 1;
      height: 1px; background: var(--border-gold);
    }
    .arrow-glyph { padding: 0 6px; flex-shrink: 0; }

    /* Divider */
    .divider {
      height: 1px; margin-bottom: 26px;
      background: linear-gradient(90deg, transparent, var(--border), transparent);
    }

    /* Section label */
    .sec-label {
      font-size: 9px; font-weight: 500;
      letter-spacing: 0.13em; text-transform: uppercase;
      color: var(--text-lite); margin-bottom: 11px;
    }

    /* ── Countdown ── */
    .cd-wrap { margin-bottom: 26px; animation: ru 0.65s 0.36s ease both; }
    .cd-row { display: grid; grid-template-columns: repeat(4,1fr); gap: 9px; }
    .cd-block {
      background: var(--cream);
      border: 1px solid var(--border);
      border-bottom: 2px solid var(--gold);
      border-radius: 3px; padding: 15px 6px 11px;
      text-align: center;
      transition: box-shadow 0.2s, border-color 0.2s;
    }
    .cd-block:hover { box-shadow: 0 4px 14px rgba(201,168,76,0.11); border-color: var(--border-gold); }
    .cd-num {
      display: block;
      font-family: 'Playfair Display', serif;
      font-size: clamp(24px, 4.5vw, 36px);
      font-weight: 600; color: var(--navy); line-height: 1;
      font-variant-numeric: tabular-nums;
      transition: transform 0.1s;
    }
    .cd-num.flip { transform: scale(0.87); }
    .cd-unit {
      display: block; font-size: 9px; font-weight: 500;
      letter-spacing: 0.12em; text-transform: uppercase;
      color: var(--text-lite); margin-top: 5px;
    }

    /* ── Progress ── */
    .prog-wrap { margin-bottom: 26px; animation: ru 0.65s 0.44s ease both; }
    .prog-meta {
      display: flex; justify-content: space-between;
      align-items: baseline; margin-bottom: 8px;
    }
    .prog-info { font-size: 12px; color: var(--text-mute); }
    .prog-pct  { font-size: 12px; font-weight: 500; color: var(--gold); }
    .prog-track {
      height: 3px; background: rgba(11,31,58,0.07);
      border-radius: 100px; overflow: hidden;
    }
    .prog-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--navy), var(--gold));
      border-radius: 100px; width: 0%;
      transition: width 2.2s cubic-bezier(0.22,1,0.36,1) 0.4s;
      position: relative;
    }
    .prog-fill::after {
      content: ''; position: absolute;
      top: 0; right: 0; bottom: 0; width: 40px;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.5));
      animation: sh 2.5s ease-in-out infinite;
    }
    @keyframes sh { 0%,100%{opacity:0} 50%{opacity:1} }

    /* ── Checklist ── */
    .list-wrap { animation: ru 0.65s 0.52s ease both; }
    .checklist { border: 1px solid var(--border); border-radius: 3px; overflow: hidden; }

    .check-item {
      display: flex; align-items: center; gap: 13px;
      padding: 12px 16px;
      font-size: 13px; color: var(--text-mute);
      border-bottom: 1px solid var(--border);
      transition: background 0.18s;
    }
    .check-item:last-child { border-bottom: none; }
    .check-item:hover { background: #fafaf4; }

    /* States: done, progress, pending */
    .check-item.state-done   { color: var(--text-mute); }
    .check-item.state-prog   { color: var(--text-mute); }
    .check-item.state-pend   { color: var(--text-lite); }

    .c-icon {
      width: 20px; height: 20px; border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      flex-shrink: 0; font-size: 10px; font-weight: 700;
      transition: background 0.4s, border-color 0.4s, color 0.4s;
    }
    /* pending */
    .c-icon.pend { background: transparent; border: 1px solid var(--border); color: var(--text-lite); }
    /* in-progress */
    .c-icon.prog { background: rgba(11,31,58,0.08); border: 1px solid rgba(11,31,58,0.22); color: var(--navy); animation: spin 2.5s linear infinite; }
    /* done */
    .c-icon.done { background: var(--green-bg); border: 1px solid var(--green-bd); color: var(--green); animation: none; transform: none; }

    @keyframes spin { to { transform: rotate(360deg); } }

    .c-text { flex: 1; }

    .c-badge {
      font-size: 9px; font-weight: 500; letter-spacing: 0.07em;
      padding: 2px 8px; border-radius: 2px; white-space: nowrap;
      transition: background 0.4s, color 0.4s;
    }
    .c-badge.b-pend { background: rgba(11,31,58,0.04); color: var(--text-lite); }
    .c-badge.b-prog { background: rgba(11,31,58,0.07); color: var(--navy); }
    .c-badge.b-done { background: var(--green-bg); color: var(--green); }

    @keyframes ru { from{opacity:0;transform:translateY(9px)} to{opacity:1;transform:translateY(0)} }

    /* ── Card footer ── */
    .card-footer {
      border-top: 1px solid var(--border);
      background: #fafaf6;
      padding: 16px 44px;
      display: flex; align-items: center; gap: 8px;
      animation: ru 0.65s 0.6s ease both;
    }
    .foot-icon { font-size: 14px; flex-shrink: 0; }
    .foot-text { font-size: 12px; color: var(--text-lite); }

    /* ── Copyright ── */
    .copyright {
      margin-top: 20px;
      font-size: 11px; color: var(--text-lite); text-align: center;
      animation: ru 0.65s 0.66s ease both;
    }

    /* ── Responsive ── */
    @media (max-width: 580px) {
      .card-header { padding: 26px 20px 24px; }
      .card-body   { padding: 24px 20px 22px; }
      .card-footer { padding: 14px 20px; }
    }
    @media (max-width: 460px) {
      .dates-row  { grid-template-columns: 1fr; gap: 6px; }
      .arrow-area { display: none; }
      .c-badge    { display: none; }
    }
    @media (max-width: 340px) {
      .cd-row { grid-template-columns: repeat(2,1fr); }
    }
  </style>
</head>
<body>

<div class="top-bar"></div>

<div class="page">
  <div class="card">

    <!-- HEADER -->
    <div class="card-header">
      <div class="logo-wrap">
        <!--
          Logo displayed in original colours — no white filter.
          If the logo has a transparent/light background, it will show naturally on navy.
          If it looks odd, swap to a white version URL below.
        -->
        <img
          src="https://img1.wsimg.com/blobby/go/1b546cda-ec27-4ad0-86da-ee80619ce4d1/downloads/b869ed05-3e73-418f-b0d4-e765beb1b6f1/Photoroom_20251003_194858.PNG?ver=1777361959791"
          alt="Company Logo"
          onerror="this.style.display='none'"
        />
      </div>

      <div class="status-pill">
        <span class="pill-dot"></span>
        Scheduled Maintenance in Progress
      </div>

      <h1 class="header-title">We'll Be Back on <em>May 5, 2026</em></h1>

      <p class="header-sub">
        Our website is temporarily suspended for mandatory <strong>regulatory compliance</strong> checks and financial system verification. We began on <strong>April 28</strong> — ahead of the scheduled April 30 date — so we can return to you as early as possible.
      </p>
    </div>

    <!-- BODY -->
    <div class="card-body">

      <!-- Key dates -->
      <div class="dates-row">
        <div class="date-block">
          <div class="date-label">Suspension started</div>
          <div class="date-val">April 28, 2026</div>
          <div class="date-note">Began early for you</div>
        </div>
        <div class="arrow-area"><span class="arrow-glyph">→</span></div>
        <div class="date-block">
          <div class="date-label">Target resumption</div>
          <div class="date-val">May 5, 2026</div>
          <div class="date-note">~120 hour window</div>
        </div>
      </div>

      <div class="divider"></div>

      <!-- Countdown -->
      <div class="cd-wrap">
        <div class="sec-label">Estimated time remaining</div>
        <div class="cd-row">
          <div class="cd-block"><span class="cd-num" id="cd-d">--</span><span class="cd-unit">Days</span></div>
          <div class="cd-block"><span class="cd-num" id="cd-h">--</span><span class="cd-unit">Hours</span></div>
          <div class="cd-block"><span class="cd-num" id="cd-m">--</span><span class="cd-unit">Minutes</span></div>
          <div class="cd-block"><span class="cd-num" id="cd-s">--</span><span class="cd-unit">Seconds</span></div>
        </div>
      </div>

      <!-- Progress -->
      <div class="prog-wrap">
        <div class="prog-meta">
          <span class="prog-info">Overall maintenance progress</span>
          <span class="prog-pct" id="pct-label">Calculating…</span>
        </div>
        <div class="prog-track"><div class="prog-fill" id="prog-fill"></div></div>
      </div>

      <!-- Checklist — all items start as pending and auto-advance with real time -->
      <div class="list-wrap">
        <div class="sec-label">Compliance &amp; maintenance checklist</div>
        <div class="checklist" id="checklist">

          <!-- Each item: data-start and data-end are hours offset from START (Apr 28 00:00) -->
          <!-- Total window = 168 h (Apr 28 → May 5). Spread 6 tasks evenly. -->

          <div class="check-item" data-start="0"   data-end="14"  id="task-0">
            <span class="c-icon pend" id="icon-0">○</span>
            <span class="c-text">System backup &amp; secure data snapshot</span>
            <span class="c-badge b-pend" id="badge-0">Pending</span>
          </div>

          <div class="check-item" data-start="14"  data-end="42"  id="task-1">
            <span class="c-icon pend" id="icon-1">○</span>
            <span class="c-text">Infrastructure health &amp; uptime diagnostics</span>
            <span class="c-badge b-pend" id="badge-1">Pending</span>
          </div>

          <div class="check-item" data-start="42"  data-end="84"  id="task-2">
            <span class="c-icon pend" id="icon-2">○</span>
            <span class="c-text">Regulatory compliance audit &amp; documentation</span>
            <span class="c-badge b-pend" id="badge-2">Pending</span>
          </div>

          <div class="check-item" data-start="84"  data-end="112" id="task-3">
            <span class="c-icon pend" id="icon-3">○</span>
            <span class="c-text">Financial data integrity &amp; security review</span>
            <span class="c-badge b-pend" id="badge-3">Pending</span>
          </div>

          <div class="check-item" data-start="112" data-end="140" id="task-4">
            <span class="c-icon pend" id="icon-4">○</span>
            <span class="c-text">Platform performance optimisation</span>
            <span class="c-badge b-pend" id="badge-4">Pending</span>
          </div>

          <div class="check-item" data-start="140" data-end="168" id="task-5">
            <span class="c-icon pend" id="icon-5">○</span>
            <span class="c-text">Final QA, testing &amp; go-live verification</span>
            <span class="c-badge b-pend" id="badge-5">Pending</span>
          </div>

        </div>
      </div>

    </div><!-- /card-body -->

    <!-- FOOTER -->
    <div class="card-footer">
      <span class="foot-icon">🔒</span>
      <span class="foot-text">All client data remains fully secure and protected throughout this maintenance period. We appreciate your patience.</span>
    </div>

  </div><!-- /card -->

  <div class="copyright">
    &copy; 2026 Your Company. All rights reserved. &nbsp;·&nbsp; Regulatory Compliance Maintenance
  </div>
</div>

<script>
  /* ── Constants ── */
  const START  = new Date('2026-04-28T00:00:00'); // when we actually took site down
  const RESUME = new Date('2026-05-05T00:00:00'); // target resume date
  const TOTAL  = RESUME - START;                  // total window in ms (168 h)

  /* ── Helpers ── */
  function pad(n) { return String(Math.max(0, Math.floor(n))).padStart(2, '0'); }

  function flip(el, raw) {
    const s = pad(raw);
    if (el.textContent !== s) {
      el.classList.add('flip');
      setTimeout(() => { el.textContent = s; el.classList.remove('flip'); }, 70);
    }
  }

  /* ── Checklist logic ──
     Each task has a start & end offset in hours from START.
     - Before task's start hour  → Pending
     - Between start & end hours → In Progress (spinning)
     - After task's end hour     → Done (ticked)
  */
  const tasks = document.querySelectorAll('.check-item');

  function updateChecklist(elapsedHours) {
    tasks.forEach((task, i) => {
      const s = parseFloat(task.dataset.start);
      const e = parseFloat(task.dataset.end);
      const icon  = document.getElementById('icon-'  + i);
      const badge = document.getElementById('badge-' + i);

      if (elapsedHours >= e) {
        // DONE
        icon.className  = 'c-icon done';
        icon.textContent = '✓';
        badge.className  = 'c-badge b-done';
        badge.textContent = 'Complete';
      } else if (elapsedHours >= s) {
        // IN PROGRESS
        icon.className  = 'c-icon prog';
        icon.textContent = '↻';
        badge.className  = 'c-badge b-prog';
        badge.textContent = 'In Progress';
      } else {
        // PENDING
        icon.className  = 'c-icon pend';
        icon.textContent = '○';
        badge.className  = 'c-badge b-pend';
        badge.textContent = 'Pending';
      }
    });
  }

  /* ── DOM refs ── */
  const elD    = document.getElementById('cd-d');
  const elH    = document.getElementById('cd-h');
  const elM    = document.getElementById('cd-m');
  const elS    = document.getElementById('cd-s');
  const elPct  = document.getElementById('pct-label');
  const elFill = document.getElementById('prog-fill');

  /* ── Tick ── */
  function tick() {
    const now  = new Date();
    const diff = RESUME - now;            // ms until resume
    const gone = now    - START;          // ms elapsed since start

    const elapsedHours = gone / 3600000;  // hours since START

    /* Countdown */
    if (diff <= 0) {
      [elD, elH, elM, elS].forEach(el => el.textContent = '00');
      elPct.textContent  = '100% complete';
      elFill.style.width = '100%';
      updateChecklist(999); // mark all done
      return;
    }

    flip(elD, diff / 86400000);
    flip(elH, (diff % 86400000) / 3600000);
    flip(elM, (diff % 3600000)  / 60000);
    flip(elS, (diff % 60000)    / 1000);

    /* Progress bar */
    const pct = Math.min(100, Math.max(0, Math.round((gone / TOTAL) * 100)));
    elPct.textContent  = pct + '% elapsed';
    elFill.style.width = pct + '%';

    /* Checklist states */
    updateChecklist(elapsedHours);
  }

  tick();
  setInterval(tick, 1000);
</script>
</body>
</html> 


