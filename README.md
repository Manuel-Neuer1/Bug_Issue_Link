# Bug_Iusse_Link

This section details the bugs and unsafe implementations identified by our framework, as referenced in Table 1 of the paper. Each reported issue includes a link to the corresponding bug report or GitHub issue where available.

### MySQL Connector/J Issues

*   **Issue 1 (Output message error with `setMaxRows()`):**
    *   [MySQL Bug #118079](https://bugs.mysql.com/bug.php?id=118079)
*   **Issue 2 (Illegal value with `executeBatch()` on non-DML statement):**
    *   [MySQL Bug #118234](https://bugs.mysql.com/bug.php?id=118234)
*   **Issue 3 (Unexpected exception with `getHoldability()`):**
    *   [MySQL Bug #118095](https://bugs.mysql.com/bug.php?id=118095)
*   **Issue 4 (`rewriteBatchedStatements` connection property unexpectedly affects query results following batch inserts):**
    *   [MySQL Bug #118138](https://bugs.mysql.com/bug.php?id=118138)
*   **Issue 6 (`allowMultiQueries` connection property unexpectedly affects `getUpdateCounts()` after batch execution):**
    *   [MySQL Bug #118167](https://bugs.mysql.com/bug.php?id=118167)
*   **Issue 7 (Atomicity of batch operation compromised by `allowMultiQueries`):**
    *   [MySQL Bug #118201](https://bugs.mysql.com/bug.php?id=118201)

### OceanBase Connector/J Issues

*   **Issue 5 (ResultSet should be closed, unexpectedly not closed):**
    *   [OceanBase GitHub Issue #2279](https://github.com/oceanbase/oceanbase/issues/2279)
*   **Issue 8 (`rewriteBatchedStatements` connection property unexpectedly affects query results following batch inserts):**
    *   [OceanBase GitHub Issue #2271](https://github.com/oceanbase/oceanbase/issues/2271)
*   **Issue 9 (Batch behavior with non-DML statement - similar to MySQL Issue 2, potentially related to `allowMultiQueries` effects):**
    *   [OceanBase GitHub Issue #2275](https://github.com/oceanbase/oceanbase/issues/2275)


*   **Issues 10-15 (ResultSet Navigation Methods on TYPE_FORWARD_ONLY):**
    *   **Description:** These issues collectively represent an OceanBase Connector/J compatibility mismatch where several `java.sql.ResultSet` navigation methods (`previous()`, `first()`, `afterLast()`, `absolute()`, `last()`, and `beforeFirst()`) do not conform to the JDK 8 JDBC API documentation [7]. The specification requires a `SQLException` to be thrown when these methods are called on a `TYPE_FORWARD_ONLY ResultSet`. OceanBase Connector/J, however, executes these calls without throwing an exception.
    *   **Reported Under:** All these related deviations (Issues 10 through 15 from our paper's Table 1) were reported and are being tracked under a single GitHub issue:
        *   [OceanBase GitHub Issue #2253](https://github.com/oceanbase/oceanbase/issues/2253)
    *   **Specific methods covered by this issue include:**
        *   Issue 10: `previous()`
        *   Issue 11: `first()`
        *   Issue 12: `afterLast()`
        *   Issue 13: `absolute()`
        *   Issue 14: `last()`
        *   Issue 15: `beforeFirst()`
