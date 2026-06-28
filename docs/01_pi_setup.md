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

## 4. Enabling I2C and varify with i2cdetect

Open your raspberry pi's terminal either through Raspberry Pi connect. 

If doing through raspberry pi home page, just click top left corner.

If doing through SSH:

``` bash
sudo raspi-config
```

Then, 

Go to interface Options, then I2C, select Yes, then OK, and Finish

Confirm check by

```bash
ls /dev/i2c*
```


### 7. Kasa Plug Timezone Setting
