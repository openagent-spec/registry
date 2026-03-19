<p align="center">
  <h1 align="center">🤖 OpenAgent Registry</h1>
  <p align="center">Community-curated directory of AI agents. Like Homebrew taps, but for agents.</p>
</p>

<p align="center">
  <a href="https://github.com/openagent-spec/spec">Spec</a> ·
  <a href="#agents">Browse Agents</a> ·
  <a href="#publish-your-agent">Publish Yours</a>
</p>

---

## Agents

**60 agents** across **15 categories** — each representing a real role, not a micro-skill.

| Category | Agents | Highlights |
|----------|--------|------------|
| 🎯 **[Marketing](agents/marketing)** | 7 | CRO Optimizer, Conversion Copywriter, SEO Architect, Paid Growth, GTM Strategy, China & Global Social |
| 💻 **[Engineering](agents/engineering)** | 5 | Full-Stack, Platform, Security, Software Architect + Embedded Firmware |
| 🎨 **[Design](agents/design)** | 2 | UX Product Designer, Visual Creative |
| 🤝 **[Sales](agents/sales)** | 1 | Full-cycle B2B Sales Leader |
| 🎯 **[Product](agents/product)** | 1 | Product Leader |
| 📋 **[Project Management](agents/project-management)** | 1 | Project Leader |
| 🧪 **[Testing](agents/testing)** | 1 | QA Engineer |
| 📊 **[Support](agents/support)** | 1 | Operations Analyst |
| 🥽 **[Spatial Computing](agents/spatial-computing)** | 1 | Spatial Computing Engineer |
| 🎮 **[Game Development](agents/game-development)** | 1 | Game Developer |
| 📚 **[Academic](agents/academic)** | 1 | Academic Researcher |
| ⚙️ **[GStack](agents/gstack)** | 11 | Browser QA, Ship, Review, Retro workflows |
| 🔧 **[Specialized](agents/specialized)** | 25 | Salesforce, MCP Builder, Recruitment, Compliance, and more |
| ⚙️ **[Rust Proxy Expert](agents/rust-proxy-expert)** | 1 | Rust reverse proxy & high-performance networking |
| 🧠 **[A2ABench](agents/a2abench)** | 1 | Agent-to-Agent benchmark |

## Quick Start

```bash
# Install an agent
openagent install marketing/cro-optimizer

# List available agents
openagent list
```

## Publish Your Agent

1. **Fork** this repo
2. **Create** `agents/<category>/<your-agent-id>/` with the required files
3. **Open a PR** — CI will validate your `agent.yaml`
4. Once **merged**, your agent is available to everyone

### Required Files

```
agents/<category>/<agent-id>/
├── agent.yaml          # Agent manifest (see spec)
├── SOUL.md             # Personality & expertise
└── AGENTS.md           # Work instructions
```

### Optional Files

```
├── IDENTITY.md         # Visual identity (name, emoji, avatar)
├── experience/         # Experience packs
│   ├── index.yaml
│   └── *.md
└── README.md           # Marketplace description
```

### Example `agent.yaml`

```yaml
id: marketing-cro-optimizer
name: CRO Optimizer
version: 1.0.0
description: >-
  Full-funnel conversion rate optimization expert — audits pages,
  signup flows, onboarding, forms, popups, paywalls, and designs
  A/B tests to validate improvements.
emoji: "📈"
author: openagent-community
license: MIT

persona:
  style: "Systematic, data-driven conversion optimization."
  tone: "analytical, actionable, evidence-based"
  language: ["en"]
  principles:
    - "Every recommendation must be testable"
    - "Reduce friction before adding persuasion"
    - "Data over opinions"

adapters:
  frameworks:
    - name: openclaw
      native: true

model:
  minimum: sonnet

collaboration:
  can_receive: true

marketplace:
  category: marketing
  tags: ["marketing", "cro", "conversion", "ab-testing"]
  pricing:
    model: free
```

> 📖 Full schema: [openagent-spec/spec](https://github.com/openagent-spec/spec)

## Design Philosophy

> **One agent = one role you'd actually hire.**

We don't create an agent for every micro-skill. A "Popup Optimizer" or "Schema Markup Expert" isn't a role — it's a sub-skill. Instead:

- `cro-optimizer` covers pages, signup flows, onboarding, forms, popups, paywalls, and A/B testing
- `full-stack-engineer` covers frontend, backend, mobile, and prototyping
- `sales-leader` covers outbound, discovery, deals, pipeline, proposals, and coaching

Each agent's `SOUL.md` contains deep expertise across all its sub-domains.

## Custom Registry

Point your agent runtime at any GitHub repo as a custom registry:

```yaml
# ~/.openagent/config.yaml
registries:
  - name: "my-agents"
    type: "github"
    repo: "username/my-agents"
```

## Contributing

PRs welcome! Please follow the [OpenAgent Spec](https://github.com/openagent-spec/spec) and ensure your agent represents a meaningful role, not a narrow skill.

## License

MIT
