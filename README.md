# mavlink_shared

[![Build with Alire](https://github.com/reznikmm/mavlink_shared/actions/workflows/alire.yml/badge.svg)](https://github.com/reznikmm/mavlink_shared/actions/workflows/alire.yml)
[![Alire](https://img.shields.io/endpoint?url=https://alire.ada.dev/badges/mavlink_shared.json)](https://alire.ada.dev/crates/mavlink_shared.html)

> MAVLink -- Micro Air Vehicle Message Marshalling Library.

This repository provides an Ada library for MAVLink, a lightweight
messaging protocol for communicating with drones and other unmanned
vehicles. The library was generated using the MAVLink code generator,
customized for the Ada programming language. The package is compatible
with the Alire package manager, enabling easy integration into Ada
projects.

## Overview

The MAVLink Ada library allows for efficient and reliable message
marshalling and unmarshalling, making it suitable for embedded applications
and ground control software. With support for multiple message types,
the library offers a robust solution for developing applications that
require communication with MAVLink-compliant devices. Features

- Generated MAVLink 1.0 and 2.0 protocol support,
  [Common Message Set](https://mavlink.io/en/messages/common.html)
- Compatible with the Ada bareboard profiles for real-time applications
- Modular structure for easy integration with existing Ada projects
- Supports message serialization and deserialization

## Installation

This auxilary package contains a few packages shared between `v1` and `v2`
MAVLink versions. It is not expected to be used directly.
Instead use required MAVLink dialect/version:

* [mavlink_common](https://github.com/reznikmm/mavlink_common/tree/v1)
* [mavlink_common_v2](https://github.com/reznikmm/mavlink_common/tree/v1)
* [mavlink_ardupilotmega](https://github.com/reznikmm/mavlink_ardupilotmega/tree/v1)
* [mavlink_ardupilotmega_v2](https://github.com/reznikmm/mavlink_ardupilotmega/tree/v2)

## Mavlink commit id

The code was generated from `b1fb5a1` commit of
the [mavlink](https://github.com/mavlink/mavlink) repo.
And `a5812a8` from [pymavlink](https://github.com/ardupilot/pymavlink) repo.
I used this steps:

```shell
python -m venv venv
source venv/bin/activate
git clone --depth=1 https://github.com/ardupilot/pymavlink/
git clone --depth=1 https://github.com/mavlink/mavlink
MDEF=$PWD/mavlink/message_definitions python -m pip install pymavlink

python3 -m pymavlink.tools.mavgen --lang=Ada --wire-protocol=2.0 \
  --output=generated mavlink/message_definitions/v1.0/common.xml
```

## Contributing

Contributions are welcome!
Please [open an issue](https://github.com/reznikmm/mavlink_shared/issues)
to discuss potential improvements or submit a pull request.

## License

This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file for more details.
