# board_manager_files
The board manager files for CH32 development boards

## Python for UF2

The latest platform entry depends on `ch32-community:pqt-python3` version
`1.0.1-base-3a57aed-1`. Keep this dependency in future platform releases that use
the Python-based UF2 recipes in `arduino_core_ch32`.

This tool reuses the published archives, SHA-256 checksums, and sizes from
[Arduino-Pico's package index](https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json).
The archives come from [pico-quick-toolchain](https://github.com/earlephilhower/pico-quick-toolchain):

- Windows: bundled Python 3.7.2, with no system Python or PATH setup required.
- macOS: bundled Python for Intel and Apple Silicon.
- Linux: a small launcher that invokes system `python3`; install Python 3
  through the distribution's package manager if needed.

The dependency is registered under `ch32-community`, so users do not need to
install the RP2040 core or add its package index. The core's UF2 recipes refer
to `{runtime.tools.pqt-python3-1.0.1-base-3a57aed-1.path}/python3`.

Merge this index update before releasing the matching core recipes. Existing
installations need a package reinstall after refreshing the index to acquire
the new tool; copying core files alone does not install dependencies. Earlier
platform entries and the existing release archives/checksums are unchanged.
