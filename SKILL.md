---
name: swiftdata-swiftui
description: 'SwiftData guidance for SwiftUI apps: model design with @Model, container/context setup, querying with @Query and FetchDescriptor, migrations with SchemaMigrationPlan, and iCloud/CloudKit sync. Use when implementing, reviewing, or troubleshooting SwiftData persistence in SwiftUI, including best practices and iCloud setup.'
---

# SwiftData SwiftUI

## Overview
Provide a concise, Apple-docs-aligned workflow for adding SwiftData to SwiftUI apps, plus best practices for modeling, queries, migrations, and iCloud sync.

## Quick start workflow
1. Define models with @Model and relationships/attributes.
2. Configure ModelContainer at the app/scene root.
3. Use @Environment(\.modelContext) for writes and @Query for view-driven fetches.
4. Add migrations when schema changes exceed automatic migration limits.
5. Configure iCloud sync only if required, and validate CloudKit schema compatibility.

## Decision points
- **Modeling details**: Read `references/swiftdata-foundations.md`.
- **Queries and paging**: Read `references/querying-fetching.md`.
- **Migrations**: Read `references/migrations.md`.
- **iCloud / CloudKit sync**: Read `references/cloudkit-icloud.md`.
- **Concurrency and testing**: Read `references/concurrency-testing.md`.

## Best-practices checklist (SwiftUI)
- Attach .modelContainer(...) at the top of the view/scene hierarchy.
- Prefer @Query for view data; use ModelContext fetch APIs for non-view tasks.
- Insert only the root of a model graph; SwiftData inserts related models automatically.
- Use @Attribute and @Relationship to make schema intent explicit.
- Use ModelConfiguration(isStoredInMemoryOnly: true) in tests.
- For iCloud sync, validate CloudKit constraints (optional relationships, no deny delete rule).

## References
- `references/swiftdata-foundations.md`
- `references/querying-fetching.md`
- `references/migrations.md`
- `references/cloudkit-icloud.md`
- `references/concurrency-testing.md`
