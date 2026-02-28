<img width="960" height="564" alt="image" src="https://github.com/user-attachments/assets/5d66b10e-1f2a-48c6-be62-792ac5f85b88" /># 🔌 Connecting a Prebuilt MCP Server: Weather-mcp-server to MCP Client: Claude (Local)

A step-by-step guide to setting up the MCP Weather Server (TypeScript) and connecting it to Claude Desktop.

---

## Step 1 — Clone the MCP Server

```bash
git clone https://github.com/modelcontextprotocol/quickstart-resources.git
cd quickstart-resources/weather-server-typescript
```

---

## Step 2 — Install Dependencies

```bash
npm install
```

---

## Step 3 — Build the Server

```bash
npm run build
```

> ✅ This generates `index.js` inside the `build/` folder.

---

## Step 4 — Configure Claude Desktop

Open your Claude MCP config file from developer settings and add the following:

```json
{
  "mcpServers": {
    "weather": {
      "command": "C:\\Program Files\\nodejs\\node.exe",
      "args": [
        "/Users/sai/Desktop/mcp_servers/weather-server-typescript/build/index.js"
      ]
    }
  }
}
```

> ⚠️ Replace `/Users/sai/Desktop/mcp_servers` with the actual absolute path to your cloned repo's folder.

### Where is the config file?

| OS | Path |
|----|------|
| **Windows** | `%APPDATA%\Claude\claude_desktop_config.json` |

---

## Step 5 — Restart Claude

Fully quit and relaunch the Claude Desktop app to apply the changes.

---

## ✅ Verify It's Working

After restarting, confirm the `weather` server is listed.
<img width="960" height="564" alt="image" src="https://github.com/user-attachments/assets/6f5a8817-55ef-4b04-b511-e4c1e8eed531" />

---

## 📁 Project Structure (After Build)

```
weather-server-typescript/
├── build/
│   └── index.js        ← The compiled server (used in config)
├── src/
│   └── index.ts        ← TypeScript source
├── package.json
└── tsconfig.json
```

## Final Output

<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/80fbbb65-5e77-4842-b896-38c0988cd767" />
