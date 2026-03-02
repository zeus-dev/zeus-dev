<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Balachandar Jayaraman — DevOps & Blockchain Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e1a;
    --surface: #0f1628;
    --surface2: #151e35;
    --border: #1e2d4d;
    --accent: #36bcf7;
    --accent2: #7c3aed;
    --accent3: #10b981;
    --text: #e2e8f0;
    --muted: #64748b;
    --highlight: #f59e0b;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Starfield background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(1px 1px at 10% 20%, rgba(54,188,247,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 30% 60%, rgba(124,58,237,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 70% 10%, rgba(54,188,247,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 90% 80%, rgba(16,185,129,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 50% 40%, rgba(255,255,255,0.2) 0%, transparent 100%),
      radial-gradient(2px 2px at 80% 30%, rgba(54,188,247,0.5) 0%, transparent 100%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 1000px;
    margin: 0 auto;
    padding: 40px 20px;
    position: relative;
    z-index: 1;
  }

  /* Header */
  .hero {
    text-align: center;
    padding: 60px 0 40px;
    position: relative;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -20px;
    left: 50%;
    transform: translateX(-50%);
    width: 600px;
    height: 300px;
    background: radial-gradient(ellipse at center, rgba(54,188,247,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2rem, 5vw, 3.5rem);
    font-weight: 800;
    background: linear-gradient(135deg, #36bcf7 0%, #7c3aed 50%, #10b981 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    letter-spacing: -1px;
    line-height: 1.1;
    margin-bottom: 8px;
  }

  .title-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    margin: 20px 0;
  }

  .tag {
    padding: 4px 14px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    border: 1px solid;
  }

  .tag-blue { color: var(--accent); border-color: rgba(54,188,247,0.3); background: rgba(54,188,247,0.06); }
  .tag-purple { color: #a78bfa; border-color: rgba(124,58,237,0.3); background: rgba(124,58,237,0.06); }
  .tag-green { color: var(--accent3); border-color: rgba(16,185,129,0.3); background: rgba(16,185,129,0.06); }

  .links {
    display: flex;
    gap: 12px;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 24px;
  }

  .link-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 8px 18px;
    border-radius: 8px;
    font-size: 12px;
    font-weight: 600;
    text-decoration: none;
    color: var(--text);
    border: 1px solid var(--border);
    background: var(--surface);
    transition: all 0.2s;
    letter-spacing: 0.3px;
  }
  .link-btn:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  /* Code block bio */
  .code-bio {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    margin: 32px 0;
    position: relative;
    overflow: hidden;
  }

  .code-bio::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
  }

  .code-header {
    display: flex;
    gap: 6px;
    margin-bottom: 16px;
    align-items: center;
  }

  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }
  .filename { margin-left: 8px; font-size: 11px; color: var(--muted); }

  pre {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.8;
    overflow-x: auto;
  }

  .kw { color: #c792ea; }
  .fn { color: #82aaff; }
  .str { color: #c3e88d; }
  .prop { color: #f78c6c; }
  .cm { color: var(--muted); font-style: italic; }

  /* Section */
  .section {
    margin: 40px 0;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* Stats grid */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transition: transform 0.3s;
  }

  .stat-card:hover::before { transform: scaleX(1); }
  .stat-card:hover { border-color: rgba(54,188,247,0.3); transform: translateY(-2px); }

  .stat-value {
    font-family: 'Syne', sans-serif;
    font-size: 1.8rem;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .stat-label { font-size: 11px; color: var(--muted); margin-top: 4px; text-transform: uppercase; letter-spacing: 0.5px; }

  /* Tech badge grid */
  .badge-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .badge {
    padding: 6px 14px;
    border-radius: 6px;
    font-size: 12px;
    font-weight: 600;
    border: 1px solid var(--border);
    background: var(--surface2);
    color: var(--muted);
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .badge:hover { border-color: var(--accent); color: var(--text); }

  /* Blockchain table */
  .chain-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0 8px;
  }

  .chain-table th {
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--muted);
    padding: 0 16px 8px;
    text-align: left;
    border-bottom: 1px solid var(--border);
  }

  .chain-table td {
    padding: 14px 16px;
    background: var(--surface);
    font-size: 13px;
  }

  .chain-table tr td:first-child { border-radius: 8px 0 0 8px; }
  .chain-table tr td:last-child { border-radius: 0 8px 8px 0; }

  .uptime-bar {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .bar-track {
    flex: 1;
    height: 4px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
    max-width: 80px;
  }

  .bar-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--accent3), var(--accent));
    border-radius: 2px;
  }

  /* WakaTime-style breakdown */
  .waka-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    font-family: 'JetBrains Mono', monospace;
  }

  .waka-row {
    display: flex;
    align-items: center;
    gap: 12px;
    margin: 8px 0;
  }

  .waka-lang { width: 90px; font-size: 13px; color: var(--text); }
  .waka-time { width: 140px; font-size: 12px; color: var(--muted); }
  .waka-track { flex: 1; height: 8px; background: var(--surface2); border-radius: 4px; overflow: hidden; }
  .waka-fill { height: 100%; border-radius: 4px; background: linear-gradient(90deg, var(--accent), var(--accent2)); }
  .waka-pct { width: 48px; font-size: 12px; color: var(--accent); text-align: right; }

  /* Two-col grid */
  .two-col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }

  @media (max-width: 640px) {
    .two-col { grid-template-columns: 1fr; }
  }

  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
  }

  .card h3 {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    margin-bottom: 16px;
    color: var(--accent);
  }

  .card ul { list-style: none; }
  .card li { font-size: 12px; color: var(--muted); padding: 5px 0; border-bottom: 1px solid rgba(30,45,77,0.5); }
  .card li:last-child { border-bottom: none; }
  .card li::before { content: '▸ '; color: var(--accent); }

  /* Philosophy */
  .philosophy-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 16px;
  }

  .phil-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px;
    transition: all 0.2s;
  }

  .phil-card:hover { border-color: rgba(124,58,237,0.4); }
  .phil-title { font-size: 12px; font-weight: 700; color: var(--accent2); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 6px; }
  .phil-text { font-size: 12px; color: var(--muted); line-height: 1.6; }

  /* Footer */
  .footer {
    text-align: center;
    padding: 60px 0 40px;
    border-top: 1px solid var(--border);
    margin-top: 60px;
    color: var(--muted);
    font-size: 12px;
  }

  .footer .tagline {
    font-family: 'Syne', sans-serif;
    font-size: 1.1rem;
    color: var(--text);
    margin-bottom: 8px;
  }

  .terminal-cursor {
    display: inline-block;
    width: 10px;
    height: 1.2em;
    background: var(--accent);
    animation: blink 1s step-end infinite;
    vertical-align: text-bottom;
    margin-left: 2px;
    border-radius: 1px;
  }

  @keyframes blink { 50% { opacity: 0; } }

  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 40px 0;
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="name">Balachandar Jayaraman</div>
    <div style="color:var(--muted); font-size:13px; margin-top:8px;">DevOps Engineer · Cloud Architect · Blockchain Specialist</div>
    <div class="title-tags">
      <span class="tag tag-blue">☸ Kubernetes</span>
      <span class="tag tag-purple">⛓ Blockchain</span>
      <span class="tag tag-green">☁ Multi-Cloud</span>
      <span class="tag tag-blue">🔗 GitOps</span>
      <span class="tag tag-purple">🦀 Go + Rust</span>
    </div>
    <div class="links">
      <a href="https://github.com/zeus-dev" class="link-btn">⬡ GitHub</a>
      <a href="https://linkedin.com/in/balachandare" class="link-btn">in LinkedIn</a>
      <a href="https://twitter.com/_27dot_" class="link-btn">✕ Twitter</a>
      <a href="mailto:balachandare@gmail.com" class="link-btn">✉ Email</a>
    </div>
  </div>

  <!-- BIO CODE BLOCK -->
  <div class="code-bio">
    <div class="code-header">
      <div class="dot dot-r"></div>
      <div class="dot dot-y"></div>
      <div class="dot dot-g"></div>
      <span class="filename">me.go</span>
    </div>
    <pre><span class="kw">type</span> <span class="fn">Engineer</span> <span class="kw">struct</span> {
  Name         <span class="fn">string</span>
  Role         []<span class="fn">string</span>
  Languages    []<span class="fn">string</span>
  Passion      <span class="fn">string</span>
  CurrentFocus <span class="fn">string</span>
}

