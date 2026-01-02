# Data Architecture & Layering

The platform follows a layered design to isolate concerns and ensure correctness.

### 1. Raw / CDC Layer
- Stores append-only CDC events
- Includes operation type and metadata
- No transformations applied
- Used for replay and audits

### 2. Cleaned / Validated Layer
- Deduplicates events
- Applies schema normalization
- Handles deletes explicitly
- Enforces data quality rules

### 3. Fact Layer
- Analytics-ready tables
- Supports derived metrics and joins
- Incrementally updated from cleaned layer
- Downstream views auto-refresh on changes

### Schema Evolution
- New columns are additive
- Backward compatibility maintained
- Unknown fields stored as JSON where needed
