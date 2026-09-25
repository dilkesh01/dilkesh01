from pathlib import Path

out = Path("/mnt/data/github_profile")
out.mkdir(exist_ok=True)

dark = r'''<svg xmlns="http://www.w3.org/2000/svg" width="1180" height="610" viewBox="0 0 1180 610" role="img" aria-label="Dilkesh Meena — Software Developer and Computer Science student">
<defs>
  <linearGradient id="bg" x1="0" y1="0" x2="1" y2="1"><stop stop-color="#030712"/><stop offset=".55" stop-color="#08111f"/><stop offset="1" stop-color="#10152b"/></linearGradient>
  <linearGradient id="line" x1="0" x2="1"><stop stop-color="#8b5cf6"/><stop offset=".5" stop-color="#22d3ee"/><stop offset="1" stop-color="#34d399"/></linearGradient>
  <radialGradient id="orb"><stop stop-color="#22d3ee" stop-opacity=".20"/><stop offset="1" stop-color="#22d3ee" stop-opacity="0"/></radialGradient>
  <pattern id="grid" width="32" height="32" patternUnits="userSpaceOnUse"><path d="M32 0H0V32" fill="none" stroke="#94a3b8" stroke-opacity=".045"/></pattern>
  <filter id="glow"><feGaussianBlur stdDeviation="5"/></filter>
  <clipPath id="clip"><rect x="18" y="18" width="1144" height="574" rx="26"/></clipPath>
</defs>
<rect width="1180" height="610" fill="#020617"/>
<g clip-path="url(#clip)">
<rect x="18" y="18" width="1144" height="574" rx="26" fill="url(#bg)"/>
<rect x="18" y="18" width="1144" height="574" fill="url(#grid)"/>
<circle cx="180" cy="170" r="300" fill="url(#orb)"/><circle cx="1010" cy="500" r="280" fill="url(#orb)"/>
<circle cx="180" cy="170" r="180" fill="none" stroke="#22d3ee" stroke-opacity=".08">
 <animateTransform attributeName="transform" type="rotate" from="0 180 170" to="360 180 170" dur="22s" repeatCount="indefinite"/>
</circle>

<!-- terminal bar -->
<rect x="18" y="18" width="1144" height="48" fill="#0f172a" fill-opacity=".88"/>
<circle cx="47" cy="42" r="6" fill="#ef4444"/><circle cx="67" cy="42" r="6" fill="#f59e0b"/><circle cx="87" cy="42" r="6" fill="#22c55e"/>
<text x="112" y="47" fill="#94a3b8" font-family="ui-monospace,monospace" font-size="14">dilkesh@github:~</text>
<text x="1050" y="47" fill="#34d399" font-family="ui-monospace,monospace" font-size="12">● ONLINE</text>

<!-- left -->
<rect x="42" y="90" width="408" height="468" rx="22" fill="#0f172a" fill-opacity=".55" stroke="#64748b" stroke-opacity=".34"/>
<text x="72" y="122" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">VISUAL.MAP</text>
<line x1="72" y1="136" x2="420" y2="136" stroke="url(#line)" stroke-opacity=".6"/>

<!-- stylized ASCII portrait -->
<g font-family="ui-monospace,monospace" font-size="10" text-anchor="middle">
<text x="246" y="180" fill="#67e8f9">       .·:+*#%#*+:.       </text>
<text x="246" y="192" fill="#22d3ee">     .:+#%%%%%%%%#*:.     </text>
<text x="246" y="204" fill="#a5f3fc">    :*%%#*+....+*#%%*:    </text>
<text x="246" y="216" fill="#67e8f9">   :#%%+.  .:::.  .+%%#:   </text>
<text x="246" y="228" fill="#22d3ee">  .#%%:   :+***+:   :%%#.  </text>
<text x="246" y="240" fill="#a5f3fc">  *%%:   +%#..#%+   :%%*  </text>
<text x="246" y="252" fill="#67e8f9">  #%%.   #%.  .%#   .%%#  </text>
<text x="246" y="264" fill="#22d3ee">  #%%.   *%+..+%*   .%%#  </text>
<text x="246" y="276" fill="#a5f3fc">  .#%%:   :*##*:   :%%#.  </text>
<text x="246" y="288" fill="#67e8f9">   :#%%+.          .+%%#:   </text>
<text x="246" y="300" fill="#22d3ee">    :*#%%*+:.  .:+*%%#*:    </text>
<text x="246" y="312" fill="#a5f3fc">     .:+#%%%%%%%%%%#+:.     </text>
<text x="246" y="324" fill="#22d3ee">        .·:+*##*+:·.        </text>
<text x="246" y="344" fill="#67e8f9">          .:||||:.          </text>
<text x="246" y="356" fill="#22d3ee">       .::||||||||::.       </text>
<text x="246" y="368" fill="#a5f3fc">     .:::||||||||||||:::.     </text>
</g>

<text x="72" y="416" fill="#f8fafc" font-family="ui-monospace,monospace" font-size="22" font-weight="700">Dilkesh Meena</text>
<text x="72" y="444" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="13">Software Developer · CSE Student</text>
<text x="72" y="478" fill="#94a3b8" font-family="ui-monospace,monospace" font-size="12">~/profile $ build --learn --ship</text>
<text x="72" y="504" fill="#34d399" font-family="ui-monospace,monospace" font-size="12">●</text>
<text x="88" y="504" fill="#cbd5e1" font-family="ui-monospace,monospace" font-size="12">exploring software + AI/ML</text>
<rect x="72" y="526" width="8" height="15" fill="#22d3ee"><animate attributeName="opacity" values="1;0;1" dur="1s" repeatCount="indefinite"/></rect>

<!-- right -->
<rect x="474" y="90" width="664" height="468" rx="22" fill="#0f172a" fill-opacity=".58" stroke="#64748b" stroke-opacity=".34"/>
<text x="508" y="122" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">SYSTEM.INFO</text>
<text x="508" y="150" fill="#64748b" font-family="ui-monospace,monospace" font-size="12">dilkesh@github:~$ ./profile.sh</text>

<g font-family="ui-monospace,monospace" font-size="14">
<text x="508" y="190" fill="#64748b">▸ NAME</text><text x="660" y="190" fill="#f8fafc">Dilkesh Meena</text>
<text x="508" y="222" fill="#64748b">▸ ROLE</text><text x="660" y="222" fill="#f8fafc">B.Tech CSE Student</text>
<text x="508" y="254" fill="#64748b">▸ INSTITUTE</text><text x="660" y="254" fill="#f8fafc">IIIT Sonepat</text>
<text x="508" y="286" fill="#64748b">▸ FOCUS</text><text x="660" y="286" fill="#22d3ee">Software · Web · AI/ML</text>
</g>

<line x1="508" y1="312" x2="1104" y2="312" stroke="#334155"/>
<text x="508" y="344" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">TECH STACK</text>

<g font-family="ui-monospace,monospace" font-size="12">
<g fill="#0b1220" stroke="#22d3ee" stroke-opacity=".55">
<rect x="508" y="360" width="88" height="30" rx="15"/><rect x="606" y="360" width="78" height="30" rx="15"/><rect x="694" y="360" width="86" height="30" rx="15"/><rect x="790" y="360" width="82" height="30" rx="15"/><rect x="882" y="360" width="88" height="30" rx="15"/><rect x="980" y="360" width="72" height="30" rx="15"/>
</g>
<text x="528" y="380" fill="#bae6fd">C/C++</text><text x="625" y="380" fill="#bae6fd">Java</text><text x="714" y="380" fill="#bae6fd">Python</text><text x="813" y="380" fill="#bae6fd">React</text><text x="904" y="380" fill="#bae6fd">MySQL</text><text x="1001" y="380" fill="#bae6fd">Git</text>
<g fill="#0b1220" stroke="#8b5cf6" stroke-opacity=".55">
<rect x="508" y="400" width="94" height="30" rx="15"/><rect x="612" y="400" width="100" height="30" rx="15"/><rect x="722" y="400" width="92" height="30" rx="15"/><rect x="824" y="400" width="120" height="30" rx="15"/>
</g>
<text x="529" y="420" fill="#ddd6fe">HTML/CSS</text><text x="633" y="420" fill="#ddd6fe">JavaScript</text><text x="744" y="420" fill="#ddd6fe">Streamlit</text><text x="846" y="420" fill="#ddd6fe">Transformers</text>
</g>

<text x="508" y="462" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">SELECTED PROJECTS</text>
<text x="508" y="488" fill="#f8fafc" font-family="ui-monospace,monospace" font-size="12">▹ SmartSyntex</text><text x="650" y="488" fill="#94a3b8" font-family="ui-monospace,monospace" font-size="12">AI/NLP summarization &amp; decision support</text>
<text x="508" y="514" fill="#f8fafc" font-family="ui-monospace,monospace" font-size="12">▹ Library Management</text><text x="700" y="514" fill="#94a3b8" font-family="ui-monospace,monospace" font-size="12">C++ · OOP · file handling</text>
<text x="508" y="540" fill="#f8fafc" font-family="ui-monospace,monospace" font-size="12">▹ Portfolio</text><text x="650" y="540" fill="#94a3b8" font-family="ui-monospace,monospace" font-size="12">responsive web development</text>
</g>
<rect x="18" y="18" width="1144" height="574" rx="26" fill="none" stroke="url(#line)" stroke-opacity=".7"/>
</svg>'''

