# SwiftData foundations (models, containers, contexts)

## Core types
- @Model macro turns a class into a persistent model and provides Observable + PersistentModel conformance.
- ModelContainer manages schema + storage configuration; ModelContext reads/writes models via the container.
- In SwiftUI, attach a container with .modelContainer(...) so EnvironmentValues.modelContext is available.

## Minimal setup (SwiftUI)
- Attach modelContainer at the top of the view/scene hierarchy so all child views share it.
- Access the context via @Environment(\.modelContext) inside views.

## Model definition notes
- SwiftData persists noncomputed properties of supported types by default.
- Use @Attribute to customize persistence behavior (e.g., unique constraints, preserve on deletion, encryption, originalName for renames).
- Use @Relationship to define relationships and delete rules; explicitly set inverse when the framework cannot infer it.
- Use @Transient for properties that should not persist.

## Storage configuration
- Use ModelConfiguration for custom storage (in-memory for tests, read-only, app group, CloudKit container selection).
- The default container auto-discovers CloudKit from entitlements; specify a ModelConfiguration when you need a specific container or to disable sync.

## Context behaviors
- The SwiftUI environment context is main-actor bound and autosaves changes.
- For manually created contexts, set autosaveEnabled if you want implicit saves.
- Insert only the root of a new model graph; related models are inserted automatically.

## Apple docs anchors
- SwiftData overview
- Model(), Attribute(), Relationship(), Transient()
- ModelContainer / ModelContext
- EnvironmentValues.modelContext, View/Scene.modelContainer
- Preserving your app’s model data across launches
