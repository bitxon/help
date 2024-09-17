# Jenkins

## Script Console

**Print out all Jobs**
```groovy
Jenkins.instance.getAllItems(Job.class).each{ 
    println it.name + " - " + it.class
}
```
**Print out all Multibrach Jobs**
```groovy
Jenkins.instance.getAllItems(org.jenkinsci.plugins.workflow.multibranch.WorkflowMultiBranchProject).each {it ->
    println it.fullName;
}
```

**Kill zombie Job**
```groovy
Jenkins.instance.getItemByFullName("multi-branch-pipeline/my-branch")
    .getBuildByNumber(73)
    .finish(
        hudson.model.Result.ABORTED,
        new java.io.IOException("Aborting build")
    );
```