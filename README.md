# Open Source Code Analysis - greenDAO

Repository Link: https://github.com/greenrobot/greenDAO

## Selected Files Overview

| File Name | Size Category | Description |
|---|---|---|
| IdentityScopeType.java | Small | Enum used to set identity scope to Session or None. |
| FastCursor.java | Small | Wrapper interface for faster cursor operations on DB queries. |
| IdentityScope.java | Medium | Base interface defining how entity caching works. |
| IdentityScopeObject.java | Medium | Cache implementation for entities with generic Object keys. |
| DaoConfig.java | Medium | Configuration class that sets up DAO properties and table mappings. |
| IdentityScopeLong.java | Large | Specialized cache for long primary keys to improve performance. |
| TableStatements.java | Large | Manages pre-compiled SQL statements like INSERT, UPDATE, and DELETE. |

## Detailed File Descriptions

### 1. IdentityScopeType.java (Small)
- **Purpose:** Configures the caching behavior for greenDAO entities.
- **Details:** Contains enum values (Session and None) to enable or disable entity caching.

### 2. FastCursor.java (Small)
- **Purpose:** Optimizes database read operations.
- **Details:** Provides a lighter cursor interface to reduce overhead when reading query results.

### 3. IdentityScope.java (Medium)
- **Purpose:** Interface for managing object identity caching.
- **Details:** Ensures that requesting an entity with the same primary key returns the exact same object instance.

### 4. IdentityScopeObject.java (Medium)
- **Purpose:** Implements caching for non-primitive keys.
- **Details:** Maps generic Object primary keys to entity instances in a thread-safe way.

### 5. DaoConfig.java (Medium)
- **Purpose:** Holds configuration details for individual DAOs.
- **Details:** Reads table metadata, maps column names, and sets up primary key and scope configurations when initialized.

### 6. IdentityScopeLong.java (Large)
- **Purpose:** Optimized cache specifically built for primitive long primary keys.
- **Details:** Avoids Java object-boxing overhead by working directly with primitive long types to save memory and speed up lookup times.

### 7. TableStatements.java (Large)
- **Purpose:** Handles execution statements for SQLite database tables.
- **Details:** Pre-compiles reusable SQL queries (Insert, Update, Delete) so SQLite doesn't have to parse raw strings every time.
