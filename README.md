<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Nang Rotha · Full-Stack & Desktop Dev | Professional GitHub UI</title>
    <!-- Google Fonts + Font Awesome 6 -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: radial-gradient(circle at 10% 30%, #eef2ff, #e0e8f0);
            font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 2rem;
        }

        /* MAIN CARD — premium glassmorphic card */
        .profile-card {
            max-width: 1280px;
            width: 100%;
            background: #ffffff;
            border-radius: 2.5rem;
            overflow: hidden;
            box-shadow: 0 30px 55px -20px rgba(0, 0, 0, 0.3), 0 2px 8px rgba(0, 0, 0, 0.02);
            transition: transform 0.25s ease, box-shadow 0.3s;
        }

        .profile-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 38px 65px -20px rgba(0, 0, 0, 0.35);
        }

        /* Header: dark tech gradient */
        .profile-header {
            background: linear-gradient(125deg, #0B1120 0%, #14212e 100%);
            padding: 2rem 2.5rem 1.8rem 2.5rem;
            color: white;
            position: relative;
        }

        .header-flex {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 1.5rem;
        }

        .identity {
            display: flex;
            align-items: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .avatar-frame {
            background: linear-gradient(135deg, #3b82f6, #a855f7);
            border-radius: 50%;
            padding: 3px;
            box-shadow: 0 15px 25px -8px rgba(0, 0, 0, 0.4);
        }

        .avatar {
            width: 100px;
            height: 100px;
            background: #0a0f1f;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            font-weight: 600;
            color: white;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="white" width="52px" height="52px"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>');
            background-repeat: no-repeat;
            background-position: center 60%;
            background-size: 52px;
            background-color: #111827;
        }

        .name-title h1 {
            font-size: 2.4rem;
            font-weight: 800;
            letter-spacing: -0.02em;
            background: linear-gradient(to right, #FFFFFF, #b9e0ff);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        .badge-group {
            display: flex;
            gap: 0.7rem;
            flex-wrap: wrap;
            margin-top: 0.5rem;
        }

        .badge {
            background: rgba(255,255,255,0.12);
            backdrop-filter: blur(6px);
            border-radius: 60px;
            padding: 0.3rem 1rem;
            font-size: 0.75rem;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            border: 0.5px solid rgba(255,255,255,0.2);
        }

        .contact-links {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            background: rgba(0,0,0,0.3);
            padding: 0.6rem 1.3rem;
            border-radius: 80px;
        }

        .contact-links a {
            color: #eef2ff;
            text-decoration: none;
            font-size: 0.85rem;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.2s;
            padding: 0.25rem 0.6rem;
            border-radius: 40px;
        }

        .contact-links a:hover {
            background: rgba(255,255,255,0.2);
            color: white;
        }

        /* stats row */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            background: rgba(0, 0, 0, 0.25);
            margin-top: 2rem;
            padding: 0.8rem 1.2rem;
            border-radius: 2rem;
            gap: 1rem;
        }

        .stat-item {
            display: flex;
            align-items: center;
            gap: 12px;
            background: rgba(255,255,255,0.06);
            padding: 0.45rem 1.2rem;
            border-radius: 40px;
        }

        .stat-number {
            font-weight: 800;
            font-size: 1.3rem;
        }

        /* main body */
        .profile-body {
            padding: 2rem 2.5rem;
            background: #ffffff;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }

        .skill-category {
            background: #fafcff;
            border-radius: 1.6rem;
            padding: 1.2rem 1.2rem 1.4rem;
            border: 1px solid #eef2f8;
            transition: all 0.2s;
            box-shadow: 0 4px 10px rgba(0,0,0,0.02);
        }

        .skill-category:hover {
            border-color: #cbdde9;
            background: white;
            box-shadow: 0 12px 20px -14px rgba(0,0,0,0.1);
        }

        .category-title {
            font-weight: 700;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 1rem;
            border-left: 4px solid #2c6e9e;
            padding-left: 0.8rem;
            color: #0f172a;
        }

        .tech-pills {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 6px;
        }

        .tech-pill {
            background: #eef2ff;
            padding: 0.4rem 1rem;
            border-radius: 36px;
            font-size: 0.8rem;
            font-weight: 500;
            color: #1e293b;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: 0.15s;
        }

        .tech-pill i {
            font-size: 0.85rem;
            color: #2c6e9e;
        }

        .tech-pill:hover {
            background: #e2eafc;
            transform: translateY(-2px);
        }

        .section-break {
            margin: 2rem 0 1.2rem;
        }

        .section-title-main {
            font-size: 1.4rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 1.2rem;
            color: #0c4e6e;
        }

        .project-highlight {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            margin-top: 0.8rem;
        }

        .mini-project {
            background: #f8fafc;
            border-radius: 1.3rem;
            padding: 0.8rem 1.2rem;
            flex: 1;
            min-width: 180px;
            border: 1px solid #e9edf2;
        }

        .footer-note {
            margin-top: 2rem;
            text-align: center;
            font-size: 0.75rem;
            color: #5b6e8c;
            border-top: 1px solid #eef2ff;
            padding-top: 1.2rem;
            display: flex;
            justify-content: center;
            gap: 24px;
            flex-wrap: wrap;
        }

        .github-metrics {
            background: linear-gradient(115deg, #f1f5fe, #ffffff);
            border-radius: 1.2rem;
            padding: 1rem 1.2rem;
            margin: 1.5rem 0 0.5rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
        }

        @media (max-width: 780px) {
            .profile-header, .profile-body {
                padding: 1.5rem;
            }
            .header-flex {
                flex-direction: column;
                align-items: start;
            }
        }

        .quote-block {
            background: #fefce8;
            padding: 0.7rem 1.2rem;
            border-radius: 1.2rem;
            font-size: 0.8rem;
            color: #7c5c2c;
            margin: 1rem 0;
            font-style: italic;
        }

        hr {
            margin: 1rem 0;
            border: none;
            height: 1px;
            background: linear-gradient(to right, #e2e8f0, transparent);
        }
    </style>
</head>
<body>
<div class="profile-card">
    <!-- HEADER with avatar and contact -->
    <div class="profile-header">
        <div class="header-flex">
            <div class="identity">
                <div class="avatar-frame">
                    <div class="avatar"></div>
                </div>
                <div class="name-title">
                    <h1>Nang Rotha</h1>
                    <div class="badge-group">
                        <span class="badge"><i class="fas fa-layer-group"></i> Full-Stack Architect</span>
                        <span class="badge"><i class="fas fa-desktop"></i> Desktop Dev (C#/C)</span>
                        <span class="badge"><i class="fas fa-database"></i> DB Specialist</span>
                    </div>
                </div>
            </div>
            <div class="contact-links">
                <a href="#"><i class="fab fa-github"></i> NangRotha</a>
                <a href="#"><i class="fab fa-linkedin"></i> rotha-pro</a>
                <a href="#"><i class="fas fa-envelope"></i> dev.roth@fullstack.com</a>
                <a href="#"><i class="fab fa-dev"></i> portfolio</a>
            </div>
        </div>
        <div class="stats-row">
            <div class="stat-item"><i class="fas fa-code-branch"></i> <span class="stat-number">38+</span> <span>repos</span></div>
            <div class="stat-item"><i class="fas fa-fire"></i> <span class="stat-number">2.1k</span> <span>commits '24</span></div>
            <div class="stat-item"><i class="fas fa-crown"></i> <span class="stat-number">14</span> <span>OSS contribs</span></div>
            <div class="stat-item"><i class="fas fa-star"></i> <span class="stat-number">560</span> <span>stars</span></div>
        </div>
    </div>

    <!-- BODY: Skills organized as full-stack + desktop, projects, etc -->
    <div class="profile-body">
        <!-- intro -->
        <div class="quote-block">
            <i class="fas fa-quote-left" style="margin-right: 8px;"></i> Full-stack engineer with desktop foundations — crafting scalable web backends, modern frontends, and performant native tools.
        </div>

        <!-- SKILLS GRID: frontend, backend, database, desktop -->
        <div class="skills-grid">
            <!-- Frontend -->
            <div class="skill-category">
                <div class="category-title"><i class="fab fa-react" style="color:#0c6e9e;"></i> Frontend Ecosystem</div>
                <div class="tech-pills">
                    <span class="tech-pill"><i class="fab fa-html5"></i> HTML5</span>
                    <span class="tech-pill"><i class="fab fa-css3-alt"></i> CSS3</span>
                    <span class="tech-pill"><i class="fab fa-tailwind"></i> Tailwind CSS</span>
                    <span class="tech-pill"><i class="fab fa-js"></i> JavaScript (ES6+)</span>
                    <span class="tech-pill"><i class="fab fa-react"></i> React.js + Vite</span>
                    <span class="tech-pill"><i class="fas fa-code"></i> JSON / REST</span>
                </div>
            </div>

            <!-- Backend & API -->
            <div class="skill-category">
                <div class="category-title"><i class="fas fa-server"></i> Backend & API</div>
                <div class="tech-pills">
                    <span class="tech-pill"><i class="fab fa-node-js"></i> Node.js</span>
                    <span class="tech-pill"><i class="fab fa-python"></i> Python</span>
                    <span class="tech-pill"><i class="fas fa-bolt"></i> FastAPI</span>
                    <span class="tech-pill"><i class="fab fa-java"></i> Java (Spring Boot)</span>
                    <span class="tech-pill"><i class="fas fa-cloud"></i> RESTful / GraphQL</span>
                </div>
            </div>

            <!-- Databases -->
            <div class="skill-category">
                <div class="category-title"><i class="fas fa-database"></i> Databases & Storage</div>
                <div class="tech-pills">
                    <span class="tech-pill"><i class="fas fa-database"></i> MySQL</span>
                    <span class="tech-pill"><i class="fas fa-database"></i> SQLite</span>
                    <span class="tech-pill"><i class="fas fa-database"></i> PostgreSQL</span>
                    <span class="tech-pill"><i class="fas fa-chart-line"></i> Prisma / SQLAlchemy</span>
                </div>
            </div>

            <!-- Desktop & Systems -->
            <div class="skill-category">
                <div class="category-title"><i class="fas fa-laptop-code"></i> Desktop & Native</div>
                <div class="tech-pills">
                    <span class="tech-pill"><i class="fab fa-windows"></i> C# (.NET / WinForms)</span>
                    <span class="tech-pill"><i class="fas fa-code"></i> C Programming</span>
                    <span class="tech-pill"><i class="fas fa-microchip"></i> Embedded logic</span>
                    <span class="tech-pill"><i class="fas fa-window-maximize"></i> WPF / MAUI</span>
                </div>
            </div>
        </div>

        <!-- featured project / highlights (full-stack & desktop) -->
        <div class="section-break">
            <div class="section-title-main">
                <i class="fas fa-rocket" style="color:#2563eb;"></i> 
                <span>Featured Engineering Work</span>
            </div>
            <div class="project-highlight">
                <div class="mini-project">
                    <div><i class="fab fa-react" style="color:#3b82f6;"></i> <strong>DevPulse Dashboard</strong></div>
                    <div style="font-size:0.75rem; margin-top: 6px;">React + Vite · Tailwind · FastAPI backend + PostgreSQL → realtime analytics</div>
                    <div class="tech-pill" style="margin-top: 8px; background:#eef2ff; width: fit-content;"><i class="fas fa-star"></i> 187 stars</div>
                </div>
                <div class="mini-project">
                    <div><i class="fas fa-database"></i> <strong>Multi-DB ORM Lite</strong></div>
                    <div style="font-size:0.75rem; margin-top: 6px;">Python + SQLAlchemy & Node.js driver for MySQL/SQLite/Postgres with migration toolkit</div>
                </div>
                <div class="mini-project">
                    <div><i class="fas fa-desktop"></i> <strong>SysMon C# Suite</strong></div>
                    <div style="font-size:0.75rem; margin-top: 6px;">Windows performance monitor & resource manager (C# + .NET 8, low-level C interop)</div>
                </div>
            </div>
        </div>

        <!-- GitHub + Additional info : fullstack journey & desktop synergy -->
        <div class="github-metrics">
            <div><i class="fab fa-github"></i> <strong>github.com/NangRotha</strong>  ·  active in fullstack tooling & desktop utilities</div>
            <div><i class="fas fa-code-pull-request"></i> 93 PRs merged  ·  <i class="fas fa-users"></i> 8 collaborators</div>
        </div>

        <!-- EXTRA DETAILS: Current focus / collaboration  and profile design -->
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 0.5rem;">
            <div style="background:#f6f9fe; border-radius: 1.4rem; padding: 1rem;">
                <div style="font-weight: 700; display: flex; gap: 8px;"><i class="fas fa-terminal"></i> 🔭 Currently building</div>
                <ul style="margin-left: 1.2rem; margin-top: 10px; font-size: 0.8rem; color: #1f2f48;">
                    <li>Full‑stack SaaS starter: React+Vite + FastAPI + Postgres</li>
                    <li>Cross‑platform desktop launcher (C# & React Native Windows)</li>
                    <li>Open source CLI for SQLite/Postgres schema visualizer</li>
                </ul>
            </div>
            <div style="background:#f6f9fe; border-radius: 1.4rem; padding: 1rem;">
                <div style="font-weight: 700; display: flex; gap: 8px;"><i class="fas fa-handshake"></i> 👯 Looking to collaborate on</div>
                <ul style="margin-left: 1.2rem; margin-top: 10px; font-size: 0.8rem; color: #1f2f48;">
                    <li>Modern dev tooling (desktop + web integration)</li>
                    <li>Open‑source database clients & admin panels</li>
                    <li>C# & Node.js interop projects</li>
                </ul>
            </div>
        </div>

        <!-- skillset details in a row: extra badges for completeness -->
        <hr>
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center; gap: 10px;">
            <div><i class="fas fa-check-circle" style="color:#2c6e9e;"></i> <strong>Full‑stack toolchain:</strong> Vite · React Router · FastAPI · JWT · SQLAlchemy</div>
            <div><i class="fas fa-check-circle" style="color:#2c6e9e;"></i> <strong>Desktop low‑level:</strong> C (pointers/memory) · C# (async/await) · Win32 API</div>
        </div>

        <!-- design / fun fact and footer -->
        <div class="footer-note" style="margin-top: 1.2rem;">
            <span><i class="fas fa-map-pin"></i> Phnom Penh / Global Remote</span>
            <span><i class="fas fa-lightbulb"></i> ⚡ Fun fact: I built a custom C interpreter for embedded scripting</span>
            <span><i class="fab fa-github-alt"></i> 1,800+ contributions last year</span>
        </div>
        
        <!-- profile footer with reach links & quote -->
        <div style="background: linear-gradient(95deg, #f0f4fa, transparent); border-radius: 1.2rem; padding: 0.8rem; margin-top: 1rem; display: flex; justify-content: space-between; flex-wrap: wrap;">
            <span style="font-size: 0.7rem;"><i class="fas fa-envelope-open-text"></i> rotha.dev@fullstack.com   |   <i class="fab fa-discord"></i> rotha.codes</span>
            <span style="font-size: 0.7rem; font-style: italic;">“Code meets design, desktop meets web — building without borders.”</span>
        </div>

        <!-- final footer -->
        <div class="footer-note">
            <span><i class="far fa-copyright"></i> Nang Rotha — Full‑Stack & Desktop Ecosystem</span>
            <span><i class="fas fa-code-branch"></i> Available for freelance & innovative collabs</span>
        </div>
    </div>
</div>
</body>
</html>
