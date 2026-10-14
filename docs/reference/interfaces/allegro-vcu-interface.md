---
myst:
  html_meta:
    description: Reference documentation for allegro-vcu, which lets a snap use snapd to access the Allegro Video Core Unit through its hardware control module.
---

(interfaces-allegro-vcu-interface)=
#  allegro-vcu interface

The `allegro-vcu` interface enables access to the Allegro Video Core Unit, using a kernel module which directly controls hardware on the device.

This interface is intended primarily to be used with {ref}`Ubuntu Core <ref-glossary_ubuntu-core>`.


## Developer details

**Auto-connect**: no

Xilinx offers IP for their devices to decode/encode video streams, by using `/dev/allegroDecodeIP` and `/dev/allegroIP` devices.

These operations should be considered privileged since the driver assumes trusted input, therefore require manual connection.

### Code examples

The test code can be found in the snapd repository: https://github.com/canonical/snapd/blob/master/interfaces/builtin/allegro_vcu_test.go

The source code for the interface is in the snapd repository:[ https://github.com/canonical/snapd/blob/master/interfaces/builtin/allegro_vcu.go](https://github.com/canonical/snapd/blob/master/interfaces/builtin/allegro_vcu.go)
