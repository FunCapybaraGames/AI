<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CapyAI - Instant Website Generator</title>
    <style>
        :root {
            --bg: #0f172a;
            --surface: #1e293b;
            --surface-2: #334155;
            --ink: #f8fafc;
            --muted: #94a3b8;
            --accent: #38bdf8;
            --accent-hover: #0ea5e9;
            --radius: 12px;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg);
            color: var(--ink);
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            width: 100%;
            max-width: 900px;
        }

        header {
            text-align: center;
            margin-bottom: 25px;
        }

        header h1 {
            margin: 0;
            font-size: 28px;
            color: var(--accent);
        }

        header p {
            color: var(--muted);
            font-size: 14px;
            margin-top: 5px;
        }

        .generator-box {
            background-color: var(--surface);
            border: 1px solid var(--surface-2);
            padding: 20px;
            border-radius: var(--radius);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            margin-bottom: 20px;
        }

        .prompt-row {
            display: flex;
            gap: 10px;
        }

        input[type="text"] {
            flex: 1;
            height: 45px;
            padding: 0 15px;
            background-color: var(--bg);
            border: 1px solid var(--surface-2);
            border-radius: 8px;
            color: var(--ink);
            font-size: 15px;
            outline: none;
        }

        input[type="text"]:focus {
            border-color: var(--accent);
        }

        button {
            background-color: var(--accent);
            color: #0f172a;
            border: none;
            padding: 0 24px;
            height: 45px;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
        }

        button:hover {
            background-color: var(--accent-hover);
        }

        .suggestions {
            display: flex;
            gap: 8px;
            margin-top: 12px;
            flex-wrap: wrap;
        }

        .chip {
            background-color: var(--bg);
            border: 1px solid var(--surface-2);
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 12px;
            color: var(--muted);
            cursor: pointer;
            transition: all 0.2s;
        }

        .chip:hover {
            border-color: var(--accent);
            color: var(--ink);
        }

        .preview-pane {
            background-color: var(--surface);
            border: 1px solid var(--surface-2);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        .preview-header {
            background-color: #111827;
            padding: 10px 15px;
            display: flex;
            align-items: center;
            gap: 8px;
            border-bottom: 1px solid var(--surface-2);
        }

        .dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: #ef4444;
        }
        .dot:nth-child(2) { background-color: #f59e0b; }
        .dot:nth-child(3) { background-color: #10b981; }

        .preview-title {
            margin-left: 10px;
            font-size: 12px;
            color: var(--muted);
            font-family: monospace;
        }

        #live-frame {
            width: 100%;
            height: 450px;
            border: none;
            background-color: #ffffff;
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>⚡ CapyAI Website Builder</h1>
        <p>Type a prompt to instantly generate and preview a fully functional web page.</p>
    </header>

    <div class="generator-box">
        <div class="prompt-row">
            <input type="text" id="promptInput" placeholder="e.g., Make a cool retro arcade landing page with a green theme..." autocomplete="off">
            <button onclick="generateWebsite()">Generate</button>
        </div>
        <div class="suggestions">
            <span style="font-size: 12px; color: var(--muted); align-self: center;">Try ideas:</span>
            <div class="chip" onclick="setPrompt('Make a dark neon gaming portfolio with a high score leaderboard')">Gaming Portfolio</div>
            <div class="chip" onclick="setPrompt('Make a clean green indie studio homepage with game download links')">Indie Studio</div>
            <div class="chip" onclick="setPrompt('Make a cozy minimal pixel art blog about capybaras')">Capybara Blog</div>
        </div>
    </div>

    <div class="preview-pane">
        <div class="preview-header">
            <div class="dot"></div>
            <div class="dot"></div>
            <div class="dot"></div>
            <span class="preview-title" id="frameTitle">preview://generated-site.html</span>
        </div>
        <iframe id="live-frame"></iframe>
    </div>
</div>

<script>
    function setPrompt(text) {
        document.getElementById('promptInput').value = text;
        generateWebsite();
    }

    function generateWebsite() {
        const prompt = document.getElementById('promptInput').value.toLowerCase();
        const frame = document.getElementById('live-frame');

        // Simple pattern engine that builds custom websites based on text prompts
        let siteTitle = "Custom Web Page";
        let bgColor = "#0f172a";
        let cardBg = "#1e293b";
        let accentColor = "#38bdf8";
        let textColor = "#f8fafc";
        let headingText = "Welcome to Your New Site";
        let bodyText = "Generated instantly by your browser AI engine.";
        let extraContent = "";

        if (prompt.includes("arcade") || prompt.includes("gaming") || prompt.includes("portfolio")) {
            siteTitle = "Arcade Hub";
            bgColor = "#090d16";
            accentColor = "#4ade80";
            headingText = "🕹️ Level Up Your Play";
            bodyText = "Explore indie browser games built by creators worldwide.";
            extraContent = `
                <div style="display: flex; gap: 10px; justify-content: center; margin-top: 20px;">
                    <div style="background: #1e293b; padding: 15px; border-radius: 8px; width: 120px; text-align: center;">🔥 Top Game</div>
                    <div style="background: #1e293b; padding: 15px; border-radius: 8px; width: 120px; text-align: center;">⭐ New Release</div>
                </div>
            `;
        } else if (prompt.includes("studio") || prompt.includes("indie")) {
            siteTitle = "CapyStudio";
            bgColor = "#111827";
            accentColor = "#38bdf8";
            headingText = "🚀 CapyGamesStudio Creator Space";
            bodyText = "Build, package, and publish lightweight games straight to the web.";
            extraContent = `
                <button style="background: #38bdf8; color: #0f172a; border: none; padding: 10px 20px; border-radius: 6px; font-weight: bold; margin-top: 15px; cursor: pointer;">Open Studio Editor</button>
            `;
        } else if (prompt.includes("capybara") || prompt.includes("blog")) {
            siteTitle = "Capybara Chronicles";
            bgColor = "#fdf8f2";
            accentColor = "#2d6a4f";
            textColor = "#2d3748";
            cardBg = "#ffffff";
            headingText = "🌿 The Cozy Capybara Blog";
            bodyText = "A calm space for peaceful coding, pixel art, and digital relaxation.";
            extraContent = `
                <p style="font-style: italic; color: #718096; margin-top: 15px;">"Small code. Big chill."</p>
            `;
        } else if (prompt.trim() !== "") {
            headingText = "Custom Idea: " + prompt;
            bodyText = "Your AI engine structured this layout on the fly!";
        }

        // Assemble the full HTML string to inject into the iframe preview
        const generatedHTML = `
            <!DOCTYPE html>
            <html>
            <head>
                <style>
                    body {
                        font-family: system-ui, sans-serif;
                        background-color: ${bgColor};
                        color: ${textColor};
                        display: flex;
                        flex-direction: column;
                        align-items: center;
                        justify-content: center;
                        height: 100vh;
                        margin: 0;
                        text-align: center;
                        padding: 20px;
                    }
                    h1 { color: ${accentColor}; margin-bottom: 10px; font-size: 26px; }
                    p { color: ${textColor === '#2d3748' ? '#4a5568' : '#94a3b8'}; max-width: 450px; line-height: 1.6; font-size: 14px; }
                    .card {
                        background: ${cardBg};
                        border: 1px solid ${textColor === '#2d3748' ? '#e2e8f0' : '#334155'};
                        padding: 30px;
                        border-radius: 12px;
                        box-shadow: 0 10px 25px rgba(0,0,0,0.1);
                    }
                </style>
            </head>
            <body>
                <div class="card">
                    <h1>${headingText}</h1>
                    <p>${bodyText}</p>
                    ${extraContent}
                </div>
            </body>
            </html>
        `;

        // Write the code directly into the iframe preview window
        const blob = new Blob([generatedHTML], { type: 'text/html' });
        frame.src = URL.createObjectURL(blob);
        document.getElementById('frameTitle').textContent = `preview://${siteTitle.toLowerCase().replace(/\s+/g, '-')}.html`;
    }

    // Run default preview on load
    window.onload = () => {
        setPrompt('Make a clean green indie studio homepage with game download links');
    };
</script>

</body>
</html>
