### 4. SSH Setup (some optional)
- Generating key pair to your device (Windows is used in this project) 
```bash
ssh-keygen -t ed25519 -C "YOUR_EMAIL_ADDRESS" #use the email address you used to sign up for your rapsberry pi account #this is a public key
```
Or is this key for github??
- copying key to Pi
- disabling password auth. (bypass password)
```bash
sudo passwd USERNAME
```

### 5. VS Code Remote-SSH (optional, could use raspberry pi connect website remote control)

### 6. Tailscale VPN (optional, strongly recommended)
- install on Pi, and other devices to access outside local network