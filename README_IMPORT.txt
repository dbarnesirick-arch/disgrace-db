DISGRACE DB BATCH EXPORT

1. Open the local disgrace-db repository folder using GitHub Desktop > Repository > Show in Explorer.
2. Extract this ZIP. Copy cards.json and cards-data.js into repository root.
3. Merge assets/cards into the existing assets/cards folder; NEVER delete older images.
4. Commit and Push origin in GitHub Desktop.
5. Website reads cards-data.js; Godot reads cards.json after its next sync.
6. legacy_import.json is optional for older manual JSON import (new card records only; existing duplicates are skipped by old importers).
This ZIP does NOT publish anything by itself.
