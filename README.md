Gradle projects that contain multiple `Test` tasks stop running all tests when hitting a test-failure in one
test tasks, if no additional configuration to the `Test` tasks has been explicity added.

This plugin sets `ignoreFailures=true` on all `Test` tasks and adds collects the projects that have failing tests.
It is recommended to apply this plugin to all projects in a multi-module project.

Goal of this plugin is to let all `Test` tasks run and let the build only fail at the end when all `Test` tasks
have finished.

Usage:

```
plugins {
    id("org.caffinitas.gradle.aggregatetestresults"") version "0.1"
}
```

A task named `aggregateTestFailures` is added to each project, which is used to collect and show the projects/test-tasks
that have failed.
