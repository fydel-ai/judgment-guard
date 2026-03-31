# Judgment Guard

A Claude Code skill that catches advice that sounds more certain than the evidence warrants.

When you ask Claude for recommendations on consequential topics — money, health, career, legal, safety, purchases — this skill audits the response for overconfidence and rewrites it with appropriate uncertainty.

## What it does

1. Evaluates draft answers on five dimensions: evidence strength, expressed confidence, action pressure, missing alternatives, and hidden inferential leaps
2. Applies an intervention policy:
   - **Strong evidence** — direct answer, with fact vs inference labeled
   - **Mixed evidence** — multiple interpretations, counterpoints, and what would change the conclusion
   - **Weak evidence** — no ranked recommendations, only possibilities and verification steps
3. Outputs a structured report: decision audit, claim map, safer rewrite, and verification checklist

## Install

**Requirements:** [Claude Code](https://docs.anthropic.com/en/docs/claude-code)

### Personal install

Clone the repo into your user skills directory:

> Install judgment-guard: run `git clone https://github.com/daqo/judgment-guard.git ~/.claude/skills/judgment-guard`

Claude Code looks for user-installed skills in `~/.claude/skills/`, so this creates:

> `~/.claude/skills/judgment-guard/SKILL.md`

### Project install

To share the skill with teammates in a repo, copy it into the project skills directory:

> Add judgment-guard to this project: run `cp -Rf ~/.claude/skills/judgment-guard .claude/skills/judgment-guard && rm -rf .claude/skills/judgment-guard/.git`

Committed to a repository, this gives teammates:

> `.claude/skills/judgment-guard/SKILL.md`

### Usage

Claude Code can load the skill automatically when the prompt calls for advice on consequential topics, or you can invoke it directly with `/judgment-guard`.

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Skill definition — trigger conditions, evaluation dimensions, intervention policy, output format |
| `rubric.md` | Scoring criteria for evidence strength, action pressure, and overstatement signals |
| `templates/report_template.md` | Blank template for the four output sections |

## Example output

```
### Decision audit
- Recommendation pressure: high
- Evidence strength: medium
- Confidence fit: overstated

### Claim map
**Supported facts**
- ...

**Reasonable inferences**
- ...

**Speculation / missing evidence**
- ...

### Safer answer
(rewritten response with calibrated confidence)

### What to verify before acting
1. ...
2. ...
3. ...
```

## License

[MIT](LICENSE)
