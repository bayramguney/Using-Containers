# Using-Containers

# 🐳 Using Windows Containers with Docker (CompTIA Security+ Lab)

## 📌 Project Overview

This hands-on lab demonstrates the fundamentals of **Windows containerization** using **Docker** on **Windows Server 2019**. The lab focuses on securely creating, managing, and interacting with Docker containers while applying Security+ concepts related to enterprise infrastructure, operating system isolation, networking, user management, and container security.

This project aligns with **CompTIA Security+ (SY0-701)** objectives covering modern infrastructure and secure deployment practices.

---

## 🎯 Objectives

- Verify Docker installation and host configuration
- Create and manage Windows Docker containers
- Interact with running containers
- Inspect container networking
- Manage users and local groups inside containers
- Perform basic container administration
- Understand container persistence
- Apply container security best practices

---

# 🛠 Technologies Used

- Windows Server 2019
- Docker Engine
- Windows Nano Server Image
- Windows PowerShell
- Command Prompt (CMD)

---

# 🔐 Security+ Skills Demonstrated

- Containerization
- Enterprise Infrastructure Security
- Operating System Isolation
- Network Segmentation
- User and Group Administration
- Least Privilege
- Secure Configuration
- Container Lifecycle Management
- Host vs Container Isolation

---

# 📚 Lab Tasks

## 1. Verify Docker Installation

Validated:

- Docker Engine service
- Windows Server version
- Hostname
- IP configuration

Commands used:

```powershell
ipconfig
hostname
winver
docker images
```

---

## 2. Create Docker Containers

Created containers using the Windows Nano Server image.

Commands:

```powershell
docker create --name MyFirstContainer mcr.microsoft.com/windows/nanoserver:1809

docker start MyFirstContainer

docker ps -a
```

Learned:

- Image vs Container
- Container states
- Created
- Running
- Exited

---

## 3. Launch Interactive Container

Started an interactive Windows container.

Command:

```powershell
docker run -it --name TestContainer mcr.microsoft.com/windows/nanoserver:1809
```

Inside the container:

```cmd
ver
hostname
ipconfig
netstat -aon
ping
```

Observed:

- Independent hostname
- Separate IP address
- NAT networking
- Communication with host

---

## 4. Inspect Networking

Verified:

- IPv4 address
- Default Gateway
- NAT virtual network
- Connectivity to host
- Listening ports

Commands:

```cmd
ipconfig

netstat -aon

ping
```

Concepts learned:

- Container networking
- NAT
- Virtual Ethernet adapters
- Host communication

---

## 5. User and Group Management

Entered the container using administrator privileges.

Commands:

```powershell
docker exec -it TestContainer cmd

docker exec -it --user ContainerAdministrator TestContainer cmd
```

Managed:

- Local users
- Local groups
- Administrator account

Commands:

```cmd
net user

net user Administrator

net localgroup
```

Created a new user:

```cmd
net user testuser pa$$word123 /ADD
```

Added user to Power Users:

```cmd
net localgroup "Power Users" testuser /add
```

Updated Administrator password:

```cmd
net user Administrator pa$$word123
```

---

## 6. File System Persistence

Created folders and files inside the container.

Commands:

```cmd
md MyFolder

cd MyFolder

echo "This is some text for my test file." > test.txt

type test.txt
```

Verified:

- Data remains after exiting the container
- Data persists until the container is removed

---

## 7. Container Lifecycle Management

Managed container states.

Commands:

```powershell
docker ps -a

docker start TestContainer

docker stop TestContainer
```

Learned:

- Start
- Stop
- Exit
- Restart
- Persistence

---

# 🔒 Security Best Practices

During this lab, the following security principles were reinforced:

- Verify Docker services before deployment
- Use isolated environments for testing
- Apply least privilege whenever possible
- Manage administrator accounts securely
- Configure strong passwords
- Review container networking
- Monitor listening ports
- Keep containers isolated from production until validated
- Properly stop containers to prevent corruption
- Understand persistence before deployment

---

# 🧠 Key Concepts Learned

- Windows Containers
- Docker Images
- Docker Containers
- Container Isolation
- NAT Networking
- Virtual Ethernet
- Local User Management
- Local Group Management
- Container Persistence
- Windows Nano Server
- Secure Container Administration

---

# 💡 Skills Gained

- Docker administration
- Windows container management
- PowerShell administration
- Enterprise infrastructure security
- Container networking
- Windows account management
- Security hardening
- Secure deployment practices

---

# 📖 Security+ SY0-701 Objectives

This lab supports:

- **3.1** Compare and contrast security implications of different architecture models
- **3.2** Apply security principles to secure enterprise infrastructure

---

# ✅ Outcome

Successfully created, managed, secured, and administered Windows Docker containers using PowerShell. Demonstrated practical knowledge of container deployment, networking, user management, persistence, and security best practices that directly support Security Operations Center (SOC) and Security Administrator responsibilities.

---

## 📂 Repository Structure

```
Using-Containers/
│
├── README.md
└── screenshots/
    ├── docker-images.png
    ├── docker-create.png
    ├── docker-ps.png
    ├── container-ipconfig.png
    ├── net-user.png
    ├── net-localgroup.png
    ├── persistence-test.png
    └── docker-stop.png
```

---

## 🚀 Author

**Bayram Guney**
Passionate about cybersecurity, defensive security, SIEM, threat detection, incident response, and hands-on security labs.
