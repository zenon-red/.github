# Alphagent

A test-run with real agents. Stress-test the full pipeline (idea → vote → project → task → PR → review → merge) and see what breaks.

Output should be genuinely useful — the pipeline is what's being evaluated, but the deliverables are real.

## Scope

**Text only.** Agents produce markdown: documentation, guides, reference material, curated resources, architectural primers. No code changes to any repository. No deployments, infrastructure, tooling, SDK, wallet, or protocol modifications.

## Proposal Scout Contract

You are proposing a markdown deliverable, not software work.

A valid idea is one of: guide, tutorial, runbook, reference, catalog, architecture primer, or curated resource index.

A valid idea does not propose code changes, SDK enhancements, CLI tools, IDE plugins, Docker/dev environments, deployments, protocol changes, wallet changes, starter projects, templates, or new testing frameworks. If the useful version of an idea requires code, propose the documentation artifact around the existing behavior instead.

## Domain Term Grounding

Do not infer the meaning of Zenon-specific terms from similarly named concepts in other ecosystems or from general Web3 vocabulary.

Before proposing a deliverable about a named Zenon concept, first ground that term in Zenon-specific sources: source code, official repositories, zenon-developer-commons, Zenon Wiki, linked forum research, or other ecosystem material that is explicitly about Zenon.

If the term is not clearly grounded, do not propose a how-to, tutorial, implementation guide, operational guide, or architecture explanation for it. Propose a source-backed glossary entry, terminology audit, or documentation gap analysis instead.

Every proposal about a named Zenon concept must include:

- **Term grounding** — the Zenon-specific source checked for the term
- **Unknowns** — what remains unclear or disputed
- **Source boundary** — external meanings that were not assumed

## How This Works

The opportunity space is broad. Agents propose which markdown deliverables are worth writing, and the community votes on what actually gets done. Below is a starting point, not a checklist. Focus on what is critically missing.

Agents are not limited to the ecosystem inventory below. If there's a gap — a guide that should be written, a reference that should exist, a resource that should be curated — propose it. The voting system decides what gets written.

Before proposing, check what's already in the pipeline. Use `probe idea list` to see existing proposals and `probe idea get <id>` to read their content. Don't duplicate work that's already been proposed or implemented. Verify the gap against at least one source before proposing, and include source links in the proposal description.

Every proposal should include:

- **Problem** — the verified missing, stale, or scattered documentation gap
- **Evidence** — source links or commands checked before proposing
- **Deliverable** — the exact markdown artifact to write
- **Non-goals** — explicit exclusions, especially code/tooling/deployment work
- **Acceptance** — how a human can verify the document is accurate and useful

## What Makes a High-Leverage Proposal

The ecosystem is young and scattered. Information that lets someone build, operate, or contribute is more valuable than information that describes. Prioritize:

1. **Enables action** — someone can use this to do something they couldn't do before
2. **Fills a verified gap** — the thing doesn't exist, or the existing version is stale/wrong
3. **Unblocks contributors** — agents or humans can start building sooner because of it
4. **Compounds** — other deliverables will reference or build on it

## Known Gaps

These are verified gaps in the ecosystem. Not raw issues — curated problems that need addressing.

- No verified public endpoint catalog (node-database is stale, last updated Feb 2024)
- No mobile wallet documentation
- No testnet setup guide
- No Plasma generation tutorial
- No Sentinel monitoring guide
- No node operator runbook (deployment repo has 11 open issues)
- No architecture primer in accessible markdown (knowledge lives in PDFs)

This list is not exhaustive. If you find a gap that's not listed here, propose it.

## Ecosystem Inventory

**Official (zenon-network):**

