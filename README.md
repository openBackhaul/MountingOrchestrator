# MountingOrchestrator  

### Location  
The MountingOrchestrator is part of the OperationSupport.  

### Description  
The MountingOrchestrator application manages the mounting of new, modified or substituting devices.  

A prerequisite for any operation to be performed is that the IP address provided as input is responsive to ping and protocol tests.  
(It is a design goal to preclude the creation of mount points for future use. So, any mount point that is not in _connected_ state undoubtedly represents some undesirable situation.)  

While creating or modifying a mount point, existing mount points of other devices (different mountName) must be protected from any harm, regardless of their state (e.g. _connected_ or _connecting_).  
This includes not modifying or deleting mount points of other devices during the process.  
Due to the required uniqueness, this also means that the IP address provided as input cannot be used to create or modify a mount point if it is already being used for a mount point of another device (would require devices with native NETCONF interface anyway).  

In general, mount points that are in _connected_ state must not be damaged.  
This includes not modifying or deleting operational mount points, regardless of whether it is the one addressed in the services request, or another.  
Despite the idempotence of the mounting service on the outside, even overwriting an existing mount point with identical values is prevented as it would lead to status changes that will cause deletion of the device from the cache.  

The MountingOrchestrator coordinates the mounting of a new device in the controller and it requests the MediatorManager for provisioning of a mediator process, if required for the respective device type. For each device kind, the MountingOrchestrator knows whether it is needed to instantiate a Mediator or the device directly supports a NETCONF interface.  

The MountingOrchestrator is able to manage a list of potential controllers.

The MountingOrchestrator shall offer the following functionalities on its first release:

- Provide list of mount points
- Adding a new mount-point
- Editing an existing mount point (if not in _connected_ state)
- Deletion of a mount point (if not in _connected_ state)
- Response indicating that the link-endpoint is ready for a link-acceptance-test
- Provide list of controllers with respective status
- Adding a new controller
- Editing status of an existing controller
- Deletion of a controller

The MountingOrchestrator shall potentially offer following functionalities in future releases:

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
