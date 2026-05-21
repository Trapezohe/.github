<a name="readme-top"></a>

<div align="center">

<img height="120" src="https://avatars.githubusercontent.com/u/262958902?s=240" alt="Trapezohe" />

<h1>Trapezohe</h1>

Local-first AI tools for people who want their context back.

[![][website-shield]][website-link]
[![][discord-shield]][discord-link]
[![][github-star]][github-link]
[![][x-shield]][x-link]

![](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

</div>

### 👋 Welcome to Trapezohe

We build tools that respect where your data lives. The cloud is convenient, but it shouldn't be the only place a memory, a workflow, or an agent can run. Everything we ship runs first on the machine in front of you, talks to local files and processes directly, and only reaches out to the network when you want it to.

[Ghast AI][ghast-website] is our flagship — a desktop AI companion that remembers, takes action, and works across the apps you already use. The repositories below are the open-source layers underneath, each usable on its own.

### ⭐️ Our Projects

| [**🐉 Ghast AI**][ghast-website]<br/>Desktop AI companion for macOS, Windows, and Linux. Persistent memory, native computer use, plugin and MCP support — all local-first.<br/><br/>[![][ghast-website-shield]][ghast-website] | <picture><img src="https://raw.githubusercontent.com/Trapezohe/companion_service/main/docs/assets/ghast-logo.png" alt="Ghast AI" width="200" /></picture> |
| :--- | :---: |
| [**🧠 Anamnesis**][anamnesis-github]<br/>Local-first interoperability layer that imports, normalizes, indexes, and serves agent memory across runtimes. Rust CLI + MCP server with SQLite + FTS + optional embeddings.<br/><br/>[![][anamnesis-shield]][anamnesis-github] | <picture><img src="https://raw.githubusercontent.com/Trapezohe/Anamnesis/main/banner.png" alt="Anamnesis" width="300" /></picture> |
| [**🖥️ Companion Service**][companion-github]<br/>Desktop runtime for the Ghast extension — local execution with permission policy, native browser pairing for Chrome / Brave / Edge, MCP host, and ACP session ingress.<br/><br/>[![][companion-shield]][companion-github] | <picture><img src="https://raw.githubusercontent.com/Trapezohe/companion_service/main/docs/assets/ghast-logo.png" alt="Companion" width="200" /></picture> |

### 📦 Ecosystem

| Repository | Purpose | Language |
| :--- | :--- | :---: |
| [**🔌 ghast-plugins**][ghast-plugins-github] | Plugin + MCP marketplace served to Ghast's in-app browser. Anthropic plugin-format compatible — Claude Code plugins drop in unchanged. | ![][lang-python] |
| [**📇 ghast-mcp-registry**][ghast-mcp-registry-github] | Curated MCP server directory rendered in Ghast → Settings → MCP → Marketplace. Edit `registry.json`, the in-app marketplace updates on next refresh. | ![][lang-json] |
| [**📖 Ghast_Doc**][ghast-doc-github] | VitePress source for the public documentation site at [docs.ghast.trapezohe.ai][ghast-website]. | ![][lang-vitepress] |

### 🏗️ How It Fits Together

```
                Ghast AI (desktop client)
                          │
       ┌──────────────────┼──────────────────┐
       │                  │                  │
   persists           resolves            runs through
       ▼                  ▼                  ▼
  ┌─────────┐    ┌─────────────────┐    ┌──────────────┐
  │Anamnesis│    │  ghast-plugins  │    │  companion_  │
  │         │    │ ghast-mcp-      │    │  service     │
  │ memory  │    │   registry      │    │              │
  │  layer  │    │ (marketplaces)  │    │ local agent  │
  │         │    │                 │    │   runtime    │
  └─────────┘    └─────────────────┘    └──────────────┘
       OSS              OSS                    OSS
```

Each open-source layer is also useful on its own — Anamnesis runs as a standalone Rust CLI and MCP server, `companion_service` ships as a local daemon any tool can pair with, and the marketplaces are plain GitHub-hosted JSON anyone can fork.

### 🤝 Contributing

We welcome PRs, plugin submissions, MCP server listings, and bug reports across every public repository.

- **Plugins** — see [ghast-plugins][ghast-plugins-github]; Anthropic-format plugins work as-is.
- **MCP servers** — open a `[Registry]` issue on [ghast-mcp-registry][ghast-mcp-registry-github] (or use the in-app submit button).
- **Memory** — Anamnesis adapters are crates; add one for a tool you use, the rest of the pipeline is shared.

<a href="https://next.ossinsight.io/analyze/Trapezohe#overview" target="_blank">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://next.ossinsight.io/widgets/official/compose-org-active-contributors/thumbnail.png?activity=active&period=past_90_days&owner_id=262958902&image_size=2x3&color_scheme=dark">
    <img src="https://next.ossinsight.io/widgets/official/compose-org-active-contributors/thumbnail.png?activity=active&period=past_90_days&owner_id=262958902&image_size=2x3&color_scheme=light">
  </picture>
</a>

### 🪪 License

Per-repository. Anamnesis is Apache-2.0; see individual repositories for the rest.

---

> \[!TIP]
>
> Help us make Trapezohe better. Product design feedback and user experience discussions are welcome via [Discord][discord-link] or directly on [GitHub Discussions][github-link].

<!-- LINK GROUP -->

[website-link]: https://ghast.trapezohe.ai
[website-shield]: https://img.shields.io/badge/website-ghast.trapezohe.ai-1da1f2?labelColor=black&style=flat-square&logo=safari&logoColor=white

[ghast-website]: https://ghast.trapezohe.ai
[ghast-website-shield]: https://img.shields.io/badge/download-ghast.trapezohe.ai-ffcb47?labelColor=black&style=flat-square&logo=apple&logoColor=white

[discord-link]: https://discord.gg/ghastai
[discord-shield]: https://img.shields.io/badge/discord-join-5865F2?labelColor=black&style=flat-square&logo=discord&logoColor=white

[github-link]: https://github.com/Trapezohe
[github-star]: https://img.shields.io/github/stars/Trapezohe?color=ffcb47&labelColor=black&style=flat-square&logo=github

[x-link]: https://x.com/Ghast_AI
[x-shield]: https://img.shields.io/badge/@Ghast__AI-follow-000000?labelColor=black&style=flat-square&logo=x&logoColor=white

[anamnesis-github]: https://github.com/Trapezohe/Anamnesis
[anamnesis-shield]: https://img.shields.io/github/stars/Trapezohe/Anamnesis?color=ffcb47&labelColor=black&style=flat-square&logo=github

[companion-github]: https://github.com/Trapezohe/companion_service
[companion-shield]: https://img.shields.io/github/stars/Trapezohe/companion_service?color=ffcb47&labelColor=black&style=flat-square&logo=github

[ghast-plugins-github]: https://github.com/Trapezohe/ghast-plugins
[ghast-mcp-registry-github]: https://github.com/Trapezohe/ghast-mcp-registry
[ghast-doc-github]: https://github.com/Trapezohe/Ghast_Doc

[lang-python]: https://img.shields.io/badge/python-3776AB?labelColor=black&style=flat-square&logo=python&logoColor=white
[lang-json]: https://img.shields.io/badge/json-000000?labelColor=black&style=flat-square&logo=json&logoColor=white
[lang-vitepress]: https://img.shields.io/badge/vitepress-1F1F1F?labelColor=black&style=flat-square&logo=vite&logoColor=yellow
