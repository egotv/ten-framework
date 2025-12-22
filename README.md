Welcome to the TEN Framework, an open-source framework for real-time multimodal conversational AI. This branch (`dev`) is our primary development environment.

## Branching Strategy

- **`main`**: Mirror of the upstream TEN Framework. Use this for pulling in framework updates.
- **`dev`**: Our development branch. All feature work and local setup should be done here.

## Prerequisites

Ensure you have the following installed on your host machine:

- **Docker & Docker Compose**: For containerized development.
- **Node.js**: v18+ (LTS).
- **Python**: 3.10.14 (Required version).

## Getting Started

### 1. Clone & Initialize Submodules

Clone the repository and initialize the submodules, including the `ego-chat-app-ten` extension.

```bash
git clone https://github.com/TEN-framework/ten-framework.git
cd ten-framework
git checkout dev
git submodule update --init --recursive
```

### 2. Configure Environment

```bash
cd ai_agents
cp .env.example .env
# Edit .env with your keys
```

### 3. Setup Development Environment

#### Option A: Dev Containers Extension (Recommended)

1. Ensure the **Dev Containers** extension is installed in **Cursor** or any editor that you are using.
2. Open the project folder in **Cursor**.
3. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS) and select **"Dev Containers: Reopen in Container"**.
4. Once the container is built and loaded, open the integrated terminal.
5. Navigate to any example agent app and start it:
   ```bash
   cd ai_agents/agents/examples/ego-chat-app-ten
   task install
   task run
   ```

#### Option B: Manual Setup

If you prefer using the terminal:

1. **Configure Environment**:

   ```bash
   cd ai_agents
   cp .env.example .env
   # Edit .env with your keys
   ```

2. **Start Containers**:

   ```bash
   docker compose up -d
   ```

3. **Enter Container & Run Agent**:

   ```bash
   docker exec -it ten_agent_dev bash

   # Inside the container:
   cd agents/examples/ego-chat-app-ten
   task install
   task run
   ```

## Agent Examples

The following examples are available in `ai_agents/agents/examples`:

- **ego-chat-app-ten**: Our custom conversational agent based on the voice-assistant--with-turn-detection example.
- **other-examples**: TEN's original example apps that they built.

| Interface         | URL                                              |
| :---------------- | :----------------------------------------------- |
| **TMAN Designer** | [http://localhost:49483](http://localhost:49483) |
| **Agent UI**      | [http://localhost:3000](http://localhost:3000)   |

---

<div align="center">
  <p>Refer to the <a href="https://theten.ai/docs">Official Documentation</a> for advanced configuration.</p>
</div>
