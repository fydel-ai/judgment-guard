# Judgment Guard

A Claude skill that calibrates trust in AI-generated advice — ensuring confidence matches evidence, no more, no less.

## Structure

```
SKILL.md                      # Skill definition — trigger conditions, evaluation dimensions, intervention policy, output format
rubric.md                     # Scoring criteria for all seven evaluation dimensions
templates/
  report_template.md          # Blank output template (Decision audit, Claim map, Hidden assumptions, Calibrated answer, What to verify)
package.json                  # npm package config — enables `npx @fydel-ai/judgment-guard`
bin/
  install.mjs                 # CLI installer — copies skill files to ~/.claude/skills/judgment-guard/
```

## How it works

1. Triggered when the user asks for advice on a consequential topic
2. Evaluates the draft answer on seven dimensions: evidence strength, assumption visibility, confidence calibration, action pressure, alternative coverage, epistemic authority, false consensus
3. Applies intervention policy based on evidence strength (strong → direct confident answer; mixed → multiple interpretations; weak → no recommendation)
4. Outputs a structured report: decision audit, claim map, hidden assumptions, calibrated answer, and verification steps

## Editing guidelines

- `SKILL.md` frontmatter (`name`, `description`, `tools`) must remain valid YAML
- The five output sections in `SKILL.md` and `templates/report_template.md` must stay in sync
- Rubric levels (high/medium/low) in `rubric.md` should match the scales used in the decision audit
- False consensus uses `none detected / possible / present` scale across all files
