# improve-dev

**Invocation:** user-only  
**Implementation:** [SKILL.md](SKILL.md)

## Description

Use `improve-dev` when writing, reviewing, or refactoring code to avoid overcomplication, make surgical changes, surface assumptions, and define verifiable success criteria.

This skill biases toward caution over speed. It asks you to think before coding, prefer simplicity, change only what is necessary, avoid common anti-patterns, and execute against clear, testable goals.

## When to use

- You are implementing a new feature or fix.
- You are reviewing code and want a structured quality checklist.
- You are refactoring and want to keep the diff minimal and safe.
- The requirements feel ambiguous or the task is easy to over-engineer.

## How to invoke

Attach or reference the skill in your prompt, for example:

```
/improve-dev
```

or

```
Use improve-dev while refactoring this module.
```

## Guidelines summary

1. **Think before coding** — state assumptions, surface tradeoffs, ask when unclear.
2. **Simplicity first** — minimum code that solves the problem; no speculative features.
3. **Surgical changes** — touch only what you must; clean up only what your changes create.
4. **Avoid anti-patterns** — mysterious names, duplication, feature envy, data clumps, primitive obsession, repeated switches, shotgun surgery, divergent change, speculative generality, message chains, middle men, refused bequest.
5. **Goal-driven execution** — define verifiable success criteria and loop until met.

## Credits

This skill was inspired by:

- Andrej Karpathy ([@karpathy](https://x.com/karpathy)) — [post on careful, simple coding](https://x.com/karpathy/status/2015883857489522876).
- Matt Pocock's `code-review` skill — [github.com/mattpocock/skills](https://github.com/mattpocock/skills/tree/main/skills/engineering/code-review).

## Example

**User:**

> Add input validation to the signup endpoint.

**Expected assistant behavior:**

- Ask which fields need validation and what the rules are.
- Write focused validation logic without adding unrelated abstractions.
- Add tests for invalid inputs and make them pass.
- Keep the change limited to the signup endpoint and its tests.