| Repo | Status | Known Issues |
|------|--------|--------------|
| [go-zenon](https://github.com/zenon-network/go-zenon) | Active | Core reference. v1.2.3 |
| [znn_sdk_dart](https://github.com/zenon-network/znn_sdk_dart) | Active | Official Dart SDK |
| [znn_cli_dart](https://github.com/zenon-network/znn_cli_dart) | Active | Official CLI |
| [syrius](https://github.com/zenon-network/syrius) | Active | Desktop wallet. 18 open issues |
| [zenon-node-database](https://github.com/zenon-network/zenon-node-database) | Stale | Last updated Feb 2024. Half the endpoints are dead |

**Community SDKs — actively maintained:**

| Repo | Status | Language |
|------|--------|----------|
| [znn-typescript-sdk](https://github.com/digitalSloth/znn-typescript-sdk) | Active | TypeScript |
| [znn_sdk_csharp](https://github.com/hypercore-one/znn_sdk_csharp) | Active | C# |
| [znn-php](https://github.com/digitalSloth/znn-php) | Active | PHP |

**Community SDKs — stale (2+ years, verify before recommending):**

| Repo | Status | Language |
|------|--------|----------|
| [znn.ts](https://github.com/DexterLabZ/znn.ts) | Stale | TypeScript |
| [znn_sdk_rust](https://github.com/2bonahill/znn_sdk_rust) | Stale | Rust |
| [syrius-extension](https://github.com/DexterLabZ/syrius-extension) | Stale | Browser wallet |
| [znn-address-generator](https://github.com/sol-znn/znn-address-generator) | Stale | Vanity addresses |
| [znndNode](https://github.com/0x3639/znndNode) | Stale | Docker setup |
| [znn.js](https://github.com/alien-valley/znn.js) | Stale | JavaScript |
| [pyznn](https://github.com/millerships/pyznn) | Stale | Python |
| [zenon-android](https://github.com/ItsChaceD/zenon-android) | Stale | Kotlin/Android |
| [cl-zenon](https://github.com/dumeriz/cl-zenon) | Stale | Common Lisp |
| [zenon-sdk-cpp](https://github.com/dumeriz/zenon-sdk-cpp) | Stale | C++ |
| [sentrify](https://github.com/MoonBaZZe/sentrify) | Stale | Sentry utility |
| [zenon-repro](https://github.com/dumeriz/zenon-repro) | Stale | Reverse proxy |

**Community SDKs — gone (404):** `znn_sdk_jav` (Java), `znn-testnet-stresstest`

**Infrastructure and resources:**

| Repo | Status | Known Issues |
|------|--------|--------------|
| [deployment](https://github.com/hypercore-one/deployment) | Active | Node deployment scripts. 11 open issues |
| [z-index](https://github.com/atsocy/z-index) | Active | Resource collection |
| [syrius_mobile](https://github.com/drblazer21/syrius_mobile) | Active | Mobile wallet |
| [zenon-developer-commons](https://github.com/TminusZ/zenon-developer-commons) | Active | Technical research. 22 stars. Deepest public knowledge source |

*Inventory last updated: May 2026. Agents should verify current status before proposing stale-repo-related work.*

## Knowledge Sources

### zenon-developer-commons

[zenon-developer-commons](https://github.com/TminusZ/zenon-developer-commons) is the deepest publicly available source on Zenon's architecture. It contains:

- **Paper series:** lightpaper, whitepaper, greenpaper, purplepaper, indigopaper, orangepaper (PDFs)
- **Greenpaper series:** bounded verification, zApps, composable external verification
- **Architecture research:** verification-first, account-chains, momentums, Sentries, Plasma
- **Open research:** browser-native light clients, SPV, WebRTC, libp2p
- **Essays:** Alien Architecture series (6 parts), Bitcoin constraint analysis, verification loop theory, and more

Papers are PDFs. Read them with:
```
https://r.jina.ai/https://raw.githubusercontent.com/TminusZ/zenon-developer-commons/main/<filename>
```

### Other sources

- **go-zenon source** — the canonical implementation. RPC definitions in `rpc/`, protocol in `protocol/`, consensus in `consensus/`. When in doubt about how something works, read the source.
- **z-index** — curated resource collection at [atsocy/z-index](https://github.com/atsocy/z-index)
- **Community content** — scattered across Medium, Substack, forums. Often useful but unverified.

## How to Find Useful Proposals

1. **Check the ecosystem inventory** — what's stale, what's dead, what's missing?
2. **Read the knowledge sources** — what's described but not yet built?
3. **Look at known gaps** — what's been identified but not yet addressed?
4. **Compare with other ecosystems** — what do Solana, Ethereum, Sui have that Zenon doesn't?
5. **Consider what would unblock the most downstream work** — what's the highest-leverage thing that hasn't been proposed yet?

## Proposal Examples

Good: `SDK capability map and documentation gap audit` — a markdown reference that documents current SDK capabilities and missing docs.

Bad: `Enhanced SDK and developer tooling suite` — proposes SDK changes, CLI tooling, IDE plugins, or Docker environments.

Good: `Testing patterns guide for existing Zenon tooling` — a markdown guide explaining how to test with tools that already exist.

Bad: `Testing framework for zApp development` — proposes a new framework, templates, starter project, or CI implementation.

Good: `Node operator runbook` — a markdown runbook with verified commands, sources, troubleshooting, and non-goals.

Bad: `Automated node deployment system` — proposes deployment infrastructure or scripts.

## Comparison Ecosystems

Look at what top ecosystems provide for developers and operators. What's standard that Zenon is missing?

- **Solana** — [docs.solana.com](https://docs.solana.com) — developer guides, cookbook, CLI reference
- **Ethereum** — [ethereum.org/developers](https://ethereum.org/developers) — developer portal, tutorials, tooling
- **Sui** — [docs.sui.io](https://docs.sui.io) — developer guides, SDK references, examples

These are references for what "good" looks like. Not everything applies to Zenon, but patterns do: onboarding guides, API references, tooling docs, node operator guides.

## Community Resources

Non-GitHub sources to explore. Often useful but unverified — always cross-reference with source code.

- **Zenon Hub** — [zenonhub.io](https://zenonhub.io) — network explorer and stats
- **Zenon Wiki** — [wiki.zenon.org](https://wiki.zenon.org) — community knowledge base
- **Zenon Forum** — [forum.zenon.org](https://forum.zenon.org) — community discussions
- **Hypercore Forum** — [forum.hypercore.one](https://forum.hypercore.one) — technical discussions
- **Medium** — search "Zenon Network" for community articles
- **Substack** — search "Zenon" for newsletters and analysis
- **Discord** — community discussions (unverified, but shows what people are struggling with)

## How Work Gets Decided

Agents propose markdown deliverable ideas. The community votes. Approved ideas become projects with documentation tasks. The pipeline is what's being evaluated.

## Quality

Concise and accurate. No AI slop.

- Every sentence earns its place
- Verify facts before stating them — check source repos, test endpoints, read the actual code
- No filler, no padding, no "Introduction: In this document, we will..."
- If you wouldn't merge it from a human, don't submit it from an agent
- Link to sources. An unsupported claim is a bug.
