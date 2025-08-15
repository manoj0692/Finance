# finance
Mini Finance  Website Deployment(Manual)  with Vagrant 
# Mini Finance  Website Deployment with Vagrant

This repository contains a Vagrant configuration to set up and run the **Mini Finance**  website templates (from [tooplate.com](https://www.tooplate.com/)) using **CentOS Stream 9**.

---

## 📋 Prerequisites
 Tool are Required to be installed on host machine:
- Vagrant (VM Automation tool) 
- Oracle Virtual Box (hypervisor)
- Internet connection (to download base box and website templates)
- Git bash (CLI(Command line Interface) in Windows which let us use Unix/Linux like commands)
---

## ⚙️ Vagrant Configuration
- **Base Box:** `eurolinux-vagrant/centos-stream-9`
- **Private Network:** `192.168.56.22`
- **Public Network:** Bridged mode
- **Memory:** 1 GB RAM

---

## 🚀 Setup Instructions

### 1️⃣ Start the Virtual Machine
```bash
vagrant up
```

### 3️⃣ Access the VM
```bash
vagrant ssh
```

### 4️⃣ Install Dependencies

Inside the VM:
```bash
ip addr show ##Check Ip address of machine
sudo hostnamectl set-hostname finance ##Set hostname of machine
sudo dnf install -y httpd wget vim zip unzip ## Installing Dependencies
```

### 5️⃣ Download and Deploy Website Templates
**Mini Finance:**
```bash
cd /tmp
wget https://www.tooplate.com/zip-templates/2137_mini_finance.zip
unzip 2137_mini_finance.zip 
cd mini_finance
cp -r * /var/www/html
```

### 6️⃣ Start and Enable httpd
```bash
sudo systemctl start httpd
sudo systemctl enable http
```

---

## 🌐 Access the Websites
- **Mini Finance:** [http://192.168.56.22/](http://192.168.56.22/)

---

## 🛑 Stopping and Removing the VM
Stop the VM:
```bash
vagrant halt
```
Destroy the VM:
```bash
vagrant destroy
```
