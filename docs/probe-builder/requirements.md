## Introduction

ProbeBuilder main purpose is to facilitate the process of creation and execution of the jmeter tests for ClusterProbe containers running in the Kubernetes. To
clearly identify the goals of this software there are a few functional and non-functional requirements that have been identified and described, and the same as
in case of Cluster Probe the also constitute its features.

### Functional Requirements:

1. Users shall be able to create test specifications using a user-friendly interface, providing details like the number of threads,
   ramp-up period, endpoint URLs, request methods, and payload data.

2. The system shall generate JMeter test plans based on the test specifications, including:
    - the number of threads
    - request configurations
    - payload values

3. The system shall be able to execute the generated JMeter test plans on the target Kubernetes cluster using the JMeter Java API.

4. After test execution, the system shall collect and store the results, including:
   - response times,
   - success rates
   - errors encountered during the tests

5. The system shall create reports with plots and charts representing the test results, making it easy for users to analyze the
   performance of their Kubernetes cluster.

### Non-functional requirements

1. The system shall be able to handle a large number of concurrent users and execute JMeter tests efficiently without significant delays.
2. The user interface should be intuitive and easy to navigate, ensuring that users can create and manage test specifications without extensive training.
3. The system shall be scalable, allowing it to support a growing number of test specifications and users as the demand increases.