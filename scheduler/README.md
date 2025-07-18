# Scheduler Components

This directory contains scheduler implementations and tools for the AI-OS project.

## SCX (Sched-Ext)

The `scx` subdirectory contains the sched-ext project, which provides extensible scheduling capabilities for Linux using BPF.

### Building

To build everything (schedulers and tools):

```bash
make
```

To build all SCX schedulers (C and Rust) and copy binaries to `sche_bin/`:

```bash
make build
```

To build only C schedulers:

```bash
make build-c
```

To build only Rust schedulers:

```bash
make build-rust
```

To build tools (scx_loader, scxctl, scxtop) and copy to `tools/`:

```bash
make build-tools
```

To generate documentation for all schedulers in `sche_description/`:

```bash
make doc
```

To clean build artifacts:

```bash
make clean
```

To update the SCX submodule:

```bash
make update
```

### Tools

The following tools are built and available in the `tools/` directory:

- **scx_loader**: Service to manage sched_ext schedulers
- **scxctl**: Command-line tool to control and monitor schedulers
- **scxtop**: Real-time scheduler statistics viewer

### Available Schedulers

SCX includes several scheduler implementations:
- scx_simple: A simple scheduler example
- scx_central: Central scheduling algorithm
- scx_flatcg: Flattened cgroup scheduler
- scx_lavd: LAVD (Latency-Aware Virtual Deadline) scheduler
- scx_layered: Layered scheduler with priority tiers
- scx_nest: Nested scheduling implementation
- scx_pair: Pair-based scheduler
- scx_qmap: Queue-map based scheduler
- scx_rlfifo: Real-time FIFO scheduler
- scx_rusty: Rust-based scheduler implementation
- scx_userland: Userspace-driven scheduler

### Requirements

- Linux kernel with sched-ext support
- Rust toolchain
- Cargo
- Clang/LLVM for BPF compilation
- libbpf development headers

### Usage

After building, the schedulers can be found in `scx/scheds/rust/scx_*/target/release/`.

Example usage:
```bash
sudo ./scx/scheds/rust/scx_simple/target/release/scx_simple
```

For more information, see the [SCX project documentation](https://github.com/sched-ext/scx).