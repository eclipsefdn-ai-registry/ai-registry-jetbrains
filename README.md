# AI Registry — JetBrains (Inferred)

> **Inferred vendor repository.** This repo is maintained by the [AI Registry](https://github.com/eclipsefdn-ai-registry/ai-registry-core) project, not by JetBrains. It pre-seeds the registry with Agent Skills JetBrains publishes for its products, and with MCP servers JetBrains operates or ships.
>
> *This entry is based solely on information published through JetBrains' official public channels. JetBrains has not endorsed, approved or validated this listing, and is not necessarily participating in the AI Registry.*

## What this repo contains

Skill approvals scoped to skills that are actually attributed to JetBrains, not the wider third-party catalog JetBrains republishes:

- `debugging-code` and `refactoring-code` — the two skills in [JetBrains/skills](https://github.com/JetBrains/skills) whose frontmatter names JetBrains as author. That repo is a JetBrains-curated snapshot of 129 skills from 15 upstream sources (Anthropic, OpenAI, Vercel, Google, and others); its own README attribution table was used to exclude everything not authored by JetBrains.
- The four TeamCity skills in [JetBrains/teamcity-skills](https://github.com/JetBrains/teamcity-skills) (`teamcity-cli`, `teamcity-first-green-build`, `teamcity-intellij`, `migrate-to-teamcity`). They used to live in `JetBrains/teamcity-cli`, which removed its `skills/` directory on 2026-10-08 in favour of this repo, so that approval was dropped.
- Product skills from JetBrains' own product repos, each in the `JetBrains` org and each repo's root `skills/` being the published artifact: [rider-skills](https://github.com/JetBrains/rider-skills) (Rider debugging, navigation, refactoring, tests and Unreal Engine), [datalore-skills](https://github.com/JetBrains/datalore-skills) (Datalore notebooks), [phpstorm-claude-marketplace](https://github.com/JetBrains/phpstorm-claude-marketplace) (PhpStorm inspections and PHP upgrades; the content is not Claude-specific), [context](https://github.com/JetBrains/context) (the `jbcontext` CLI), plus single skills from [youtrack-apps](https://github.com/JetBrains/youtrack-apps) (`youtrack-apps-skill`), [klibs-io](https://github.com/JetBrains/klibs-io) (`kmp-libraries-expert`) and [youtrack-cli](https://github.com/JetBrains/youtrack-cli) (`.agents/skills/youtrack-cli`, which the README tells users to install).
- All skills under `skills/*` in [Kotlin/kotlin-agent-skills](https://github.com/Kotlin/kotlin-agent-skills) — hosted under the separate `Kotlin` GitHub org, but explicitly labeled with JetBrains' own "Incubator" project badge (see [github.com/JetBrains](https://github.com/JetBrains#jetbrains-on-github) for what that badge means) and each `SKILL.md` self-attributed to JetBrains. The Kotlin org's other agent-skills repo, `Kotlin/kotlin-backend-agent-skills`, carries no such badge and its skills are attributed to "Kotlin" rather than "JetBrains" in JetBrains' own catalog — it is deliberately excluded here for lack of a first-party JetBrains signal.

Each approval file uses glob or explicit multi-path source paths so newly published skills are picked up automatically on the next registry consolidation.

MCP approvals for:

- **JetBrains MCP Server** (`com.jetbrains/mcp-server`) — the MCP server bundled with IntelliJ-based IDEs (enabled by default since 2025.2). It isn't listed in the official Anthropic/modelcontextprotocol.io registry, so this approval supplies its own `metadata` (fallback name/description) and a generic `config` instead of relying on registry lookup — `mcpRegistryVerified` will read `false`, which the schema treats as a warning, not a blocker. The config is the officially published stdio connection (`npx -y @jetbrains/mcp-proxy`, from the `@jetbrains` npm scope), which JetBrains' own docs still point to as the way to wire up clients like Claude Desktop or VS Code that aren't auto-detected by the in-IDE setup flow — even though its original standalone GitHub repos (`JetBrains/mcp-jetbrains`, `JetBrains/mcp-server-plugin`) are archived/deprecated in favor of the bundled plugin. Marked `selfPublished: true` since the plugin (JetBrains Marketplace, verified publisher "JetBrains s.r.o.") and the npm package are both first-party JetBrains artifacts.

- **TeamCity MCP Plugin** (`com.jetbrains/teamcity-mcp`) and **YouTrack Remote MCP Server** (`com.jetbrains/youtrack-mcp`) — MCP servers built into a TeamCity server (2026.1+, plugin) and into every YouTrack site (2025.3+), documented on jetbrains.com. Neither is in the MCP registry, and both carry no `config`: the endpoint is on the user's own TeamCity or YouTrack host, which the config schema cannot express as a placeholder.
- **klibs.io MCP Server** (`io.klibs/mcp-server`) — the public, unauthenticated MCP endpoint of JetBrains' Kotlin Multiplatform library catalog, `https://api.klibs.io/mcp`.

No Agent Plugin approval is included: no agent-plugins.org-conformant plugin (`plugin.json` manifest) was found published by JetBrains.

## Documentation

See the [Vendor Guide](https://github.com/eclipsefdn-ai-registry/ai-registry-core#vendor-guide) in the central repository for how vendor repos work, how to add approvals, and how validation runs.
