<div align="center">

<!-- Replace with your actual logo URL once hosted -->
<img src="https://github.com/user-attachments/assets/14668cde-4637-4d83-b886-7dee6fe0d177" alt="RosFit" width="120" />

# RosFit

**Open-source control plane for robots and IoT devices.**

Self-Hostable | RosFit Cloud | ROS2-native

[![Website](https://img.shields.io/badge/Website-rosfit.io-000?style=flat-square)](https://rosfit.io)
[![Docs](https://img.shields.io/badge/Docs-docs.rosfit.io-000?style=flat-square)](https://docs.rosfit.io)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue?style=flat-square)](https://github.com/rosfit/rosfit/blob/main/LICENSE)

</div>

---

## Why RosFit

Every robotics and IoT team rebuilds the same infrastructure — telemetry pipelines, live maps, remote control, OTA updates. We packaged it into one open-source platform you can run on your own hardware, in your own network.

- **Self-hosted first** — `docker compose up` and you're live in 10 minutes
- **ROS2-native** — first-class support for DDS topics, SLAM, and teleoperation
- **Cloud-optional** — switch to RosFit Cloud when you want managed hosting, switch back any time
- **No vendor lock-in** — Apache 2.0, your data, your hardware

## Quick start

```bash
git clone https://github.com/rosfit/rosfit
cd rosfit
docker compose up -d
```

## Repositories

| Repo | What it is |
|---|---|
| [`rosfit`](https://github.com/rosfit/rosfit) | The platform — dashboard, API, and worker. Run with Docker Compose. |
| [`rosfit-ros`](https://github.com/rosfit/rosfit-ros) | ROS2 packages — agent, messages, launch files. Install on your robot. |
| [`rosfit-python`](https://github.com/rosfit/rosfit-python) | Python SDK and CLI. `pip install rosfit` |
| [`docs`](https://github.com/rosfit/docs) | Documentation source for [docs.rosfit.io](https://docs.rosfit.io) |

## Built for

* 🏭 **Industrial operators** running robots where data can't leave the premises
* 🌾 **Agricultural & research teams** in regulated industries
* 🚀 **Robotics startups** that want to ship the robot, not the dashboard
