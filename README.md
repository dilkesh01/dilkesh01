from pathlib import Path
import zipfile, re

base = Path("/mnt/data/dilkesh_github_best")
base.mkdir(exist_ok=True)

# Premium dark/light SVG. Self-contained, no JS/external assets.
svg_common = r'''<svg xmlns="http://www.w3.org/2000/svg" width="1280" height="680" viewBox="0 0 1280 680" role="img" aria-labelledby="title desc">
<title id="title">Dilkesh Meena GitHub profile</title>
<desc id="desc">Computer Science student and developer profile with terminal interface, technical stack, projects and animated accents.</desc>
<defs>
  <linearGradient id="bg" x1="0" y1="0" x2="1" y2="1"><stop offset="0" stop-color="BG1"/><stop offset=".52" stop-color="BG2"/><stop offset="1" stop-color="BG3"/></linearGradient>
  <linearGradient id="accent" x1="0" x2="1"><stop stop-color="#8b5cf6"/><stop offset=".48" stop-color="#22d3ee"/><stop offset="1" stop-color="#34d399"/></linearGradient>
  <linearGradient id="card" x1="0" y1="0" x2="1" y2="1"><stop stop-color="CARD1"/><stop offset="1" stop-color="CARD2"/></linearGradient>
  <radialGradient id="halo"><stop stop-color="#22d3ee" stop-opacity=".20"/><stop offset="1" stop-color="#22d3ee" stop-opacity="0"/></radialGradient>
  <pattern id="grid" width="32" height="32" patternUnits="userSpaceOnUse"><path d="M32 0H0V32" fill="none" stroke="#94a3b8" stroke-opacity=".055"/></pattern>
  <filter id="blur"><feGaussianBlur stdDeviation="16"/></filter>
  <filter id="soft"><feGaussianBlur stdDeviation="4"/></filter>
  <clipPath id="frame"><rect x="16" y="16" width="1248" height="648" rx="28"/></clipPath>
</defs>
<rect width="1280" height="680" fill="OUTER"/>
<g clip-path="url(#frame)">
  <rect x="16" y="16" width="1248" height="648" rx="28" fill="url(#bg)"/>
  <rect x="16" y="16" width="1248" height="648" fill="url(#grid)"/>
  <circle cx="180" cy="160" r="300" fill="url(#halo)"/>
  <circle cx="1100" cy="570" r="330" fill="url(#halo)" opacity=".55"/>

  <!-- top terminal -->
  <rect x="16" y="16" width="1248" height="52" fill="TOP" fill-opacity=".9"/>
  <circle cx="46" cy="42" r="6" fill="#ef4444"/><circle cx="66" cy="42" r="6" fill="#f59e0b"/><circle cx="86" cy="42" r="6" fill="#22c55e"/>
  <text x="112" y="47" fill="MUTED" font-family="ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,monospace" font-size="14">dilkesh@github:~</text>
  <text x="1140" y="47" text-anchor="end" fill="#34d399" font-family="ui-monospace,monospace" font-size="12">● PROFILE ONLINE</text>

  <!-- left identity -->
  <rect x="40" y="92" width="450" height="548" rx="22" fill="url(#card)" stroke="BORDER" stroke-opacity=".5"/>
  <text x="72" y="126" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">01 / IDENTITY</text>
  <line x1="72" y1="142" x2="458" y2="142" stroke="url(#accent)" stroke-opacity=".55"/>

  <!-- abstract ASCII / code portrait -->
  <g font-family="ui-monospace,monospace" font-size="10" text-anchor="middle">
    <text x="265" y="180" fill="#67e8f9">        .·:+*#%%%%#*+:.        </text>
    <text x="265" y="192" fill="#22d3ee">      .:+#%%%%%%%%%%%%#*:.      </text>
    <text x="265" y="204" fill="#a5f3fc">     :*%%%#*+......+*#%%%*:     </text>
    <text x="265" y="216" fill="#67e8f9">    :#%%*:  .::::::.  :*%%#:    </text>
    <text x="265" y="228" fill="#22d3ee">   .#%%:  :+********+:  :%%#.   </text>
    <text x="265" y="240" fill="#a5f3fc">   *%%:  +%#  .  .  #%+  :%%*   </text>
    <text x="265" y="252" fill="#67e8f9">   #%%.  #%+   ()   +%#  .%%#   </text>
    <text x="265" y="264" fill="#22d3ee">   #%%.  +%#  .  .  #%+  .%%#   </text>
    <text x="265" y="276" fill="#a5f3fc">   .#%%:  :+********+:  :%%#.   </text>
    <text x="265" y="288" fill="#67e8f9">    :#%%*:            :*%%#:    </text>
    <text x="265" y="300" fill="#22d3ee">     :*%%%#*+......+*#%%%*:     </text>
    <text x="265" y="312" fill="#a5f3fc">      .:+#%%%%%%%%%%%%#+:.      </text>
    <text x="265" y="324" fill="#22d3ee">         .·:+*####*+:·.         </text>
    <text x="265" y="346" fill="#67e8f9">           .:|||||:.             </text>
    <text x="265" y="358" fill="#22d3ee">        .::|||||||||::.          </text>
    <text x="265" y="370" fill="#a5f3fc">      .:::|||||||||||||:::.      </text>
    <text x="265" y="382" fill="#22d3ee">    .::::|||||||||||||||::::.    </text>
  </g>

  <text x="72" y="430" fill="TEXT" font-family="ui-monospace,monospace" font-size="27" font-weight="700">Dilkesh Meena</text>
  <text x="72" y="458" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="14">Software Developer · CSE Student</text>
  <text x="72" y="490" fill="MUTED" font-family="ui-monospace,monospace" font-size="12">$ whoami</text>
  <text x="72" y="512" fill="TEXT2" font-family="ui-monospace,monospace" font-size="12">builder • problem solver • learner</text>
  <text x="72" y="548" fill="#34d399" font-family="ui-monospace,monospace" font-size="12">●</text>
  <text x="90" y="548" fill="MUTED" font-family="ui-monospace,monospace" font-size="12">building with code &amp; exploring AI/ML</text>
  <rect x="72" y="574" width="8" height="16" fill="#22d3ee"><animate attributeName="opacity" values="1;0;1" dur="1.05s" repeatCount="indefinite"/></rect>
  <text x="92" y="588" fill="MUTED" font-family="ui-monospace,monospace" font-size="11">ready to build_</text>

  <!-- right system -->
  <rect x="514" y="92" width="726" height="548" rx="22" fill="url(#card)" stroke="BORDER" stroke-opacity=".5"/>
  <text x="548" y="126" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">02 / SYSTEM.INFO</text>
  <text x="548" y="154" fill="MUTED" font-family="ui-monospace,monospace" font-size="12">dilkesh@github:~$ ./profile.sh</text>

  <g font-family="ui-monospace,monospace" font-size="14">
    <text x="548" y="194" fill="MUTED">▸ NAME</text><text x="704" y="194" fill="TEXT">Dilkesh Meena</text>
    <text x="548" y="226" fill="MUTED">▸ ROLE</text><text x="704" y="226" fill="TEXT">B.Tech CSE Student</text>
    <text x="548" y="258" fill="MUTED">▸ INSTITUTE</text><text x="704" y="258" fill="TEXT">IIIT Sonepat</text>
    <text x="548" y="290" fill="MUTED">▸ FOCUS</text><text x="704" y="290" fill="#22d3ee">Software · Web · AI/ML</text>
  </g>

  <line x1="548" y1="314" x2="1206" y2="314" stroke="BORDER"/>
  <text x="548" y="346" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">03 / TECH STACK</text>

  <!-- stack pills -->
  <g font-family="ui-monospace,monospace" font-size="12">
    <g fill="PILL" stroke="#22d3ee" stroke-opacity=".5">
      <rect x="548" y="362" width="92" height="31" rx="15"/><rect x="650" y="362" width="78" height="31" rx="15"/>
      <rect x="738" y="362" width="88" height="31" rx="15"/><rect x="836" y="362" width="82" height="31" rx="15"/>
      <rect x="928" y="362" width="88" height="31" rx="15"/><rect x="1026" y="362" width="72" height="31" rx="15"/>
    </g>
    <text x="569" y="383" fill="#bae6fd">C/C++</text><text x="670" y="383" fill="#bae6fd">Java</text><text x="758" y="383" fill="#bae6fd">Python</text><text x="858" y="383" fill="#bae6fd">React</text><text x="950" y="383" fill="#bae6fd">MySQL</text><text x="1047" y="383" fill="#bae6fd">Git</text>
    <g fill="PILL" stroke="#8b5cf6" stroke-opacity=".5">
      <rect x="548" y="403" width="98" height="31" rx="15"/><rect x="656" y="403" width="104" height="31" rx="15"/>
      <rect x="770" y="403" width="94" height="31" rx="15"/><rect x="874" y="403" width="124" height="31" rx="15"/>
    </g>
    <text x="568" y="424" fill="#ddd6fe">HTML/CSS</text><text x="678" y="424" fill="#ddd6fe">JavaScript</text><text x="791" y="424" fill="#ddd6fe">Streamlit</text><text x="895" y="424" fill="#ddd6fe">Transformers</text>
  </g>

  <line x1="548" y1="456" x2="1206" y2="456" stroke="BORDER"/>
  <text x="548" y="486" fill="#22d3ee" font-family="ui-monospace,monospace" font-size="12" letter-spacing="2">04 / SELECTED WORK</text>
  <text x="548" y="514" fill="TEXT" font-family="ui-monospace,monospace" font-size="12">▹ SmartSyntex</text>
  <text x="704" y="514" fill="MUTED" font-family="ui-monospace,monospace" font-size="12">AI/NLP summarization &amp; decision support</text>
  <text x="548" y="540" fill="TEXT" font-family="ui-monospace,monospace" font-size="12">▹ Library Management</text>
  <text x="748" y="540" fill="MUTED" font-family="ui-monospace,monospace" font-size="12">C++ · OOP · file handling</text>
  <text x="548" y="566" fill="TEXT" font-family="ui-monospace,monospace" font-size="12">▹ Developer Portfolio</text>
  <text x="748" y="566" fill="MUTED" font-family="ui-monospace,monospace" font-size="12">responsive web development</text>

  <text x="548" y="604" fill="#34d399" font-family="ui-monospace,monospace" font-size="11">status: building • learning • shipping</text>
</g>
<rect x="16" y="16" width="1248" height="648" rx="28" fill="none" stroke="url(#accent)" stroke-opacity=".72"/>
</svg>'''

