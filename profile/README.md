<p align="center">
  <img src="https://avatars.githubusercontent.com/u/Trapezohe?s=160" alt="Trapezohe" width="120" height="120" />
</p>

<h1 align="center">Trapezohe</h1>

<p align="center">
  <strong>Local-first AI tools for people who want their context back.</strong>
</p>

<p align="center">
  <a href="https://ghast.trapezohe.ai"><img src="https://img.shields.io/badge/website-ghast.trapezohe.ai-1da1f2?style=for-the-badge&labelColor=555" alt="Website" /></a>
  <a href="https://discord.gg/ghastai"><img src="https://img.shields.io/badge/Discord-Join-5865F2?style=for-the-badge&labelColor=555&logo=discord&logoColor=white" alt="Discord" /></a>
  <a href="https://x.com/Ghast_AI"><img src="https://img.shields.io/badge/X-@Ghast__AI-000000?style=for-the-badge&labelColor=555&logo=x&logoColor=white" alt="@Ghast_AI" /></a>
</p>

---

We build tools that respect where your data lives. The cloud is convenient,
but it shouldn't be the only place a memory, a workflow, or an agent can run.
Everything we ship runs first on the machine in front of you, talks to local
files and processes directly, and only reaches out to the network when you
want it to.

## Products

### 🐉 Ghast AI

A desktop AI companion that remembers, takes action, and works across the
apps you already use. macOS, Windows, and Linux. Built around three ideas:

- **Memory that survives** — conversations, notes, and per-app context
  persist in plain files on your disk, not someone else's database.
- **Computer use that's useful** — drive native apps and the browser
  through Accessibility, AppleScript, and a per-app playbook system so
  the model isn't guessing.
- **Plugin and MCP support** — bring your own tools via the Anthropic
  plugin format and any MCP server.

→ [ghast.trapezohe.ai](https://ghast.trapezohe.ai)

### 🧠 Anamnesis

A local-first interoperability layer that imports, normalizes, indexes,
and serves agent memory across runtimes. If you have months of context
sitting in Codex, mem0, Claude Code, OpenClaw, or some other tool's
local cache, Anamnesis lets it move with you.

Standalone Rust project — works without Ghast and is happy to feed
context to any MCP-aware agent.

→ [`Anamnesis`](https://github.com/Trapezohe/Anamnesis) · [Blueprint](https://github.com/Trapezohe/Anamnesis/blob/main/docs/BLUEPRINT.md)

---

## Open-source repositories

| Repo | Language | Purpose |
|---|---|---|
| [**Anamnesis**](https://github.com/Trapezohe/Anamnesis) | Rust | Cross-agent memory interop. CLI + MCP server, SQLite + FTS + optional embeddings. |
| [**companion_service**](https://github.com/Trapezohe/companion_service) | Rust | Desktop runtime for the Ghast extension — local execution, browser pairing for Chrome / Brave / Edge, MCP host, ACP ingress. |
| [**ghast-plugins**](https://github.com/Trapezohe/ghast-plugins) | Python | Plugin + MCP marketplace served to Ghast's in-app browser. Anthropic plugin format compatible — Claude Code plugins drop in unchanged. |
| [**ghast-mcp-registry**](https://github.com/Trapezohe/ghast-mcp-registry) | JSON | Curated MCP server directory rendered in Ghast → Settings → MCP → Marketplace. |
| [**Ghast_Doc**](https://github.com/Trapezohe/Ghast_Doc) | VitePress | Documentation site source. |

## Architecture at a glance

```
┌──────────────────────────────────────────────────────────────────┐
│                       Ghast AI (desktop)                          │
│   ┌─────────────┐   ┌──────────────┐   ┌────────────────────┐   │
│   │ Chat + UI   │   │ Skills &     │   │ Browser, Computer  │   │
│   │ Memory      │   │ Plugins      │   │ Use, Native Tools  │   │
│   └──────┬──────┘   └──────┬───────┘   └─────────┬──────────┘   │
└──────────┼─────────────────┼─────────────────────┼──────────────┘
           │ persists into   │ resolves via        │ runs through
           ▼                 ▼                     ▼
   ┌──────────────┐  ┌────────────────────┐  ┌─────────────────┐
   │  Anamnesis   │  │ ghast-plugins      │  │ companion_      │
   │  memory      │  │ ghast-mcp-registry │  │ service         │
   │  layer       │  │ (marketplaces)     │  │ (local runtime) │
   └──────────────┘  └────────────────────┘  └─────────────────┘
```

Each open-source layer is also usable on its own. Anamnesis runs as a
standalone Rust CLI + MCP server. `companion_service` ships as a local
daemon any tool can pair with. The marketplaces are plain GitHub-hosted
JSON.

## Get involved

- **Try Ghast** — download from [ghast.trapezohe.ai](https://ghast.trapezohe.ai).
- **Star [Anamnesis](https://github.com/Trapezohe/Anamnesis)** if scattered
  agent memory is your problem too.
- **List your MCP server** — open a `[Registry]` issue in
  [ghast-mcp-registry](https://github.com/Trapezohe/ghast-mcp-registry)
  (or use the in-app "Submit listing" button).
- **Ship a plugin** — see [ghast-plugins](https://github.com/Trapezohe/ghast-plugins);
  Anthropic-format plugins work as-is.
- **Talk to us** — [Discord](https://discord.gg/ghastai) ·
  [@Ghast_AI](https://x.com/Ghast_AI) on X.

## License

Per-repository. Anamnesis is Apache-2.0. See individual repos for the
rest.

---

<p align="center">
  <sub>Made by humans + agents at Trapezohe. Your data stays where it started.</sub>
</p>
