# egpuctl

A quick shell script to change gpu drivers for direct VM passthrough.


# VERY Helpful Resources

- [ArchWiki QEMU](https://wiki.archlinux.org/title/QEMU)
- [ArchWiki PCI Passthrough](https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF)
- [Arch Wiki NVIDIA](https://wiki.archlinux.org/title/NVIDIA)

# Getting Started

1. Clone the repo
2. Allow execution (`chmod +x egpuctl`)

# Usage

The options are very bare bones. 

- `-v / --to-vfio` sets an override pointer such that the VM can access the raw PCI device 
- `-n / --to-host` removes the override pointer (or does nothing if there isn't one set already)

# Examples 

## Example 1: Set up for VM passthrough

Typically this will not require a reboot, but YMMV.

`./egpuctl --to-vfio`

## Example 2: Undo overrides, use the GPU with the base system

Some systems are finnicky with this, I strongly suggest rebooting when trying to use the gpu with the base system again.

`./egpuctl --to-host`

# Test Setup

- Make/Model: Framework 13 / 12th Gen intel
- Distro: Arch
- Kernel: 6.1.37-1-lts
- eGPU Enclosure: Akitio Node Titan
- GPU: NVIDIA 1070ti
- VM OS: Windows 11

# Known Issues / TODO

- [ ] Does not default to help screen
