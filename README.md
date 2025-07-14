
# Eaglercraft Multiplayer Setup (BungeeCord + Server + Relay)

This repository provides a full setup to run an Eaglercraft multiplayer environment using BungeeCord, a Minecraft server, and a relay system. This guide will walk you through how to run it inside a GitHub Codespace.

---

## 🚀 Getting Started

### 1. Open in Codespace
Click on the green **Code** button and choose **"Open with Codespaces"**. This will clone the repository and launch your development environment.

---

## 🖥️ Terminal Setup

Once the Codespace is open:

1. Open **3 terminal tabs**.
2. In **each tab**, run the following command to enter root mode:

```bash
sudo -s
```

---

## 📂 Running the Services

Now, execute the following in each terminal **tab**:

### ➤ Terminal 1: Start BungeeCord
```bash
cd /bungee
sudo java -jar bungee.jar
```

### ➤ Terminal 2: Start Minecraft Server
```bash
cd /server
sudo java -jar server.jar
```

### ➤ Terminal 3: Start Relay (with Debug Mode)
```bash
cd /relay
sudo java -jar relay.jar --debug
```

---

## 🌐 Port Forwarding

Go to the **Ports** tab in Codespaces and make sure to **forward the following ports**:

- `8081` → Used to connect the web client to the server
- `6699` → Used by the relay for singleplayer LAN connections

---

## 🕹️ Connecting from the Eaglercraft Client

### 🔹 Add Relay in Singleplayer

1. Open **Singleplayer → Join Shared World → Network Settings**.
2. Add a new relay using the forwarded `6699` port.
   - Change the protocol from `https://` to `wss://`
   - Example: `wss://<your-port-6699-url>`

### 🔹 Add Server in Multiplayer

1. Go to **Multiplayer → Add Server**.
2. Use the forwarded `8081` port.
   - Change the protocol from `https://` to `wss://`
   - Example: `wss://<your-port-8081-url>`

---

✅ Once these steps are done, you’re ready to play! Relays and servers are now set up and running.