light = dark.replace('fill="#020617"/>','fill="#e2e8f0"/>',1).replace('fill="url(#bg)"/>','fill="url(#bg)"/>',1)
light = light.replace('<stop stop-color="#030712"/><stop offset=".55" stop-color="#08111f"/><stop offset="1" stop-color="#10152b"/>','<stop stop-color="#ffffff"/><stop offset=".55" stop-color="#f8fafc"/><stop offset="1" stop-color="#eef6ff"/>')
light = light.replace('fill="#0f172a" fill-opacity=".88"','fill="#ffffff" fill-opacity=".92"')
light = light.replace('fill="#0f172a" fill-opacity=".55"','fill="#ffffff" fill-opacity=".70')
light = light.replace('fill="#0f172a" fill-opacity=".58"','fill="#ffffff" fill-opacity=".76')
light = light.replace('fill="#f8fafc"','fill="#0f172a"')
light = light.replace('fill="#cbd5e1"','fill="#334155"')
light = light.replace('fill="#94a3b8"','fill="#475569"')
light = light.replace('fill="#0b1220"','fill="#ffffff"')

readme = '''# 👋 Hi, I'm Dilkesh Meena

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./light.svg">
  <img src="./dark.svg" alt="Dilkesh Meena — Software Developer and Computer Science student">
</picture>

## 🚀 About Me

🎓 **B.Tech Computer Science & Engineering** student at **IIIT Sonepat**  
💻 Interested in **Software Development, Web Development, AI/ML and NLP**  
🧠 Practising **Data Structures & Algorithms** and building practical projects.

## 🛠️ Tech Stack

| Area | Technologies |
|---|---|
| 💻 Languages | C, C++, Java, Python, JavaScript |
| 🌐 Web | HTML, CSS, React, Bootstrap |
| 🗄️ Database | MySQL |
| 🤖 AI / ML | NLP, Hugging Face Transformers, Streamlit |
| 🔧 Tools | Git, GitHub, VS Code |

## 📌 Featured Projects

### 🤖 SmartSyntex
AI-based intelligent data summarization and decision-support project using NLP/deep-learning technologies.

### 📚 Library Management System
C++ console application using OOP concepts and file handling.

### 🌐 Developer Portfolio
Responsive portfolio project built with HTML, CSS, JavaScript and React concepts.

## 🎯 Current Focus

```text
DSA → Software Engineering → Web Development → AI/ML
