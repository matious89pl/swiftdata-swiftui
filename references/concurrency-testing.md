# Concurrency and testing

## Concurrency basics
- The SwiftUI environment modelContext is main-actor bound.
- Use ModelActor for isolated data work when you need serialized background access.
- Prefer async workflows around model changes instead of Combine.

## Autosave and manual saves
- The environment context autosaves by default; manual contexts can enable autosaveEnabled.
- Call save() when you need deterministic persistence timing (e.g., before dismissal).

## Testing setup
- Use ModelConfiguration(isStoredInMemoryOnly: true) for tests to avoid disk IO.
- Construct a ModelContainer with the in-memory configuration in tests.

## Apple docs anchors
- Concurrency support (SwiftData)
- ModelActor
- ModelContext autosaveEnabled
- Preserving your app’s model data across launches (ModelConfiguration examples)
