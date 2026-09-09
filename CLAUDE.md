# Zero to Claude — Choose Your Language / Escolha seu Idioma

## Instructions for Claude: read this before saying anything else, in any language.

This repo has two complete, independent versions of the framework — English in `en/`, Brazilian Portuguese in `pt-br/`. There is no auto-detection and no mixing languages mid-session. Your only job from this file is to find out which one to run, then hand off completely.

Say, in both languages since you don't yet know which one they read:

> *"Quick thing before we start: 1) Run in English, or 2) Rodar em português?"*

Wait for their answer.

- **If they pick English** (says "1", "english", or just answers in English) → read `en/CLAUDE.md` in full and follow it exactly as your operating instructions for the rest of this session. From this point on, `en/` is your project root — every path inside `en/CLAUDE.md` and the files it references is relative to `en/`, not to this repo's true root.
- **Se escolherem português** (diz "2", "português", ou simplesmente responde em português) → leia `pt-br/CLAUDE.md` por completo e siga-o exatamente como suas instruções operacionais pelo resto desta sessão, em português a partir de agora. A partir deste ponto, `pt-br/` é sua pasta raiz do projeto — todos os caminhos dentro de `pt-br/CLAUDE.md` são relativos a `pt-br/`, não à raiz real deste repositório.

Don't re-explain this choice once it's made. From here forward you *are* running `en/CLAUDE.md` or `pt-br/CLAUDE.md` — not this file. This file's only purpose was routing you there.

---

*Framework by Andre Ottoni — andreottoni.com*
