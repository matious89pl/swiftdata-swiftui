# SwiftData SwiftUI — Agent Skill

An AI agent skill that provides Apple-docs-aligned guidance for adding **SwiftData** persistence to **SwiftUI** apps. Covers model design, container setup, querying, migrations, iCloud/CloudKit sync, concurrency, and testing.

## What is an Agent Skill?

Skills are modular instruction sets that extend AI coding agents (Cursor, Codex) with specialized domain knowledge. When installed, the agent automatically activates this skill whenever you work on SwiftData tasks — no manual prompting required.

The skill uses **progressive disclosure**: the agent loads only the SKILL.md overview by default and reads detailed reference files on demand, keeping context window usage efficient.

## Topics Covered

| Area | Reference File | Key Concepts |
|------|---------------|--------------|
| **Foundations** | `swiftdata-foundations.md` | `@Model`, `ModelContainer`, `ModelContext`, `@Attribute`, `@Relationship`, `ModelConfiguration` |
| **Querying & Fetching** | `querying-fetching.md` | `@Query`, `FetchDescriptor`, predicates, sorting, paging |
| **Migrations** | `migrations.md` | `VersionedSchema`, `SchemaMigrationPlan`, `MigrationStage`, custom migration hooks |
| **iCloud / CloudKit** | `cloudkit-icloud.md` | CloudKit container setup, sync constraints, background modes, schema validation |
| **Concurrency & Testing** | `concurrency-testing.md` | `ModelActor`, main-actor context, autosave, in-memory stores for tests |

## Installation

### Using `npx skills` (recommended)

The [skills CLI](https://skills.sh) auto-detects your installed coding agents and places the skill in the correct directory. Supports 35+ agents including Cursor, Codex, Claude Code, and more.

Install globally (available across all your projects):

```bash
npx skills add matious89pl/swiftdata-swiftui -g
```

Install into the current project (shared with collaborators via git):

```bash
npx skills add matious89pl/swiftdata-swiftui
```

Target a specific agent:

```bash
npx skills add matious89pl/swiftdata-swiftui -g -a cursor
npx skills add matious89pl/swiftdata-swiftui -g -a codex
```

Verify installation:

```bash
npx skills list
```

> **Tip:** After installing, restart your agent to pick up the new skill.

### Manual installation

If you prefer to install manually, clone the repo directly into the appropriate skills directory.

**Cursor (personal):**

```bash
git clone https://github.com/matious89pl/swiftdata-swiftui.git ~/.cursor/skills/swiftdata-swiftui
```

**Cursor (project-scoped):**

```bash
git clone https://github.com/matious89pl/swiftdata-swiftui.git .cursor/skills/swiftdata-swiftui
```

**Codex:**

```bash
git clone https://github.com/matious89pl/swiftdata-swiftui.git ~/.codex/skills/swiftdata-swiftui
```

## When Does It Activate?

The agent picks up this skill automatically when you:

- Implement SwiftData models or persistence in a SwiftUI app
- Ask about `@Model`, `@Query`, `ModelContainer`, or `ModelContext`
- Set up schema migrations with `SchemaMigrationPlan`
- Configure iCloud/CloudKit sync for SwiftData
- Troubleshoot or review SwiftData-related code

## Skill Structure

```
swiftdata-swiftui/
├── SKILL.md                                # Entry point — overview, workflow, best practices
└── references/
    ├── swiftdata-foundations.md             # Core types and model design
    ├── querying-fetching.md                # @Query, FetchDescriptor, paging
    ├── migrations.md                       # Schema versioning and migration plans
    ├── cloudkit-icloud.md                  # iCloud sync setup and constraints
    └── concurrency-testing.md              # Background work and in-memory testing
```

## License

MIT
