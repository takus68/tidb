# Session Package Test Case Map

This document maps test scenarios to their corresponding test functions in the `session` package.

## Session Lifecycle

| Scenario | Test Function | File |
|----------|--------------|------|
| Session creation and initialization | `TestSession` | `session_test.go` |
| Session close and cleanup | `TestSessionClose` | `session_test.go` |
| Session variable inheritance | `TestSessionVars` | `session_test.go` |
| Concurrent session access | `TestConcurrentSession` | `session_test.go` |

## Transaction Management

| Scenario | Test Function | File |
|----------|--------------|------|
| Begin/Commit/Rollback | `TestTransaction` | `session_test.go` |
| Optimistic transaction conflict | `TestOptimisticTxnConflict` | `tidb_test.go` |
| Pessimistic transaction | `TestPessimisticTxn` | `tidb_test.go` |
| Auto-commit behavior | `TestAutocommit` | `session_test.go` |
| Transaction retry logic | `TestRetry` | `session_test.go` |
| Statement rollback on error | `TestStmtRollback` | `session_test.go` |

## System Variables

| Scenario | Test Function | File |
|----------|--------------|------|
| Set/Get system variables | `TestSysVars` | `session_test.go` |
| Scope validation (global vs session) | `TestSysVarScope` | `session_test.go` |
| sql_mode handling | `TestSQLMode` | `session_test.go` |
| time_zone variable | `TestTimeZone` | `session_test.go` |
| character set variables | `TestCharset` | `session_test.go` |

## Privilege and Authentication

| Scenario | Test Function | File |
|----------|--------------|------|
| User login authentication | `TestAuth` | `session_test.go` |
| Privilege check on DDL | `TestPrivilege` | `session_test.go` |
| GRANT/REVOKE operations | `TestGrantRevoke` | `session_test.go` |

## Schema and Metadata

| Scenario | Test Function | File |
|----------|--------------|------|
| Schema version update | `TestSchemaVersion` | `session_test.go` |
| Infoschema staleness | `TestInfoSchemaChanged` | `session_test.go` |
| Table cache invalidation | `TestTableCacheInvalidation` | `session_test.go` |

## Notes

- Most session tests live in `session/session_test.go` and `session/tidb_test.go`.
- Failpoint-based tests for retry and conflict scenarios require the `failpoint` build tag.
- Integration tests involving real TiKV should use the `tidb-realtikv-runner` skill.
