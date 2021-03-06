## Summary

This package contains a BEAM pipeline that populates a Cloud SQL database from a
Datastore backup. The pipeline uses an unsynchronized Datastore export and
overlapping CommitLogs generated by the Nomulus server to recreate a consistent
Datastore snapshot, and writes the data to a Cloud SQL instance.

## Pipeline Visualization

The golden flow graph of the InitSqlPipeline is saved both as a text-base
[DOT file](../../../../../../test/resources/google/registry/beam/initsql/pipeline_golden.dot)
and a
[.png file](../../../../../../test/resources/google/registry/beam/initsql/pipeline_golden.png).
A test compares the flow graph of the current pipeline with the golden graph,
and will fail if changes are detected. When this happens, run the Gradle task
':core:updateInitSqlPipelineGraph' to update the golden files and review the
changes.
