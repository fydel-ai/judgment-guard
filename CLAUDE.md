# Judgment Guard

A Claude skill that detects when advice projects more certainty than the evidence supports, then rewrites it with appropriate confidence.

## Structure

```
SKILL.md                      # Skill definition — trigger conditions, evaluation dimensions, intervention policy, output format
rubric.md                     # Scoring criteria for evidence strength, action pressure, and overstatement signals
templates/
  report_template.md          # Blank output template (Decision audit, Claim map, Safer answer, What to verify)
```

## How it works

1. Triggered when the user asks for advice on a consequential topic
2. Evaluates the draft answer on five dimensions: evidence strength, expressed confidence, action pressure, missing alternatives, hidden inferential leaps
3. Applies intervention policy based on evidence strength (strong → direct answer; mixed → multiple interpretations; weak → no recommendation)
4. Outputs a structured report: decision audit, claim map, safer rewrite, and verification steps

## Editing guidelines

- `SKILL.md` frontmatter (`name`, `description`, `tools`) must remain valid YAML
- The four output sections in `SKILL.md` and `templates/report_template.md` must stay in sync
- Rubric levels (high/medium/low) in `rubric.md` should match the scales used in the decision audit
