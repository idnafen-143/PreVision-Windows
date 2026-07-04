# PreVision Desktop — Intelligent Solar & Energy Storage Sizing App (Windows Edition)

PreVision Desktop brings the power of our industrial-grade, full-stack solar PV and battery energy storage sizing application directly to your local workstation. Packaged as a lightweight, zero-dependency Windows executable (`.exe`), it allows engineers, installers, and project developers to perform end-to-end site audits, electrical sizing, and protection coordination locally, with or without a continuous internet connection.

This repository contains the distribution assets, local configuration profiles, and compilation utilities for the standalone PC version.

---

## 🌟 Desktop-Specific Features

* **Zero Dependencies:** Runs natively on Windows without requiring Node.js, Docker, or external runtimes.
* **Hybrid Connectivity Engine:** Seamlessly fetches real-time meteorological data (NASA, PVGIS, Open-Meteo) when online, and automatically falls back to built-in offline climate tables when working in remote field environments.
* **Local Workspace Preservation:** Keeps all sizing configurations, calculated single-line diagrams, and client bills of materials (BOM) local to your machine.
* **Instant Deployment:** A true portable app—no installation required. Simply run the executable alongside its localized asset delivery folder.

---

## 📁 PC Distribution Structure

Ensure that the executable and its compiled frontend directory remain synchronized in the same workspace directory:

```text
├── PreVision.exe          # Lightweight native Windows server launcher
├── dist/                  # Local distribution folder containing compiled SPA assets
│   ├── index.html         # Main UI entry point
│   ├── assets/            # Bundled UI components, SVG graphs, and sizing calculation scripts
│   └── offline_climate/   # Fallback meteorological dataset for offline sizing
└── README.txt             # End-user troubleshooting and quick-start guide

```

---

## 🚀 Quick Start Guide

### 1. Launching the App

1. Download and extract the release package. Ensure `PreVision.exe` and the `dist` folder live in the same directory.
2. Double-click `PreVision.exe`.
3. A command console will initialize the local server, and your default web browser will automatically open to `http://localhost:3000`.

> 💡 **Tip:** If your browser fails to launch automatically, simply copy and paste `http://localhost:3000` into any modern browser.

### 2. Bypassing Windows SmartScreen

Because this independent build is distributed outside the Microsoft App Store without a commercial code-signing certificate, Windows SmartScreen may present a blue warning window on the first launch:

1. Click **"More info"**
2. Click **"Run anyway"** *(Windows will remember this preference and will not prompt you again for this release).*

### 3. Closing the Application

To shut down the local sizing engine and release the networking port, simply **close the black console window**.

---

## 🛠️ Troubleshooting & Port Management

* **Port Conflicts (*Could not find a free port*):** PreVision searches for an open local port between 3000 and 3019. If you receive a port conflict error, another application (such as a local development server) is occupying those ports. Free up the ports or restart your workstation.
* **Antivirus False Positives:** Heuristic engines occasionally flag unsigned, independently built binaries. The core, open-source engine logic can be audited at any time in our primary web repository. If blocked silently, try right-clicking the file and selecting **“Run as administrator”**.
* **Network Isolation:** While the app is perfectly optimized for offline use, geocoding coordinates via city names requires an internet handshake. If offline, pass your exact target latitude and longitude directly into the system parameters to trigger the mathematical sizing models manually.
