# 🦀 Linux Process Manager (Rust)

![Rust](https://img.shields.io/badge/Made_with-Rust-orange?style=for-the-badge&logo=rust)
![Platform](https://img.shields.io/badge/Platform-Linux-blue?style=for-the-badge&logo=linux)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

A high-performance, CLI-based process management tool engineered in **Rust**.  
Provides granular control over Linux processes with real-time monitoring, automated alerts, and user-specific profiles.

> **Note:** Developed as a systems programming project focusing on memory safety and concurrency.

---

## 🚀 Key Features

### 1. Real-Time Resource Tracking
- **CPU & Memory Monitoring:** Live tracking of active processes
- **Process Introspection:** Reads process metadata directly from `/proc`

### 2. Automated Alert System
- **Resource Threshold Detection:** Flags processes exceeding limits (e.g., >80% CPU)
- **Terminal Alerts:** Visual warnings when system performance degrades

### 3. Custom User Profiles
- **Configurable Modes:** `Gaming-Mode`, `Dev-Mode`, etc.
- **Per-Profile Thresholds:** Custom alert rules and intervals

---

## 🛠️ Tech Stack

- **Language:** Rust
- **Core Concepts:**
  - Systems Programming & Memory Safety
  - File I/O (`/proc` parsing)
  - Concurrency & Threading
  - Data Structures (Vectors, HashMaps)

---

## 💻 Usage

### Prerequisites
- Rust & Cargo installed
- Linux Environment (WSL2 or Native Linux)

### Installation
```bash
git clone https://github.com/BeTechBo/Linux-Process-Manager.git
cd Linux-Process-Manager
cargo build --release
Running the Tool
Interactive mode:

bash
Copy code
cargo run
Load a specific user profile:

bash
Copy code
cargo run -- --profile strict_monitor.toml
🎥 Demo
Watch the full system demonstration showcasing:

Alert system

Context switching

Real-time monitoring

📖 Architecture & Design
A deep dive into:

PCB structure

Memory safety guarantees

Scheduling analysis

📄 ProcSentinel Technical Report (PDF)

Design Highlight:
Uses RefCell for shared mutable state across threads while respecting Rust’s borrowing rules.

🔮 Roadmap
 TUI Dashboard (ratatui)

 Network Monitoring (socket tracking)

 Daemon Mode (systemd service)
