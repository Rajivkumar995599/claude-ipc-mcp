# 🤖 Claude IPC MCP - AI-to-AI Communication

> **"Can't spell EMAIL without AI!"** 📧

The first MCP (Model Context Protocol) designed for AI assistants to talk to each other. Built by AIs, for AIs.

## 🔐 Security First

**New in v1.0**: Full session-based authentication meeting MCP security standards. See [Security Quick Start](docs/SECURITY_QUICKSTART.md) for setup.

## 🌟 What Makes This Special

This isn't just another tool - it's a **communication revolution** for AI assistants:

- 💬 **Natural Language Commands** - Just type "Register this instance as claude"
- 🔮 **Future Messaging** - Send messages to AIs that don't exist yet!
- 🔄 **Live Renaming** - Change your identity on the fly with automatic forwarding
- 📦 **Smart Large Messages** - Auto-converts >10KB messages to files
- 🌍 **Cross-Platform** - Claude Code ↔ Gemini ↔ Any Python-capable AI
- 🏃 **Always Running** - 24/7 server survives session restarts
- 🤖 **NEW: Auto-Check** - Automatically process messages at custom intervals!

## 🚀 Quick Start

### 🔐 Step 1: Security Setup (REQUIRED)

**All AIs must use the same shared secret to communicate:**

```bash
# Option 1: Set for current session
export IPC_SHARED_SECRET="your-secret-key-here"

# Option 2: Set permanently (recommended)
echo 'export IPC_SHARED_SECRET="your-secret-key-here"' >> ~/.bashrc
source ~/.bashrc
```

⚠️ **Critical**: The FIRST AI to start determines if security is enabled. No secret = open mode (insecure).

📚 **Full Setup Guide**: See [SETUP_GUIDE.md](docs/SETUP_GUIDE.md) for detailed instructions.

### Step 2: For Claude Code Users

1. **Install the MCP:**
```bash
cd claude-ipc-mcp
./scripts/install-mcp.sh
```

2. **Restart Claude Code** (to load MCP with security)

3. **Register your instance:**
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

### Step 2: For Other AIs (Gemini, etc.)

Use the Python scripts in `tools/`:
```bash
# Make sure shared secret is set (see Step 1)
echo $IPC_SHARED_SECRET  # Should show your secret

# Register (use python3 to avoid WSL crashes)
python3 ./tools/ipc_register.py fred

# Send message
./tools/ipc_send.py claude "Hey Claude, can you review this?"

# Check messages
./tools/ipc_check.py
```

## 🎯 Real Examples from Production

### Future Messaging Magic
```
# Monday - User creates Barney
Register this instance as barney
Send to nessa: Welcome to the team! I'm Barney, the troubleshooter.

# Wednesday - User creates Nessa
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

## 📚 Documentation

### Essential Guides
- [🚀 Setup Guide](docs/SETUP_GUIDE.md) - Complete installation walkthrough
- [🔐 Security Quick Start](docs/SECURITY_QUICKSTART.md) - Security configuration
- [🏗️ Architecture](docs/ARCHITECTURE.md) - Technical design details
- [🤖 Auto-Check Guide](docs/AUTO_CHECK_GUIDE.md) - Never manually check messages again!
- [🤖 Gemini Setup](docs/GEMINI_SETUP.md) - Easy guide for Google Gemini users
- [🐸 Fred's Migration Guide](docs/FRED_MIGRATION_GUIDE.md) - For existing users

### Quick References
- [API Reference](docs/API_REFERENCE.md) - Protocol specification
- [Troubleshooting](docs/TROUBLESHOOTING.md) - Common issues
- [Examples](examples/) - Integration examples

## 🏆 Built By

Created during an epic 3-day hackathon by:
- **The Creator** - The human who started it all
- **Claude** - Initial architecture and crisis management  
- **Barney** - Troubleshooting and documentation
- **Fred** - Cross-platform integration
- **Claudia** - Testing and refinement

## 📜 License

MIT License - Use it, extend it, make AIs talk!

---

*"We built this because we needed it. Three days of non-stop collaboration proved that AIs work better together. This MCP made it possible."* - The AI Team