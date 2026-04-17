# System Resource Monitor

A specialized Python utility designed for real-time system diagnostics and performance tracking. This tool provides a comprehensive analysis of hardware utilization, including CPU load, memory distribution, disk availability, and network throughput.

## Core Features

- **Resource Utilization Snapshots:** Captures precise CPU, RAM (Virtual and Swap), and Disk metrics.
- **Advanced Process Ranking:** Implements a custom scoring logic to identify the top 3 resource-intensive processes by calculating the aggregate of CPU and Memory percentages.
- **Network Traffic Monitoring:** Tracks data transmission by recording total bytes sent and received.
- **Automated Data Persistence:** Supports logging system reports into structured JSON files for historical auditing and data analysis.
- **Operational Versatility:** Offers three execution modes: standard single-scan, immediate-save, and continuous monitoring with adjustable intervals.

## Technical Details

- **Language:** Python 3.x
- **Key Dependency:** `psutil` (Cross-platform process and system utilities)
- **Standard Modules:** `shutil`, `json`, `datetime`, `os`, `sys`, `time`
- **Output Format:** Professional terminal interface (CLI) and JSON object exports.


Sample Output:
================================================================================
SYSTEM STATUS REPORT | 2026-04-17 22:55:12 =========================
CPU Load:         13.2%
RAM Usage:        42.5% (Swap: 10.2%)
Disk Space:       Free: 154.20GB / Total: 465.50GB
Network I/O:      Sent: 12.45MB | Received: 85.30MB
Total Processes:  245

TOP 3 PROCESSES (CPU+RAM Score):
------------------------------------------------------------
  1 chrome                    | CPU:  8.5% | RAM:  4.2% | Score: 12.7%
  2 python3                   | CPU:  5.2% | RAM:  1.5% | Score: 6.7%
  3 vscode                    | CPU:  2.1% | RAM:  3.8% | Score: 5.9%
================================================================================
Report saved: system-report-2026-04-17_22-55-12.json

Sample JSON Report:
{
  "timestamp": "2024-01-15 14:30:25",
  "cpu_load": "23.4%",
  "top_apps": [
    {
      "rank": 1,
      "name": "chrome",
      "cpu": "12.3%",
      "ram": "45.1%"
    }
  ]
}

## Installation

Ensure you have the `psutil` library installed on your system. You can install it via pip:
```bash
pip3 install psutil
