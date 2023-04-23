# Maven

## Version Switch

```bash
# Set particular version
mvn versions:set -DnewVersion=1.1-SNAPSHOT -DprocessAllModules=true -DgenerateBackupPoms=false

# Remove '-SNAPSHOT' suffix
mvn versions:set -DremoveSnapshot -DprocessAllModules=true -DgenerateBackupPoms=false

# Switch to new next Snapshot version
mvn versions:set -DnextSnapshot -DprocessAllModules=true -DgenerateBackupPoms=false
```

## Dependencies 
```bash
# Display dependency tree (use verbose to show version resolution reason)
mvn dependency:tree -Dverbose=true
```
