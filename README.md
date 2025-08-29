# Dummy Service with systemd

![Shell Script](https://img.shields.io/badge/Bash-Script-green?logo=gnu-bash&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Service-blue?logo=linux&logoColor=white)
![systemd](https://img.shields.io/badge/systemd-AutoStart-critical?logo=linux&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)


A simple **Linux background service** built with a Bash script and managed by **systemd**.  
This project simulates an application that writes logs every 10 seconds and automatically restarts if it fails.

---
# Project URL
```
https://roadmap.sh/projects/dummy-systemd-service
```

## **Project Overview**

- `dummy.sh` → a Bash script that appends messages to `/var/log/dummy-service.log` every 10 seconds.  
- `dummy.service` → a systemd unit file to:
  - Start the script on boot
  - Keep it running in the background
  - Restart automatically if it crashes

---

## **Architecture**

 ****

![Architecture Diagram]<img width="1024" height="1024" alt="Architecture diagram" src="https://github.com/user-attachments/assets/d01ce7cc-75f4-424c-8e19-e8f6ea55e386" />

*(Example: A simple flow showing `dummy.sh` → systemd → logs)*  

---

## **Features**

- Background service with **auto-start on boot**  
- **Automatic restart** on failure using `Restart=always`  
- Centralized log viewing via `journalctl`  
- Minimal and lightweight — pure Bash, no external dependencies  

---

## **Getting Started**

### **1. Clone the repository**
```bash
git clone https://github.com/sumit0920/dummy-service-systemd.git
cd dummy-service-systemd
````

### **2. Copy files to correct locations**

```bash
sudo cp dummy.sh /usr/local/bin/
sudo chmod +x /usr/local/bin/dummy.sh

sudo cp dummy.service /etc/systemd/system/
```

### **3. Reload systemd and start the service**

```bash
sudo systemctl daemon-reload
sudo systemctl start dummy
sudo systemctl enable dummy
```

---

## **Usage**

### **Manage the service**

```bash
sudo systemctl start dummy       # start service
sudo systemctl stop dummy        # stop service
sudo systemctl restart dummy     # restart service
sudo systemctl enable dummy      # start on boot
sudo systemctl disable dummy     # disable auto-start
sudo systemctl status dummy      # check status
```

### **Check service logs**

```bash
sudo journalctl -u dummy -f
```

### **Check application logs**

```bash
tail -f /var/log/dummy-service.log
```

---

## **Testing Auto-Restart**

Kill the process manually to verify systemd automatically restarts it:

```bash
sudo pkill -f dummy.sh
sudo systemctl status dummy
```

---

## **Project Structure**

```
dummy-service-systemd/
│
├── dummy.sh # Bash script writing logs every 10s
├── dummy.service # systemd service unit file
├── README.md # Project documentation (this file)
├── LICENSE # Open-source license (MIT)
└──.gitignore # Ignoring log files and temp files
 
```
## **Screenshots**

Here’s an example of the service running successfully:
Dummy Service Running

<img width="1192" height="532" alt="Screenshot 2025-08-29 212437" src="https://github.com/user-attachments/assets/16e10379-81eb-49c0-8206-e13b97ae05f1" />

<img width="1904" height="684" alt="Screenshot 2025-08-29 212510" src="https://github.com/user-attachments/assets/c606b23a-6739-4b0f-9d9b-c798a76c0f7c" />


<img width="1156" height="414" alt="Screenshot 2025-08-29 212627" src="https://github.com/user-attachments/assets/035291e7-b9c8-47ce-a870-eb1b660d5541" />


<img width="1110" height="365" alt="Screenshot 2025-08-29 212719" src="https://github.com/user-attachments/assets/a072051c-fa3f-49f4-b42c-5abfddccbc2c" />


<img width="896" height="532" alt="Screenshot 2025-08-29 212745" src="https://github.com/user-attachments/assets/3d087666-4390-4655-986d-cd32634fa0fc" />


<img width="1173" height="299" alt="Screenshot 2025-08-29 212834" src="https://github.com/user-attachments/assets/2b23518a-415b-4971-85aa-43708dc2a691" />




---

## **License**

This project is licensed under the [MIT License](./LICENSE).
You are free to use, modify, and distribute this project.

---

## **Contributions**

Feel free to open issues or pull requests to improve this project.

---

## **Author**

**Sumit Sharma**
- [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sumitsharma-ss/)
- [![X](https://img.shields.io/badge/X-black?style=flat&logo=twitter&logoColor=white)](https://x.com/sumitsharma_95)
- [![Medium](https://img.shields.io/badge/Medium-12100E?style=flat&logo=medium&logoColor=white)](https://medium.com/@devopswithsumit)
- [![GitHub](https://img.shields.io/badge/GitHub-100000?style=flat&logo=github&logoColor=white)](https://github.com/sumit0920)
---
