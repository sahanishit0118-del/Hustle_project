# Hustle_project
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Kumar Akshat — CCIE Security Portfolio</title>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --muted:#94a3b8; --accent:#06b6d4; --glass: rgba(255,255,255,0.03);
      --max-width:1100px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; font-family:Inter,system-ui,Arial; background:linear-gradient(180deg,#071020 0%, #061427 70%); color:#e6eef6; -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale; padding:32px 16px;
      display:flex; justify-content:center;
    }
    .wrap{width:100%; max-width:var(--max-width)}

    header{display:flex;align-items:center;gap:18px;margin-bottom:22px}
    .avatar{width:92px;height:92px;border-radius:16px;background:linear-gradient(135deg,var(--accent),#0ea5a4);display:flex;align-items:center;justify-content:center;font-weight:700;color:#042028;font-size:28px;box-shadow:0 6px 18px rgba(3,7,18,0.6)}
    h1{margin:0;font-size:28px}
    p.lead{margin:4px 0 0;color:var(--muted)}

    .grid{display:grid;grid-template-columns:1fr 380px;gap:20px}
    @media (max-width:980px){.grid{grid-template-columns:1fr}}

    main .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:14px;padding:20px;box-shadow:0 8px 30px rgba(2,6,12,0.7);}

    .section-title{display:flex;align-items:center;justify-content:space-between;margin-bottom:12px}
    .section-title h2{margin:0;font-size:18px}
    .meta{color:var(--muted);font-size:13px}

    .hero-blurb{line-height:1.6;color:#dbeafe}

    /* Skills & progress */
    .skill{margin-bottom:12px}
    .skill .bar{height:10px;background:var(--glass);border-radius:999px;overflow:hidden}
    .skill .bar > i{display:block;height:100%;background:linear-gradient(90deg,var(--accent),#60a5fa);border-radius:999px}

    /* Accordion */
    .accordion .item{border-top:1px solid rgba(255,255,255,0.03);padding:12px 0}
    .accordion button{background:none;border:0;width:100%;text-align:left;padding:0;color:inherit;display:flex;justify-content:space-between;align-items:center;font-weight:600}
    .accordion .content{margin-top:10px;color:var(--muted);line-height:1.6;display:none}
    .accordion .open .content{display:block}

    /* Timeline */
    .timeline{border-left:2px solid rgba(255,255,255,0.04);padding-left:18px}
    .timeline .event{position:relative;padding:14px 0}
    .timeline .event:before{content:'';position:absolute;left:-11px;top:18px;width:12px;height:12px;border-radius:50%;background:var(--accent);box-shadow:0 0 0 4px rgba(6,182,212,0.08)}

    /* Footer */
    footer{margin-top:18px;color:var(--muted);font-size:13px;text-align:center}

    /* Buttons */
    .btn{background:linear-gradient(90deg,var(--accent),#60a5fa);border:0;padding:8px 12px;border-radius:10px;color:#012027;font-weight:700;cursor:pointer}
    .ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:6px 10px;border-radius:10px;color:var(--muted)}

    /* Contact card */
    .contact-card{display:flex;flex-direction:column;gap:12px}
    .contact-row{display:flex;gap:10px;align-items:center}
    .tag{background:rgba(255,255,255,0.02);padding:6px 8px;border-radius:8px;font-size:13px}

    /* small screens */
    @media (max-width:480px){header{gap:12px}.avatar{width:72px;height:72px;font-size:22px}}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="avatar">KA</div>
      <div>
        <h1>Kumar Akshat <span style="font-weight:500;color:var(--muted);font-size:15px">— Pursuing CCIE Security</span></h1>
        <p class="lead">Network engineer in training focused on advanced security architectures, secure routing, firewalls, threat defense and automation.</p>
      </div>
      <div style="margin-left:auto;display:flex;gap:8px;align-items:center">
        <button class="btn" onclick="downloadHTML()">Download HTML</button>
        <button class="ghost" onclick="toggleTheme()" title="Toggle simple theme">Toggle Theme</button>
      </div>
    </header>

    <div class="grid">
      <div>
        <section class="card">
          <div class="section-title"><h2>About CCIE Security</h2><div class="meta">Deep technical credential — routing & security</div></div>
          <div class="hero-blurb">
            The CCIE Security is one of the most respected expert-level certifications for network security professionals. It validates hands-on mastery of designing, implementing and troubleshooting complex security solutions at scale. The program typically includes a written/qualification exam and a hands-on lab exam.
          </div>
        </section>

        <section class="card" style="margin-top:18px">
          <div class="section-title"><h2>Exam blueprint & topics</h2><div class="meta">High-level areas to master</div></div>

          <div class="accordion" id="topics">
            <div class="item open">
              <button onclick="toggleItem(this)">Security Architecture & Design</button>
              <div class="content">
                Covers security models, segmentation, secure network design, zero-trust concepts, multi-site secure architecture, key management, and threat modeling. Focus on designing resilient, scalable security controls that meet compliance and operational needs.
              </div>
            </div>
            <div class="item">
              <button onclick="toggleItem(this)">Secure Infrastructure (Routing & Switching)</button>
              <div class="content">Secure routing, route filtering, control-plane protection, SD-WAN security, secure BGP/OSPF practices, control-plane policing and secure management plane design.</div>
            </div>
            <div class="item">
              <button onclick="toggleItem(this)">Firewalls & Threat Defense</button>
              <div class="content">NGFWs, stateful inspection, NAT, policy design, SSL/TLS inspection, intrusion prevention systems (IPS), sandboxing, and integration with threat intelligence platforms.</div>
            </div>
            <div class="item">
              <button onclick="toggleItem(this)">VPNs & Secure Remote Access</button>
              <div class="content">IPsec, SSL VPNs, DMVPN, FlexVPN, secure remote access design, clientless access considerations and scaling remote access for large organisations.</div>
            </div>
            <div class="item">
              <button onclick="toggleItem(this)">Identity, Access & Endpoint Security</button>
              <div class="content">AAA (RADIUS/TACACS+), device and user authentication strategies, certificate lifecycle management, Network Access Control (NAC), and integration with endpoint detection and response.</div>
            </div>
            <div class="item">
              <button onclick="toggleItem(this)">Automation, Monitoring & Orchestration</button>
              <div class="content">Automation with Python and APIs, Ansible playbooks for security, telemetry collection (Syslog, NetFlow, gNMI), SIEM integration, and automated incident response playbooks.</div>
            </div>
          </div>
        </section>

        <section class="card" style="margin-top:18px">
          <div class="section-title"><h2>Lab format & what to expect</h2><div class="meta">Hands-on, timed and practical</div></div>
          <p class="lead" style="color:var(--muted)">The lab exam is typically an 8-hour hands-on practical exam where you are given a complex multi-site security problem to solve using vendor equipment/software. You'll be expected to:</p>
          <ul style="color:var(--muted);line-height:1.7">
            <li>Design and implement secure routing and segmentation.</li>
            <li>Deploy and tune NGFW policies and IPS.</li>
            <li>Configure scalable VPNs and remote access solutions.</li>
            <li>Automate repetitive tasks via CLI scripts or APIs.</li>
            <li>Troubleshoot active faults and meet service-level objectives under time pressure.</li>
          </ul>
          <p style="color:var(--muted)">Scoring rewards correctness, scope, and efficiency — practicing time management and reading lab requirements carefully is essential.</p>
        </section>

        <section class="card" style="margin-top:18px">
          <div class="section-title"><h2>Study plan & practical tips</h2><div class="meta">6–12 month plan (example)</div></div>
          <ol style="color:var(--muted);line-height:1.7">
            <li><strong>Months 1–2:</strong> Core routing & secure infrastructure refresh (BGP, OSPF, QoS fundamentals).</li>
            <li><strong>Months 3–4:</strong> Firewalls, NGFW features, access control, NAT, IPS tuning.</li>
            <li><strong>Months 5–6:</strong> VPNs, identity, NAC, and end-to-end design projects.</li>
            <li><strong>Months 7–9:</strong> Lab practice — full timed labs with write-ups and peer review.</li>
            <li><strong>Months 10–12:</strong> Weak-area focus, mock labs, and exam readiness checks.</li>
          </ol>
          <p style="color:var(--muted)"><strong>Practical tips:</strong> practice labs under timed conditions, keep a lab notebook with commands & troubleshooting steps, automate repetitive tasks, and practice documenting your changes quickly and clearly.</p>
        </section>

        <section class="card" style="margin-top:18px">
          <div class="section-title"><h2>Projects & sample hands-on tasks</h2><div class="meta">Showcase ideas for portfolio</div></div>
          <ul style="color:var(--muted);line-height:1.7">
            <li>Design a multi-tenant secure network with micro-segmentation and firewall rules per tenant.</li>
            <li>Implement DMVPN with centralised firewall enforcement and AAA integration.</li>
            <li>Create an automation pipeline (Ansible/Python) to deploy firewall policies in stages and verify traffic flow with tests.</li>
            <li>Build telemetry dashboards from firewall logs & NetFlow for threat hunting.</li>
          </ul>
        </section>

      </div>

      <!-- Sidebar -->
      <aside>
        <div class="card contact-card">
          <div>
            <div class="section-title"><h2>Quick profile</h2><div class="meta">Contact & skills</div></div>
            <div style="display:flex;flex-direction:column;gap:8px">
              <div class="contact-row"><div class="tag">Name</div><div class="meta">Kumar Akshat</div></div>
              <div class="contact-row"><div class="tag">Goal</div><div class="meta">Pursuing CCIE Security</div></div>
              <div class="contact-row"><div class="tag">Location</div><div class="meta">(Add your city)</div></div>
            </div>
          </div>

          <div style="margin-top:12px">
            <div class="section-title"><h2>Skills</h2><div class="meta">Self-rated</div></div>
            <div class="skill"><div style="display:flex;justify-content:space-between"><strong>Network Security</strong><span class="meta">80%</span></div><div class="bar"><i style="width:80%"></i></div></div>
            <div class="skill"><div style="display:flex;justify-content:space-between"><strong>Firewalls/IPS</strong><span class="meta">75%</span></div><div class="bar"><i style="width:75%"></i></div></div>
            <div class="skill"><div style="display:flex;justify-content:space-between"><strong>VPNs & Remote Access</strong><span class="meta">78%</span></div><div class="bar"><i style="width:78%"></i></div></div>
            <div class="skill"><div style="display:flex;justify-content:space-between"><strong>Automation (Python/Ansible)</strong><span class="meta">65%</span></div><div class="bar"><i style="width:65%"></i></div></div>
          </div>

          <div style="margin-top:12px">
            <div class="section-title"><h2>Study timeline</h2><div class="meta">Planned milestones</div></div>
            <div class="timeline">
              <div class="event"><strong>Month 1–2</strong><div class="meta">Routing & infra refresh</div></div>
              <div class="event"><strong>Month 3–4</strong><div class="meta">Firewalls, IPS, policies</div></div>
              <div class="event"><strong>Month 5–6</strong><div class="meta">VPNs & Identity</div></div>
              <div class="event"><strong>Month 7–9</strong><div class="meta">Lab practice</div></div>
            </div>
          </div>

          <div style="margin-top:12px">
            <div class="section-title"><h2>Contact</h2><div class="meta">Share links</div></div>
            <div style="display:flex;flex-direction:column;gap:8px">
              <a class="ghost" href="#" onclick="alert('Add your LinkedIn/Github link in the HTML to make this live')">Add LinkedIn</a>
              <a class="ghost" href="#" onclick="alert('Add your GitHub link in the HTML to make this live')">Add GitHub</a>
            </div>
          </div>
        </div>
      </aside>
    </div>

    <footer>
      Built as a single-file portfolio — customise the content, links and your location. Good luck with your CCIE Security journey, Kumar!
    </footer>
  </div>

  <script>
    // Simple accordion toggles
    function toggleItem(el){
      const parent = el.parentElement;
      parent.classList.toggle('open');
    }

    // Theme toggle: invert colors as a tiny demo
    let dark = true;
    function toggleTheme(){
      dark = !dark;
      if(!dark){
        document.documentElement.style.setProperty('--bg','#f7fafc');
        document.documentElement.style.setProperty('--card','#ffffff');
        document.documentElement.style.setProperty('--muted','#475569');
        document.documentElement.style.setProperty('--accent','#0ea5a4');
        document.body.style.color='#042028';
        document.body.style.background='linear-gradient(180deg,#f8fafc 0%, #eef2ff 70%)';
      } else {
        document.documentElement.style.setProperty('--bg','#0f1724');
        document.documentElement.style.setProperty('--card','#0b1220');
        document.documentElement.style.setProperty('--muted','#94a3b8');
        document.documentElement.style.setProperty('--accent','#06b6d4');
        document.body.style.color='#e6eef6';
        document.body.style.background='linear-gradient(180deg,#071020 0%, #061427 70%)';
      }
    }

    // Download the HTML file (self) — helpful if user wants a local copy
    function downloadHTML(){
      const filename = 'Kumar_Akshat_CCIE_Security_Portfolio.html';
      const html = document.documentElement.outerHTML;
      const blob = new Blob([html], {type: 'text/html'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href = url; a.download = filename; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
    }

    // Small accessibility: keyboard toggles
    document.addEventListener('keydown', (e)=>{
      if(e.key==='/' && e.ctrlKey){
        alert('Tip: Use the Toggle Theme button to switch appearance, or Download HTML to save a local copy.');
      }
    });
  </script>
</body>
</html>

