# network-config

## Description
network-config controller

## Usage

### Fetch the package
`kpt pkg get REPO_URI[.git]/PKG_PATH[@VERSION] network-config`
Details: https://kpt.dev/reference/cli/pkg/get/

### View package content
`kpt pkg tree network-config`
Details: https://kpt.dev/reference/cli/pkg/tree/

### Apply the package
```
kpt live init network-config
kpt live apply network-config --reconcile-timeout=2m --output=table
```
Details: https://kpt.dev/reference/cli/live/
