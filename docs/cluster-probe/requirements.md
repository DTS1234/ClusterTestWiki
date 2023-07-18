## Introduction

As it was mentioned before Cluster Probe is meant to run on any container, however its main goal is to be a load receiver for Kubernetes cluster especially for
the reCluster architecture. In order to make the testing process most effective there are several functional and non-functional requirements that were
identified, they also constitute the most important features of the Cluster Probe.

### Functional requirements

1. The system shall produce workloads based on a defined and measurable load specifications
2. The system shall be able to produce intense I/O operations.
3. The system shall be able to produce long-lasting or time specified intensive cpu tasks.
4. The system shall be able to produce multiple asynchronous computing tasks.
5. The system shall be able to receive data through the HTTP protocol.

### Non-functional requirements

1. The system shall be capable of handling a high volume of concurrent requests for each endpoint efficiently.
2. The system shall handle errors gracefully and provide appropriate error messages to clients.
3. The system API shall be well-documented and contain an intuitive interface, allowing users to understand and interact with the endpoints easily.