<span class="prop">me</span> := <span class="fn">Engineer</span>{
  Name:         <span class="str">"Balachandar Jayaraman"</span>,
  Role:         []<span class="fn">string</span>{<span class="str">"DevOps"</span>, <span class="str">"Cloud Architect"</span>, <span class="str">"Blockchain Specialist"</span>},
  Languages:    []<span class="fn">string</span>{<span class="str">"Go"</span>, <span class="str">"Python"</span>, <span class="str">"Shell"</span>, <span class="str">"Solidity"</span>, <span class="str">"YAML"</span>},
  Passion:      <span class="str">"Building infrastructure that powers Web3"</span>,
  CurrentFocus: <span class="str">"Kubernetes + Blockchain + Go 🚀"</span>,
}

<span class="cm">// By day: architecting scalable cloud solutions</span>
<span class="cm">// By night: deploying blockchain nodes across multiple networks</span></pre>
  </div>

  <!-- METRICS -->
  <div class="section">
    <div class="section-title">📈 Impact Metrics</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-value">50+</div>
        <div class="stat-label">Blockchain Nodes Deployed</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">8</div>
        <div class="stat-label">Networks Supported</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">90%</div>
        <div class="stat-label">Faster Deploys via GitOps</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">$2M+</div>
        <div class="stat-label">Cloud Infrastructure Managed</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">20+</div>
        <div class="stat-label">K8s Clusters in Prod</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">99.99%</div>
        <div class="stat-label">Uptime SLA</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">100+</div>
        <div class="stat-label">Automated Pipelines</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">Zero</div>
        <div class="stat-label">Security Incidents in Prod</div>
      </div>
    </div>
  </div>

  <!-- WEEKLY CODING -->
  <div class="section">
    <div class="section-title">⏱ Weekly Development Breakdown</div>
    <div class="waka-block">
      <div class="waka-row">
        <div class="waka-lang">Go</div>
        <div class="waka-time">12 hrs 30 mins</div>
        <div class="waka-track"><div class="waka-fill" style="width:48.5%; background: linear-gradient(90deg,#00ADD8,#36bcf7)"></div></div>
        <div class="waka-pct">48.50%</div>
      </div>
      <div class="waka-row">
        <div class="waka-lang">YAML</div>
        <div class="waka-time">4 hrs 15 mins</div>
        <div class="waka-track"><div class="waka-fill" style="width:16.5%; background: linear-gradient(90deg,#f59e0b,#fbbf24)"></div></div>
        <div class="waka-pct">16.50%</div>
      </div>
      <div class="waka-row">
        <div class="waka-lang">Python</div>
        <div class="waka-time">3 hrs 45 mins</div>
        <div class="waka-track"><div class="waka-fill" style="width:14.55%; background: linear-gradient(90deg,#3776AB,#60a5fa)"></div></div>
        <div class="waka-pct">14.55%</div>
      </div>
      <div class="waka-row">
        <div class="waka-lang">Terraform</div>
        <div class="waka-time">2 hrs 50 mins</div>
        <div class="waka-track"><div class="waka-fill" style="width:11%; background: linear-gradient(90deg,#7B42BC,#a78bfa)"></div></div>
        <div class="waka-pct">11.00%</div>
      </div>
      <div class="waka-row">
        <div class="waka-lang">Bash</div>
        <div class="waka-time">2 hrs 10 mins</div>
        <div class="waka-track"><div class="waka-fill" style="width:8.45%; background: linear-gradient(90deg,#4EAA25,#34d399)"></div></div>
        <div class="waka-pct">8.45%</div>
      </div>
      <div class="waka-row">
        <div class="waka-lang">Other</div>
        <div class="waka-time">15 mins</div>
        <div class="waka-track"><div class="waka-fill" style="width:1%; background: var(--border)"></div></div>
        <div class="waka-pct">1.00%</div>
      </div>
    </div>
  </div>

  <!-- BLOCKCHAIN TABLE -->
  <div class="section">
    <div class="section-title">⛓ Blockchain Network Expertise</div>
    <div style="overflow-x:auto">
    <table class="chain-table">
      <thead>
        <tr>
          <th>Network</th>
          <th>Services Deployed</th>
          <th>Uptime</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>🟠 Bitcoin — Full nodes, Lightning</td>
          <td style="color:var(--muted)">Mining pools, Payment processors</td>
          <td>
            <div class="uptime-bar">
              <div class="bar-track"><div class="bar-fill" style="width:99.8%"></div></div>
              <span style="font-size:12px;color:var(--accent3)">99.98%</span>
            </div>
          </td>
        </tr>
        <tr>
          <td>🔵 Ethereum — Validators, Archive</td>
          <td style="color:var(--muted)">DeFi protocols, NFT platforms</td>
          <td>
            <div class="uptime-bar">
              <div class="bar-track"><div class="bar-fill" style="width:100%"></div></div>
              <span style="font-size:12px;color:var(--accent3)">99.99%</span>
            </div>
          </td>
        </tr>
        <tr>
          <td>🟣 Polygon — Validator infra</td>
          <td style="color:var(--muted)">Gaming dApps, DeFi bridges</td>
          <td>
            <div class="uptime-bar">
              <div class="bar-track"><div class="bar-fill" style="width:99.7%"></div></div>
              <span style="font-size:12px;color:var(--accent3)">99.97%</span>
            </div>
          </td>
        </tr>
        <tr>
          <td>🟡 BSC — Full nodes, APIs</td>
          <td style="color:var(--muted)">DEX platforms, Yield farms</td>
          <td>
            <div class="uptime-bar">
              <div class="bar-track"><div class="bar-fill" style="width:99.6%"></div></div>
              <span style="font-size:12px;color:var(--accent3)">99.96%</span>
            </div>
          </td>
        </tr>
        <tr>
          <td>🔍 Blockscout — Multi-chain</td>
          <td style="color:var(--muted)">Custom explorer deployments</td>
          <td>
            <div class="uptime-bar">
              <div class="bar-track"><div class="bar-fill" style="width:100%"></div></div>
              <span style="font-size:12px;color:var(--accent3)">99.99%</span>
            </div>
          </td>
        </tr>
        <tr>
          <td>⚡ Lightning Network</td>
          <td style="color:var(--muted)">Payment channels</td>
          <td>
            <div class="uptime-bar">
              <div class="bar-track"><div class="bar-fill" style="width:99.5%"></div></div>
              <span style="font-size:12px;color:var(--accent3)">99.95%</span>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
    </div>
  </div>

  <!-- WHAT I BUILD -->
  <div class="section">
    <div class="section-title">🚀 What I Build</div>
    <div class="two-col">
      <div class="card">
        <h3>☸ Cloud Native Solutions</h3>
        <ul>
          <li>Multi-cloud K8s clusters with auto-scaling & self-healing</li>
          <li>GitOps workflows with ArgoCD / Flux</li>
          <li>Infrastructure as Code with Terraform & Pulumi</li>
          <li>Observability stacks (Prometheus, Grafana, ELK)</li>
          <li>Service meshes for microservices (Istio, Linkerd)</li>
          <li>Zero-trust security implementations</li>
        </ul>
      </div>
      <div class="card">
        <h3>⛓ Blockchain Infrastructure</h3>
        <ul>
          <li>Multi-chain node infra (ETH, BTC, BSC, Polygon)</li>
          <li>Blockscout explorer deployments & customization</li>
          <li>High-performance RPC endpoints</li>
          <li>DeFi protocol infrastructure & monitoring</li>
          <li>NFT marketplace backends</li>
          <li>Validator nodes with 99.99% uptime</li>
        </ul>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-title">💻 Tech Stack</div>
    <div style="display:flex; flex-direction:column; gap:16px;">
      <div>
        <div style="font-size:11px; color:var(--muted); text-transform:uppercase; letter-spacing:1px; margin-bottom:10px;">Languages</div>
        <div class="badge-grid">
          <span class="badge">🔵 Go</span>
          <span class="badge">🐍 Python</span>
          <span class="badge">💻 Bash</span>
          <span class="badge">🟡 JavaScript</span>
          <span class="badge">⬡ Solidity</span>
          <span class="badge">🦀 Rust</span>
        </div>
      </div>
      <div>
        <div style="font-size:11px; color:var(--muted); text-transform:uppercase; letter-spacing:1px; margin-bottom:10px;">Cloud & Infra</div>
        <div class="badge-grid">
          <span class="badge">☁ AWS</span>
          <span class="badge">☁ Azure</span>
          <span class="badge">☁ GCP</span>
          <span class="badge">🌊 DigitalOcean</span>
          <span class="badge">🔴 Hetzner</span>
          <span class="badge">🔶 Cloudflare</span>
        </div>
      </div>
      <div>
        <div style="font-size:11px; color:var(--muted); text-transform:uppercase; letter-spacing:1px; margin-bottom:10px;">Orchestration & IaC</div>
        <div class="badge-grid">
          <span class="badge">☸ Kubernetes</span>
          <span class="badge">🐳 Docker</span>
          <span class="badge">⛵ Helm</span>
          <span class="badge">🔷 Terraform</span>
          <span class="badge">🔴 Ansible</span>
          <span class="badge">🟣 Pulumi</span>
          <span class="badge">🟠 ArgoCD</span>
          <span class="badge">🕊 Flux</span>
        </div>
      </div>
      <div>
        <div style="font-size:11px; color:var(--muted); text-transform:uppercase; letter-spacing:1px; margin-bottom:10px;">Observability</div>
        <div class="badge-grid">
          <span class="badge">📊 Prometheus</span>
          <span class="badge">📈 Grafana</span>
          <span class="badge">🔍 ELK Stack</span>
          <span class="badge">🟣 Datadog</span>
          <span class="badge">🟢 New Relic</span>
        </div>
      </div>
    </div>
  </div>

  <!-- PHILOSOPHY -->
  <div class="section">
    <div class="section-title">🎨 DevOps Philosophy</div>
    <div class="philosophy-grid">
      <div class="phil-card">
        <div class="phil-title">Automation</div>
        <div class="phil-text">Automate everything that can be automated</div>
      </div>
      <div class="phil-card">
        <div class="phil-title">Reliability</div>
        <div class="phil-text">Build systems that heal themselves</div>
      </div>
      <div class="phil-card">
        <div class="phil-title">Security</div>
        <div class="phil-text">Security by design, not as an afterthought</div>
      </div>
      <div class="phil-card">
        <div class="phil-title">Scalability</div>
        <div class="phil-text">Ready for 10x growth without breaking</div>
      </div>
      <div class="phil-card">
        <div class="phil-title">Observability</div>
        <div class="phil-text">You can't fix what you can't see</div>
      </div>
      <div class="phil-card">
        <div class="phil-title">Simplicity</div>
        <div class="phil-text">Complexity is the enemy of reliability</div>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="tagline">Building the infrastructure for Web3, one commit at a time<span class="terminal-cursor"></span></div>
    <div style="margin-top:12px;">☕ Powered by coffee and terminal commands · 🍕 Deploys better after pizza</div>
  </div>

</div>
</body>
</html>
