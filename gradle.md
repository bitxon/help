# Gradle

## Troubleshooting

```shell
# Get info about task execution order
gradle --dry-run <TASK>
# Get info about task options
gradle -q help --task <TASK>
# Get info about dependencies
gradle dependencies
# Get info about dependencies
gradle dependencies
# Get info about properties
gradle -q properties
```

## Build

```shell
# Re-Run up-to-date tasks
gradle --rerun-tasks build
```