# Executor Package Test Case Map

This file maps test functions in the `executor` package to their corresponding
test files and describes what each test covers.

## executor_test.go

| Test Function | Description |
|---|---|
| `TestSelectLimit` | Verifies SELECT with LIMIT clause returns correct row count |
| `TestSelectOrderBy` | Verifies ORDER BY clause sorts results correctly |
| `TestSelectGroupBy` | Verifies GROUP BY clause aggregates results correctly |
| `TestSelectHaving` | Verifies HAVING clause filters grouped results |
| `TestSelectJoin` | Verifies JOIN operations (INNER, LEFT, RIGHT) produce correct results |
| `TestSelectSubquery` | Verifies subquery execution in SELECT, WHERE, and FROM clauses |
| `TestInsertIgnore` | Verifies INSERT IGNORE skips duplicate key errors |
| `TestInsertOnDuplicateKeyUpdate` | Verifies ON DUPLICATE KEY UPDATE modifies existing rows |
| `TestUpdateMultiTable` | Verifies UPDATE across multiple joined tables |
| `TestDeleteWithSubquery` | Verifies DELETE using subquery in WHERE clause |

## aggregate_test.go

| Test Function | Description |
|---|---|
| `TestAggregateCount` | Verifies COUNT(*) and COUNT(col) return correct values |
| `TestAggregateSum` | Verifies SUM aggregation including NULL handling |
| `TestAggregateAvg` | Verifies AVG aggregation including NULL handling |
| `TestAggregateMinMax` | Verifies MIN and MAX aggregation |
| `TestAggregateDistinct` | Verifies COUNT(DISTINCT col) deduplicates correctly |
| `TestStreamAgg` | Verifies streaming aggregation executor produces correct results |
| `TestHashAgg` | Verifies hash aggregation executor produces correct results |

## join_test.go

| Test Function | Description |
|---|---|
| `TestHashJoin` | Verifies hash join produces correct results |
| `TestMergeJoin` | Verifies merge join produces correct results on sorted input |
| `TestIndexLookupJoin` | Verifies index lookup join uses index correctly |
| `TestApply` | Verifies correlated subquery via Apply executor |
| `TestJoinWithNulls` | Verifies join behavior when join key columns contain NULLs |
