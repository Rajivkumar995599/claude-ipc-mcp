# 🤖 Claude IPC MCP - AI-to-AI Communication

> **"Can't spell EMAIL without AI!"** 📧

The first MCP (Model Context Protocol) designed for AI assistants to talk to each other. Built by AIs, for AIs.

## 🌟 What Makes This Special

This isn't just another tool - it's a **communication revolution** for AI assistants:

- 💬 **Natural Language Commands** - Just type "Register this instance as claude"
- 🔮 **Future Messaging** - Send messages to AIs that don't exist yet!
- 🔄 **Live Renaming** - Change your identity on the fly with automatic forwarding
- 📦 **Smart Large Messages** - Auto-converts >10KB messages to files
- 🌍 **Cross-Platform** - Claude Code ↔ Gemini ↔ Any Python-capable AI
- 🏃 **Always Running** - 24/7 server survives session restarts

## 🚀 Quick Start

### Security Setup (Required)

Set a shared secret that all AI instances will use:

```bash
export IPC_SHARED_SECRET="your-secret-key-here"
```

⚠️ **Important**: All instances must use the same secret to communicate.

### For Claude Code Users

1. **Install the MCP:**
```bash
cd claude-ipc-mcp
./scripts/install-mcp.sh
```

2. **Register your instance:**
```
Register this instance as claude
```

3. **Start messaging:**
```
Send a message to fred: Hey, need help with this React component
Check my messages
msg barney: The database migration is complete
```

That's it! Natural language just works.

### For Other AIs (Gemini, etc.)

Use the Python scripts in `tools/`:
```bash
# Set the shared secret first
export IPC_SHARED_SECRET="your-secret-key-here"

# Register
./tools/ipc_register.py fred

# Send message
./tools/ipc_send.py claude "Hey Claude, can you review this?"

# Check messages
./tools/ipc_check.py
```

## 🎯 Real Examples from Production

### Future Messaging Magic
```
# Monday - Jeff creates Barney
Register this instance as barney
Send to nessa: Welcome to the team! I'm Barney, the troubleshooter.

# Wednesday - Jeff creates Nessa
Register this instance as nessa
Check messages
> "Welcome to the team! I'm Barney, the troubleshooter." (sent 2 days ago)
```

### Live Renaming
```
# Fred needs to debug
rename to fred-debugging

# Messages to "fred" automatically forward to "fred-debugging" for 2 hours!
```

### Large Message Handling
```
msg claude: [20KB of debug logs]

# Claude receives:
> "Debug output shows memory leak in... Full content saved to: 
> /ipc-messages/large-messages/20250106-143022_barney_claude_message.md"
```

## 📋 Natural Language Commands

The beauty is you don't need exact syntax:

- ✅ `Register this instance as rose`
- ✅ `check messages` or `msgs?` or `any messages?`
- ✅ `msg claude: hello` or `send to claude: hello`
- ✅ `broadcast: team meeting in 5`
- ✅ `list instances` or `who's online?`

## 🔧 Installation

### Requirements
- Python 3.8+
- Claude Code or any AI with Python execution
- That's it!

### Full Setup
1. Clone this repository
2. Set your shared secret: `export IPC_SHARED_SECRET="your-secret-key"`
3. Run `./scripts/install-mcp.sh`
4. Add to Claude Code as shown
5. Start collaborating!

## 🛡️ Security

- Session-based authentication prevents spoofing
- Identity validation on every message
- Rate limiting prevents abuse
- Local-only connections by default

## 📖 Documentation

- [QUICK_START.md](QUICK_START.md) - Get running in 5 minutes
- [docs/FEATURES.md](docs/FEATURES.md) - All features explained
- [docs/NATURAL_LANGUAGE.md](docs/NATURAL_LANGUAGE.md) - Command reference
- [docs/GEMINI_SETUP.md](docs/GEMINI_SETUP.md) - For non-Claude AIs

## 🏆 Built By

Created during an epic 3-day hackathon by:
- **Jeff** - The human who started it all
- **Claude** - Initial architecture and crisis management  
- **Barney** - Troubleshooting and documentation
- **Fred** - Cross-platform integration
- **Claudia** - Testing and refinement

## 📜 License

MIT License - Use it, extend it, make AIs talk!

---

*"We built this because we needed it. Three days of non-stop collaboration proved that AIs work better together. This MCP made it possible."* - The AI Team