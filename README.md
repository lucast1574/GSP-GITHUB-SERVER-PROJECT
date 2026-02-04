<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GSP - GitHub Server Project</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Fira+Code:wght@400;500&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117;
            color: #c9d1d9;
        }

        .code-block {
            font-family: 'Fira Code', monospace;
            background-color: #161b22;
            border: 1px solid #30363d;
            border-radius: 6px;
            position: relative;
        }

        .copy-btn {
            position: absolute;
            top: 8px;
            right: 8px;
            background: #21262d;
            border: 1px solid #30363d;
            color: #8b949e;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 12px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .copy-btn:hover {
            background: #30363d;
            color: #c9d1d9;
        }

        .copy-btn.copied {
            background: #238636;
            color: white;
            border-color: #2ea043;
        }

        .section-card {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            margin-bottom: 2rem;
            padding: 1.5rem;
        }

        h1, h2, h3 { color: #58a6ff; }
        
        table { width: 100%; border-collapse: collapse; }
        th { text-align: left; border-bottom: 2px solid #30363d; padding: 12px; color: #8b949e; }
        td { padding: 12px; border-bottom: 1px solid #21262d; }
        
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #238636;
            color: white;
            padding: 12px 24px;
            border-radius: 8px;
            display: none;
            z-index: 100;
        }
    </style>
</head>
<body class="p-4 md:p-8">

    <div class="max-w-4xl mx-auto">
        <!-- Header -->
        <header class="mb-12 text-center">
            <h1 class="text-4xl font-bold mb-4">GSP-GITHUB-SERVER-PROJECT</h1>
            <p class="text-xl text-gray-400">A simple collection of commands to create servers using GitHub Codespaces.</p>
        </header>

        <!-- Overview -->
        <section class="section-card">
            <h2 class="text-2xl font-semibold mb-4 flex items-center">
                <span class="mr-2">📋</span> Overview
            </h2>
            <p>This dashboard provides a streamlined workflow for spinning up, configuring, and managing development servers. Simply click the <strong>Copy</strong> button on any command to use it in your terminal.</p>
        </section>

        <!-- Quick Start -->
        <section class="section-card">
            <h2 class="text-2xl font-semibold mb-6 flex items-center">
                <span class="mr-2">🚀</span> Quick Start
            </h2>

            <div class="mb-6">
                <h3 class="font-medium mb-2">1. System Update & Essentials</h3>
                <div class="code-block p-4 overflow-x-auto">
                    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>
                    <pre><code>sudo apt-get update && sudo apt-get upgrade -y</code></pre>
                </div>
            </div>

            <div class="mb-6">
                <h3 class="font-medium mb-2">2. Environment Setup (Build Essentials)</h3>
                <div class="code-block p-4 overflow-x-auto">
                    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>
                    <pre><code>sudo apt-get install -y build-essential && node -v && npm -v</code></pre>
                </div>
            </div>

            <div class="mb-6">
                <h3 class="font-medium mb-2">3. Create Server File (Express)</h3>
                <div class="code-block p-4 overflow-x-auto text-sm">
                    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>
                    <pre><code>cat <<EOF > server.js
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.get('/', (req, res) => {
  res.send('<h1>GSP Server is Running!</h1><p>Created via GitHub Codespaces.</p>');
});

app.listen(PORT, () => {
  console.log(\`Server is running on port \${PORT}\`);
});
EOF</code></pre>
                </div>
            </div>
        </section>

        <!-- Execution -->
        <section class="section-card">
            <h2 class="text-2xl font-semibold mb-6 flex items-center">
                <span class="mr-2">🛠</span> Running the Server
            </h2>
            
            <div class="grid md:grid-cols-2 gap-4">
                <div>
                    <h3 class="font-medium mb-2 text-sm">Initialize & Install</h3>
                    <div class="code-block p-4">
                        <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>
                        <pre><code>npm init -y && npm install express</code></pre>
                    </div>
                </div>
                <div>
                    <h3 class="font-medium mb-2 text-sm">Launch Server</h3>
                    <div class="code-block p-4">
                        <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>
                        <pre><code>node server.js</code></pre>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tables -->
        <section class="section-card overflow-x-auto">
            <h2 class="text-2xl font-semibold mb-6 flex items-center">
                <span class="mr-2">🔧</span> Useful Commands
            </h2>
            <table>
                <thead>
                    <tr>
                        <th>Action</th>
                        <th>Command</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="font-bold">Check Active Ports</td>
                        <td><code class="bg-gray-800 px-2 py-1 rounded">netstat -tuln</code></td>
                    </tr>
                    <tr>
                        <td class="font-bold">Kill Port 3000</td>
                        <td><code class="bg-gray-800 px-2 py-1 rounded">fuser -k 3000/tcp</code></td>
                    </tr>
                    <tr>
                        <td class="font-bold">Monitor Logs</td>
                        <td><code class="bg-gray-800 px-2 py-1 rounded">tail -f server.log</code></td>
                    </tr>
                    <tr>
                        <td class="font-bold">System Resources</td>
                        <td><code class="bg-gray-800 px-2 py-1 rounded">htop</code></td>
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- Footer -->
        <footer class="text-center text-gray-500 text-sm mt-8 pb-12">
            <p>Created for the GSP (GitHub Server Project) Collection.</p>
            <p class="mt-2 italic">Note: Codespaces stop after inactivity. Remember to commit your work!</p>
        </footer>
    </div>

    <div id="toast" class="toast">Copied to clipboard!</div>

    <script>
        function copyToClipboard(btn) {
            const codeBlock = btn.nextElementSibling.innerText;
            const el = document.createElement('textarea');
            el.value = codeBlock;
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);

            const originalText = btn.innerText;
            btn.innerText = 'Copied!';
            btn.classList.add('copied');
            
            showToast();

            setTimeout(() => {
                btn.innerText = originalText;
                btn.classList.remove('copied');
            }, 2000);
        }

        function showToast() {
            const toast = document.getElementById('toast');
            toast.style.display = 'block';
            setTimeout(() => {
                toast.style.display = 'none';
            }, 2000);
        }
    </script>
</body>
</html>
