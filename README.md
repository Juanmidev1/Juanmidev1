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
  <img src="https://skillicons.dev/icons?i=python,rust,docker,linux,git,github,javascript&theme=light" alt="Tools & technologies" />
  <br>
  <img alt="n8n" src="https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" />
  <img alt="Claude" src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white" />
  <img alt="Gemini API" src="https://img.shields.io/badge/Gemini%20API-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white" />
</p>

---

## 🚀 Featured public projects

### [repo-pack](https://github.com/Juanmidev1/repo-pack)

Rust CLI that packs a whole repository into a single text block ready for an LLM context window. Offline, a few milliseconds on a typical repo, shipped as a single binary.

**What it solves:** feeding a model the right code without blowing the token budget. Instead of dumping every file, it can keep only signatures via tree-sitter AST compression (`--skeleton`, `--focus`), redact secrets, and pack just what changed in git plus the files that import it (`--diff main --impact`).

**Key features:**
- XML or Markdown output, clipboard copy and token statistics (`--stats`, `--max-tokens`)
- Respects `.gitignore`, with extension, glob and size filters
- Built-in MCP server so assistants can request packed context directly
- Prebuilt binaries for Linux, macOS and Windows

**Stack:** Rust · tree-sitter · clap · ignore  
**Status:** active

[![View repository](https://img.shields.io/badge/View%20repository-repo--pack-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/repo-pack)

---

### [synapse-code-mcp](https://github.com/Juanmidev1/synapse-code-mcp)

A code-intelligence MCP server that connects local repositories with AI assistants via the Model Context Protocol. Instead of copy-pasting files into the prompt, the assistant explores the codebase dynamically — pulling only what it needs, when it needs it.

**What it solves:** high-quality context at scale. Most AI tools already index files; Synapse tackles a different problem: sending the model only the relevant API surface (not the whole file), mapping import dependencies, and offering semantic search powered by ripgrep — all with compression ratios verified by automated tests.

**Stack:** TypeScript · Node.js · ts-morph · Vitest · MCP SDK
**Status:** active, contributions welcome

[![View repository](https://img.shields.io/badge/View%20repository-synapse--code--mcp-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/synapse-code-mcp)

---

### [mcp-tap](https://github.com/Juanmidev1/mcp-tap)

Transparent `stdio` proxy, JSON-RPC 2.0 profiler and token auditor for Model Context Protocol servers.

**What it solves:** MCP servers over `stdio` are hard to debug, since `stdout` is the transport and you can't see how slow each call is or how many tokens it costs the model. `mcp-tap` wraps the server command, forwards every byte unchanged and writes a `.jsonl` trace of what happened.

**Key features:**
- Per-call latency, matching requests and responses by JSON-RPC `id` (including server-to-client requests)
- Token audit per request/response, flagging tool responses over a configurable limit
- MCP-aware: records tool names, resource URIs, protocol errors and `isError` results
- Live `tail` of a running session and a `report` summary afterwards

**Stack:** Rust · Tokio · serde · clap  
**Status:** active, CI on every push

[![View repository](https://img.shields.io/badge/View%20repository-mcp--tap-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/mcp-tap)

---

### [net-watch](https://github.com/Juanmidev1/net-watch)

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

[![View repository](https://img.shields.io/badge/View%20repository-net--watch-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/net-watch)

---

<p align="center">
  <i>Looking to scale your technical operations or explore a collaboration?</i><br>
  <b><a href="mailto:tortilladev1@gmail.com">Reach out and let's talk. ⚡</a></b>
</p>

<br>

> **P.S.** The small number of public repos on my profile doesn't reflect my actual activity — most of my code and projects live in private repositories and production environments built for clients and internal systems.
