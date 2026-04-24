# DDL Test Case Map

This document maps DDL-related test scenarios to their corresponding test files and functions in the TiDB codebase.

## Package: `pkg/ddl`

| Test Scenario | File | Function |
|---|---|---|
| Create table basic | `ddl_test.go` | `TestCreateTable` |
| Create table with constraints | `ddl_test.go` | `TestCreateTableWithConstraint` |
| Drop table | `ddl_test.go` | `TestDropTable` |
| Add column | `ddl_test.go` | `TestAddColumn` |
| Drop column | `ddl_test.go` | `TestDropColumn` |
| Modify column type | `ddl_test.go` | `TestModifyColumn` |
| Add index | `ddl_test.go` | `TestAddIndex` |
| Drop index | `ddl_test.go` | `TestDropIndex` |
| Rename table | `ddl_test.go` | `TestRenameTable` |
| Truncate table | `ddl_test.go` | `TestTruncateTable` |
| Create database | `db_test.go` | `TestCreateDatabase` |
| Drop database | `db_test.go` | `TestDropDatabase` |
| Alter database charset | `db_test.go` | `TestAlterDatabaseCharset` |

## Package: `pkg/ddl/ingest`

| Test Scenario | File | Function |
|---|---|---|
| Ingest index basic | `ingest_test.go` | `TestAddIndexIngest` |
| Ingest index with duplicate keys | `ingest_test.go` | `TestAddIndexIngestDuplicateKey` |
| Ingest index rollback | `ingest_test.go` | `TestAddIndexIngestRollback` |

## Package: `tests/integrationtest` (DDL SQL Logic Tests)

| Test Scenario | File |
|---|---|
| DDL general statements | `testdata/ddl_suite/ddl.test` |
| Partition DDL | `testdata/ddl_suite/partition.test` |
| Column type change | `testdata/ddl_suite/column_type_change.test` |
| Auto increment behavior | `testdata/ddl_suite/auto_increment.test` |

## Notes

- DDL tests that require real TiKV should use the `tidb-realtikv-runner` skill.
- Failpoint-based DDL concurrency tests should use the `tidb-failpoint-test-runner` skill.
- Integration test SQL cases should be recorded/updated using the `tidb-integrationtest-recorder` skill.
