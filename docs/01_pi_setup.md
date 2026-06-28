# System Set-up Needs

This document covers how the Raspberry Pi 3B was coonfigured as the core controller for this CEA incubation system with temperature and humidity monitoring. I walks through hardware selection, OS installation, I2C setup, remote access via SSh and VS Code, and off-network access via Tailscale VPN.

--- 

## 1. Hardware Used
| Component | Details |
|---|---|
| Single-board computer | Raspberry Pi (This project used 3B)|
| Storage | 32 GB MicroSD card (Class 10 recommended) |
| Sensors | SHT40 (temp/humidity, I2C), SCD30 (CO₂/temp/humidity, I2C) |
| Smart plugs | Kasa HS103 (controlled via 'python-kasa') |

- Set up Raspberry PI connect and download Rapsberry pi imager with this link:
- https://www.youtube.com/watch?v=rvCaN1PSKY0

## 2. IInstalling Raspberry Pi OS, Initial Pi Configuration


- Set up Raspberry PI connect and download Rapsberry pi imager with this walkthrough video: https://www.youtube.com/watch?v=rvCaN1PSKY0

- Creating host name
- enabling SSH
- enabling I2C
## 3. Locate Pi's IP Address

Once the Pi is booted and connected to your network, find its local IP address. YHou can do it a few ways: 

**Option A - From the Pi directly (via Raspberry Pi connect or a monitor):**
```bash
hostname -I # Command to find out the IP address
# Output example: 192.168.1.72 - the first address (the first segments) is the local IP
```
Write this IP down. You'll need it for SH and for referencing the Pi from your local network.

### 4. SSH Setup (some optional)
- Generating key pair to your device (Windows is used in this project) 
```bash
ssh-keygen -t ed25519 -C "YOUR_EMAIL_ADDRESS" #use the email address you used to sign up for your rapsberry pi account #this is a public key
```
Or is this key for github??
- copying key to Pi
- disabling password auth.

### 5. VS Code Remote-SSH (optional, could use raspberry pi connect website remote control)

### 6. Tailscale VPN (optional, strongly recommended)
- install on Pi, and other devices to access outside local network

### 7. Kasa Plug Timezone Setting
