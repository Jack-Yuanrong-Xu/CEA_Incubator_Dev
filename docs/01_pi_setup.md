# System Set-up Needs

This file includes all the hardware and software needed to build this working incubation system with temperature and humidity monitoring. 

### 1. Hardware and software
- Raspberry PI (This project used 3B)
- MicroSD Card  
- Set up Raspberry PI connect and download Rapsberry pi imager with this link:
- https://www.youtube.com/watch?v=rvCaN1PSKY0
### 2. Initial Pi Configuration
- Creating host name
- enabling SSH
- enabling I2C
### 3. Locate Pi's IP Address
- Connect to your raspberry PI via raspberry pi connect
'''bash
hostname -I # Command to find out the IP address which is the first segments of numbers. e.g. 192.168.1.72
'''

### 4. SSH Setup (some optional)
- Generating key pair to your device (Windows is used in this project) 
    ssh-keygen -t ed25519 -C "YOUR_EMAIL_ADDRESS" #use the email address you used to sign up for your rapsberry pi account #this is a public key

Or is this key for github??
- copying key to Pi
- disabling password auth.

### 5. VS Code Remote-SSH (optional, could use raspberry pi connect website remote control)

### 6. Tailscale VPN (optional, strongly recommended)
- install on Pi, and other devices to access outside local network

### 7. Kasa Plug Timezone Setting
