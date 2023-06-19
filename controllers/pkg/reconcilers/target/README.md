# target reconciler

The traget reconciler acts upon the `Target CRD`. The `Target CR` contains the configuration that is applicable to connect to a device.

Right now the focus is on gnmi, but the target could be leveraged for other protocols such as netconf or REST based targets.

The target controller uses a provider model and checks if the provider is supported by the reconciler. Only if it is supported the target controller will connect to the device

it uses the secret to lookup the credentials and the address to connect to the target. Based on the information a gnmi connection is setup to the targeted device. The respective client is retained in a cache to be leeveraged by other components of the system

## open issue

secrets can change and we should use a reconcile loop for secrets