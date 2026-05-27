<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Nang Rotha · Full-Stack & Desktop Architect | Professional UI</title>
    <!-- Google Fonts (Inter) + Font Awesome 6 Free -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #eef2f9 0%, #d9e2ef 100%);
            font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 2rem;
        }

        /* MAIN CARD — Modern glassmorphism + subtle depth */
        .profile-container {
            max-width: 1280px;
            width: 100%;
            background: #ffffff;
            border-radius: 2.5rem;
            overflow: hidden;
            box-shadow: 0 30px 50px -20px rgba(0, 0, 0, 0.25), 0 8px 20px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s ease, box-shadow 0.2s;
        }

        .profile-container:hover {
            transform: translateY(-3px);
            box-shadow: 0 40px 60px -20px rgba(0, 0, 0, 0.3);
        }

        /* HEADER SECTION: avatar + headline + contact */
        .hero-header {
            background: linear-gradient(110deg, #0c1427 0%, #1a2741 100%);
            padding: 2rem 2.8rem;
            color: white;
        }

        .hero-flex {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 1.5rem;
        }

        .identity-area {
            display: flex;
            align-items: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .avatar-ring {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            padding: 5px;
            backdrop-filter: blur(4px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }

        .avatar-icon {
            width: 100px;
            height: 100px;
            background: linear-gradient(145deg, #2b3b6e, #121d36);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3.2rem;
            font-weight: 700;
            color: white;
            border: 2px solid rgba(255,255,240,0.7);
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="white" width="52px" height="52px"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>');
            background-repeat: no-repeat;
            background-position: center 60%;
            background-size: 50px;
        }

        .name-badge h1 {
            font-size: 2.4rem;
            font-weight: 800;
            letter-spacing: -0.02em;
            background: linear-gradient(to right, #FFFFFF, #B9D0FF);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .role-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.7rem;
            margin-top: 0.5rem;
        }

        .pill {
            background: rgba(255,255,255,0.12);
            backdrop-filter: blur(5px);
            border-radius: 40px;
            padding: 0.3rem 1rem;
            font-size: 0.75rem;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            border: 0.5px solid rgba(255,255,255,0.25);
        }

        .contact-strip {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            background: rgba(0, 0, 0, 0.3);
            padding: 0.6rem 1.2rem;
            border-radius: 60px;
        }

        .contact-strip a {
            color: #f0f3ff;
            text-decoration: none;
            font-size: 0.85rem;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.2s;
            padding: 0.2rem 0.6rem;
            border-radius: 40px;
        }

        .contact-strip a:hover {
            background: rgba(255,255,255,0.2);
            transform: scale(1.02);
        }

        /* stats row */
        .insight-stats {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 1rem;
            margin-top: 2rem;
            background: rgba(0,0,0,0.2);
            padding: 0.8rem 1.2rem;
            border-radius: 2rem;
        }

        .stat-block {
            display: flex;
            align-items: center;
            gap: 12px;
            background: rgba(255,255,255,0.05);
            padding: 0.4rem 1.2rem;
            border-radius: 2rem;
        }

        .stat-number {
            font-weight: 800;
            font-size: 1.3rem;
        }

        /* MAIN BODY */
        .profile-body {
            padding: 2rem 2.5rem;
            background: #ffffff;
        }

        /* two column layout (skill heavy) */
        .skills-grid {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 2.2rem;
        }

        @media (max-width: 850px) {
            .skills-grid {
                grid-template-columns: 1fr;
                gap: 2rem;
            }
            .hero-header {
                padding: 1.5rem;
            }
            .profile-body {
                padding: 1.5rem;
            }
        }

        .section-card {
            margin-bottom: 2rem;
        }

        .section-title {
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 700;
            font-size: 1.2rem;
            color: #0f1a2e;
            margin-bottom: 1rem;
            border-left: 4px solid #2c7a5e;
            padding-left: 0.8rem;
        }

        .tech-cloud {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 6px;
        }

        .skill-tag {
            background: #eef2ff;
            padding: 0.45rem 1rem;
            border-radius: 40px;
            font-size: 0.8rem;
            font-weight: 500;
            color: #1a2c3e;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.2s;
        }

        .skill-tag i {
            font-size: 0.9rem;
            color: #2c6e5c;
        }

        .skill-tag:hover {
            background: #e0e8fc;
            transform: translateY(-2px);
        }

        .subgroup {
            margin: 1rem 0 0.5rem 0;
            font-weight: 600;
            font-size: 0.85rem;
            color: #2c3e66;
            letter-spacing: -0.2px;
        }

        .project-entry {
            background: #f9fbfe;
            border-radius: 1.2rem;
            padding: 1rem 1.2rem;
            margin-bottom: 1rem;
            border: 1px solid #eef2f8;
            transition: all 0.2s;
        }

        .project-entry:hover {
            background: #ffffff;
            border-color: #cddfe7;
            box-shadow: 0 5px 12px rgba(0,0,0,0.03);
        }

        .project-title {
            font-weight: 700;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .project-desc {
            font-size: 0.85rem;
            color: #2d3a4b;
            margin: 6px 0 8px 0;
            line-height: 1.4;
        }

        .tech-used {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 8px;
        }

        .mini-badge {
            background: #e6edf6;
            border-radius: 20px;
            padding: 0.2rem 0.7rem;
            font-size: 0.7rem;
            font-weight: 500;
        }

        .github-metrics {
            background: #f1f5f9;
            border-radius: 1.5rem;
            padding: 1rem;
            margin-top: 1rem;
            text-align: center;
        }

        .fun-footer {
            margin-top: 1.5rem;
            border-top: 1px solid #e9edf2;
            padding-top: 1.2rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            font-size: 0.75rem;
            color: #4b6584;
        }

        .quote-block {
            background: #fef8e7;
            border-radius: 1rem;
            padding: 0.6rem 1rem;
            font-size: 0.8rem;
            color: #a1622c;
            margin: 1rem 0 0.5rem 0;
        }

        i {
            margin-right: 2px;
        }
    </style>
</head>
<body>
<div class="profile-container">
    <!-- HERO SECTION with fullstack identity -->
    <div class="hero-header">
        <div class="hero-flex">
            <div class="identity-area">
                <div class="avatar-ring">
                    <div class="avatar-icon"></div>
                </div>
                <div class="name-badge">
                    <h1>Nang Rotha</h1>
                    <div class="role-tags">
                        <span class="pill"><i class="fas fa-layer-group"></i> Full-Stack Architect</span>
                        <span class="pill"><i class="fas fa-desktop"></i> Desktop Engineer</span>
                        <span class="pill"><i class="fas fa-cloud-upload-alt"></i> API Specialist</span>
                        <span class="pill"><i class="fas fa-database"></i> DB Designer</span>
                    </div>
                </div>
            </div>
            <div class="contact-strip">
                <a href="#"><i class="fab fa-github"></i> NangRotha</a>
                <a href="#"><i class="fab fa-linkedin"></i> rotha-dev</a>
                <a href="#"><i class="fas fa-envelope"></i> rotha@fullstack.dev</a>
                <a href="#"><i class="fab fa-dev"></i> portfolio</a>
            </div>
        </div>
        <!-- stats row: contributions / projects / experience -->
        <div class="insight-stats">
            <div class="stat-block"><i class="fas fa-code-branch"></i> <span class="stat-number">40+</span> <span>repos</span></div>
            <div class="stat-block"><i class="fas fa-rocket"></i> <span class="stat-number">14</span> <span>production apps</span></div>
            <div class="stat-block"><i class="fas fa-trophy"></i> <span class="stat-number">5+</span> <span>years exp</span></div>
            <div class="stat-block"><i class="fas fa-globe"></i> <span class="stat-number">3</span> <span>continents</span></div>
        </div>
    </div>

    <!-- BODY: ALL SKILLS + PROJECTS + DESKTOP SHOWCASE -->
    <div class="profile-body">
        <div class="skills-grid">
            <!-- LEFT COLUMN: frontend + backend + database + desktop mastery -->
            <div>
                <!-- FRONTEND SKILLS -->
                <div class="section-card">
                    <div class="section-title"><i class="fas fa-code" style="color:#2c7a5e;"></i> Frontend Ecosystem</div>
                    <div class="tech-cloud">
                        <span class="skill-tag"><i class="fab fa-html5"></i> HTML5</span>
                        <span class="skill-tag"><i class="fab fa-css3-alt"></i> CSS3</span>
                        <span class="skill-tag"><i class="fab fa-tailwind"></i> Tailwind CSS</span>
                        <span class="skill-tag"><i class="fab fa-js"></i> JavaScript (ES6+)</span>
                        <span class="skill-tag"><i class="fab fa-react"></i> React.js + Vite</span>
                        <span class="skill-tag"><i class="fas fa-code"></i> JSON / REST</span>
                    </div>
                </div>

                <!-- BACKEND SKILLS (multilingual) -->
                <div class="section-card">
                    <div class="section-title"><i class="fas fa-server"></i> Backend & APIs</div>
                    <div class="tech-cloud">
                        <span class="skill-tag"><i class="fab fa-php"></i> PHP</span>
                        <span class="skill-tag"><i class="fab fa-node-js"></i> Node.js</span>
                        <span class="skill-tag"><i class="fab fa-python"></i> Python</span>
                        <span class="skill-tag"><i class="fas fa-bolt"></i> FastAPI</span>
                        <span class="skill-tag"><i class="fab fa-java"></i> Java (Spring)</span>
                    </div>
                </div>

                <!-- DATABASE expertise -->
                <div class="section-card">
                    <div class="section-title"><i class="fas fa-database"></i> Database Engineering</div>
                    <div class="tech-cloud">
                        <span class="skill-tag"><i class="fas fa-database"></i> MySQL</span>
                        <span class="skill-tag"><i class="fas fa-database"></i> SQLite</span>
                        <span class="skill-tag"><i class="fas fa-database"></i> PostgreSQL</span>
                        <span class="skill-tag"><i class="fas fa-chart-line"></i> Prisma / ORM</span>
                    </div>
                </div>

                <!-- DESKTOP & SYSTEMS (C#, C) -->
                <div class="section-card">
                    <div class="section-title"><i class="fas fa-desktop"></i> Desktop / Native</div>
                    <div class="tech-cloud">
                        <span class="skill-tag"><i class="fab fa-windows"></i> C# (.NET / WPF)</span>
                        <span class="skill-tag"><i class="fas fa-microchip"></i> C Programming</span>
                        <span class="skill-tag"><i class="fas fa-terminal"></i> WinForms / CLI</span>
                        <span class="skill-tag"><i class="fas fa-code"></i> Low-level optimizations</span>
                    </div>
                    <div class="quote-block" style="margin-top: 12px;">
                        <i class="fas fa-laptop-code"></i>  Desktop tools + performance-critical systems, embedded C & cross-platform GUIs.
                    </div>
                </div>

                <!-- additional fullstack badge -->
                <div class="github-metrics" style="background:#eef3fa;">
                    <i class="fas fa-chart-simple"></i> <strong>Full-Stack DNA</strong> — seamless integration from UI to DB & desktop runtimes
                    <div style="font-size:0.7rem; margin-top: 6px;">⚡ 12+ microservices | 6 desktop utilities | realtime dashboards</div>
                </div>
            </div>

            <!-- RIGHT COLUMN: featured projects, collab & github highlights -->
            <div>
                <!-- project showcase: fullstack + desktop -->
                <div class="section-card">
                    <div class="section-title"><i class="fas fa-rocket"></i> Signature projects</div>
                    <div class="project-entry">
                        <div class="project-title"><i class="fab fa-react"></i> <span>HR Fusion Suite</span> <span style="font-size:0.7rem;">(Fullstack + Desktop)</span></div>
                        <div class="project-desc">React + Vite frontend, FastAPI backend + PostgreSQL. Desktop companion built with C# for offline sync & reporting.</div>
                        <div class="tech-used"><span class="mini-badge">React/Vite</span><span class="mini-badge">FastAPI</span><span class="mini-badge">PostgreSQL</span><span class="mini-badge">C# WinForms</span></div>
                    </div>
                    <div class="project-entry">
                        <div class="project-title"><i class="fas fa-charging-station"></i> <span>Inventory Nexus</span></div>
                        <div class="project-desc">Node.js + Express backend, SQLite embedded DB, Tailwind dashboard + Java Spring admin panel, C scanner integration.</div>
                        <div class="tech-used"><span class="mini-badge">Node.js</span><span class="mini-badge">SQLite</span><span class="mini-badge">Tailwind</span><span class="mini-badge">Java</span></div>
                    </div>
                    <div class="project-entry">
                        <div class="project-title"><i class="fas fa-cloud-upload-alt"></i> <span>API Orchestrator (Python/FAST)</span></div>
                        <div class="project-desc">High-performance async API gateway with JWT, rate limiting and MySQL sharding. Used by 3 fintech prototypes.</div>
                        <div class="tech-used"><span class="mini-badge">FastAPI</span><span class="mini-badge">MySQL</span><span class="mini-badge">Docker</span><span class="mini-badge">Pydantic</span></div>
                    </div>
                </div>

                <!-- Current focus + collaboration -->
                <div class="section-card">
                    <div class="section-title"><i class="fas fa-handshake"></i> Open to collaborate</div>
                    <div style="background: #f5f9ff; border-radius: 1.2rem; padding: 1rem;">
                        <div style="display: flex; gap: 12px; flex-wrap: wrap; margin-bottom: 12px;">
                            <span class="pill" style="background:#e2ecfe; color:#1f3b62;"><i class="fas fa-microchip"></i> 🔭 Building: Cross-platform dev toolkit (C + React)</span>
                            <span class="pill" style="background:#e2ecfe; color:#1f3b62;"><i class="fas fa-brain"></i> 🌱 Learning: WebAssembly & Rust</span>
                        </div>
                        <p style="font-size: 0.85rem;">👯 Looking to collaborate on: fullstack open source, desktop utilities, database tooling.  
                        💬 Ask me about: full-stack architecture, hybrid desktop/web apps, API design, or C# interop.</p>
                        <div style="margin-top: 12px;"><i class="fas fa-map-marker-alt"></i> Remote / Phnom Penh · UTC+7</div>
                    </div>
                </div>

                <!-- GitHub activity / contributions & fun fact -->
                <div class="section-card">
                    <div class="section-title"><i class="fab fa-github-alt"></i> GitHub pulse</div>
                    <div class="github-metrics">
                        <div style="display: flex; justify-content: space-between; flex-wrap: wrap; gap: 8px;">
                            <span><i class="fas fa-code-pull-request"></i> 156 PRs merged</span>
                            <span><i class="fas fa-star"></i> 780 stars across projects</span>
                            <span><i class="fas fa-fire"></i> 38w streak</span>
                        </div>
                        <hr style="margin: 12px 0; border-color:#dfe7ef;">
                        <div style="font-size: 0.75rem; text-align: left;">
                            <i class="fas fa-chart-line"></i> Top languages: TypeScript, Python, C#, Java, C
                        </div>
                        <div class="quote-block" style="background:#eef2f5; margin-top: 12px;">
                            <i class="fas fa-lightbulb"></i> ⚡ Fun fact: I wrote a C interpreter for a custom DSL during university — now it's a side tool for automation.
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- FOOTER: final touch, fullstack credo -->
        <div class="fun-footer">
            <div><i class="fas fa-crown"></i> Fullstack + Desktop: bridging modern web, robust backends & native power</div>
            <div>
                <i class="fab fa-github"></i> github.com/NangRotha &nbsp;|&nbsp;
                <i class="fas fa-globe"></i> rotha.dev
            </div>
        </div>
        <div style="text-align: center; font-size: 0.7rem; padding-top: 1rem; color:#5c6e8c;">
            <i class="fas fa-code"></i>  HTML · CSS · Tailwind · React · Node · Python · FastAPI · Java · C# · C · MySQL · SQLite · PostgreSQL  —  always building.
        </div>
    </div>
</div>
</body>
</html>
