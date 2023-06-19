# network config reconciler

The network config reconciler acts upon the `Network Config CRD`. A `Network Config CR` is applicable to a specific target indicated by the node-name key `"nephio.org/node-name"` in the CR. The reconciler uses gnmi to interact with the target device.

For any operation the nodeNameKey is looked up in the target list to retrieve the gnmi client. If no client is available the reconiciler retries.

The CR stores the desried status in the spec and the last applied configuration in the status of the CR.

For a delete operation, if the lifecycle policy is Delete the last applied configuration is deleted through gnmi from the device.

For a create/update operation the configuration differences between the last applied configuration and the new desired configuration are applied to the device using gnmi