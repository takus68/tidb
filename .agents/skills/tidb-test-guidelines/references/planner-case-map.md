# Planner Package Test Case Map

This document maps test functions in the `planner` package to their corresponding test files and categories.

## core/

| Test Function | File | Category |
|---|---|---|
| TestPredicatePushDown | core/integration_test.go | predicate pushdown |
| TestOuterJoinElimination | core/integration_test.go | join elimination |
| TestBuildKeyInfo | core/logical_plan_test.go | key info |
| TestDecorrelate | core/integration_test.go | subquery decorrelation |
| TestEliminateProjection | core/integration_test.go | projection elimination |
| TestMaxMinEliminate | core/integration_test.go | agg elimination |
| TestColumnPruning | core/logical_plan_test.go | column pruning |
| TestAllocID | core/logical_plan_test.go | plan id allocation |
| TestSelectView | core/integration_test.go | view handling |
| TestUnion | core/logical_plan_test.go | set operations |
| TestAggPushDown | core/integration_test.go | agg pushdown |
| TestDeriveStats | core/stats_test.go | statistics derivation |
| TestIndexJoinHint | core/integration_test.go | index join hints |
| TestSubquery | core/logical_plan_test.go | subquery planning |
| TestDAGPlanBuilderSimpleCase | core/physical_plan_test.go | physical plan building |
| TestDAGPlanBuilderJoin | core/physical_plan_test.go | join physical plans |
| TestDAGPlanBuilderSubquery | core/physical_plan_test.go | subquery physical plans |
| TestIndexLookUpJoin | core/physical_plan_test.go | index lookup join |
| TestMPPPlanCreation | core/integration_test.go | mpp planning |
| TestPushDownToTiFlash | core/integration_test.go | tiflash pushdown |

## memo/

| Test Function | File | Category |
|---|---|---|
| TestNewGroup | memo/group_test.go | memo group creation |
| TestGroupExpr | memo/group_expr_test.go | group expression |
| TestCopyOnWriteContext | memo/group_test.go | context handling |

## cascades/

| Test Function | File | Category |
|---|---|---|
| TestImplGroupExpr | cascades/transformation_rules_test.go | transformation rules |
| TestPredicatePushDownRule | cascades/transformation_rules_test.go | predicate pushdown |
| TestImplementationRules | cascades/implementation_rules_test.go | implementation rules |

## Notes

- Integration tests in `core/integration_test.go` cover end-to-end plan shape validation.
- Stats tests require `statistics` package mocks or real histogram data.
- MPP/TiFlash tests may require mock store with TiFlash replica setup.
