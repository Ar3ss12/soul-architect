# Soul Architect 🧠🏗️

> Create living personas with cognitive architecture, not just speech patterns.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Changelog](https://img.shields.io/badge/changelog-follow-blue.svg)](CHANGELOG.md)

---

## What is this?

**Soul Architect** is an OpenClaw skill for creating detailed persona definitions (STYLE_MANIFESTO) that drive authentic content generation. Unlike simple "voice cloning," this creates the underlying *mind* — including logic, flaws, cognitive distortions, and behavioral patterns.

Use this skill to clone:
- **Real people** (yourself, colleagues, experts)
- **Historical figures** (Einstein, Tesla, Jobs)
- **Fictional characters** (movie heroes, book characters, original creations)

---

## Quick Start: Add to Your Agent

### Step 1: Copy the Skill

**Windows (PowerShell):**
```powershell
# Clone or download this repo, then copy:
xcopy /E /I soul-architect %USERPROFILE%\.openclaw\workspace\skills\soul-architect
```

**macOS / Linux:**
```bash
# Clone or download this repo, then copy:
cp -r soul-architect ~/.openclaw/workspace/skills/
```

**Manual:**
1. Download this folder
2. Place in `~/.openclaw/workspace/skills/` (or `%USERPROFILE%\.openclaw\workspace\skills\`)
3. Restart OpenClaw

### Step 2: Configure Paths (Optional)

If your workspace is in a custom location, edit the paths in `scripts/synthesize.py`:

```python
# Line 16: Change output directory if needed
output_dir = Path(f"personas/{name}")  # Default: ./personas/

# Or set absolute path:
output_dir = Path(f"/your/custom/path/personas/{name}")
```

### Step 3: Use the Skill

Once installed, the skill activates automatically when you ask the right questions.

---

## How to Talk to Your Agent

### ✅ Correct Triggers

**For real people:**
- "Create a soul/persona for [name]"
- "Make a STYLE_MANIFESTO for [name]"
- "Clone [name]'s personality for content generation"
- "I want to generate texts in my own voice"
- "Build a digital twin of [name]"

**For historical figures:**
- "Create a persona for [name] (historical figure)"
- "Make a manifesto for [name]"
- "Clone [famous person]'s thinking style"

**For fictional characters:**
- "Create a persona for [character name] from [movie/book]"
- "Make a soul for a fictional character"
- "Build a persona for my original character"

### ❌ Wrong Triggers (Won't Work)

- "Write a text" → too vague, doesn't specify persona creation
- "Do an analysis" → this is for other skills
- "Describe a person" → too vague
- "Tell me about [person]" → this is research, not cloning

### Example Dialogues

**Example 1: Clone yourself**
```
You: Create a soul for me. I want you to generate texts in my voice.
Agent: [Loads soul-architect] → Research → Creates STYLE_MANIFESTO.md
```

**Example 2: Clone a famous person**
```
You: Make a STYLE_MANIFESTO for Elon Musk. I want to generate posts in his style.
Agent: [Loads soul-architect] → Research → Creates manifesto
You: [Later] Generate a tweet about a new product as Elon Musk.
Agent: [Uses the manifesto] → Generates tweet
```

**Example 3: Fictional character**
```
You: Create a persona for the Joker from Batman.
Agent: [Loads soul-architect] → Research → Creates manifesto
```

---

## When to Use This Skill

### Use soul-architect when:

- ✅ You want to clone a person's voice for content generation
- ✅ You need a detailed cognitive profile (not just speech patterns)
- ✅ You're building a "living soul" that can think/react as that person
- ✅ You want consistent persona across multiple content types (posts, emails, scripts)

### DON'T use soul-architect when:

- ❌ You just want a one-off text in someone's style → Too heavy for simple tasks
- ❌ You need simple voice cloning without cognitive depth → Use lighter alternatives
- ❌ You're analyzing a person without intent to generate → Use research skills

---

## What You Get

Each persona gets a **9-section manifesto** covering:

```
1. Core Identity          — Psychological foundation
2. Cognitive Architecture — How they think
3. Chaos Dynamics         — Illogical patterns
4. Reaction Matrix        — Triggers and responses
5. Interaction Dynamics   — Social scenarios
6. Micro-Behaviors        — Body language in text
7. Uniqueness             — Deviations and weirdness
8. Linguistic DNA         — Language code
9. Domain Adapters        — Universal modules
```

### Example Output

```markdown
# STYLE MANIFESTO: Steve Jobs

## 1. Core Identity
- **Primary Driver:** Prove that art and technology can merge into something revolutionary
- **Core Trauma:** Being fired from Apple (1985) — the company he founded
- **Values Rank:** Simplicity > Perfection > Speed
- **Worldview:** The world is divided into "insanely great" and "shit"

## 8. Linguistic DNA
- **Sentence length:** Short, punchy. Average 6-8 words
- **Signature phrases:** "Insanely great", "Boom", "It just works"
- **Rhetorical devices:** Triads ("Simple. Clean. Beautiful."), rhetorical questions
- **Tone:** Direct, no qualifiers, absolute statements
- **Forbidden:** "I think", "maybe", "perhaps" — speaks in certainties
```

---

## Integration with Other AI Agents

This skill is designed for **OpenClaw**, but the concept can be adapted to other AI coding agents. Here's how:

### OpenClaw (Primary Platform)

**Location:** `~/.openclaw/workspace/skills/` (macOS/Linux) or `%USERPROFILE%\.openclaw\workspace\skills\` (Windows)

```bash
# Copy the skill
cp -r soul-architect ~/.openclaw/workspace/skills/

# Or on Windows PowerShell:
xcopy /E /I soul-architect %USERPROFILE%\.openclaw\workspace\skills\soul-architect
```

**Activation:** Automatic when you use trigger phrases in chat.

**Config:** Skills are auto-loaded from the `skills/` directory. No config needed.

---

### Claude Code (Anthropic)

**Location:** Project-level `.claude/` folder or global `~/.claude/`

```bash
# Project-specific (recommended)
mkdir -p .claude/skills
cp -r soul-architect .claude/skills/

# Or add instructions directly to .claude/instructions.md
cat soul-architect/SKILL.md >> .claude/instructions.md
```

**Usage:** Same triggers work in chat — "Create a persona for [name]"

**Note:** Claude Code uses project-level rules by default. For global availability, copy to `~/.claude/skills/`.

---

### Cline (VS Code Extension)

**Location:** Project root `.clinerules` or `~/.cline/rules/` for global

```bash
# Project-specific
cat soul-architect/SKILL.md >> .clinerules

# Or create a dedicated rule file
mkdir -p .cline/rules
cp soul-architect/SKILL.md .cline/rules/soul-architect.md
```

**Usage:** Reference in chat: "Use soul-architect pattern to create a persona for..."

**Settings:** Enable "Read project rules" in Cline settings.

---

### Roo Code (VS Code Extension)

**Location:** Project root `.roo/rules/` or `.roorules`

```bash
# Create rules directory
mkdir -p .roo/rules

# Copy the skill
cp soul-architect/SKILL.md .roo/rules/soul-architect.md

# Or append to main rules file
cat soul-architect/SKILL.md >> .roorules
```

**Usage:** Tag in chat: "@soul-architect Create a persona for [name]"

**Settings:** Enable "Custom rules" in Roo Code extension settings.

---

### Cursor (AI IDE)

**Location:** `.cursor/rules/` for project rules or `.cursorrules` file

```bash
# Create rules directory (if not exists)
mkdir -p .cursor/rules

# Copy as a named rule
cp soul-architect/SKILL.md .cursor/rules/soul-architect.md

# Or use the single-file format
cp soul-architect/SKILL.md .cursorrules
```

**Usage:** 
- Chat: "@soul-architect Create a persona..."
- Comments: `// cursor-rule: soul-architect`

**Settings:** Cursor automatically loads `.cursorrules` and `.cursor/rules/`.

---

### GitHub Copilot (VS Code / JetBrains)

**Location:** `.github/copilot-instructions.md` (project-level)

```bash
# Create GitHub folder (if not exists)
mkdir -p .github

# Add skill instructions
cat soul-architect/SKILL.md >> .github/copilot-instructions.md
```

**Usage:** Reference in comments or chat:
```javascript
// Create a persona using soul-architect pattern
// @persona: Elon Musk
```

**Note:** Copilot Chat reads from `.github/copilot-instructions.md` automatically.

---

### Windsurf (Codeium)

**Location:** `.windsurf/rules/` or `.windsurfrules`

```bash
mkdir -p .windsurf/rules
cp soul-architect/SKILL.md .windsurf/rules/soul-architect.md
```

**Usage:** Chat: "Use soul-architect to create a persona for..."

---

### Generic Pattern (Any AI Agent)

If your agent supports custom instructions or rules:

1. **Copy** the `SKILL.md` content
2. **Paste** into your agent's custom instructions file
3. **Add trigger phrase** that your agent recognizes
4. **Test** with a simple persona request

**Common locations:**

| Agent | File/Location |
|-------|---------------|
| Cline | `.clinerules` or `.cline/rules/` |
| Roo Code | `.roorules` or `.roo/rules/` |
| Cursor | `.cursorrules` or `.cursor/rules/` |
| Claude Code | `.claude/instructions.md` or `.claude/skills/` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Windsurf | `.windsurfrules` or `.windsurf/rules/` |
| OpenClaw | `~/.openclaw/workspace/skills/` |

---

## Files

```
soul-architect/
├── SKILL.md              # Agent-facing skill definition
├── README.md             # This file (human documentation)
├── CHANGELOG.md          # Version history and updates
├── LICENSE.txt           # MIT License
├── .gitignore            # Git ignore rules
├── scripts/
│   └── synthesize.py     # Optional CLI helper
└── references/           # Templates (if applicable)
```

---

## License

MIT License — use freely, attribute kindly.

## Contributing

1. Fork the repo
2. Create a feature branch
3. Submit a pull request with examples

---

## GitHub Badges (Optional)

Add these badges to your repository for automatic star tracking and visibility:

```markdown
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/Ar3ss12/soul-architect.svg?style=social&label=Star)](https://github.com/Ar3ss12/soul-architect)
[![GitHub forks](https://img.shields.io/github/forks/Ar3ss12/soul-architect.svg?style=social&label=Fork)](https://github.com/Ar3ss12/soul-architect)
[![Changelog](https://img.shields.io/badge/changelog-follow-blue.svg)](CHANGELOG.md)
```

**Replace `YOUR_USERNAME` with your GitHub username.**

**Available badges:**
- ⭐ Stars counter — auto-updates as people star your repo
- 🍴 Forks counter — shows fork activity
- 📄 License badge — shows MIT license
- 📝 Changelog badge — links to change history

---

*"A persona without cognitive architecture is just a voice. A persona with architecture is a soul."*