# Querying and fetching

## SwiftUI @Query macro
- Use @Query for view-driven fetches; it keeps views updated when models change.
- Provide a Predicate and SortDescriptor(s) via @Query initializers.
- Use the FetchDescriptor-based @Query when you need paging (fetchLimit/fetchOffset) or includePendingChanges.

## FetchDescriptor
- Use FetchDescriptor(predicate:sortBy:) to define filters and ordering.
- Set fetchLimit and fetchOffset for pagination.
- Set includePendingChanges when you need unsaved changes in results.

## ModelContext fetch APIs
- Use modelContext.fetch(_:) or fetchCount(_:) when you are outside SwiftUI or need custom control.
- Use fetchIdentifiers to avoid loading full objects when you only need IDs.

## Best practices
- Keep predicates and sorts stable; change parameters explicitly (avoid recreating @Query too frequently).
- Fetch only what the UI needs; use paging for large datasets.
- If a view updates a model, prefer editing the model directly rather than re-fetching it.

## Apple docs anchors
- Query macro (all initializers)
- FetchDescriptor (predicate, sortBy, fetchLimit, fetchOffset, includePendingChanges)
- ModelContext fetch APIs
- Predicate and SortDescriptor (Foundation)
