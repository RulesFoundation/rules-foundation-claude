---
description: "Encode a statute into RAC format with full multi-agent workflow"
argument-hint: "<citation> (e.g., '26 USC 1', '26 USC 32(c)(2)(A)')"
---

# Encode Statute

Runs the autorac encoding pipeline (self-contained, no plugin agents).

## Usage

```
/encode 26 USC 1
/encode 26 USC 32
/encode 7 USC 2017(a)
```

## What Happens

The autorac CLI runs the full pipeline:

1. **Encoding** - Claude encodes subsections into .rac files
2. **Oracles** - Validates against PolicyEngine and TAXSIM
3. **Review** - 4 LLM reviewers run checklists in parallel
4. **Logging** - Records to autorac experiment DB

## Invoke

```bash
cd ~/RulesFoundation/autorac && source .venv/bin/activate && autorac encode "$ARGUMENTS"
```
