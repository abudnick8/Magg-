<!DOCTYPE html>      
<html lang="en">      
<head>      
  <meta charset="UTF-8" />      
  <title>Magg$ â€“ Money for the Future</title>      
  <meta name="viewport" content="width=device-width, initial-scale=1" />      
  <style>      
    :root {      
      --bg: #050608;      
      --bg-alt: #090b10;      
      --accent: #39ff88;      
      --accent-soft: rgba(57,255,136,0.08);      
      --text: #f8fafc;      
      --muted: #9ca3af;      
      --danger: #f97373;      
      --border: #1f2933;      
      --card: #0b0f18;      
      --shadow-soft: 0 18px 45px rgba(0,0,0,0.65);      
      --radius-lg: 18px;      
      --radius-md: 12px;      
      --radius-pill: 999px;      
    }      
      
    * {      
      box-sizing: border-box;      
      margin: 0;      
      padding: 0;      
    }      
      
    body {      
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "SF Pro Text",      
        "Segoe UI", sans-serif;      
      background: radial-gradient(circle at top, #0b1220 0, #020617 55%, #000 100%);      
      color: var(--text);      
      min-height: 100vh;      
      display: flex;      
      justify-content: center;      
      align-items: flex-start;      
      padding: 32px 16px;      
    }      
      
    .shell {      
      width: 100%;      
      max-width: 1120px;      
      background: radial-gradient(circle at top left, #020617 0, #020617 40%, #000 100%);      
      border-radius: 32px;      
      border: 1px solid #111827;      
      box-shadow: 0 24px 60px rgba(0,0,0,0.85);      
      padding: 28px 28px 24px;      
      position: relative;      
      overflow: hidden;      
    }      
      
    .shell::before {      
      content: "";      
      position: absolute;      
      inset: -40%;      
      background:      
        radial-gradient(circle at 0 0, rgba(56,189,248,0.12) 0, transparent 60%),      
        radial-gradient(circle at 100% 0, rgba(52,211,153,0.09) 0, transparent 55%);      
      opacity: 0.9;      
      pointer-events: none;      
      z-index: -1;      
    }      
      
    header {      
      display: flex;      
      justify-content: space-between;      
      align-items: center;      
      margin-bottom: 24px;      
    }      
      
    .brand {      
      display: flex;      
      align-items: center;      
      gap: 10px;      
    }      
      
    .brand-icon {      
      width: 26px;      
      height: 26px;      
      border-radius: 10px;      
      background: conic-gradient(      
        from 220deg,      
        #22c55e,      
        #a855f7,      
        #38bdf8,      
        #22c55e      
      );      
      display: flex;      
      align-items: center;      
      justify-content: center;      
      box-shadow: 0 0 0 1px rgba(15,23,42,0.8),      
                  0 0 24px rgba(34,197,94,0.35);      
    }      
      
    .brand-icon span {      
      font-size: 15px;      
      font-weight: 700;      
      color: #020617;      
    }      
      
    .brand-text {      
      display: flex;      
      flex-direction: column;      
    }      
      
    .brand-name {      
      font-weight: 600;      
      letter-spacing: 0.04em;      
      font-size: 14px;      
      text-transform: uppercase;      
    }      
      
    .brand-tag {      
      font-size: 11px;      
      color: var(--muted);      
      letter-spacing: 0.16em;      
      text-transform: uppercase;      
    }      
      
    .header-right {      
      display: flex;      
      align-items: center;      
      gap: 10px;      
    }      
      
    .pill {      
      font-size: 11px;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
      padding: 6px 10px;      
      border-radius: 999px;      
      border: 1px solid rgba(148,163,184,0.25);      
      background: rgba(15,23,42,0.85);      
      color: var(--muted);      
      display: flex;      
      gap: 8px;      
      align-items: center;      
    }      
      
    .pill-dot {      
      width: 6px;      
      height: 6px;      
      border-radius: 999px;      
      background: var(--accent);      
      box-shadow: 0 0 0 4px rgba(34,197,94,0.18);      
    }      
      
    .pill-danger .pill-dot {      
      background: var(--danger);      
      box-shadow: 0 0 0 4px rgba(248,113,113,0.25);      
    }      
      
    .pill-danger {      
      border-color: rgba(248,113,113,0.4);      
    }      
      
    main {      
      display: grid;      
      grid-template-columns: minmax(0, 1.2fr) minmax(0, 1fr);      
      gap: 22px;      
    }      
      
    .hero {      
      display: flex;      
      flex-direction: column;      
      gap: 18px;      
    }      
      
    .badge-row {      
      display: flex;      
      flex-wrap: wrap;      
      gap: 10px;      
      align-items: center;      
    }      
      
    .badge {      
      font-size: 11px;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
      padding: 6px 10px;      
      border-radius: 999px;      
      border: 1px solid rgba(148,163,184,0.25);      
      background: rgba(15,23,42,0.82);      
      color: var(--muted);      
      display: inline-flex;      
      gap: 8px;      
      align-items: center;      
    }      
      
    .badge strong {      
      color: var(--accent);      
      font-weight: 500;      
    }      
      
    .hero-title {      
      font-size: clamp(32px, 3vw, 40px);      
      line-height: 1.15;      
      letter-spacing: -0.04em;      
    }      
      
    .hero-title span {      
      background: linear-gradient(to right, #f9fafb, #e5e7eb);      
      -webkit-background-clip: text;      
      color: transparent;      
    }      
      
    .hero-subtitle {      
      font-size: 14px;      
      color: var(--muted);      
      max-width: 460px;      
    }      
      
    .hero-subtitle strong {      
      color: #e5e7eb;      
      font-weight: 500;      
    }      
      
    .hero-actions {      
      display: flex;      
      flex-wrap: wrap;      
      gap: 10px;      
      margin-top: 4px;      
    }      
      
    .btn {      
      border-radius: var(--radius-pill);      
      border: 1px solid transparent;      
      padding: 8px 16px;      
      font-size: 13px;      
      font-weight: 500;      
      cursor: pointer;      
      display: inline-flex;      
      align-items: center;      
      gap: 10px;      
      background: none;      
      color: var(--text);      
    }      
      
    .btn-primary {      
      background: radial-gradient(circle at top left, #4ade80 0, #22c55e 35%, #16a34a 100%);      
      color: #022c22;      
      box-shadow: 0 12px 30px rgba(34,197,94,0.35);      
      border-color: rgba(74,222,128,0.4);      
    }      
      
    .btn-primary:hover {      
      filter: brightness(1.06);      
    }      
      
    .btn-outline {      
      border-color: rgba(148,163,184,0.35);      
      background: rgba(15,23,42,0.8);      
      color: var(--muted);      
    }      
      
    .btn-outline:hover {      
      border-color: rgba(148,163,184,0.55);      
    }      
      
    .btn-pill-label {      
      font-size: 11px;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
      color: var(--muted);      
    }      
      
    .note {      
      font-size: 11px;      
      color: var(--muted);      
      max-width: 420px;      
    }      
      
    .note strong {      
      color: #e5e7eb;      
      font-weight: 500;      
    }      
      
    .note a {      
      color: var(--accent);      
      text-decoration: none;      
    }      
      
    .note a:hover {      
      text-decoration: underline;      
    }      
      
    /* NEW: ticker search + grid */      
      
    .ticker-section {      
      margin-top: 10px;      
      padding-top: 14px;      
      border-top: 1px solid rgba(30,64,175,0.6);      
    }      
      
    .ticker-header {      
      display: flex;      
      justify-content: space-between;      
      align-items: center;      
      gap: 10px;      
      margin-bottom: 10px;      
    }      
      
    .ticker-title {      
      font-size: 11px;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
      color: var(--muted);      
    }      
      
    .ticker-search {      
      flex: 0 0 180px;      
      position: relative;      
    }      
      
    .ticker-search input {      
      width: 100%;      
      padding: 7px 10px 7px 24px;      
      background: rgba(15,23,42,0.9);      
      border-radius: 999px;      
      border: 1px solid rgba(148,163,184,0.5);      
      color: var(--text);      
      font-size: 12px;      
      outline: none;      
    }      
      
    .ticker-search input::placeholder {      
      color: rgba(148,163,184,0.7);      
    }      
      
    .ticker-search-icon {      
      position: absolute;      
      left: 8px;      
      top: 50%;      
      transform: translateY(-50%);      
      font-size: 11px;      
      color: rgba(148,163,184,0.9);      
    }      
      
    .ticker-grid {      
      display: grid;      
      grid-template-columns: repeat(auto-fill, minmax(110px, 1fr));      
      gap: 8px;      
    }      
      
    .ticker-card {      
      background: rgba(15,23,42,0.9);      
      border-radius: 12px;      
      border: 1px solid rgba(30,64,175,0.6);      
      padding: 8px 9px;      
      display: flex;      
      flex-direction: column;      
      gap: 3px;      
      min-height: 52px;      
    }      
      
    .ticker-card-header {      
      display: flex;      
      justify-content: space-between;      
      align-items: baseline;      
    }      
      
    .ticker-symbol {      
      font-size: 13px;      
      font-weight: 600;      
      letter-spacing: 0.08em;      
    }      
      
    .ticker-name {      
      font-size: 10px;      
      color: var(--muted);      
      text-transform: uppercase;      
    }      
      
    .ticker-price {      
      font-size: 13px;      
      font-weight: 500;      
    }      
      
    .ticker-change {      
      font-size: 11px;      
      font-weight: 500;      
    }      
      
    .ticker-change.pos {      
      color: #4ade80;      
    }      
      
    .ticker-change.neg {      
      color: #f97373;      
    }      
      
    .ticker-meta {      
      font-size: 10px;      
      color: var(--muted);      
    }      
      
    /* Right column panel */      
      
    .panel {      
      background: radial-gradient(circle at top, #020617 0, #020617 45%, #020617 100%);      
      border-radius: var(--radius-lg);      
      border: 1px solid rgba(31,41,55,0.9);      
      box-shadow: var(--shadow-soft);      
      padding: 16px 16px 14px;      
      display: flex;      
      flex-direction: column;      
      gap: 10px;      
      position: relative;      
      overflow: hidden;      
    }      
      
    .panel::before {      
      content: "";      
      position: absolute;      
      inset: -25%;      
      background:      
        radial-gradient(circle at 5% 0, rgba(56,189,248,0.22) 0, transparent 55%),      
        radial-gradient(circle at 85% 0, rgba(52,211,153,0.12) 0, transparent 55%);      
      opacity: 0.9;      
      pointer-events: none;      
      z-index: -1;      
    }      
      
    .panel-header {      
      display: flex;      
      justify-content: space-between;      
      align-items: center;      
      margin-bottom: 2px;      
    }      
      
    .panel-title {      
      font-size: 13px;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
      color: var(--muted);      
    }      
      
    .status-chip {      
      display: inline-flex;      
      align-items: center;      
      gap: 8px;      
      padding: 4px 9px;      
      border-radius: 999px;      
      background: rgba(15,23,42,0.96);      
      border: 1px solid rgba(148,163,184,0.45);      
      font-size: 11px;      
      color: var(--muted);      
    }      
      
    .status-dot {      
      width: 7px;      
      height: 7px;      
      border-radius: 999px;      
      background: var(--danger);      
      box-shadow: 0 0 0 4px rgba(248,113,113,0.3);      
    }      
      
    .status-label {      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
    }      
      
    .status-value {      
      font-weight: 500;      
      color: #e5e7eb;      
    }      
      
    .status-warning {      
      color: #f97373;      
      font-size: 11px;      
      margin-top: 6px;      
    }      
      
    .status-warning strong {      
      color: #fecaca;      
      font-weight: 500;      
    }      
      
    .signal-header {      
      display: flex;      
      justify-content: space-between;      
      align-items: baseline;      
      margin-top: 6px;      
      margin-bottom: 4px;      
    }      
      
    .signal-label {      
      font-size: 11px;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
      color: var(--muted);      
    }      
      
    .signal-value {      
      font-size: 12px;      
      color: var(--muted);      
    }      
      
    .signal-value strong {      
      color: #e5e7eb;      
      font-weight: 500;      
    }      
      
    .signal-card {      
      margin-top: 2px;      
      background: rgba(15,23,42,0.92);      
      border-radius: var(--radius-md);      
      border: 1px dashed rgba(148,163,184,0.4);      
      padding: 12px 12px 10px;      
      display: flex;      
      flex-direction: column;      
      gap: 10px;      
    }      
      
    .signal-main {      
      display: flex;      
      justify-content: space-between;      
      align-items: center;      
      gap: 8px;      
    }      
      
    .signal-side {      
      text-align: right;      
    }      
      
    .signal-tag {      
      font-size: 11px;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
      color: var(--muted);      
    }      
      
    .signal-score {      
      font-size: 26px;      
      font-weight: 600;      
      letter-spacing: -0.04em;      
      background: linear-gradient(to bottom right, #4ade80, #22c55e, #16a34a);      
      -webkit-background-clip: text;      
      color: transparent;      
    }      
      
    .signal-phrase {      
      font-size: 13px;      
      color: #e5e7eb;      
    }      
      
    .signal-phrase span {      
      color: #4ade80;      
      font-weight: 500;      
    }      
      
    .signal-meta {      
      font-size: 11px;      
      color: var(--muted);      
    }      
      
    .signal-meta strong {      
      color: #e5e7eb;      
      font-weight: 500;      
    }      
      
    .signal-footer {      
      display: flex;      
      justify-content: space-between;      
      align-items: center;      
      font-size: 11px;      
      color: var(--muted);      
    }      
      
    .signal-footer span {      
      color: #e5e7eb;      
      font-weight: 500;      
    }      
      
    .signal-badge {      
      font-size: 11px;      
      padding: 4px 10px;      
      border-radius: 999px;      
      border: 1px solid rgba(74,222,128,0.5);      
      background: rgba(21,128,61,0.14);      
      color: #bbf7d0;      
      text-transform: uppercase;      
      letter-spacing: 0.16em;      
    }      
      
    .signal-badge span {      
      color: #4ade80;      
    }      
      
    @media (max-width: 800px) {      
      .shell {      
        padding: 22px 18px 18px;      
      }      
      main {      
        grid-template-columns: minmax(0, 1fr);      
      }      
      .ticker-header {      
        flex-direction: column;      
        align-items: flex-start;      
      }      
      .ticker-search {      
        width: 100%;      
      }      
    }      
      
    @media (max-width: 520px) {      
      header {      
        flex-direction: column;      
        align-items: flex-start;      
        gap: 10px;      
      }      
      .header-right {      
        width: 100%;      
        justify-content: space-between;      
      }      
      .hero-actions {      
        flex-direction: column;      
        align-items: flex-start;      
      }      
      .btn {      
        width: 100%;      
        justify-content: center;      
      }      
    }      
  </style>      
</head>      
<body>      
  <div class="shell">      
    <header>      
      <div class="brand">      
        <div class="brand-icon">      
          <span>M</span>      
        </div>      
        <div class="brand-text">      
          <div class="brand-name">Magg$</div>      
          <div class="brand-tag">Money for the future</div>      
        </div>      
      </div>      
      <div class="header-right">      
        <div class="pill pill-danger">      
          <div class="pill-dot"></div>      
          <span>Live signals offline</span>      
        </div>      
      </div>      
    </header>      
      
    <main>      
      <section class="hero">      
        <div class="badge-row">      
          <div class="badge">      
            <span>Algorithmic Sentiment</span>      
            <strong>Experimental</strong>      
          </div>      
          <div class="badge">      
            <span>Humans:</span> <strong>Fading edge</strong>      
          </div>      
        </div>      
      
        <h1 class="hero-title">      
          <span>Money for the future.</span>      
        </h1>      
      
        <p class="hero-subtitle">      
          Magg$ watches the crowd, measures what they believe, and generates a contrarian sentiment signal for traders who know they are their own worst <strong>enemy</strong>.      
        </p>      
      
        <div class="hero-actions">      
          <button class="btn btn-primary">      
            <span>Get early access</span>      
          </button>      
          <button class="btn btn-outline">      
            <span class="btn-pill-label">View signal model</span>      
          </button>      
        </div>      
      
        <p class="note">      
          Magg$ is an experimental research tool and not financial advice. You are responsible for your own trading decisions; assume Magg$ will be catastrophically      
          <strong>wrong</strong>.      
        </p>      
      
        <!-- NEW: TICKERS SECTION -->      
        <section class="ticker-section" aria-label="Watchlist">      
          <div class="ticker-header">      
            <div class="ticker-title">Core watchlist Â· 13 tickers</div>      
            <div class="ticker-search">      
              <span class="ticker-search-icon">ðŸ”</span>      
              <input      
                id="tickerSearch"      
                type="text"      
                placeholder="Search ticker (e.g. NVDA)"      
                autocomplete="off"      
              />      
            </div>      
          </div>      
      
          <div id="tickerGrid" class="ticker-grid">      
            <!-- Each card: symbol, name, fake price/change (for now) -->      
            <article class="ticker-card" data-symbol="SPY" data-name="S&P 500 ETF">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">SPY</div>      
                  <div class="ticker-name">S&amp;P 500 ETF</div>      
                </div>      
                <div class="ticker-price">$475.12</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+0.8%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="SPX" data-name="S&P 500 Index">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">SPX</div>      
                  <div class="ticker-name">S&amp;P 500 Index</div>      
                </div>      
                <div class="ticker-price">4,890.34</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change neg">-0.3%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="QQQ" data-name="Nasdaq 100 ETF">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">QQQ</div>      
                  <div class="ticker-name">Nasdaq 100 ETF</div>      
                </div>      
                <div class="ticker-price">$410.27</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+1.1%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="NVDA" data-name="NVIDIA">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">NVDA</div>      
                  <div class="ticker-name">NVIDIA</div>      
                </div>      
                <div class="ticker-price">$602.18</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+2.3%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="TSLA" data-name="Tesla">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">TSLA</div>      
                  <div class="ticker-name">Tesla</div>      
                </div>      
                <div class="ticker-price">$189.04</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change neg">-1.5%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="AAPL" data-name="Apple">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">AAPL</div>      
                  <div class="ticker-name">Apple</div>      
                </div>      
                <div class="ticker-price">$196.72</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+0.4%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="AMZN" data-name="Amazon">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">AMZN</div>      
                  <div class="ticker-name">Amazon</div>      
                </div>      
                <div class="ticker-price">$167.90</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+0.9%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="MSFT" data-name="Microsoft">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">MSFT</div>      
                  <div class="ticker-name">Microsoft</div>      
                </div>      
                <div class="ticker-price">$397.55</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+0.6%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="GOOGL" data-name="Alphabet">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">GOOGL</div>      
                  <div class="ticker-name">Alphabet</div>      
                </div>      
                <div class="ticker-price">$145.82</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change neg">-0.2%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="META" data-name="Meta Platforms">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">META</div>      
                  <div class="ticker-name">Meta Platforms</div>      
                </div>      
                <div class="ticker-price">$382.44</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+1.6%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="HOOD" data-name="Robinhood">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">HOOD</div>      
                  <div class="ticker-name">Robinhood</div>      
                </div>      
                <div class="ticker-price">$12.34</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change neg">-0.7%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="GLD" data-name="Gold ETF">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">GLD</div>      
                  <div class="ticker-name">Gold ETF</div>      
                </div>      
                <div class="ticker-price">$192.10</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change pos">+0.3%</span>      
              </div>      
            </article>      
      
            <article class="ticker-card" data-symbol="SLV" data-name="Silver ETF">      
              <div class="ticker-card-header">      
                <div>      
                  <div class="ticker-symbol">SLV</div>      
                  <div class="ticker-name">Silver ETF</div>      
                </div>      
                <div class="ticker-price">$24.68</div>      
              </div>      
              <div class="ticker-meta">      
                Session bias Â· <span class="ticker-change neg">-0.4%</span>      
              </div>      
            </article>      
          </div>      
        </section>      
        <!-- END TICKERS SECTION -->      
      
      </section>      
      
      <aside class="panel" aria-label="Live Sentiment Panel">      
        <div class="panel-header">      
          <div>      
            <div class="panel-title">Algorithmic sentiment</div>      
          </div>      
          <div class="status-chip">      
            <div class="status-dot"></div>      
            <span class="status-label">Status</span>      
            <span class="status-value">Paused</span>      
          </div>      
        </div>      
      
        <div class="status-warning">      
          <strong>No active orders.</strong> Live trading integration is disabled while Magg$ is recalibrating its model.      
        </div>      
      
        <div class="signal-header">      
          <div class="signal-label">Live signal</div>      
          <div class="signal-value">      
            0 <strong>active</strong>      
          </div>      
        </div>      
      
        <div class="signal-card">      
          <div class="signal-main">      
            <div>      
              <div class="signal-tag">Current sentiment score</div>      
              <div class="signal-score">0.00</div>      
            </div>      
            <div class="signal-side">      
              <div class="signal-phrase">      
                Crowd is <span>undecided</span>      
              </div>      
              <div class="signal-meta">      
                Model confidence <strong>0%</strong> Â· Refreshes in <strong>00:00</strong>      
              </div>      
            </div>      
          </div>      
      
          <div class="signal-footer">      
            <div>      
              Calibrated on <span>crypto + macro narratives</span>.      
            </div>      
            <div class="signal-badge">      
              <span>Paper</span> Mode      
            </div>      
          </div>      
        </div>      
      </aside>      
    </main>      
  </div>      
      
  <!-- NEW: simple search logic -->      
  <script>      
    const searchInput = document.getElementById('tickerSearch');      
    const cards = Array.from(document.querySelectorAll('.ticker-card'));      
      
    searchInput.addEventListener('input', function () {      
      const q = this.value.trim().toUpperCase();      
      
      cards.forEach(card => {      
        const symbol = card.dataset.symbol.toUpperCase();      
        const name = card.dataset.name.toUpperCase();      
      
        const matches =      
          q === '' ||      
          symbol.includes(q) ||      
          name.includes(q);      
      
        card.style.display = matches ? '' : 'none';      
      });      
    });      
  </script>      
</body>      
</html>    
