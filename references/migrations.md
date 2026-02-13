# Migrations

## When to add a migration plan
- Rely on automatic migrations for simple additive changes.
- Provide a SchemaMigrationPlan when changes exceed automatic migration capabilities.

## Key types
- VersionedSchema defines a schema version and the models it includes.
- MigrationStage describes a migration step between two VersionedSchema versions.
- SchemaMigrationPlan enumerates stages to move across versions.

## Workflow
1. Define versioned schemas (V1, V2, ...).
2. Define a SchemaMigrationPlan with stages (lightweight or custom).
3. Create the ModelContainer with the migrationPlan parameter.

## Custom migration hooks
- Use MigrationStage.custom(... willMigrate/didMigrate ...) to transform data in a controlled context.

## Apple docs anchors
- SchemaMigrationPlan, MigrationStage, VersionedSchema
- ModelContainer init(for:migrationPlan:configurations:)
