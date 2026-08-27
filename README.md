# Vlad — Final Boss

![Vlad — Final Boss](assets/vlad-final-boss.png)

An adversarial handoff gate for AI agents. Vlad audits every “done,” “tested,”
“merged,” and “deployed” claim by demanding a fresh receipt from the layer the user
actually experiences.

Vlad does not make the work. Vlad decides whether the work has earned a handoff.

## Install

In Codex, ask the built-in installer to install this GitHub repository:

```text
$skill-installer https://github.com/justinfowler925/vlad-final-boss
```

Or clone it into the user-level skills directory documented by OpenAI:

```bash
git clone https://github.com/justinfowler925/vlad-final-boss.git ~/.agents/skills/vlad-final-boss
```

Codex discovers skills in `~/.agents/skills` automatically. If it does not appear,
restart Codex. See the [official skill documentation](https://developers.openai.com/codex/skills).

For a repository-scoped installation, clone or copy the directory to
`.agents/skills/vlad-final-boss` in that repository.

## Use

```text
$vlad-final-boss audit the completion claims in this handoff.
```

Useful variants:

- `Vlad: PR #42`
- `Vlad offline`
- `Vlad re-verify`
- `Vlad fix F2`

The default audit is read-only. Fix mode requires explicit authorization.

## Verdicts

- `PASS` — every scoped claim has a fresh independent receipt.
- `FAIL` — a receipt is missing or contradicted.
- `UNSURE` — the unresolved measurement is named; no result is invented.

## Why the character?

“Did you check it?” can sound like distrust. Vlad means it as a discipline: do not
trust assumed state; inspect the thing itself. The image is deliberately theatrical
and entirely fictional. The character makes the gate memorable. The receipts make it
useful.

## License

MIT. See [LICENSE](LICENSE).
