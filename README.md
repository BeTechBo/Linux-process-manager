# 🦀 Linux Process Manager (Rust)

A high-performance, CLI-based process management tool engineered from scratch in Rust. This tool provides granular control over Linux processes, focusing on real-time resource monitoring, automated alerts for system bottlenecks, and user-specific configuration profiles. 

*Note: Architected as an independent deep-dive into systems programming, focusing on implementing memory-safe concurrency and raw OS-level interactions without relying on heavy external abstractions.*

## 🚀 Key Features

* **Real-Time Resource Tracking**
    * **CPU & Memory Monitoring:** Live tracking of resource consumption for active processes.
    * **Process Introspection:** Deeply inspects process states and metadata directly from the `/proc` filesystem using raw system calls.
* **Automated Alert System**
    * **Resource-Draining Detection:** Automatically flags processes that exceed defined thresholds (e.g., >80% CPU usage or high memory leaks).
    * **User Alerts:** Visual notifications in the terminal when a process is degrading system performance.
* **Custom User Profiles**
    * **Configurable Environments:** Supports creating distinct profiles for different users or use-cases (e.g., `Gaming-Mode`, `Dev-Mode`).
    * **Custom Thresholds:** Each profile allows for unique alert settings and tracking intervals.

## 📂 Code Highlights (For Reviewers)
If you are reviewing this codebase, I recommend starting with these core logic files:
* `src/alert_manager.rs`: Contains the custom alerting logic, utilizing Rust enums and threshold tracking to manage active system states and TTL cleanups.
* `src/process_parser.rs` *(Note: update this filename to whatever actually parses /proc)*: Demonstrates file I/O and data extraction directly from Linux's virtual filesystem.

## 🛠️ Tech Stack

* **Language:** Rust
* **Core Concepts:** Systems Programming & Memory Safety, File I/O (parsing `/proc`), Concurrency & Threading, Data Structures (Vectors, HashMaps).

## 💻 Usage

### Prerequisites
* Rust & Cargo installed
* Linux Environment (WSL2 or Native Linux)

### Installation

```bash
git clone [https://github.com/BeTechBo/Linux-Process-Manager.git](https://github.com/BeTechBo/Linux-Process-Manager.git)
cd Linux-Process-Manager
cargo build --release
```


Running the Tool
To start the process manager in interactive mode:
cargo run

To load a specific user profile (e.g., for strict monitoring):
cargo run -- --profile strict_monitor.toml

🎥 Demonstration & Architecture
See it in Action: Watch the full system demonstration, including the alert system and context switching in real-time Here.

Architecture & Design: For a deep dive into the system's design choices, including the PCB structure, memory safety guarantees, and scheduling analysis, please read the full technical report Here.

🔮 Roadmap & Future Improvements
[ ] GUI Dashboard: Implement a TUI (Text User Interface) using ratatui for better visualization.

[ ] Network Monitoring: Add socket tracking to identify processes consuming high bandwidth.

[ ] Daemon Mode: Allow the tool to run in the background as a systemd service.