dark = svg_common
dark = dark.replace("BG1","#030712").replace("BG2","#08111f").replace("BG3","#10152b")
dark = dark.replace("OUTER","#020617").replace("TOP","#0f172a").replace("CARD1","#0f172a").replace("CARD2","#111827")
dark = dark.replace("BORDER","#475569").replace("MUTED","#94a3b8").replace("TEXT","#f8fafc").replace("TEXT2","#cbd5e1").replace("PILL","#07111f")

light = svg_common
light = light.replace("BG1","#ffffff").replace("BG2","#f8fafc").replace("BG3","#eef6ff")
light = light.replace("OUTER","#e2e8f0").replace("TOP","#ffffff").replace("CARD1","#ffffff").replace("CARD2","#f8fafc")
light = light.replace("BORDER","#cbd5e1").replace("MUTED","#64748b").replace("TEXT","#0f172a").replace("TEXT2","#334155").replace("PILL","#f8fafc")

readme = r'''<div align="center">

# 👋 Hi, I'm Dilkesh Meena

### 💻 Software Developer • CSE Student • AI/ML Explorer

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./light.svg">
  <img src="./dark.svg" alt="Dilkesh Meena — Software Developer and Computer Science student">
</picture>

</div>

## 🚀 About Me

🎓 B.Tech **Computer Science & Engineering** student at **IIIT Sonepat**  
💻 Building projects across **software, web development and AI/ML**  
🧠 Strengthening **Data Structures & Algorithms, OOP, databases and problem solving**  
🤖 Exploring **NLP, Hugging Face Transformers and intelligent applications**

## 🧰 Tech Stack

### 💻 Languages
![C](https://img.shields.io/badge/C-111827?style=for-the-badge&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-111827?style=for-the-badge&logo=cplusplus&logoColor=white)
![Java](https://img.shields.io/badge/Java-111827?style=for-the-badge&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-111827?style=for-the-badge&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-111827?style=for-the-badge&logo=javascript&logoColor=white)

### 🌐 Web & Database
![HTML5](https://img.shields.io/badge/HTML5-111827?style=for-the-badge&logo=html5&logoColor=E34F26)
![CSS3](https://img.shields.io/badge/CSS3-111827?style=for-the-badge&logo=css3&logoColor=1572B6)
![React](https://img.shields.io/badge/React-111827?style=for-the-badge&logo=react&logoColor=61DAFB)
![Bootstrap](https://img.shields.io/badge/Bootstrap-111827?style=for-the-badge&logo=bootstrap&logoColor=7952B3)
![MySQL](https://img.shields.io/badge/MySQL-111827?style=for-the-badge&logo=mysql&logoColor=4479A1)

### 🤖 AI / ML & Tools
![Python](https://img.shields.io/badge/NLP-111827?style=for-the-badge&logo=python&logoColor=3776AB)
![Hugging Face](https://img.shields.io/badge/HuggingFace-111827?style=for-the-badge&logo=huggingface&logoColor=FFD21E)
![Git](https://img.shields.io/badge/Git-111827?style=for-the-badge&logo=git&logoColor=F05032)
![GitHub](https://img.shields.io/badge/GitHub-111827?style=for-the-badge&logo=github&logoColor=white)
![VS Code](https://img.shields.io/badge/VS%20Code-111827?style=for-the-badge&logo=visualstudiocode&logoColor=007ACC)

## 🌟 Featured Projects

| Project | Description |
|---|---|
| 🤖 **SmartSyntex** | AI-based intelligent data summarization and decision-support project using NLP/deep-learning technologies. |
| 📚 **Library Management System** | C++ console application demonstrating OOP concepts and file handling. |
| 🌐 **Developer Portfolio** | Responsive portfolio project built with HTML, CSS, JavaScript and React concepts. |
| 🎬 **Netflix Clone** | Responsive front-end clone project using web technologies. |

## 📈 What I'm Working On

```text
DSA & Problem Solving
        ↓
Software Engineering
        ↓
Web Development
        ↓
AI / ML & NLP
        ↓
Building practical projects 🚀
