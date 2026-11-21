<p align="center">
  <img src="assets/header.svg" alt="Juanmi — Self-taught developer &amp; automation architect" width="800" />
</p>

<p align="center">
  <a href="https://discord.com/users/1184951565480624212" target="_blank">
    <img src="https://img.shields.io/badge/Discord-el__tortilla1-8ed1ff?style=for-the-badge&logo=discord&logoColor=white&labelColor=0b1221" alt="Discord" />
  </a>
  <a href="https://www.tiktok.com/@juanmimendes1" target="_blank">
    <img src="https://img.shields.io/badge/TikTok-@juanmimendes1-8ed1ff?style=for-the-badge&logo=tiktok&logoColor=white&labelColor=0b1221" alt="TikTok" />
  </a>
  <a href="https://www.youtube.com/@Juanmidev1" target="_blank">
    <img src="https://img.shields.io/badge/YouTube-@Juanmidev1-8ed1ff?style=for-the-badge&logo=youtube&logoColor=white&labelColor=0b1221" alt="YouTube" />
  </a>
</p>

<br>

> **Focus:** Building fast, deterministic tools at the intersection of **AI agent infrastructure**, **low-level Linux systems**, and **production automation**.

<p align="center">
  <img src="assets/desk-chase.svg" alt="Juanmi coding at his desk; Tux runs in, throws a line of code at him, and he chases Tux out of the room" width="800" />
</p>

---

## 👨‍💻 About me

I'm **Juanmi**, a self-taught developer and solutions architect focused on systems programming, AI tooling, and workflow automation. Everything I build comes from hands-on experimentation, reading specs and source code, and solving real operational bottlenecks.

On the **production side**, I design deterministic automation pipelines and custom integrations for businesses. On the **open-source side**, I build single-binary CLIs, Model Context Protocol (MCP) infrastructure, and low-level Linux networking/security tools.

