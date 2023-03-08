# Pi Usage Monitor
A python script that monitors the temperature, RAM usage, and CPU usage of a Raspberry Pi system and sends it through a Discord webhook every minute. <br />
![it work](https://user-images.githubusercontent.com/30084485/223586659-3a030bed-69e8-43c8-8e23-083257df742e.png)<br />

# Installation
<b>THIS WILL ONLY WORK ON RASPBERRY PI.</b>
### `wget https://raw.githubusercontent.com/CarrionAndOn/Linux-Usage-Monitor/main/install.sh && bash install.sh`<br />
It will install any dependencies for you if you do not already have them, do not worry about installing them.<br />
If the OS you installed onto your Pi has a graphic desktop, you can download it directly from the releases.<br />
Or, you can install it manually with the instructions below.<br />

# Manual Installation
<b>NOTE: I HAVE ONLY TESTED THIS IN UBUNTU, NO IDEA IF IT WORKS IN ANY OTHER OPERATING SYSTEMS ON THE PI.</b><br />
psutil MUST be installed for this to work.<br />
Install it with "pip install psutil"<br />
If you don't have pip, install python3-pip with "apt install python3-pip"<br />
<br />
Run `wget https://raw.githubusercontent.com/CarrionAndOn/Linux-Usage-Monitor/main/usagemonitor.py`<br />
Run `wget https://raw.githubusercontent.com/CarrionAndOn/Linux-Usage-Monitor/main/usagemonitor.conf`<br />
Run `nano usagemonitor.conf`<br />
Change YOUR_WEBHOOK_URL to the URL of your discord webhook.<br />
Change the time to whatever you want it to be in seconds, or leave it.<br />
Run `mv usagemonitor.py /opt/`<br />
Run `mv usagemonitor.conf /opt/`<br />
Run the file with "python3 /opt/usagemonitor.py" to make sure it works<br />
Use systemctl, supervisor, nohup, or any other service daemon to run the file in the background<br />
An example service file for systemctl is in the source code.<br />

# Uninstallation
Run `systemctl stop usagemonitor && rm /opt/usagemonitor.* && rm /etc/systemd/system/usagemonitor.service`<br />
