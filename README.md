<p align="center">
  <img src="https://raw.githubusercontent.com/rosfit/.github/main/assets/rosfit-logo.png" alt="RosFit" width="200" />
</p>

<h3 align="center">Fit your ROS2 robot into Cloud and control it from anywhere.</h3>

<p align="center">
  Open-source bridge & management platform for connecting ROS2 robots to the cloud.<br/>
  Self-hosted with Docker Compose. Zero custom code. Works in minutes.
</p>

<p align="center">
  <a href="https://github.com/rosfit/rosfit">Get Started</a> · <a href="https://rosfit.dev">Docs</a> · <a href="https://github.com/rosfit/rosfit/issues">Report Bug</a>
</p>

---

### The problem

- Connecting a ROS2 robot to the cloud takes **months** of custom work — MQTT bridges, auth, dashboards, OTA pipelines, all built from scratch every time. 
- Existing platforms cost $200+/robot/month and lock you into their ecosystem.

### What RosFit does

One YAML config and your robot become managable via cloud.


### Architecture

```mermaid
graph LR
    subgraph Robot
        R1[ROS2 Nodes] <-->|topics| B[RosFit Bridge]
    end

    B <-->|MQTT TLS| E[EMQX Broker]

    subgraph RosFit-Cloud
        E --> H[Message Handler]
        H --> PG[(TimescaleDB)]
        H --> S3[(MinIO)]
        E <--> SH[Shadow Service]
        SH <--> RD[(Redis)]
        API[Backend] --> PG
        API --> RD
        API --> S3
        DASH[Dashboard] --> API
        DASH <-->|WebSocket| E
    end
```

### MVP features

| Feature | What it does |
|---------|-------------|
| **MQTT Bridge** | Bridges ROS2 topics to MQTT with a YAML config — publish, subscribe, throttle |
| **Real-time Dashboard** | See all robots, status, telemetry charts — live via WebSocket |
| **Remote Commands** | Send commands from REST API or dashboard, get structured responses |
| **Device Shadow** | Desired vs reported config state — change robot settings without SSH |
| **OTA Updates** | Upload firmware, deploy to fleet with rollback on failure |
| **Token Auth** | JWT-based device and user authentication with per-device topic isolation |

### Roadmap

* **Phase 1** — Bridge + Dashboard + Commands *(in progress)*
* **Phase 2** — Shadow + OTA + Telemetry charts
* **Phase 3** — TLS, RBAC, alerts, webhooks
* **Phase 4** — RosFit Cloud (managed SaaS at `rosfit.dev`)
