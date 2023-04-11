Delete this link at the end of the specification process:  
- [Roadmap to Specification](../../issues/1)

# MountingOrchestrator

### Location
The MountingOrchestrator is part of the OperationSupport.

### Description
After getting triggered, e.g. by a specific status setting or manually, the MountingOrchestrator mounts a new device in the controller and it requests the MediatorManager for provisioning of a mediator process, if required for the respective device type. Future versions might implement load sharing algorithms or protection functions, if not covered by the infrastructure layer.

The MountingOrchestrato can also provide the list of mounted devices.

The MountingOrchestrator is able to manage a list of potential controllers, and it will mount new device in the ACTIVE controller, that can be configured through exposed services. 

The MountingOrchestrator is able to manage different Device Kinds: for each device kind, the MountingOrchestrator knows if it is needed to instantiate a Mediator wither the device directly support a NETCONF interface. The list of supported Device Kinds is fully configurable through exposed services.

### Relevance
The MountingOrchestrator is required for connecting devices to the controller.

### Resources
- [Specification](./spec/)
- [TestSuite](./testing/)
- [Implementation](./server/)

### Comments
./.
