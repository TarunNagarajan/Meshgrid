# Meshgrid: 100-Day Build Plan

Meshgrid is a lightweight, scalable software framework implementing a Message-Passing Tile Grid (NoC-inspired) system. It facilitates efficient inter-tile communication via message passing, enabling research and development of distributed, parallel computing architectures on low-power embedded platforms.

| Day | Build Task | Learning Objective |
|-----|------------|--------------------------------------|
| 1 | Set up repo, create project structure | Learn how to design a modular C++ project: `src/`, `include/`, `tests/`, `examples/`. Deeply understand why separation of concerns matters in large system design. |
| 2 | Set up CMake + build system | Learn to write `CMakeLists.txt` from scratch. Understand targets, headers, linking, and Raspberry Pi toolchain cross-compilation. |
| 3 | Design `Tile` class interface | Learn C++ class design principles: interfaces, encapsulation, separation of logic (compute, state, communication). |
| 4 | Implement Tile lifecycle (init/run/exit) | Learn about embedded system software loops and main execution cycles (e.g., idle loops, event polling). |
| 5 | Design `Grid` manager interface | Learn top-down system coordination design: grid boot-up, topology handling, tile registration. |
| 6 | Implement grid creation and boot sequence | Study system boot protocols and distributed system startup sequences. |
| 7 | Implement tile-to-tile message protocol v0 | Learn about synchronous/asynchronous message-passing models, queues, and mailbox design. |
| 8 | Add `Mailbox` class for message buffering | Deep dive into producer-consumer queues, thread-safe design (mutex, spinlock alternatives for RPi). |
| 9 | Add grid config file parsing (YAML/JSON) | Learn to parse config files and map grid layouts dynamically using C++ parsers. |
| 10 | Design visual CLI debug interface | Study text-based rendering tools (ncurses), or simple logging with color-coded logs for tiles. |
| 11 | Write first test: spawn grid + run tiles | Learn unit test design for embedded simulators. Understand test harness design. |
| 12 | Add event loop inside tile (`on_message`, `on_tick`) | Learn about event-driven architecture, function dispatch, and callbacks in embedded systems. |
| 13 | Add example: broadcast "hello world" to neighbors | Learn tile addressing, 2D neighbor discovery (north/south/east/west), and routing table basics. |
| 14 | Add message handler switch table | Learn about function pointer tables and dynamic dispatch in C++. |
| 15 | Add tests for mailbox and grid boot | Understand how to write coverage-focused tests for message-driven systems. |
| 16 | Refactor tile/grid/comm to `include/` headers | Practice modularization and forward declarations. Learn header hygiene. |
| 17 | Add simulation time control (ticks, cycles) | Study hardware tick clocks, global time vs local time, and discrete event sim concepts. |
| 18 | Implement tile-to-grid reporting messages | Learn about command-response models in networks and logging mechanisms. |
| 19 | Add topology visualizer (ASCII) | Learn 2D text rendering for topology overlays and node state coloring. |
| 20 | Document interfaces in `README.md` | Practice software documentation principles and auto-doc tooling (e.g., Doxygen). |
| 21 | Add basic load balancer algorithm (round-robin) | Study load balancing strategies in tiled NoCs: RR, weighted, queue-aware. |
| 22 | Add CLI args for simulation runtime | Learn argument parsing, flags, and how to cleanly expose runtime configs. |
| 23 | Add stats collector module (msgs/sec, utilization) | Study metrics instrumentation, performance counters, logging throughput. |
| 24 | Test tile drop/rejoin behavior | Learn failure tolerance principles and grid reconfiguration upon node loss. |
| 25 | Add timeout & retry logic to mailbox | Learn embedded retransmission protocols and how to model reliability. |
| 26 | Simulate 3x3 grid with traffic | Learn to visualize live systems and interpret performance/debug logs. |
| 27 | Add task queues to tile | Study cooperative multitasking within embedded tiles (queue of commands). |
| 28 | Add message priorities | Learn message priority queues and how to implement fair vs strict priority models. |
| 29 | Write `tile_test.cpp` with multiple cases | Practice test-driven design with unit+integration tests. |
| 30 | Midpoint refactor: decouple comm logic fully | Revisit separation of transport vs compute logic in embedded NoCs. |
| 31 | Add support for toroidal wrapping topology | Study grid boundary conditions and wrapping edge cases (common in 2D meshes). |
| 32 | Implement simple FSM in tiles | Learn finite state machines in embedded contexts (state enums, transitions, handlers). |
| 33 | Add cellular automata demo (Conway's Game of Life) | Learn local neighbor state computation and distributed updates. |
| 34 | Add broadcast and multicasting capabilities | Study different messaging scopes: unicast, multicast, broadcast. |
| 35 | Implement heartbeat ping/pong between tiles | Learn health monitoring protocols (periodic keepalives). |
| 36 | Add ACK/NACK support to messages | Study reliable vs unreliable message models. |
| 37 | Add grid-level task distributor module | Learn central scheduling in distributed mesh systems. |
| 38 | Integrate with SDL2 for GUI visualizer (optional) | Learn SDL2 basics: rendering grid state, node activity, and stats. |
| 39 | Add metrics logger (CSV export) | Practice profiling and structured output for benchmarking. |
| 40 | Simulate dynamic grid reconfiguration | Study resilience strategies in mesh networks. |
| 41 | Add distributed barrier sync primitive | Learn about distributed synchronization models (barriers, locks, semaphores). |
| 42 | Design mailbox as ring buffer | Learn about circular buffers and zero-copy design. |
| 43 | Study RPi3 hardware and MMU basics | Learn memory-mapped I/O, peripheral access, and ARM MMU. |
| 44 | Build minimal RPi3 toolchain (cross-compile) | Learn cross-compilation, linker scripts, and setting `CFLAGS`/`LDFLAGS`. |
| 45 | Port core Meshgrid engine to RPi3 (headless) | Learn RPi-specific build configs, wiring, and terminal-only interfacing. |
| 46 | Add logging over UART | Study serial communication and UART logging on embedded boards. |
| 47 | Run Meshgrid on 2+ RPis via Ethernet | Learn physical deployment, SSH-based automation, static IP setup. |
| 48 | Add stress-test mode (many messages/sec) | Learn about throughput limits, bottlenecks, and saturation handling. |
| 49 | Profile memory usage per tile | Study embedded memory tracing and leak detection tools. |
| 50 | Document all internal protocols in `/docs` | Learn good systems protocol spec writing practices. |
| 51–60 | Build real distributed demo app: distributed sorting |
| 51 | Add array partitioning into tiles | Learn data distribution techniques across tile-local storage |
| 52 | Implement local bubble/quick sort | Study basic embedded-friendly sorting implementations |
| 53 | Add neighbor-to-neighbor comparison + exchange | Learn about bitonic sorting networks, neighbor comparison-exchange |
| 54 | Add round-based control (global ticks for sort stages) | Practice round synchronization in distributed systems |
| 55 | Add visualization of sort progress | Practice progress monitoring in distributed settings |
| 56 | Add fault-injection and recovery during sort | Learn testing for robustness in edge-case behavior |
| 57 | Tune sort memory layout (cache-optimal layout) | Study memory coalescing and spatial locality |
| 58 | Add stats on sort time, messages, efficiency | Learn metrics for distributed algorithm benchmarking |
| 59 | Test on full 5x5 grid | Practice grid configuration scaling and debugging |
| 60 | Write mini paper/summary on sorting demo | Learn to write system design docs, microbenchmarks |
| 61–70 | Build second demo: message-passing BFS traversal |
| 71–80 | Add grid self-healing protocol |
| 81–90 | Add simulated DVFS support + energy logging |
| 91–100 | Polish, document, and benchmark full system |
