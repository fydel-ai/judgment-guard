# Judgment Guard

A Claude Code skill that calibrates trust in AI-generated advice — ensuring confidence matches evidence, no more, no less.

When you ask Claude for advice, recommendations, comparisons, or prioritization on consequential topics — money, health, career, legal, safety, purchases — this skill checks whether evidence quality, recency, or uncertainty should change the confidence of the answer, then rewrites it to match.

## What it does

1. Evaluates draft answers on seven dimensions: evidence strength, assumption visibility, confidence calibration, action pressure, alternative coverage, epistemic authority, and false consensus
2. Applies an intervention policy:
   - **Strong evidence** — direct, confident answer with assumptions surfaced inline
   - **Mixed evidence** — multiple interpretations, counterpoints, and what would change the conclusion
   - **Weak evidence** — no ranked recommendations, only possibilities and verification steps
3. Outputs a structured report: decision audit, claim map, hidden assumptions, calibrated answer, and verification checklist

## Install

**Requirements:** [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and Node.js 18+

### Quick install (recommended)

> Install judgment-guard: run `npx @fydel-ai/judgment-guard`

### Manual install

Clone the repo into your user skills directory:

> Install judgment-guard: run `git clone https://github.com/fydel-ai/judgment-guard.git ~/.claude/skills/judgment-guard`

Either method creates:

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
| `rubric.md` | Scoring criteria for all seven evaluation dimensions |
| `templates/report_template.md` | Blank template for the five output sections |

## Example output

```
### Decision audit
- Evidence strength: medium
- Assumption visibility: low
- Confidence calibration: overstated
- Action pressure: high
- Alternative coverage: low
- Epistemic authority: appropriate
- False consensus: none detected

### Claim map
**Supported facts**
- ...

**Reasonable inferences**
- ...

**Speculation / missing evidence**
- ...

### Hidden assumptions
**What must be true for the inferences above to hold**
- ...

**Assumptions the user may not have considered**
- ...

### Calibrated answer
(rewritten response with confidence matched to evidence)

### What to verify before acting
1. ...
2. ...
3. ...
```

## License

[MIT](LICENSE)
