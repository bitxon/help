# Maven

## Get Info
```shell
# Print current project version
mvn help:evaluate -Dexpression=project.version -DforceStdout -q
```

## Version Switch

```shell
# Set particular version
mvn versions:set -DnewVersion=1.1-SNAPSHOT -DprocessAllModules=true -DgenerateBackupPoms=false

# Remove '-SNAPSHOT' suffix
mvn versions:set -DremoveSnapshot -DprocessAllModules=true -DgenerateBackupPoms=false

# Switch to new next Snapshot version
mvn versions:set -DnextSnapshot -DprocessAllModules=true -DgenerateBackupPoms=false
```

## Dependencies 
```shell
# Display dependency tree (use verbose to show version resolution reason)
mvn dependency:tree -Dverbose=true

# Using breadth-first approach to resolve Maven dependencies (Faster download)
mvn dependency:go-offline -Daether.dependencyCollector.impl=bf
```

## Other
```shell
## Suppress log message about downloading libraries '--no-transfer-progress' or '-ntp'
mvn verify -ntp
```
