# 🦀 Linux Process Manager (Rust)

![Rust](https://img.shields.io/badge/Made_with-Rust-orange?style=for-the-badge&logo=rust)
![Platform](https://img.shields.io/badge/Platform-Linux-blue?style=for-the-badge&logo=linux)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

A high-performance, CLI-based process management tool engineered in **Rust**. This tool provides granular control over Linux processes, focusing on real-time resource monitoring, automated alerts for system bottlenecks, and user-specific configuration profiles.

> **Note:** Developed as a systems programming project to explore memory safety and concurrency in an OS context.

---

## 🚀 Key Features

### 1. Real-Time Resource Tracking
* **CPU & Memory Monitoring:** Live tracking of resource consumption for active processes.
* **Process Introspection:** deeply inspects process states and metadata directly from the `/proc` filesystem.

### 2. Automated Alert System
* **Resource-Draining Detection:** The system automatically flags processes that exceed defined thresholds (e.g., >80% CPU usage or high memory leaks).
* **User Alerts:** visual notifications in the terminal when a process is degrading system performance.

### 3. Custom User Profiles
* **Configurable Environments:** Supports creating distinct profiles for different users or use-cases (e.g., `Gaming-Mode`, `Dev-Mode`).
* **Custom Thresholds:** Each profile allows for unique alert settings and tracking intervals.

---

## 🛠️ Tech Stack

* **Language:** Rust
* **Core Concepts:**
    * Systems Programming & Memory Safety
    * File I/O (parsing `/proc`)
    * Concurrency & Threading
    * Data Structures (Vectors, HashMaps for process tables)

---

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

```Bash
cargo run
To load a specific user profile (e.g., for strict monitoring):
```
```Bash
cargo run -- --profile strict_monitor.toml
```
## 🎥 See it in Action
Watch the full system demonstration, including the alert system and context switching in real-time.

## 📖 Architecture & Design
For a deep dive into the system's design choices, including the PCB structure, memory safety guarantees, and scheduling analysis, please read the full technical report:

## 📄 Read the ProcSentinel Technical Report (PDF)

Design Highlight: The system uses a RefCell pattern to manage shared state across threads while adhering to Rust's strict borrowing rules.

## 🔮 Roadmap & Future Improvements
[ ] GUI Dashboard: Implement a TUI (Text User Interface) using ratatui for better visualization.

[ ] Network Monitoring: Add socket tracking to identify processes consuming high bandwidth.

[ ] Daemon Mode: Allow the tool to run in the background as a systemd service.

