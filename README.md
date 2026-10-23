# agents

## Writing and Code Standards

This project follows two guiding principles:

### Simplified Technical English (STE)

All documentation, comments, and naming use Simplified Technical English. STE rules:

- Use short, clear sentences. One idea per sentence.
- Use approved words where possible. Avoid jargon and ambiguous terms.
- Write in active voice. Say who does what.
- Keep paragraphs short. Maximum 6 sentences per paragraph.
- Do not use more than one meaning for the same word.

### Clean Code (Robert C. Martin)

All code follows the principles from *Clean Code: A Handbook of Agile Software Craftsmanship*:

- **Meaningful names** — Variables, functions, and classes must have clear, intention-revealing names. Do not use abbreviations or single letters (except loop counters).
- **Small functions** — Each function does one thing. Keep functions short.
- **Single Responsibility** — Each module, class, or function has one reason to change.
- **DRY (Don't Repeat Yourself)** — Do not duplicate logic. Extract shared behavior.
- **Clean formatting** — Use consistent indentation and spacing. Code reads top to bottom like a narrative.
- **Minimal comments** — Code explains itself through good names and structure. Add comments only when the "why" is not obvious.
- **Error handling** — Handle errors cleanly. Do not ignore exceptions. Do not return null when you can avoid it.
- **Tests** — Write tests that are fast, independent, repeatable, and self-validating. Tests follow the same quality standards as production code.
