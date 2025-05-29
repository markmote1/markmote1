<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mark Mote - Full Stack Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 50%, #16213e 100%);
            color: #E0E0E0;
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .translate-btn {
            position: fixed;
            top: 20px;
            right: 20px;
            background: linear-gradient(135deg, #FF6B9D, #C77DFF);
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s ease;
            z-index: 1000;
            box-shadow: 0 4px 15px rgba(255, 107, 157, 0.3);
        }

        .translate-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 107, 157, 0.4);
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .name {
            font-size: 3rem;
            font-weight: 700;
            background: linear-gradient(135deg, #00D9FF, #FF6B9D, #C77DFF);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
        }

        .typing-animation {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.5rem;
            color: #FF6B9D;
            margin-bottom: 20px;
        }

        .subtitle {
            font-size: 1.2rem;
            color: #E0E0E0;
            margin-bottom: 30px;
        }

        .section {
            margin-bottom: 50px;
        }

        .section-title {
            font-size: 2rem;
            font-weight: 600;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .about-card {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            padding: 30px;
            border-radius: 20px;
            border: 2px solid #FF6B9D;
            margin: 20px 0;
            box-shadow: 0 8px 32px rgba(255, 107, 157, 0.1);
        }

        .about-card li {
            margin-bottom: 15px;
            list-style: none;
            position: relative;
            padding-left: 30px;
        }

        .about-card li::before {
            content: attr(data-emoji);
            position: absolute;
            left: 0;
            top: 0;
        }

        .highlight {
            font-weight: 600;
        }

        .tech-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .tech-category h4 {
            font-size: 1.2rem;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .tech-category p {
            color: #B0B0B0;
            line-height: 1.8;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }

        .project-card {
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 100%);
            padding: 30px;
            border-radius: 20px;
            border: 2px solid;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card:nth-child(1) { border-color: #00D9FF; }
        .project-card:nth-child(2) { border-color: #FF6B9D; }
        .project-card:nth-child(3) { border-color: #C77DFF; }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .project-card h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            font-weight: 600;
        }

        .project-card p {
            margin-bottom: 10px;
            color: #B0B0B0;
        }

        .project-link {
            color: #00D9FF;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .project-link:hover {
            color: #FF6B9D;
        }

        .stats-section {
            text-align: center;
            margin: 40px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .stat-item img {
            border-radius: 15px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
        }

        .current-work-card {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            padding: 30px;
            border-radius: 20px;
            border: 2px solid #C77DFF;
            margin: 20px 0;
            box-shadow: 0 8px 32px rgba(199, 125, 255, 0.1);
        }

        .current-work-card li {
            margin-bottom: 12px;
            list-style: none;
            position: relative;
            padding-left: 30px;
        }

        .current-work-card li::before {
            content: attr(data-emoji);
            position: absolute;
            left: 0;
            top: 0;
        }

        .goals-list {
            margin-top: 20px;
        }

        .goals-list li {
            margin-bottom: 12px;
            color: #E0E0E0;
            font-size: 1.1rem;
        }

        .connect-section {
            text-align: center;
            font-size: 1.1rem;
            margin: 30px 0;
        }

        .connect-section a {
            color: #00D9FF;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .connect-section a:hover {
            color: #FF6B9D;
        }

        .quote-section {
            text-align: center;
            margin: 50px 0;
        }

        .quote {
            font-size: 1.5rem;
            font-style: italic;
            color: #FF6B9D;
            margin-bottom: 20px;
        }

        .thanks {
            font-size: 1.2rem;
            color: #00D9FF;
            margin-bottom: 15px;
        }

        .footer-text {
            color: #B0B0B0;
            margin-bottom: 20px;
        }

        .profile-views {
            display: inline-block;
            margin-top: 20px;
        }

        @media (max-width: 768px) {
            .name {
                font-size: 2rem;
            }
            
            .typing-animation {
                font-size: 1.2rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .tech-section {
                grid-template-columns: 1fr;
            }
        }

        .color-1 { color: #00D9FF; }
        .color-2 { color: #FF6B9D; }
        .color-3 { color: #C77DFF; }
    </style>
</head>
<body>
    <button class="translate-btn" onclick="toggleLanguage()">
        <span id="btn-text">Translate to Swahili</span>
    </button>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1 class="name" data-en="👋 Hey there, I'm Mark Mote (@markmote1)" data-sw="👋 Hujambo, mimi ni Mark Mote (@markmote1)">👋 Hey there, I'm Mark Mote (@markmote1)</h1>
            
            <div class="typing-animation" data-en="Full Stack Developer • AI & Machine Learning Explorer • Mobile App Developer • Creative Problem Solver" data-sw="Msanidi Programu Kamili • Mchunguzi wa AI na Ujifunzaji wa Mashine • Msanidi Programu za Simu • Mtatuzi Bunifu wa Matatizo">
                Full Stack Developer • AI & Machine Learning Explorer • Mobile App Developer • Creative Problem Solver
            </div>
            
            <div class="subtitle" data-en="🚀 Passionate Full Stack Developer specializing in building sleek, scalable, and user-centric applications" data-sw="🚀 Msanidi Programu mwenye shauku anayefanya kazi katika kujenga programu nzuri, zinazoweza kupanuka, na zinazolenga kwa watumiaji">
                🚀 Passionate Full Stack Developer specializing in building sleek, scalable, and user-centric applications
            </div>
        </div>

        <!-- About Section -->
        <div class="section">
            <h2 class="section-title color-3" data-en="🧑‍💻 About Me" data-sw="🧑‍💻 Kuhusu Mimi">🧑‍💻 About Me</h2>
            <div class="about-card">
                <ul>
                    <li data-emoji="🔭" data-en="Currently Exploring: Deep diving into Python, AI/ML, and Data Science to expand my technical horizons" data-sw="Ninachojifunza Sasa: Kujifunza kwa kina Python, AI/ML, na Sayansi ya Data ili kupanua maarifa yangu ya kiufundi">
                        <span class="color-1 highlight">Currently Exploring:</span> Deep diving into <strong>Python, AI/ML, and Data Science</strong> to expand my technical horizons
                    </li>
                    <li data-emoji="🌐" data-en="Web Development Expert: Proficient in Next.js, React, Supabase, Node.js, MongoDB, PostgreSQL, TailwindCSS" data-sw="Mtaalamu wa Utengenezaji wa Tovuti: Stadi katika Next.js, React, Supabase, Node.js, MongoDB, PostgreSQL, TailwindCSS">
                        <span class="color-2 highlight">Web Development Expert:</span> Proficient in <strong>Next.js, React, Supabase, Node.js, MongoDB, PostgreSQL, TailwindCSS</strong>
                    </li>
                    <li data-emoji="📱" data-en="Mobile Development: Building cross-platform applications for Android & iOS using React Native and Flutter" data-sw="Utengenezaji wa Programu za Simu: Kujenga programu za majukwaa mbalimbali za Android na iOS kwa kutumia React Native na Flutter">
                        <span class="color-3 highlight">Mobile Development:</span> Building cross-platform applications for <strong>Android & iOS</strong> using React Native and Flutter
                    </li>
                    <li data-emoji="🎨" data-en="UI/UX Enthusiast: Creating pixel-perfect, responsive designs that prioritize user experience" data-sw="Mpenzi wa UI/UX: Kuunda miundo kamilifu, inayojibu ambayo inaweka uzoefu wa mtumiaji mbele">
                        <span class="color-1 highlight">UI/UX Enthusiast:</span> Creating pixel-perfect, responsive designs that prioritize user experience
                    </li>
                    <li data-emoji="🛠️" data-en="DevOps & Cloud: Experience with AWS, Vercel, Docker, and CI/CD pipelines" data-sw="DevOps na Wingu: Uzoefu wa AWS, Vercel, Docker, na miradi ya CI/CD">
                        <span class="color-2 highlight">DevOps & Cloud:</span> Experience with <strong>AWS, Vercel, Docker, and CI/CD pipelines</strong>
                    </li>
                    <li data-emoji="💼" data-en="Freelancer & Entrepreneur: Running ArtArkTech - delivering innovative digital solutions" data-sw="Mfanyakazi Huru na Mjasiriamali: Kuongoza ArtArkTech - kutoa suluhisho za kidijitali za ubunifu">
                        <span class="color-3 highlight">Freelancer & Entrepreneur:</span> Running <strong>ArtArkTech</strong> - delivering innovative digital solutions
                    </li>
                    <li data-emoji="🎯" data-en="2024 Goals: Master AI integration in web applications and launch 3 SaaS products" data-sw="Malengo ya 2024: Kushinda uunganishaji wa AI katika programu za wavuti na kuzindua bidhaa 3 za SaaS">
                        <span class="color-1 highlight">2024 Goals:</span> Master AI integration in web applications and launch 3 SaaS products
                    </li>
                    <li data-emoji="⚡" data-en="Fun Fact: East or West, home is the best! 🏠 Also, I can debug code faster with coffee ☕" data-sw="Ukweli wa Kufurahisha: Mashariki au Magharibi, nyumbani ni bora zaidi! 🏠 Pia, ninaweza kurekebisha msimbo haraka zaidi na kahawa ☕">
                        <span class="color-2 highlight">Fun Fact:</span> <em>East or West, home is the best!</em> 🏠 Also, I can debug code faster with coffee ☕
                    </li>
                </ul>
            </div>
        </div>

        <!-- Tech Stack Section -->
        <div class="section">
            <h2 class="section-title color-2" data-en="🛠️ Tech Stack & Tools" data-sw="🛠️ Vifaa vya Kiteknolojia na Zana">🛠️ Tech Stack & Tools</h2>
            <div class="tech-section">
                <div class="tech-category">
                    <h4 class="color-1" data-en="Frontend Development" data-sw="Utengenezaji wa Sehemu ya Mbele">Frontend Development</h4>
                    <p data-en="React • Next.js • Vue.js • TypeScript • JavaScript • TailwindCSS • HTML5 • CSS3" data-sw="React • Next.js • Vue.js • TypeScript • JavaScript • TailwindCSS • HTML5 • CSS3">React • Next.js • Vue.js • TypeScript • JavaScript • TailwindCSS • HTML5 • CSS3</p>
                </div>
                <div class="tech-category">
                    <h4 class="color-3" data-en="Backend Development" data-sw="Utengenezaji wa Sehemu ya Nyuma">Backend Development</h4>
                    <p data-en="Node.js • Python • Express.js • Django • FastAPI" data-sw="Node.js • Python • Express.js • Django • FastAPI">Node.js • Python • Express.js • Django • FastAPI</p>
                </div>
                <div class="tech-category">
                    <h4 class="color-2" data-en="Databases & Cloud" data-sw="Hifadhidata na Wingu">Databases & Cloud</h4>
                    <p data-en="MongoDB • PostgreSQL • Supabase • Firebase • AWS • Vercel" data-sw="MongoDB • PostgreSQL • Supabase • Firebase • AWS • Vercel">MongoDB • PostgreSQL • Supabase • Firebase • AWS • Vercel</p>
                </div>
                <div class="tech-category">
                    <h4 class="color-1" data-en="Mobile Development" data-sw="Utengenezaji wa Programu za Simu">Mobile Development</h4>
                    <p data-en="React Native • Flutter • Ionic" data-sw="React Native • Flutter • Ionic">React Native • Flutter • Ionic</p>
                </div>
                <div class="tech-category">
                    <h4 class="color-3" data-en="AI/ML & Data Science" data-sw="AI/ML na Sayansi ya Data">AI/ML & Data Science</h4>
                    <p data-en="TensorFlow • Pandas • NumPy • OpenAI • Scikit-learn" data-sw="TensorFlow • Pandas • NumPy • OpenAI • Scikit-learn">TensorFlow • Pandas • NumPy • OpenAI • Scikit-learn</p>
                </div>
                <div class="tech-category">
                    <h4 class="color-2" data-en="Tools & DevOps" data-sw="Zana na DevOps">Tools & DevOps</h4>
                    <p data-en="Git • Docker • VS Code • Figma • Postman • Linux" data-sw="Git • Docker • VS Code • Figma • Postman • Linux">Git • Docker • VS Code • Figma • Postman • Linux</p>
                </div>
            </div>
        </div>

        <!-- Projects Section -->
        <div class="section">
            <h2 class="section-title color-3" data-en="🚀 Featured Projects" data-sw="🚀 Miradi Iliyoangaziwa">🚀 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3 class="color-1" data-en="🎨 ArtArkTech Company Website" data-sw="🎨 Tovuti ya Kampuni ya ArtArkTech">🎨 ArtArkTech Company Website</h3>
                    <p data-en="Modern, responsive business website with glassmorphism design" data-sw="Tovuti ya biashara ya kisasa, inayojibu yenye muundo wa glassmorphism">Modern, responsive business website with glassmorphism design</p>
                    <p><span class="color-2 highlight" data-en="Tech:" data-sw="Teknolojia:">Tech:</span> <span data-en="Next.js, TailwindCSS, Framer Motion" data-sw="Next.js, TailwindCSS, Framer Motion">Next.js, TailwindCSS, Framer Motion</span></p>
                    <p><span class="color-3 highlight" data-en="Features:" data-sw="Vipengele:">Features:</span> <span data-en="Dynamic animations, responsive design, contact forms" data-sw="Mielekeo ya kielelezo, muundo unaojibu, fomu za mawasiliano">Dynamic animations, responsive design, contact forms</span></p>
                    <a href="https://artarktech-company.vercel.app/" class="project-link" data-en="🔗 Live Demo" data-sw="🔗 Onyesho la Moja kwa Moja">🔗 Live Demo</a>
                </div>
                
                <div class="project-card">
                    <h3 class="color-2" data-en="📱 AI-Powered Mobile App" data-sw="📱 Programu ya Simu Inayotumia AI">📱 AI-Powered Mobile App</h3>
                    <p><em data-en="Coming Soon" data-sw="Inakuja Hivi Karibuni">Coming Soon</em> - <span data-en="Cross-platform app integrating machine learning" data-sw="Programu ya majukwaa mbalimbali inayojumuisha ujifunzaji wa mashine">Cross-platform app integrating machine learning</span></p>
                    <p><span class="color-3 highlight" data-en="Tech:" data-sw="Teknolojia:">Tech:</span> <span data-en="React Native, Python FastAPI, TensorFlow" data-sw="React Native, Python FastAPI, TensorFlow">React Native, Python FastAPI, TensorFlow</span></p>
                    <p><span class="color-1 highlight" data-en="Features:" data-sw="Vipengele:">Features:</span> <span data-en="AI recommendations, real-time processing, offline capabilities" data-sw="Mapendekezo ya AI, usindikaji wa wakati halisi, uwezo wa kutofunga">AI recommendations, real-time processing, offline capabilities</span></p>
                </div>
                
                <div class="project-card">
                    <h3 class="color-3" data-en="🛍️ E-Commerce Platform" data-sw="🛍️ Jukwaa la Biashara ya Kielektroniki">🛍️ E-Commerce Platform</h3>
                    <p><em data-en="In Development" data-sw="Katika Maendeleo">In Development</em> - <span data-en="Full-stack e-commerce solution" data-sw="Suluhisho kamili la biashara ya kielektroniki">Full-stack e-commerce solution</span></p>
                    <p><span class="color-2 highlight" data-en="Tech:" data-sw="Teknolojia:">Tech:</span> <span data-en="Next.js, Supabase, Stripe, TailwindCSS" data-sw="Next.js, Supabase, Stripe, TailwindCSS">Next.js, Supabase, Stripe, TailwindCSS</span></p>
                    <p><span class="color-1 highlight" data-en="Features:" data-sw="Vipengele:">Features:</span> <span data-en="Admin dashboard, inventory management, analytics" data-sw="Dashibodi ya msimamizi, usimamizi wa hisa, uchanganuzi">Admin dashboard, inventory management, analytics</span></p>
                </div>
            </div>
        </div>

        <!-- GitHub Stats Section -->
        <div class="section">
            <h2 class="section-title color-1" data-en="📊 GitHub Analytics" data-sw="📊 Uchanganuzi wa GitHub">📊 GitHub Analytics</h2>
            <div class="stats-section">
                <div class="stats-grid">
                    <div class="stat-item">
                        <img height="180" src="https://github-readme-stats.vercel.app/api?username=markmote1&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&title_color=FF6B9D&icon_color=00D9FF&text_color=E0E0E0&bg_color=0f0f23" alt="GitHub Stats"/>
                    </div>
                    <div class="stat-item">
                        <img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=markmote1&layout=compact&langs_count=8&theme=tokyonight&title_color=FF6B9D&text_color=E0E0E0&bg_color=0f0f23" alt="Top Languages"/>
                    </div>
                </div>
                
                <div style="margin: 20px 0;">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=markmote1&theme=tokyonight&ring=FF6B9D&fire=00D9FF&currStreakLabel=C77DFF&background=0f0f23" alt="GitHub Streak" />
                </div>
                
                <div style="margin: 20px 0;">
                    <img src="https://github-readme-activity-graph.vercel.app/graph?username=markmote1&theme=tokyo-night&hide_border=true&bg_color=0f0f23&color=E0E0E0&line=FF6B9D&point=00D9FF" alt="GitHub Activity Graph" />
                </div>
            </div>
        </div>

        <!-- Achievements Section -->
        <div class="section">
            <h2 class="section-title color-2" data-en="🏆 GitHub Achievements" data-sw="🏆 Mafanikio ya GitHub">🏆 GitHub Achievements</h2>
            <div class="stats-section">
                <img src="https://github-profile-trophy.vercel.app/?username=markmote1&theme=tokyonight&no-frame=true&margin-w=15&margin-h=15&column=7&title=Stars,Followers,Commits,Repositories,MultipleLang,PullRequest,Issues" alt="GitHub Trophies" />
            </div>
        </div>

        <!-- Current Work Section -->
        <div class="section">
            <h2 class="section-title color-1" data-en="💡 What I'm Currently Working On" data-sw="💡 Ninachofanya Sasa">💡 What I'm Currently Working On</h2>
            <div class="current-work-card">
                <ul>
                    <li data-emoji="🤖" data-en="Building an AI-powered web application that helps developers optimize their code" data-sw="Kujenga programu ya wavuti inayotumia AI inayosaidia wasanidi programu kuboresha msimbo wao">
                        Building an <strong>AI-powered web application</strong> that helps developers optimize their code
                    </li>
                    <li data-emoji="📚" data-en="Learning Machine Learning algorithms and their practical applications" data-sw="Kujifunza kanuni za Ujifunzaji wa Mashine na matumizi yake ya vitendo">
                        Learning <strong>Machine Learning algorithms</strong> and their practical applications
                    </li>
                    <li data-emoji="🎨" data-en="Designing a component library for faster React development" data-sw="Kubuni maktaba ya vipengele kwa maendeleo ya haraka ya React">
                        Designing a <strong>component library</strong> for faster React development
                    </li>
                    <li data-emoji="📖" data-en="Writing technical blogs about modern web development practices" data-sw="Kuandika blogu za kiufundi kuhusu mazoea ya kisasa ya utengenezaji wa tovuti">
                        Writing technical blogs about <strong>modern web development practices</strong>
                    </li>
                    <li data-emoji="🚀" data-en="Planning to launch ArtArkTech Academy - online coding bootcamp" data-sw="Kupanga kuzindua ArtArkTech Academy - kambi ya mafunzo ya kusanidi mtandaoni">
                        Planning to launch <strong>ArtArkTech Academy</strong> - online coding bootcamp
                    </li>
                </ul>
            </div>
        </div>

        <!-- Goals Section -->
        <div class="section">
            <h2 class="section-title color-2" data-en="🎯 2025 Goals & Aspirations" data-sw="🎯 Malengo na Matarajio ya 2025">🎯 2025 Goals & Aspirations</h2>
            <ul class="goals-list">
                <li data-en="Master TensorFlow and build 3 AI-integrated applications" data-sw="Kushinda TensorFlow na kujenga programu 3 zilizojumuisha AI">☐ Master <strong>TensorFlow</strong> and build 3 AI-integrated applications</li>
                <li data-en="Contribute to 5 open-source projects" data-sw="Kuchangia miradi 5 ya chanzo huria">☐ Contribute to <strong>5 open-source projects</strong></li>
                <li data-en="Launch 2 successful SaaS products" data-sw="Kuzindua bidhaa 2 za SaaS zilizofanikiwa">☐ Launch <strong>2 successful SaaS products</strong></li>
                <li data-en="Grow ArtArkTech client base to 50+ satisfied customers" data-sw="Kuongeza mteja wa ArtArkTech hadi 50+ wateja walioridhi">☐ Grow <strong>ArtArkTech</strong> client base to 50+ satisfied customers</li>
                <li data-en="Speak at 2 tech conferences about modern web development" data-sw="Kuzungumza katika mikutano 2 ya teknolojia kuhusu utengenezaji wa kisasa wa tovuti">☐ Speak at <strong>2 tech conferences</strong> about modern web development</li>
                <li data-en="Mentor 10 junior developers in their coding journey" data-sw="Kuongoza wasanidi programu 10 wadogo katika safari yao ya kusanidi">☐ Mentor <strong>10 junior developers</strong> in their coding journey</li>
            </ul>
        </div>

        <!-- Connect Section -->
        <div class="section">
            <h2 class="section-title color-3" data-en="🤝 Let's Connect & Collaborate" data-sw="🤝 Hebu Tuungane na Kushirikiana">🤝 Let's Connect & Collaborate</h2>
            <div class="connect-section">
                <p>
                    <strong data-en="Website:" data-sw="Tovuti:">Website:</strong> <a href="https://artarktech-company.vercel.app/">artarktech-company.vercel.app</a> • 
                    <strong data-en="Email:" data-sw="Barua pepe:">Email:</strong> <a href="mailto:markmote12@gmail.com">markmote12@gmail.com</a> • 
                    <strong data-en="LinkedIn:" data-sw="LinkedIn:">LinkedIn:</strong> <a href="https://linkedin.com/in/markmote" data-en="Mark Mote" data-sw="Mark Mote">Mark Mote</a> • 
                    <strong data-en="Twitter:" data-sw="Twitter:">Twitter:</strong> <a href="https://twitter.com/markmote1">@markmote1</a> • 
                    <strong data-en="GitHub:" data-sw="GitHub:">GitHub:</strong> <a href="https://github.com/markmote1">markmote1</a>
                </p>
            </div>
        </div>

        <!-- Quote Section -->
        <div class="section">
            <div class="quote-section">
                <div class="quote" data-en="🌟 \"Code is like humor. When you have to explain it, it's bad.\" – Cory House" data-sw="🌟 \"Msimbo ni kama utani. Unapohitaji kuueleza, si mzuri.\" – Cory House">
                    🌟 "Code is like humor. When you have to explain it, it's bad." – Cory House
                </div>
                
                <div class="thanks" data-en="Thanks for stopping by!" data-sw="Asante kwa kutembelea!">
                    Thanks for stopping by! ⭐️
                </div>
                
                <div class="footer-text" data-en="If you like what you see, don't forget to star some repositories and follow for more awesome projects!" data-sw="Ikiwa unapenda unachokiona, usisahau kupiga nyota baadhi ya makazi na kufuata kwa miradi zaidi ya ajabu!">
                    If you like what you see, don't forget to star some repositories and follow for more awesome projects!
                </div>
                
                <div class="profile-views">
                    <img src="https://komarev.com/ghpvc/?username=markmote1&color=FF6B9D&style=for-the-badge&label=PROFILE+VIEWS" alt="Profile Views" />
                </div>
            </div>
        </div>
    </div>

    <script>
        let isSwahili = false;

        const translations = {
            'btn-text-en': 'Translate to Swahili',
            'btn-text-sw': 'Tafsiri kwa Kiingereza'
        };

        function toggleLanguage() {
            isSwahili = !isSwahili;
            const elements = document.querySelectorAll('[data-en][data-sw]');
            const btnText = document.getElementById('btn-text');
            
            elements.forEach(element => {
                if (isSwahili) {
                    element.textContent = element.getAttribute('data-sw');
                } else {
                    element.textContent = element.getAttribute('data-en');
                }
            });

            // Update button text
            if (isSwahili) {
                btnText.textContent = translations['btn-text-sw'];
            } else {
                btnText.textContent = translations['btn-text-en'];
            }

            // Add smooth transition effect
            document.body.style.transition = 'all 0.3s ease';
            setTimeout(() => {
                document.body.style.transition = '';
            }, 300);
        }

        // Add some interactive animations
        document.addEventListener('DOMContentLoaded', function() {
            // Animate cards on scroll
            const cards = document.querySelectorAll('.project-card, .about-card, .current-work-card');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            });

            cards.forEach(card => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(card);
            });

            // Add typing effect to the main title
            const typingElement = document.querySelector('.typing-animation');
            const text = typingElement.textContent;
            typingElement.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < text.length) {
                    typingElement.textContent += text.charAt(i);
                    i++;
                    setTimeout(typeWriter, 50);
                }
            }
            
            setTimeout(typeWriter, 1000);
        });

        // Add smooth scrolling for better UX
        document.documentElement.style.scrollBehavior = 'smooth';
    </script>
</body>
</html>
