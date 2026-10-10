# jmo-skills

The skills from my hackathon workflow, packaged for Claude Code and other coding agents.

## Install in Claude Code

Run these in your terminal:

```sh
claude plugin marketplace add 23jmo/jmo-skills
claude plugin install jmo-workflow@jmo-skills
```

Restart Claude Code after installing. The plugin provides:

| Command | What it does | Creator |
| --- | --- | --- |
| `/jmo-workflow:interview` | Interview you about a project and save an implementation spec in `.plans/` | Johnathan Mo |
| `/jmo-workflow:ste` | Explain technical ideas in clear, precise language | Johnathan Mo |
| `/jmo-workflow:better-ui` | Polish interface surfaces, icons, and motion | [Jakub Krehel](https://github.com/jakubkrehel/skills/tree/main/skills/better-ui) |
| `/jmo-workflow:animate` | Build purposeful interface animations | [Emil Kowalski](https://github.com/emilkowalski/skills/tree/main/skills/animate) |
| `/jmo-workflow:agentation` | Set up visual feedback attached to page elements | [Benji Taylor](https://github.com/benjitaylor/agentation/tree/main/skills/agentation) |
| `/jmo-workflow:codex` | Hand off an implementation, review, or second opinion to the Codex CLI | Johnathan Mo; standalone wrapper |

The original `/codex` reference from the video is [gstack by Garry Tan](https://github.com/garrytan/gstack/tree/main/codex). It depends on the larger gstack installation. This plugin includes a new, portable handoff skill instead; for gstack's exact review/challenge/consult workflow, follow [its installation guide](https://github.com/garrytan/gstack#install--about-30-seconds).

Codex handoffs require the [Codex CLI](https://developers.openai.com/codex/cli/) installed and signed in. Agentation setup installs its application package in your project; live feedback additionally requires its MCP server. Those runtimes and account access are not included in the plugin.

## Install individual skills in other agents

```sh
npx skills add 23jmo/jmo-skills
```

Or select individual skills:

```sh
npx skills add 23jmo/jmo-skills --skill interview
npx skills add 23jmo/jmo-skills --skill ste
```

Restart your agent after installation. Claude's plugin commands are namespaced; individual skill installs typically use the short names shown in the video. You only need one installation method per agent.

## Optional MCP connections

Install only the services your project uses:

```sh
claude plugin install jmo-supabase@jmo-skills
claude plugin install jmo-neon@jmo-skills
claude plugin install jmo-stripe@jmo-skills
```

Restart Claude Code and run `/mcp` to authenticate each installed service with your own account. These plugins contain public server URLs, not credentials. Use development projects and Stripe sandboxes for hackathon work. Installing a plugin does not create a database, Stripe account, or subscription.

Provider setup and permissions: [Supabase](https://supabase.com/docs/guides/ai-tools/mcp), [Neon](https://neon.com/guides/neon-mcp-server-github-copilot-vs-code), [Stripe](https://docs.stripe.com/mcp).

## Other tools from the video

- [Superset](https://superset.sh/) — workspace for managing coding agents and worktrees.
- [Wispr Flow](https://ref.wisprflow.ai/johnathan-mo-yt) — my creator link for one month of Flow Pro.

## Credits and licenses

My `interview`, `ste`, and standalone `codex` skills, plugin manifests, and documentation are [MIT licensed](LICENSE). `ste` is a practical writing guide; it does not claim formal ASD-STE100 compliance.

The bundled `better-ui` and `animate` directories are unchanged upstream snapshots with their MIT licenses included. `agentation` is distributed under its own **PolyForm Shield 1.0.0** license, included in its directory; it is not covered by this repository's MIT license. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and [UPSTREAM.json](UPSTREAM.json) for attribution and pinned source revisions.

Related skills named in upstream guidance (such as `review-animations` or `better-typography`) are separate optional skills available from those creators, not commands bundled here.

## Validate locally

```sh
claude plugin validate --strict .claude-plugin/plugin.json
claude plugin validate --strict .claude-plugin/marketplace.json
claude plugin validate skills
claude plugin validate --strict plugins/jmo-supabase
claude plugin validate --strict plugins/jmo-neon
claude plugin validate --strict plugins/jmo-stripe
```
