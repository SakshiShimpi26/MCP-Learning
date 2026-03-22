# 🚀 Model Context Protocol (MCP) Server with FastMCP

## 📌 Overview

The **Model Context Protocol (MCP)** is a standardized way for AI systems to interact with external tools, data sources, and services.

Traditionally, AI systems operate in isolation — they rely only on the context provided in a prompt. This leads to fragmented workflows where users must manually copy data between systems.

MCP solves this by enabling a structured communication layer between AI clients (like Claude Desktop) and external systems.

---

## ❗ The Problem MCP Solves

With the rise of LLMs, AI adoption evolved in multiple stages:

* Initial experimentation (creative prompts, exploration)
* Professional usage (debugging code, summarizing documents)
* Integration into tools (Copilot, AI assistants in apps)

However, a major issue emerged:

### 🔴 Fragmented Context

* AI in one tool cannot access data from another
* Developers manually copy-paste large amounts of data
* Context assembly becomes time-consuming

👉 This leads to inefficiency, often called **"copy-paste hell"**

---

## 💡 The Core Idea of MCP

MCP introduces a unified way for AI systems to interact with external capabilities.

Instead of building custom integrations for every tool:

* AI connects to MCP servers
* MCP servers expose capabilities in a standard format

### 🔁 Simplified Architecture

```
        AI Client (Claude)
               ↓
        MCP Server
               ↓
        External Tools / Functions
```

---

## 🧠 Key Concepts

### 1. Client–Server Model

* **Client**: AI application (e.g., Claude Desktop)
* **Server**: Your MCP server implementation

The client sends structured requests, and the server executes them.

---

### 2. MCP Primitives

MCP defines three fundamental building blocks:

#### 🛠️ Tools

Executable functions that the AI can call

#### 📄 Resources

Structured data that the AI can read

#### 🧾 Prompts

Reusable templates that guide AI behavior

---

### 3. Communication Layer

MCP uses **JSON-RPC 2.0** as its communication protocol.

This allows remote function execution in a structured format.

Example idea:

```
Request → "Run function with parameters"
Response → "Here is the result"
```

---

## ⚖️ MCP vs Traditional Integrations

### Without MCP

* Each AI tool integrates separately with each service
* Complexity grows as N × M
* Different authentication and formats

### With MCP

* Standardized interface
* Scalable integrations (N + M)
* Reduced maintenance

---

## 🏗️ Project Implementation

This project demonstrates a basic MCP server using **FastMCP**.

### 📂 Structure

```
.
├── main.py
├── fastmcp.json
├── pyproject.toml
├── README.md
```

---

## ⚙️ Setup

### 1. Install dependencies

```
pip install uv
```

### 2. Initialize project

```
uv init
```

### 3. Install FastMCP

```
uv add fastmcp
```

---

## 🧪 Running the Server

### Development mode

```
uv run fastmcp dev main.py
```

### Production run

```
uv run fastmcp run main.py
```

---

## 🔗 Connecting with Claude Desktop

```
uv run fastmcp install claude-desktop main.py
```

After installation, the tools exposed by the server become available inside Claude Desktop.

---

## 🛠️ Example Tools Implemented

The server exposes basic tools to demonstrate MCP functionality.

### Dice Roll Tool

```
def roll_dice(n_dice: int = 1) -> list[int]:
```

### Addition Tool

```
def add_numbers(a: float, b: float) -> float:
```

These tools showcase how MCP enables AI to invoke external functions dynamically.

---

## 🔍 How It Works End-to-End

1. User interacts with Claude
2. Claude identifies a required action
3. MCP request is sent to the server
4. Server executes the tool
5. Response is returned to Claude

---

## 🚀 Benefits

* Decoupled architecture
* Scalable integrations
* Reduced development overhead
* Consistent communication layer
* Easier tool reuse across AI systems

---

## 🔮 Future Enhancements

This server can be extended with:

* File system access
* API integrations (GitHub, Slack, etc.)
* Database querying
* Workflow automation

---

## 📌 Conclusion

MCP represents a shift from isolated AI systems to **connected, action-capable AI**.

By implementing an MCP server, you enable AI systems to move beyond conversation and interact with real-world tools in a structured and scalable way.

---

## 🧑‍💻 Author

Sakshi Shimpi
AI/ML Engineer
