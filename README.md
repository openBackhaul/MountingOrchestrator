Delete this link at the end of the specification process:  
- [Roadmap to Specification](../../issues/1)

# MountingOrchestrator

### Location
The MountingOrchestrator is part of the OperationSupport.

### Description
After getting triggered, e.g. by a specific status setting or manually, the MountingOrchestrator mounts a new device in the controller and it requests the MediatorManager for provisioning of a mediator process, if required for the respective device type. Future versions might implement load sharing algorithms or protection functions, if not covered by the infrastructure layer.

### Relevance
The MountingOrchestrator is required for connecting devices to the controller.

### Resources
- [Specification](./spec/)
- [TestSuite](./testing/)
- [Implementation](./server/)

### Comments
./.
