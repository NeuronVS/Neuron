<div align="center">

# Welcome to Neuron.

<div align="center">
	<img
		src="./cube.png"
	 	alt="Void Welcome"
		width="300"
	 	height="300"
	/>
</div>

### The AI code editor that actually remembers your codebase.

**Neuron vs. Cursor vs. Windsurf — persistent memory, AST intelligence, and one-click deploy without the credit-counting.**

[Download Latest Release](#download) · [Report a Bug](../../issues) · [Request a Feature](../../issues)

</div>

---

## Why developers are looking past Cursor and Windsurf

Cursor and Windsurf are both excellent editors, and both have converged on $20/mo Pro pricing and similar agent capabilities in 2026. But neither solves the problem that actually slows teams down: **AI assistants that forget everything the moment a session ends.**

Neuron is built around a different idea — memory should be a first-class system, not a side effect of a large context window.

- 🧬 **Persistent Memory** — Neuron remembers your codebase, your decisions, and your architecture across sessions. Not "Memories" as a feature bolt-on — a full episodic/semantic/procedural memory graph.
- 🌳 **Real AST Indexing** — Tree-sitter powered code intelligence: call graphs, type hierarchies, and impact prediction, not just embeddings or keyword search.
- 🚀 **One-Click Deploy & Test** — Spin up a local preview or deploy straight from the IDE.
- 📚 **Live Framework Docs** — Auto-fetches current docs for your stack so the AI isn't limited to stale training data.
- 🔑 **True BYOK** — Use your own API keys or local models for free, forever. No quotas, no credit math.
- 🔒 **Local-First** — Your code and your index never have to leave your machine.

---

## Neuron vs. Cursor vs. Windsurf

| | **Neuron** | **Cursor** | **Windsurf** |
|---|---|---|---|
| Persistent memory across sessions | ✅ Full memory graph (episodic/semantic/procedural) | ❌ No | ⚠️ "Memories" — limited, session-scoped |
| AST-level code intelligence | ✅ Tree-sitter, call graphs, impact prediction | ⚠️ Limited | ⚠️ Limited | 
| One-click deploy from IDE | ✅ Brewing | ❌ No | ⚠️ Cloud sessions only (Devin handoff) |
| Auto-fetched framework docs | ✅ Yes | ❌ No | ❌ No |
| Bring your own API key | ✅ Yes, free forever + OpenRouter FREE | ✅ Yes | ❌ Not supported |
| Free Tier | 
| Pricing model | Free (BYOK) or flat $5–$40/seat | Flat-rate, $20-$60/mo Pro | Quota-based, $20-200/mo Pro (daily/weekly limits) |
| Team tier | $30-$60/seat/mo | $40-$120/seat/mo | $60/team+$40/seat/mo |
| IDE coverage | Full VS Code extension support | Standalone editor only | 40+ IDEs (VS Code, JetBrains, Vim, Xcode) |
| Index portability | ✅ Stored in-repo (`.neuron` folder), travels with your project | ❌ No | ❌ No |
| Closed-source, no enterprise license enforcement | ✅ Honor-system licensing | ❌ Commercial license required | ❌ Commercial license required |

---

## How Neuron's memory is different

Cursor has no persistent memory system — context resets between sessions. Windsurf's "Memories" feature helps Cascade recall some prior context, but it isn't a structured, queryable system.

Neuron treats memory as infrastructure:

1. **Working memory** — what you're actively doing this session.
2. **Long-term memory graph** — episodic (what happened), semantic (what's true about your codebase), procedural (how your team works) — persisted indefinitely.
3. **Project-local index** — memory and AST data live in a `.neuron` folder inside your repo. Clone the project, and your teammates inherit the full index automatically. No cloud sync, no separate infrastructure.

The result: ask Neuron *"why did we structure auth this way?"* months later, and it knows — without you re-explaining anything.

---

## Pricing comparison

### Free tier, side by side

This is where the gap is widest. Most "free" AI IDE tiers are designed to run out fast.

| | **Neuron Free** | **Cursor Free** | **Windsurf Free** |
|---|---|---|---|
| Autocomplete / Tab | ✅ Unlimited | ⚠️ Limited | ✅ Unlimited |
| AI requests | **500/month** | Limited free requests | 25 prompt credits |
| Refresh cycle | Monthly, no daily/weekly cap | Monthly pool | Daily/weekly quota (resets, can't bank usage) |
| Time to exhaustion (active use) | Days of real development | Hours to a day | ~1–2 days |
| Memory / indexing on free tier | ✅ Full Engram memory + AST indexing | ❌ N/A | ⚠️ Limited |
| BYOK on free tier | ✅ Yes — unlimited, no quota at all | ✅ Yes | ❌ Not supported |

The practical difference: Windsurf's quota system resets daily/weekly, so you can't save up usage for a big task — a single large Cascade session can burn a meaningful chunk of your weekly allocation. Neuron's 500 free requests are a flat monthly pool with no daily ceiling, so you can front-load a big refactor one day and go quiet the next without losing anything. And if you bring your own API key on Neuron, there's no request cap at all — free tier or not.

### Paid Plan

| Plan | Neuron | Cursor | Windsurf |
|---|---|---|---|
| Entry paid | $5/mo 
| Mid tier | $10/mo | $20/mo | $20/mo |
| Team | $40/seat/mo | $40/seat/mo | $40/seat/mo |
| Top tier | BYOK  | $200/mo (Ultra) | $200/mo (Max) |

Neuron's BYOK tier has no usage quotas or credit math — if you bring your own key or run a local model, it's free indefinitely.

---

## Core features

### 🌳 AST-powered code intelligence
Real parsed syntax trees via tree-sitter — functions, classes, types, imports, exports, and call sites across your whole project, with the ability to predict the blast radius of a change before you make it.

### 🚀 One-click deploy & preview
Hit deploy and Neuron spins up a local server instantly. Ship to your preferred host when ready — no Docker or manual setup required.

### 📚 Always-current framework knowledge
Working in Laravel, Tailwind, or Livewire? Neuron fetches and indexes the latest framework docs locally so the AI isn't limited to its training cutoff.

### 🧭 Visual agent workflows *(coming soon)*
Design multi-agent pipelines visually — planner, builder, reviewer — and watch them hand off tasks to each other automatically.

### 🔑 Your model, your rules
Plug in OpenAI, Anthropic, local models via Ollama, or anything OpenAI-compatible.

---

## Download

This repository hosts releases and tracks issues for Neuron. The full source is closed and maintained by the Neuron team.

👉 **[Download the latest release](../../releases/latest)**

Found a bug or have a feature request? **[Open an issue](../../issues/new)** — we read everything.

---

## Engram — The Memory System

The core innovation. A biologically-inspired three-tier memory architecture spanning 30+ Rust modules.

### Three Tiers

| Tier | Name | What it stores | Lifetime |
|------|------|---------------|----------|
| **0** | Sensory Buffer | Raw input from current turn — messages, tool results, recalled memories | Single turn (ring buffer, configurable; default 5 entries) |
| **1** | Working Memory | Active context — priority-evicted slots with token budgets (derived from the model's context window: ~10%, clamped 2,048–32,768 tokens) | Current session |
| **2** | Long-Term Memory Graph | Persistent knowledge across sessions — episodic, semantic, procedural | Permanent (with decay) |

### Long-Term Memory Graph

Three interconnected stores with typed graph edges:

- **Episodic** — "what happened." Conversations, events, results. Each memory has an importance score, strength (decays via Ebbinghaus curve), scope, and optional vector embedding.
- **Semantic** — "what is true." Subject-predicate-object triples. `("Project", "uses", "Rust + TypeScript")`. Auto-reconsolidated when facts update.
- **Procedural** — "how to do things." Step-by-step procedures with trigger conditions and success/failure tracking.

### Advanced Retrieval Pipeline

Not just keyword search. A four-stage pipeline:

1. **Gating** — classifies each query into one of five actions (Skip / Retrieve / DeepRetrieve / Refuse / Defer) so trivial queries skip the search entirely. Inspired by CRAG.
2. **Hybrid Search** — BM25 full-text + vector semantic search across all three stores simultaneously.
3. **Reranking** — Reciprocal Rank Fusion (RRF, k=60), Maximal Marginal Relevance (MMR), cross-type deduplication.
4. **Quality Gating** — NDCG scoring, CRAG 3-tier classification (Correct / Ambiguous / Incorrect). Every search returns quality metrics.

### Consolidation & Decay

Runs automatically every 5 minutes:
- **Pattern clustering** — extracts semantic patterns from episodic memories
- **Contradiction detection** — finds and resolves conflicting knowledge
- **FadeMem dual-layer decay** — LML (beta=0.8) / SML (beta=1.2) Ebbinghaus forgetting curves
- **Garbage collection** — with transactional savepoint rollback to prevent quality degradation
- **Memory fusion** — merges memories with cosine similarity >= 0.75, creates tombstones for superseded entries

### Dream Replay

Hippocampal-inspired background process. When the application is idle, Engram re-embeds memories, discovers new connections, and strengthens important recall pathways.

### Cognitive Modules

- **Emotional Memory** — affective scoring (valence, arousal, dominance) with flashbulb encoding for high-importance events
- **Meta-Cognition** — knowledge confidence mapping and self-reflection
- **Intent Classifier** — 6-intent query routing
- **Entity Tracker** — canonical name resolution across memories
- **Abstraction Tree** — 4-level hierarchical semantic compression for context window packing
- **Memory Bus** — pub/sub event bus with scoped read capabilities for cross-component memory sync

---

## The Engine

Neuron owns its agent engine end-to-end — a Rust-native AI agent runtime living in `crates/Neuron-engine/` alongside the IDE.

### Agent Loop

The core execution cycle:
1. **Assemble context** — budget-aware prompt assembly (system prompt capped at 45% of context, history at 35% minimum, reply tokens reserved)
2. **Send to model** — stream through the provider abstraction
3. **Execute tools** — dispatch tool calls through the sandbox
4. **Repeat** — until final response or max rounds

Built-in safety:
- **Tool circuit breaker** — tracks consecutive failures per tool, injects nudges after 3, blocks after 5
- **Repetition detector** — hashes tool call signatures, detects and breaks loops
- **Yield signaling** — graceful interruption when user sends a new message mid-turn
- **Token budget enforcement** — context window never exceeded, budget-aware at every stage

### Configurable Agent Profiles

Each agent in Neuron is a profile you can configure independently — its own model, system prompt, capability set, and **specialty** drawn from a fixed taxonomy: `coder`, `researcher`, `designer`, `communicator`, `security`, `general`. The model-routing layer resolves per-agent, per-specialty overrides through a 5-level fallback hierarchy.

You switch agents from the chat panel; one agent runs at a time. (Boss/worker orchestration with goal decomposition and automatic delegation is on the roadmap, not in the current build.)

### 10 AI Providers

| Provider | Implementation |
|----------|---------------|
| Anthropic | Native Messages API |
| Google | Native Gemini API |
| OpenAI | Native API |
| DeepSeek | OpenAI-compatible |
| Moonshot (Kimi) | OpenAI-compatible |
| xAI (Grok) | OpenAI-compatible |
| Mistral | OpenAI-compatible |
| OpenRouter | OpenAI-compatible |
| Ollama | Local models, OpenAI-compatible |
| Custom | Any OpenAI-compatible endpoint |

Every provider implements the `AiProvider` trait — streaming, tool use, thinking/reasoning tokens, model capability detection. Model routing resolves per-agent overrides, falling back through a 5-level hierarchy.

### MCP Server Support

Full Model Context Protocol integration:
- **Stdio transport** — spawns MCP servers as child processes
- **SSE transport** — HTTP long-polling for remote servers
- Tool discovery, invocation, and result validation
- Multi-server lifecycle management with health monitoring

---

## AST Indexing

Tree-sitter powered code intelligence. Not grep. Not regex. Actual parsed ASTs.

### Supported Languages

Full tree-sitter parsing: **TypeScript, JavaScript, TSX, JSX, Rust, Python, Go, C, C++, Java, Ruby, CSS, JSON**
Typed AST parsing: **Solidity** (via solang-parser)
Regex extraction: **Move, COBOL, Fortran**

### What Gets Indexed

Every file produces a `FileIndex`:
- **Symbols** — functions, classes, types, traits, interfaces
- **Imports** — local and external dependencies
- **Exports** — public API surface
- **Call sites** — who calls whom, with position data
- **Type references** — type hierarchies and usage
- **Scopes** — lexical scope information

These roll up into a `ProjectIndex` with a full dependency graph, framework detection, entry point identification, and config file tracking.

### Agent Tools

The agent queries the index directly:

| Tool | What it does |
|------|-------------|
| `ast_callers` | Find every caller of a function across the entire codebase |
| `ast_callees` | Trace what a function calls |
| `ast_impact` | Predict what breaks if you change something |
| `ast_definition` | Jump to definition |
| `ast_type_info` | Understand type hierarchies |
| `search_semantic` | Find code by meaning (embedding-based) |
| `search_text` | Find code by keyword |

The agent understands your codebase structure without reading every file. It knows call graphs, impact radius, and type relationships before it writes a single line.

---

## 10-Layer Security

Security is not a feature — it's the architecture.

| Layer | What it does |
|-------|-------------|
| **1. Rust type system** | No null pointers, no data races, no use-after-free. Compile-time guarantees. |
| **2. Memory encryption** | PII detected via 17 regex patterns + LLM classification. Three tiers: Cleartext, Sensitive (AES-256-GCM + searchable summary), Confidential (fully encrypted, vector-only search). |
| **3. Sandbox enforcement** | All file operations forced through QuickJS sandbox with HostApi trait. No raw filesystem access from agent. |
| **4. Tool circuit breaker** | Blocks tools after 5 consecutive failures. Prevents infinite loops and resource exhaustion. |
| **5. MCP isolation** | External MCP servers run in separate processes. Tool results validated before injection. |
| **6. Keychain integration** | API keys stored in OS keychain (macOS Keychain, Linux secret-service). Single unlock, encrypted at rest. |
| **7. Token budget enforcement** | Context window never exceeded. Prevents context overflow attacks. |
| **8. GDPR compliance** | Automatic PII tier escalation, key rotation with re-encryption, memory purge capabilities. |
| **9. Audit trail** | Every operation logged — agent actions, tool calls, memory access, security decisions. Queryable history. |
| **10. Secure deletion** | When memories are purged (GC, fusion, or GDPR right-to-erasure), content fields are overwritten with zeros before the row is deleted, so recovered DB pages don't yield plaintext. |

---

## The Sandbox

The agent executes code in a **QuickJS** (rquickjs) sandbox with a controlled `HostApi`:

```js
function run(ctx) {
  var src = ctx.file_read("src/app.ts");
  src = src.replace("oldFunction", "newFunction");
  ctx.file_write("src/app.ts", src);
  var result = ctx.exec("npm test");
  return { success: result.exit_code === 0 };
}
```

The `ctx` object exposes: `file_read`, `file_write`, `list_dir`, `exec`, `git_status`, `git_diff`, `git_log`, `git_branches`, `search`, `diagnostics`, `selection`, `open_files`.

No raw filesystem access. No network access. No child process spawning outside the HostApi. The host controls exactly what the agent can do.

---


## FAQ

**Is Neuron a fork of Cursor or Windsurf?**
No. Neuron is built on a different foundation and adds persistent memory, AST indexing, and deployment tooling that neither Cursor nor Windsurf currently offer.

**How is Neuron's memory different from Windsurf's "Memories" feature?**
Windsurf's Memories help Cascade recall some context across sessions, but it isn't a structured system. Neuron maintains a full memory graph — episodic, semantic, and procedural — that's queryable and persists indefinitely.

**Does Neuron use quotas or credits like Windsurf?**
No. BYOK usage on Neuron has no quotas or credit consumption. Paid tiers are flat monthly pricing.

**Can my team share an index?**
Yes — the `.neuron` index folder lives in your project. Cloning the repo shares the index automatically.

**Is my code sent anywhere?**
Only if you choose a hosted model provider. With BYOK or local models, everything stays on your machine.

---

<div align="center">

**[⬇ Download Neuron](../../releases/latest)** · **[🐛 Report an Issue](../../issues/new)**

</div>

**[⬇ Download Neuron](../../releases/latest)** · **[🐛 Report an Issue](../../issues/new)**

</div>

