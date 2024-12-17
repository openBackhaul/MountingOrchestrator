Delete this link at the end of the specification process:  
- [Roadmap to Specification](../../issues/1)

# MountingOrchestrator

### Location
The MountingOrchestrator is part of the OperationSupport.

### Description
The MountingOrchestrator application will handle the mounting of new, modified or substituting devices.

A prerequisite for any operation being executed is that the new, modified or substituting device can be reached over a DCN connection. 

The MountingOrchestrator coordinates the mounting of a new device in the controller and it requests the MediatorManager for provisioning of a mediator process, if required for the respective device type. For each device kind, the MountingOrchestrator knows whether it is needed to instantiate a Mediator or the device directly supports a NETCONF interface.  

The MountingOrchestrator is able to manage a list of potential controllers.

The MountingOrchestrator shall offer the following functionalities on its first release:

- Provide list of mount-points
- Adding a new mount-point
- Editing an existing mount-point
- Deletion of a mount-point
- Indication that the link-endpoint is ready for a link-acceptance-test
- Provide list of controllers with respective status
- Adding a new controller
- Editing status of an existing controller
- Deletion of a controller

The MountingOrchestrator shall potentially offer following fucntionalities in future releases:

- Migrating devices to a different controller
- Backup and restore
- Provide status information of mounting procedure (e.g. "10 mounts successful at time x")  and audit log
- Gathering application performance statistics


### Relevance
The MountingOrchestrator is required for connecting devices to the controller.

### Dependencies
- [AccessPlanningToolProxy](https://github.com/openBackhaul/AccessPlanningToolProxy)  
- [ConnectionPreparation](https://github.com/openBackhaul/ConnectionPreparation)  
- [MediatorManager](https://github.com/openBackhaul/MediatorManager)  
- [LinkIdIntoLtpWriter](https://github.com/openBackhaul/LinkIdIntoLtpWriter)  
- [MicroWaveDeviceGatekeeper](https://github.com/openBackhaul/MicroWaveDeviceGatekeeper)  // (to turn performance-monitoring on; to confirm if really necessary)
- [PerformanceManagement](https://github.com/openBackhaul/PerformanceManagement)  
- [MicroWaveDeviceInventory](https://github.com/openBackhaul/MicroWaveDeviceInventory)  
- ODL Controller

### Resources
- [Specification](./spec/)
- [TestSuite](./testing/)
- [Implementation](./server/)

### Comments
./.