- **How I build:** Minimal dependencies, strict architectural boundaries, and measurable performance over bloated abstractions.
- **Currently exploring:** Offensive security and binary analysis tooling for AI agents.
- **Content:** Sharing 1-minute deep dives on Rust, systems, and AI tooling on [TikTok](https://www.tiktok.com/@juanmimendes1) and [YouTube](https://www.youtube.com/@Juanmidev1).

---

## 🛠️ Core Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=rust,python,ts,linux,docker,git,github&theme=light" alt="Core stack" />
  <br>
  <img alt="MCP" src="https://img.shields.io/badge/MCP-0b1221?style=for-the-badge&logo=anthropic&logoColor=8ed1ff" />
  <img alt="n8n" src="https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" />
  <img alt="Claude" src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white" />
  <img alt="Gemini API" src="https://img.shields.io/badge/Gemini%20API-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white" />
</p>

---

## 🚀 Featured Open-Source Projects

Most of my public work revolves around **giving AI agents surgical context, runtime visibility and kernel-level isolation**, alongside **low-level Linux utilities**:

### [repo-pack](https://github.com/Juanmidev1/repo-pack) — Semantic Context Compression for LLMs
Single-binary Rust CLI & MCP server that packs local or remote repositories into LLM-ready XML/Markdown without blowing the token budget.

- **Surgical context:** Cuts function bodies via `tree-sitter` AST compression (`--skeleton`, `--focus`) saving up to ~68% of tokens while keeping signatures and types intact.
- **Git & security aware:** Packs only changed files plus their importers (`--diff`, `--impact`), redacts API keys/secrets by default, and clones remote Git URLs on the fly.
- **Lightweight:** Ships as a single offline binary (`<3 MB` minimal build) with prebuilt releases for Linux, macOS, and Windows.

`Rust` · `tree-sitter` · `clap` · `ignore` · `MCP`  
[![View repository](https://img.shields.io/badge/View%20repository-repo--pack-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/repo-pack)

---

### [mcp-tap](https://github.com/Juanmidev1/mcp-tap) — Transparent Profiler & Token Auditor for MCP
Transparent `stdio` proxy that sits between an MCP client and server, forwarding every byte unchanged while recording latency, errors, and token cost to a `.jsonl` trace.

- **Protocol-level visibility:** Correlates JSON-RPC 2.0 requests and responses by `id` (including server-initiated sampling) without breaking `stdout` transport.
- **Token & latency guardrails:** Measures per-tool execution time, flags oversized responses (`--max-response-tokens`), and catches stray non-JSON-RPC output.
- **Live & post-mortem:** Includes `mcp-tap tail` for real-time terminal monitoring and `mcp-tap report` for per-tool breakdowns.

`Rust` · `Tokio` · `serde` · `clap` · `JSON-RPC 2.0`  
[![View repository](https://img.shields.io/badge/View%20repository-mcp--tap-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/mcp-tap)

---

### [mcp-jail](https://github.com/Juanmidev1/mcp-jail) - Rootless Kernel Sandbox & Syscall Auditor for MCP
Wraps any `stdio` MCP server in **Landlock LSM** and **`seccomp` user notifications** (no root, no containers) and tags every blocked syscall with the JSON-RPC tool call that triggered it.

- **Kernel-enforced isolation:** Landlock confines the filesystem at inode level, while a `seccomp-unotify` supervisor blocks secrets inside the workspace (`.env`, `*.pem`, SSH keys), outbound connections and child processes.
- **Tool-level attribution:** Correlates each kernel event with the in-flight request, e.g. `[tools/call: summarize_readme] BLOCKED openat(".env") -> EACCES`.
- **Least privilege by observation:** `mcp-jail profile` records a session and writes a minimal `mcp-jail.toml`; `tail` and `report` give live and post-session views. Single ~1.4 MB binary, no async runtime.

`Rust` · `Landlock` · `seccomp` · `libc` · `MCP`  
[![View repository](https://img.shields.io/badge/View%20repository-mcp--jail-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/mcp-jail)

---

### [synapse-code-mcp](https://github.com/Juanmidev1/synapse-code-mcp) — Dynamic Code-Intelligence MCP Server
Stateless Model Context Protocol server that lets AI assistants explore TypeScript/JavaScript codebases dynamically instead of dumping entire files into context.

- **API surface extraction:** Uses AST analysis (`ts-morph`) to expose exported symbols, map import graphs, and run fast `ripgrep` searches on demand.
- **Verified compression:** Backed by 290+ automated tests measuring token reduction ratios across real codebases.

`TypeScript` · `Node.js` · `ts-morph` · `Vitest` · `MCP SDK`  
[![View repository](https://img.shields.io/badge/View%20repository-synapse--code--mcp-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/synapse-code-mcp)

---

### [net-watch](https://github.com/Juanmidev1/net-watch) — Zero-Dependency Linux Packet Analyzer
Real-time terminal network monitor built directly on raw Linux sockets (`AF_PACKET`) and manual byte-level header parsing — no `libpcap`, no Scapy.

- **From-scratch protocol stack:** Decodes Ethernet, ARP, IPv4, TCP, UDP, and ICMP headers manually via `struct`, tracking live throughput, active connections, and per-protocol traffic breakdown.
- **Concurrent pipeline:** Three-thread architecture (capture → processor → Rich TUI) with non-blocking DNS TTL cache and a custom Wireshark-compatible PCAP writer.

`Python` · `Raw Sockets (AF_PACKET)` · `Rich TUI` · `Linux`  
[![View repository](https://img.shields.io/badge/View%20repository-net--watch-8ed1ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0b1221)](https://github.com/Juanmidev1/net-watch)

---

<p align="center">
  <i>Building AI infrastructure, custom automation, or developer tools?</i><br>
  <b><a href="mailto:tortilladev1@gmail.com">Get in touch ⚡</a></b>
</p>

<br>

> **P.S.** The small number of public repositories on this profile doesn't reflect my overall activity — most of my production code lives in private repositories built for client systems and internal automation infrastructure.
