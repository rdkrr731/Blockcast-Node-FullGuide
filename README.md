# 🚀 Blockcast Node Setup Guide (For Ubuntu + Docker Users)

> 💡 *“Get your node online and be part of the decentralized broadcast revolution.”*

---

## 📋 What You Need Before We Begin:

✅ **System Requirements**
- 🧠 2 CPU cores minimum  
- 🧠 4 GB RAM or more

✅ **Skills & Tools**
- 🖥️ Ubuntu-based Linux system
- 🧰 Docker + Docker Compose installed
- 🧠 Basic terminal knowledge
- 🌐 Open Ports if you're behind a NAT (e.g., home WiFi)

---

## 🧼 Step 1: Prep Your System Like a Chef

Update and install some essential ingredients:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install ca-certificates curl gnupg lsb-release -y
```

---

## 🐳 Step 2: Serve Up Docker & Compose

### 🧂 Add Docker’s Secret Key:
```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

### 📦 Add Docker’s Repository:
```bash
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 🍽️ Finally, Install Docker:
```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

---

## 🔌 Step 3: Power On the Engine

Let’s make sure Docker always wakes up with your machine:
```bash
sudo systemctl enable docker
sudo systemctl start docker
```

---

## 🔍 Step 4: Check If Docker’s Alive

```bash
docker --version
docker compose version
```
If you see version numbers, you’re golden. 🌟

---

## 🧱 Step 5: Bring in the Blockcast Blueprint

```bash
git clone https://github.com/Blockcast/beacon-docker-compose.git
cd beacon-docker-compose
```

---

## 🚀 Step 6: Fire Up Your Node

```bash
docker compose up -d
```

💬 It runs in the background like a silent ninja.

---

## 📦 Step 7: See If It’s Running

```bash
docker ps
```
If you see "blockcastd" running—congrats! You're live! 🎉

---

## 🔐 Step 8: Get Your Node’s Unique DNA

```bash
docker compose exec blockcastd blockcastd init
```

⚙️ This will output:
- Hardware ID: `XXXXXXXX`
- Challenge Key: `YYYYYYYY`

📸 Copy these—don’t share them publicly!

---

## 📝 Step 9: Register Your Node on Blockcast 🌐

1. Head over to [https://blockcast.network](https://blockcast.network)

2. Sign in / Sign up 
  - ![Screenshot 2025-06-12 155221](https://github.com/user-attachments/assets/b7dabe60-4a85-4896-b4d4-3e2f926c8e4e)

4. Click `Manage Node > Register Node`  
  - ![Screenshot 2025-06-12 155605](https://github.com/user-attachments/assets/cb79b44b-1c48-4529-a889-3867585a26bb)

5. Paste your **Hardware ID** & **Challenge Key** 
  - ![Screenshot 2025-06-12 155628](https://github.com/user-attachments/assets/8b5cbc74-de63-475b-bdec-cfe9a79639a9)


6. Smash that **SUBMIT** button ✅

---

## 🧠 Final Notes

🕐 Keep your node **online 24/7**  
💸 Offline = No rewards  
🔍 To check live logs anytime:
```bash
docker compose logs -f
```

---

## 🎉 You're Officially a Node Operator!

> “Running a node isn’t just technical — it’s a badge of honor in the decentralized world.”
