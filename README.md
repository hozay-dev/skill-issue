# jmo-skills

The agent skills from my hackathon workflow.

This repo contains the two skills I made and use at the start of projects:

- `interview` asks detailed, useful questions and turns the answers into a written spec that the agent can follow.
- `ste` rewrites technical explanations in clear, precise language when an agent starts speaking in jargon.

## Install

Install both skills:

```bash
npx skills add 23jmo/jmo-skills
```

Or install one:

```bash
npx skills add 23jmo/jmo-skills --skill interview
npx skills add 23jmo/jmo-skills --skill ste
```

Restart your coding agent after installation so it discovers the new skills.

## Other skills from the video

These are open-source skills and tools made by other creators. Install them from their original repositories so you get the current version and the correct supporting files.

| Skill | What I use it for | Source |
| --- | --- | --- |
| `better-ui` | Auditing and polishing an interface | [jakubkrehel/skills](https://github.com/jakubkrehel/skills/tree/main/skills/better-ui) |
| `animate` | Applying strong motion-design principles | [emilkowalski/skills](https://github.com/emilkowalski/skills/tree/main/skills/animate) |
| `agentation` | Attaching visual feedback to exact elements on a page | [benjitaylor/agentation](https://github.com/benjitaylor/agentation/tree/main/skills/agentation) |
| `codex` | Asking Codex for an independent review or technical second opinion | [garrytan/gstack](https://github.com/garrytan/gstack/tree/main/codex) |

## Notes

`ste` is a practical writing guide inspired by the goals of Standard Technical English. It does not claim formal ASD-STE100 compliance.

## License

The original `interview` and `ste` skills in this repository are available under the MIT License.
