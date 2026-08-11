# AI Registry — JetBrains (Inferred)

> **Inferred vendor repository.** This repo is maintained by the [AI Registry](https://github.com/eclipsefdn-ai-registry/ai-registry-core) project, not by JetBrains. It pre-seeds the registry with Agent Skills published by JetBrains at [github.com/JetBrains/skills](https://github.com/JetBrains/skills), [github.com/JetBrains/teamcity-cli](https://github.com/JetBrains/teamcity-cli), and [github.com/Kotlin/kotlin-agent-skills](https://github.com/Kotlin/kotlin-agent-skills).
>
> *This entry is based solely on information published through JetBrains' official public channels. JetBrains has not endorsed, approved or validated this listing, and is not necessarily participating in the AI Registry.*

## What this repo contains

Skill approvals scoped to skills that are actually attributed to JetBrains, not the wider third-party catalog JetBrains republishes:

- `debugging-code` and `refactoring-code` — the two skills in [JetBrains/skills](https://github.com/JetBrains/skills) whose frontmatter names JetBrains as author. That repo is a JetBrains-curated snapshot of 129 skills from 15 upstream sources (Anthropic, OpenAI, Vercel, Google, and others); its own README attribution table was used to exclude everything not authored by JetBrains.
- All skills under `skills/*` in [JetBrains/teamcity-cli](https://github.com/JetBrains/teamcity-cli) (e.g. `teamcity-cli`, `migrate-to-teamcity`) — official JetBrains GitHub org repo, each `SKILL.md` self-attributed to JetBrains.
- All skills under `skills/*` in [Kotlin/kotlin-agent-skills](https://github.com/Kotlin/kotlin-agent-skills) — hosted under the separate `Kotlin` GitHub org, but explicitly labeled with JetBrains' own "Incubator" project badge (see [github.com/JetBrains](https://github.com/JetBrains#jetbrains-on-github) for what that badge means) and each `SKILL.md` self-attributed to JetBrains. The Kotlin org's other agent-skills repo, `Kotlin/kotlin-backend-agent-skills`, carries no such badge and its skills are attributed to "Kotlin" rather than "JetBrains" in JetBrains' own catalog — it is deliberately excluded here for lack of a first-party JetBrains signal.

Each approval file uses glob or explicit multi-path source paths so newly published skills are picked up automatically on the next registry consolidation.

No MCP server or Agent Plugin approval is included: JetBrains' current MCP offering is a closed-source, bundled IDE plugin (no public source repo to point a `serverId`/source at — its standalone predecessor repos, `JetBrains/mcp-jetbrains` and `JetBrains/mcp-server-plugin`, are both deprecated), and no agent-plugins.org-conformant plugin (`plugin.json` manifest) was found published by JetBrains.

## Documentation

See the [Vendor Guide](https://github.com/eclipsefdn-ai-registry/ai-registry-core#vendor-guide) in the central repository for how vendor repos work, how to add approvals, and how validation runs.
