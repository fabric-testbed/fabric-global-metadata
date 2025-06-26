# FABRIC Global Meta Data Repository

This repository provides structured configuration and metadata used across the FABRIC testbed, including by tools such as [FABlib](https://github.com/fabric-testbed/fabrictestbed-extensions), the FABRIC Portal, and other services that rely on up-to-date infrastructure information.

## Contents

### 1. `facility_ports.json`
Describes the set of known Facility Ports (FPs) at various FABRIC-connected sites, including:
- Port name
- Description

**Example Entry**:
```json
{
  "RENC-BEN": {
    "description": "BEN at RENCI"
  }
}
```
### 2. `os_images.json`
Contain information about the supported OS images across FABRIC sites, including:

Example Format:
```
{
  "default_centos8_stream": {
    "description": "CentOS 8 Stream (default install)",
    "default_user": "centos"
  }
}
```
## Usage
These files are meant to be consumed as remote configuration sources via:
- Python (FABlib plugins)
- Portal UI
- Or internal system scripts/tools

To fetch and use:
```
import requests
fp_data = requests.get(
    "https://raw.githubusercontent.com/fabric-testbed/fabric-global-metadata/main/facility_ports.json"
).json()
```
## License
This repository is maintained under the MIT License.
