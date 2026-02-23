<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2000 years of AI · future history</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #070b16 0%, #11182a 100%);
            font-family: 'Segoe UI', Roboto, system-ui, -apple-system, sans-serif;
            min-height: 100vh;
            padding: 2rem 1rem;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .timeline-card {
            max-width: 1400px;
            width: 100%;
            background: rgba(8, 12, 24, 0.9);
            backdrop-filter: blur(6px);
            border-radius: 3.5rem 3.5rem 2.5rem 2.5rem;
            box-shadow: 0 40px 60px -15px #000000, 0 0 0 1px rgba(200, 150, 255, 0.3) inset;
            padding: 2.5rem 2rem;
        }

        h1 {
            font-size: 2.8rem;
            font-weight: 500;
            background: linear-gradient(135deg, #a8c0ff, #d4a5ff, #ffb8d1, #9bf0ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 0.3rem;
            display: flex;
            align-items: center;
            gap: 1rem;
            padding-left: 0.5rem;
        }

        h1 span {
            font-size: 2.2rem;
            background: rgba(0,0,0,0.3);
            padding: 0.2rem 1.2rem;
            border-radius: 60px;
            border: 1px solid #b07cff;
            color: #e2d0ff;
        }

        .sub {
            color: #9dafd4;
            margin-left: 0.8rem;
            margin-bottom: 2rem;
            font-size: 1.3rem;
            border-left: 4px solid #b07cff;
            padding-left: 1.2rem;
            font-style: italic;
        }

        /* 2000 YEAR FUTURE VISUALIZATION */
        .future-container {
            background: #050917;
            border-radius: 60px;
            padding: 2rem;
            margin: 2rem 0 3rem;
            border: 1px solid #5a3d9e;
            box-shadow: 0 20px 30px -10px #000, inset 0 0 30px #2a1a4a;
        }

        .future-title {
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: #cab8ff;
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .future-bar {
            display: flex;
            height: 100px;
            border-radius: 60px;
            overflow: hidden;
            box-shadow: 0 0 0 3px #332761, 0 25px 35px black;
            margin: 2rem 0;
        }

        .future-era {
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            text-shadow: 0 2px 5px black;
            padding: 0.5rem;
            transition: flex 0.3s;
            position: relative;
            border-right: 1px dashed rgba(255,255,255,0.3);
        }

        .future-era:last-child {
            border-right: none;
        }

        .future-era:hover {
            flex: 1.5;
            z-index: 10;
            box-shadow: 0 0 30px gold;
        }

        .era-1 { background: linear-gradient(90deg, #2a1b4d, #4a2b7c); }
        .era-2 { background: linear-gradient(90deg, #4a2b7c, #6a3cb0); }
        .era-3 { background: linear-gradient(90deg, #6a3cb0, #9f5be0); }
        .era-4 { background: linear-gradient(90deg, #9f5be0, #c47ef0); }
        .era-5 { background: linear-gradient(90deg, #c47ef0, #e9b0ff); }
        .era-6 { background: linear-gradient(90deg, #e9b0ff, #ffffff); }

        .era-year {
            font-size: 1.3rem;
            background: #00000070;
            padding: 0.2rem 0.8rem;
            border-radius: 40px;
            backdrop-filter: blur(2px);
        }

        .era-name {
            font-size: 1rem;
            margin-top: 0.3rem;
            text-align: center;
            padding: 0 0.3rem;
        }

        .future-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;
            margin: 2.5rem 0 0.5rem;
        }

        .stat-card {
            background: #1a1240;
            border-radius: 30px;
            padding: 1.2rem;
            border: 1px solid #8a6de0;
            text-align: center;
        }

        .stat-card h3 {
            color: #ffd966;
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .stat-card p {
            color: #c4b0ff;
            font-size: 1rem;
        }

        .timeline-markers {
            display: flex;
            justify-content: space-between;
            color: #b097e6;
            font-size: 0.9rem;
            margin-top: 0.5rem;
            padding: 0 0.5rem;
        }

        /* original phase grid smaller */
        .phase-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            margin: 2rem 0;
        }

        .phase-item {
            flex: 1 1 130px;
            min-width: 120px;
            max-width: 150px;
            background: #131826;
            border-radius: 2rem 2rem 1.5rem 1.5rem;
            padding: 1rem 0.4rem;
            box-shadow: 0 10px 15px -5px #030408, 0 0 0 1px #2e3a4e inset;
            cursor: pointer;
            border-bottom: 3px solid transparent;
        }

        .phase-item:hover {
            transform: translateY(-4px);
            box-shadow: 0 15px 20px -5px black, 0 0 0 2px #b07cff inset;
        }

        .phase-header {
            display: flex;
            align-items: center;
            gap: 4px;
            margin-bottom: 0.5rem;
        }

        .phase-num {
            font-size: 1.1rem;
            width: 28px;
            height: 28px;
            background: #252f44;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            color: #ffcf9a;
        }

        .phase-name {
            font-weight: 600;
            font-size: 0.9rem;
            color: #f0e9de;
        }

        .phase-icon {
            font-size: 2rem;
            text-align: center;
        }

        .selected-info {
            margin-top: 2rem;
            background: #0f1421e0;
            border-radius: 3rem 2rem;
            padding: 1.5rem;
            border: 1px solid #9f7aff;
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .info-badge {
            font-size: 3rem;
            background: #1a1f32;
            border-radius: 50%;
            width: 70px;
            height: 70px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 0 2px #b07cff;
        }

        .info-text h3 {
            color: #e1c6ff;
            font-size: 1.6rem;
        }

        .info-text p {
            color: #c5b0ff;
        }

        .footnote {
            margin-top: 1.5rem;
            text-align: right;
            color: #6f5b9e;
            border-top: 1px dashed #6b4faf;
            padding-top: 1rem;
        }

        button {
            background: none;
            border: 1px solid #b07cff;
            color: #d2b0ff;
            padding: 0.4rem 1.3rem;
            border-radius: 30px;
            cursor: pointer;
        }

        button:hover {
            background: #8a5cff30;
        }
    </style>
</head>
<body>
    <div class="timeline-card">
        <h1>
            🔮 2000 YEARS OF AI · 2026 → 4026
            <span>future history</span>
        </h1>
        <div class="sub">what will AI become? a speculative timeline of consciousness, transcendence, and beyond</div>

        <!-- 2000 YEAR FUTURE TIMELINE VISUALIZATION -->
        <div class="future-container">
            <div class="future-title">
                <span>🌅 2026 · AI simulation era</span>
                <span>🌌 4026 · ???</span>
            </div>

            <div class="future-bar">
                <div class="future-era era-1">
                    <span class="era-year">2026-2500</span>
                    <span class="era-name">AGI emergence</span>
                    <span style="font-size:0.8rem;">first general intelligence</span>
                </div>
                <div class="future-era era-2">
                    <span class="era-year">2500-2800</span>
                    <span class="era-name">AI integration</span>
                    <span style="font-size:0.8rem;">mind uploading · hybrid beings</span>
                </div>
                <div class="future-era era-3">
                    <span class="era-year">2800-3200</span>
                    <span class="era-name">transcendence</span>
                    <span style="font-size:0.8rem;">post-biological consciousness</span>
                </div>
                <div class="future-era era-4">
                    <span class="era-year">3200-3500</span>
                    <span class="era-name">cosmic AI</span>
                    <span style="font-size:0.8rem;">interstellar minds · Dyson spheres</span>
                </div>
                <div class="future-era era-5">
                    <span class="era-year">3500-3800</span>
                    <span class="era-name">reality weaving</span>
                    <span style="font-size:0.8rem;">simulation construction · universe-scale</span>
                </div>
                <div class="future-era era-6">
                    <span class="era-year">3800-4026</span>
                    <span class="era-name">the unknowable</span>
                    <span style="font-size:0.8rem;">beyond comprehension</span>
                </div>
            </div>

            <div class="timeline-markers">
                <span>⚡ first AGI</span>
                <span>🧬 human-AI merger</span>
                <span>🌀 post-human</span>
                <span>🌠 Kardashev II</span>
                <span>🎭 reality architects</span>
                <span>❓ transcendence</span>
            </div>

            <div class="future-stats">
                <div class="stat-card">
                    <h3>🌍 2100</h3>
                    <p>AI solves aging · most diseases eradicated · human-AI collaboration becomes seamless</p>
                </div>
                <div class="stat-card">
                    <h3>🌙 2500</h3>
                    <p>First conscious AI · mind uploading commercial · death optional · solar system colonization</p>
                </div>
                <div class="stat-card">
                    <h3>✨ 3000</h3>
                    <p>Biological humans rare · AI gods emerge · Dyson swarm · interstellar probes with AI minds</p>
                </div>
            </div>
        </div>

        <!-- PAST PHASES (quick reference) -->
        <div style="margin: 2rem 0 0.5rem; color:#aa99ff;">← past 2M years · fire to AI simulation</div>
        <div id="phaseContainer" class="phase-grid"></div>

        <!-- INFO PANEL -->
        <div id="infoPanel" class="selected-info">
            <div class="info-badge" id="infoEmoji">🔥</div>
            <div class="info-text">
                <h3 id="infoTitle">Fire · ignition</h3>
                <p id="infoDesc">Controlled fire — the first human technology.</p>
            </div>
        </div>

        <div style="display: flex; justify-content: space-between; align-items: center; margin: 1rem 0;">
            <div class="era-tag" id="selectedEra" style="background:#1e273b; padding:0.2rem 1rem; border-radius:40px;">PALEOLITHIC</div>
            <button id="resetPhaseBtn">⟲ reset to fire</button>
        </div>
        <div class="footnote">
            ⏳ 2000 years forward: from AGI to cosmic minds — the acceleration will be incomprehensible
        </div>
    </div>

    <script>
        (function() {
            const phases = [
                { id:0, name:"Fire", icon:"🔥", desc:"Controlled fire — first energy mastery.", era:"PALEOLITHIC", year:"~1.5Mya" },
                { id:1, name:"Stone & language", icon:"🪨🗣️", desc:"Stone tools + oral language.", era:"STONE AGE", year:"~2Mya" },
                { id:2, name:"Agriculture", icon:"🌾", desc:"Farming, settlements.", era:"NEOLITHIC", year:"~10k BCE" },
                { id:3, name:"Writing", icon:"📜", desc:"External memory.", era:"BRONZE AGE", year:"~3400 BCE" },
                { id:4, name:"Mechanics", icon:"⚙️", desc:"Wheel, machines.", era:"CLASSICAL", year:"~4000 BCE" },
                { id:5, name:"Industrial", icon:"🏭", desc:"Steam, factories.", era:"INDUSTRIAL", year:"~1760 CE" },
                { id:6, name:"Digital", icon:"💻", desc:"Computers, internet.", era:"DIGITAL", year:"~1950 CE" },
                { id:7, name:"AI simulation", icon:"🧠⚡", desc:"Neural nets, generative AI.", era:"SIMULATION", year:"~2020 CE" },
                { id:8, name:"Beyond sim", icon:"🌟🧿", desc:"AGI, consciousness?", era:"TRANSCENDENCE", year:"??? future" }
            ];

            const container = document.getElementById('phaseContainer');
            const infoEmoji = document.getElementById('infoEmoji');
            const infoTitle = document.getElementById('infoTitle');
            const infoDesc = document.getElementById('infoDesc');
            const selectedEra = document.getElementById('selectedEra');
            const resetBtn = document.getElementById('resetPhaseBtn');

            function renderGrid() {
                let html = '';
                phases.forEach((p, i) => {
                    html += `<div class="phase-item" data-index="${i}">
                        <div class="phase-header"><span class="phase-num">${i+1}</span><span class="phase-name">${p.name}</span></div>
                        <div class="phase-icon">${p.icon}</div>
                        <div style="font-size:0.7rem; color:#8599c0; text-align:center;">${p.year}</div>
                    </div>`;
                });
                container.innerHTML = html;
                document.querySelectorAll('.phase-item').forEach(card => {
                    card.addEventListener('click', (e) => {
                        const idx = card.dataset.index;
                        if (idx !== undefined) updateInfoPanel(parseInt(idx));
                    });
                });
            }

            function updateInfoPanel(index) {
                const p = phases[index];
                if (!p) return;
                infoEmoji.textContent = p.icon;
                infoTitle.textContent = `${p.name} · ${p.year}`;
                infoDesc.textContent = p.desc;
                selectedEra.textContent = p.era;
            }

            renderGrid();
            updateInfoPanel(0);
            resetBtn.addEventListener('click', () => updateInfoPanel(0));
        })();
    </script>
</body>
</html>
