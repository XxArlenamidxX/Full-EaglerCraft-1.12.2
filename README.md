# 🧠 Full EaglerCraft 1.12.2 Setup Guide (Codespaces Edition)

This guide will help you set up and run the Full EaglerCraft 1.12.2 project inside a GitHub Codespace. It includes the BungeeCord proxy, the Minecraft server, and the relay server—all working together with ports exposed.

---

## 🚀 Getting Started

### Step 1: Open the Repository in a Codespace

1. Fork or clone this repository.
2. Open the repository in a **Codespace** by clicking **"Code" > "Codespaces" > "Create codespace on main"**.

---

## 🖥️ Terminal Setup

Once the Codespace is ready:

### Step 2: Open 3 Terminal Tabs

In the Codespace interface:

- Open **three terminal tabs**.
- In **each tab**, elevate to root with:

```bash
sudo -s
```

---

## 🧩 Running the Components

### Tab 1: Start BungeeCord

```bash
cd bungee
java -jar bungee.jar
```

### Tab 2: Start Minecraft Server

```bash
cd server
java -jar server.jar
```

### Tab 3: Start Relay Server (Debug Mode)

```bash
cd relay
java -jar relay.jar --debug
```

---

## 🌐 Port Forwarding

After all components are running:

1. Go to the **"Ports"** tab in your Codespace (usually on the bottom panel).
2. **Forward the following ports**:
   - `8081` → for the frontend connection.
   - `6699` → for the relay communication.

---

## 🕹️ Client Setup (Singleplayer & Multiplayer)

### 🔁 Add Relay (Singleplayer > Join Shared World)

1. Launch your Eaglercraft client.
2. Navigate to:
   - `Singleplayer` → `Join Shared World` → `Network Settings`
3. Click **"Add Relay"**
4. Use the following:
   - **Relay Address**: `wss://<your-8081-port-url>`
   - **Relay Port**: `6699` (from forwarded port)
   - Change the `https://` protocol to `wss://` when copying from port URLs.

### 🌍 Add Multiplayer Server

1. Navigate to `Multiplayer` → `Add Server`
2. Use the **8081 port** as the server address:
   - Replace `https://` with `wss://`

For example:
```
https://<your-url>.github.dev:8081 → wss://<your-url>.github.dev:8081
```

---

## ✅ Everything Is Ready!

You’ve now:

- Started the BungeeCord proxy
- Ran the Minecraft server
- Launched the relay with debug mode
- Forwarded the required ports
- Connected your client to the relay and server

You're all set to play EaglerCraft with full relay and multiplayer support!

---

## 📄 License

This project is open-source and free to use under the [MIT License](LICENSE).
