# iCloud / CloudKit sync with SwiftData

## Capabilities required
- Enable iCloud (with CloudKit) capability.
- Enable Background Modes with Remote notifications for CloudKit change delivery.

## Container selection
- By default, SwiftData uses the first CloudKit container in entitlements.
- Use ModelConfiguration(cloudKitDatabase:) to:
  - force a specific container (.private("iCloud..."))
  - use automatic detection (.automatic)
  - disable SwiftData sync entirely (.none)

## Schema compatibility cautions
- Unique constraints are not enforced by CloudKit during sync.
- CloudKit requires relationships to be optional; avoid nonoptional relationships.
- Delete rule .deny is not supported for CloudKit sync.
- If SwiftData cannot infer a relationship inverse, set it explicitly before saving.

## Dev schema initialization
- Initialize the CloudKit development schema using the Core Data CloudKit integration, then unload the store before constructing ModelContainer.
- Promote schema to production before release; CloudKit schemas are additive only.

## Troubleshooting tools
- Use the CloudKit Database app to inspect schema, data, and deploy schema to production.

## Apple docs anchors
- Syncing model data across a person’s devices (all subsections)
- ModelConfiguration.CloudKitDatabase
- CloudKit: Enabling CloudKit in your app, CloudKit Database app
