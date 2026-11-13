<p align="center">
  <img src="assets/header.svg" alt="Juanmi — Software engineer &amp; automation architect" width="800" />
</p>


<p align="center">
  <a href="https://discord.com/users/1184951565480624212" target="_blank">
    <img src="https://img.shields.io/badge/💬%20Discord-el_tortilla1-8ed1ff?style=for-the-badge&logo=discord&logoColor=white&labelColor=0b1221" />
  </a>
</p>

<br>

> **My mission:** Turning operational chaos into profitable, scalable tech assets through modular architecture and purposeful code.

<p align="center">
  <img src="assets/desk-chase.svg" alt="juanmidev coding at his desk; Tux runs in, throws a line of code at him, and he chases Tux out of the room" width="800" />
</p>

---

## 👨‍💻 About me

I'm **Juanmi**, a self-taught developer and solutions architect passionate about new technologies and intelligent automation. My skills come from years of hands-on practice, constant research, and solving real-world problems — which lets me approach development from a pragmatic, efficient, no-nonsense perspective.

I design deterministic systems and robust software architectures. My focus is on real business impact, making sure every system is a scalable, auditable asset free of unnecessary technical debt.

---

## 🧠 Development Philosophy

* **Practical, functional code:** I reject temporary fixes that create future problems. I prioritize structural rigor and clean code.
* **Innovation with purpose:** I love new technologies, but I only adopt them when they bring clear strategic value and ROI.
* **Technical sustainability:** I build modular systems that allow for growth and continuous auditing without compromising the stability of the core engine.

---

## 🛠️ Tools & technologies

I don't tie myself to a fixed stack — I adapt to the problem. These are the tools I work with regularly in production:

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,docker,linux,git,github,javascript&theme=light" alt="Tools & technologies" />
  <br>
  <img alt="n8n" src="https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" />
  <img alt="Claude" src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white" />
  <img alt="Gemini API" src="https://img.shields.io/badge/Gemini%20API-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white" />
</p>

---

## 🚀 Featured public projects

### [synapse-code-mcp](https://github.com/Eltortilla1/synapse-code-mcp)

A code-intelligence MCP server that connects local repositories with AI assistants via the Model Context Protocol. Instead of copy-pasting files into the prompt, the assistant explores the codebase dynamically — pulling only what it needs, when it needs it.

**What it solves:** high-quality context at scale. Most AI tools already index files; Synapse tackles a different problem: sending the model only the relevant API surface (not the whole file), mapping import dependencies, and offering semantic search powered by ripgrep — all with compression ratios verified by automated tests.

**Stack:** TypeScript · Node.js · ts-morph · Vitest · MCP SDK
**Status:** active, contributions welcome

[![View repository](https://img.shields.io/badge/View%20repository-synapse--code--mcp-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Eltortilla1/synapse-code-mcp)

---

### [net-watch](https://github.com/Eltortilla1/net-watch)

Real-time network packet analyzer for the terminal. Built
entirely on raw Linux sockets and manual protocol parsing —
no Scapy, no libpcap, no external capture library of any kind.

**What it does:** captures every Ethernet frame passing through
a network interface and decodes it to its protocol components
in real time — active connections, per-destination traffic,
protocol breakdown (TCP/UDP/ICMP/ARP), and live throughput,
updated every 500 ms.

**Under the hood:** three concurrent threads (capture →
processor → display), manual byte-level parsing of IPv4/TCP/
UDP/ICMP/ARP headers using Python's `struct` module,
thread-safe statistics with a sliding rate window, non-blocking
DNS resolution via `ThreadPoolExecutor` with TTL cache, and a
PCAP writer implemented from scratch (no libpcap) that produces
files readable by Wireshark.

**Stack:** Python · Raw sockets (`AF_PACKET`) · Rich TUI ·
threading · struct · termios  
**Status:** stable, Linux only

[![View repository](https://img.shields.io/badge/View%20repository-net--watch-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Eltortilla1/net-watch)

---

### [prompt-bench](https://github.com/Eltortilla1/prompt-bench)

CLI to benchmark prompts across multiple LLMs in parallel —
compare latency, token usage and estimated cost in a single
terminal table.

**What it does:** send the same prompt to Gemini, GPT and Grok
simultaneously and get back a Rich table with latency per model,
input/output tokens, estimated cost in USD, and a visual quality
bar. Runs are saved as JSON with full responses for later review
or export.

**Key features:**
- Parallel async calls to all providers via `asyncio + httpx`
- `--models provider:model` syntax to target specific model versions
- `--system` flag for shared system prompt across all providers
- `--repeat N` to average latency over multiple runs and detect
  response variance
- Export any run to Markdown or CSV for documentation
- Extensible: adding a new provider is a single file + 3 lines
  in the registry

**Stack:** Python · asyncio · httpx · Rich · Click  
**Providers:** Gemini · OpenAI · Grok (xAI)  
**Status:** active

[![View repository](https://img.shields.io/badge/View%20repository-prompt--bench-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Eltortilla1/prompt-bench)

---

<p align="center">
  <i>Looking to scale your technical operations or explore a collaboration?</i><br>
  <b><a href="mailto:tortilladev1@gmail.com">Reach out and let's talk. ⚡</a></b>
</p>

<br>

> **P.S.** The small number of public repos on my profile doesn't reflect my actual activity — most of my code and projects live in private repositories and production environments built for clients and internal systems.
