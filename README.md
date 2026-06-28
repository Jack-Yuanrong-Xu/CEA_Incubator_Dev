## CEA_Incubator_Dev

Follow instruction in docs first. It will reference the actual python files within scripts and services. 

The structure of our filing system is flexible, however, my original project followed this format:

CEA-System/
|-sensors
|-data logging
|-controls


### Troubleshooting tips

Raspberry pi address changes
- create static IP address
- may need to erase previously written files if new IP address is used


### Service file and script edits

Check active running code
```bash
ps aux | grep python
```
check kasa log
```bash
tail -f /tmp/kasa.log
```
check log content
```bash
cat /tmp/kasa.log
```
heck log
```bash
journalctl -u cea-control.service -f

journalctl -u cea-control.service --since "2026-04-20 06:00"
```
Check type of service
```bash
sudo systemctl list-units --type=service | grep cea
sudo systemctl list-units --type=service | grep sensor
```
check sensors i2c location
```bash
i2cdetect -y 1
```
to edit the script
```bash
nano /home/jackyuanrongxu/CEA-Systcatem/CEA-System/Control/kasa_control.py
```
pull from GitHub
```bash
git pull --rebase origin main
git push
```
push change to GitHub
```bash
cd /home/jackyuanrongxu/CEA-System
git add .
git commit -m "COMMENTS"
git push
```
restart after change
```bash
sudo systemctl restart cea-control.service
```
check running status and printed items
```bash
sudo systemctl status cea-control.service
```
check voltage
```bash
dmesg | grep -i "voltage\|power\|throttl"
```
check current state
```bash
vcgencmd get_throttled
```