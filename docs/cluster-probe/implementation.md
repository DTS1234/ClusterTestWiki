### Introduction

Cluster Probe is written in Java 17, and it uses the Spring Boot Framework.
Each feature's code is stored in its own java package.

All packages expose a service class that can be injected as a dependency to the
Controller, the REST api web layer class. Any error that has occurred during the test is handled by the ErrorHandler class that specifies an appropriate
message and returns the error response entity.

![img.png](../img/cluster-probe-packages.png)

### File operations

FileOperations service is using java standard development kit libraries to implement the creation, update and the deletion for files. Those operations are
performed based on the data specified in FileSystemSpecification class object.

![img1.png](../img/file-operations.png)

there is only one public method implemented for the `FileOperationsService` all the files created will be stored under the projects directory
in the 'test' folder, then the number of files will be created based on parameters specified in the specification object.

![img2.png](../img/sf.png)

<figure>
<figcaption align="center"><em>Specification class</em></figcaption>
</figure>

If the `fileContent` parameter will be null or empty no write operations will be performed.

![img.png](../img/file-contents-if.png)

After all the operations are performed files and the 'test' directory are deleted:
![img.png](../img/delete-files.png)

### Stress ng

In order to implement the stress ng jobs invocation, `TestService` creates an appropiate stress ng job based on the `TestSpecification` parameters,
not all parameters are required so mostly `TestService` class implements the logic for creating the job accurately.

![img.png](../img/mappingComands.png)
<hr>

![img.png](../img/testSpecifciation.png)
<figure>
<figcaption align="center"><em>Specification class</em></figcaption>
</figure>

for each parameter in the specification there is an according mapping method in the service class that based on whether the parameter is correct or not it
creates an appropriate part of the command. There is also an option for receiving a plain command as a string, if this one is available and
the `isCommand` flag is set to `true` the rest of the parameters will be ignored. 

![img.png](../img/isCommand.png)

Whenever the `durationInSeconds` parameter will not be available there is a default 24 hours value set in the `mapTestTimeCommand`:
![img.png](../img/test-time-command.png)

### Transactional
