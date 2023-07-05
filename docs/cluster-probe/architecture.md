Cluster Probe is written in Java 17, and it uses the Spring Boot Framework.
Each feature's code is stored in its own java package.

All packages expose a service class that can be injected as a dependency to the
Controller, the REST api web layer class. Any error that has occurred during the test is handled by the ErrorHandler class that specifies an appropriate
message and returns the error response entity.

![img.png](cluster-probe-packages.png)