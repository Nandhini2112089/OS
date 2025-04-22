
**Operating Systems**

## **Introduction**
An **Operating System (OS)** is the interface between a computer user and the computer hardware. It is a system software that manages:
- File Management
- Memory Management
- Process Management
- Input/Output Handling
- Peripheral Devices (e.g., disk drives, printers)

---

## **Kernel**
The **Kernel** is the core of an operating system, managing:
- System resources (CPU, memory, I/O devices)
- System calls (from applications to hardware)
- Abstraction between software and hardware

It is loaded into memory at boot and remains there until shutdown.

### **Types of Kernels**
| Type             | Description                                                                 | Example        |
|------------------|-----------------------------------------------------------------------------|----------------|
| **Monolithic**   | All OS services run in kernel space. High efficiency but risk of crashes.  | Linux          |
| **Microkernel**  | Only essential services in kernel space; others run in user space.          | Minix, QNX     |
| **Hybrid**       | Mix of monolithic and microkernel; efficient and reliable.                  | macOS, Windows |

---

## **System Call**
A **System Call** is a special function that allows processes to request services from the OS, such as:
- File Management: `open()`, `read()`, `write()`, `close()`
- Process Management: `fork()`, `exec()`, `exit()`
- Memory Management: `malloc()`, `free()`
- Device Management: `read()`, `write()` to hardware

---

## **Memory Management Techniques**

### **Paging**
- Divides logical memory into fixed-size **pages** and physical memory into **frames**
- Uses a **Page Table** for mapping pages to frames
- If a required page isn't in RAM, a **Page Fault** occurs and it's loaded from disk

### **Segmentation**
- Divides memory into **segments** (e.g., Code, Stack, Data)
- Each segment has a **base address** and **limit**
- OS translates logical to physical addresses using a **Segment Table**

### **Fragmentation**
| Type                | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Internal**        | Wasted space **within** allocated memory blocks                            |
| **External**        | Wasted space **between** memory blocks, not contiguous                      |

---

## **Linux File System Tree**

- Follows a hierarchical (tree-like) structure rooted at `/`
- **Everything is a file**, or a running process

| Path      | Description                                          |
|-----------|------------------------------------------------------|
| `/bin`    | Essential binaries (`ls`, `cp`, `mv`, etc.)          |
| `/sbin`   | System binaries for admin (`reboot`, `shutdown`)     |
| `/boot`   | Bootloader files (e.g., GRUB), kernel                |
| `/dev`    | Device files (`sda`, `tty`)                          |
| `/etc`    | Configuration files                                  |
| `/home`   | User personal directories                            |
| `/lib`, `/lib64` | Shared libraries                              |
| `/mnt`    | Temporary mount point                                |
| `/media`  | Mounted media (USB, DVD)                             |
| `/root`   | Root user home directory                             |
| `/run`    | Runtime info (PIDs, sockets)                         |
| `/srv`    | Service data (HTTP, FTP)                             |
| `/sys`    | Kernel and hardware details                          |
| `/tmp`    | Temporary files                                      |
| `/opt`    | Optional application packages                        |

---

## **Windows vs Linux Directory Mapping**

| Linux Path | Windows Equivalent      | Purpose                   |
|------------|--------------------------|---------------------------|
| `/`        | `C:\`                    | Root directory            |
| `/home/`   | `C:\Users\`              | User home directories     |
| `/etc/`    | `C:\Windows\System32\`   | System config             |
| `/dev/`    | Device Manager           | Hardware devices          |
| `/proc/`   | Task Manager             | Running processes         |

---

## **Common Linux Commands**

| Command      | Description                                                    |
|--------------|----------------------------------------------------------------|
| `ls`         | List directory contents                                        |
| `pwd`        | Show current working directory                                 |
| `cd`         | Change directory                                               |
| `mkdir`      | Create directories (`-m` to set permissions)                  |
| `rmdir`      | Remove empty directories                                       |
| `mv`         | Move or rename files                                           |
| `cp`         | Copy files                                                     |
| `rm`         | Remove files/directories (`-r`, `-f`, `-i` options)            |
| `touch`      | Create empty files                                             |
| `ln`         | Create symbolic links                                          |
| `cat`        | Show file contents                                             |
| `clear`      | Clear terminal                                                 |
| `echo`       | Output string                                                  |
| `less`       | Scrollable file viewing                                        |
| `man`        | Show manual pages                                              |
| `uname`      | Show system information                                        |
| `whoami`     | Show current username                                          |
| `tar`        | Compress/extract files                                         |
| `grep`       | Search within text                                             |
| `head`/`tail`| Show top/bottom lines of a file                                |
| `diff`/`cmp` | Compare files                                                  |
| `comm`       | Combine comparison results                                     |
| `sort`       | Sort file contents                                             |
| `export`     | Set environment variables                                      |
| `zip`/`unzip`| Compress/Extract zip files                                     |
| `service`    | Start/stop system services                                     |
| `ps`         | Show running processes                                         |
| `kill`       | Terminate processes (by PID)                                   |
| `df`         | Show disk space usage                                          |
| `mount`      | Mount storage devices                                          |
| `chmod`      | Change file permissions                                        |
| `chown`      | Change file ownership                                          |
| `ifconfig`   | Show network config                                            |
| `traceroute` | Trace network hops                                             |
| `wget`       | Download files via HTTP/FTP                                   |
| `ufw`/`iptables` | Firewall utilities                                         |
| `sudo`       | Run commands as superuser                                      |
| `cal`        | Show calendar                                                  |
| `alias`      | Create command shortcuts                                       |
| `whereis`    | Find binaries, source, and man pages                          |
| `whatis`     | Show command purpose                                           |
| `top`        | Show real-time system stats                                    |
| `useradd`/`usermod` | Add or edit users                                       |
| `passwd`     | Set/change user password                                       |

---

## **Linters**
Linters analyze code for issues such as:
- Syntax errors
- Style/formatting inconsistencies
- Unused variables

### **Types of Linters**
1. **Syntax Linters** – Detect errors that may cause runtime issues.
2. **Style Linters** – Enforce code formatting and best practices.

They can be used standalone or integrated into IDEs and CI/CD pipelines.

---

## **ARM vs x86 Architecture**

| Feature             | ARM (RISC)                              | x86 (CISC)                                 |
|---------------------|------------------------------------------|--------------------------------------------|
| Instruction Set     | Simple, fixed-size                      | Complex, variable-size                     |
| Power Efficiency    | High (fewer transistors, less heat)     | Lower (more transistors, more heat)        |
| Usage               | Mobile devices, embedded systems        | Desktops, servers                          |

---

## **GRUB (GNU GRUB Bootloader)**

- GRUB = **GR**and **U**nified **B**ootloader
- Loaded by BIOS/UEFI
- Loads the Linux Kernel into memory
- Supports multiple OS booting

**Components:**
- **Bootloader** – Loads OS into memory
- **Boot Manager** – Selects OS to boot (if more than one)

---

## **Server OS vs Desktop OS**

| Server OS                                | Desktop OS                          |
|------------------------------------------|--------------------------------------|
| Designed for multi-user environments     | Optimized for single users           |
| Mostly CLI-based                         | GUI-based                            |
| Provides services like DNS, FTP, SSH     | Basic networking (Wi-Fi, Bluetooth)  |
| Resource management for concurrent users | Personal application performance     |

---

## **Custom OS**
A **Custom OS** is specifically built or modified to:
- Enhance control
- Improve security/performance
- Serve niche applications (e.g., embedded systems, kiosk modes)

---

## **Linux Package Managers: APT vs YUM vs DNF**

| Feature                  | **APT** (Debian/Ubuntu)               | **YUM** (CentOS/RHEL)                      | **DNF** (Fedora/RHEL8+)                    |
|--------------------------|----------------------------------------|--------------------------------------------|--------------------------------------------|
| Package Format           | `.deb`                                 | `.rpm`                                     | `.rpm`                                     |
| Install Package          | `sudo apt install pkg`                | `sudo yum install pkg`                    | `sudo dnf install pkg`                    |
| Remove Package           | `sudo apt remove/purge pkg`           | `sudo yum remove pkg`                     | `sudo dnf remove pkg`                     |
| Autoremove Unused        | `sudo apt autoremove`                 | `yum autoremove`                          | `sudo dnf autoremove`                     |
| List Installed Packages  | `apt list --installed`               | `yum list installed`                      | `dnf list installed`                      |
| Search Packages          | `apt search pkg`                      | `yum search pkg`                          | `dnf search pkg`                          |

---

## **Open Source vs Proprietary Linux**

| Type              | Description                                                       | Example                    |
|-------------------|-------------------------------------------------------------------|----------------------------|
| **Open Source**   | Source code is public and modifiable                              | Ubuntu, Debian             |
| **Proprietary**   | Source code is restricted, maintained by vendors                  | Red Hat Enterprise Linux   |

---

## **Docker: `docker commit`**
`docker commit` is used to save changes in a container by creating a new image from its current state.

### **Why Use It?**
You made changes inside a container (e.g., added a user, installed software, edited files).
You want to save those changes so they don't get lost when the container exits.
You want to create a custom image from an existing container setup.

### **Syntax**
docker commit [ options ] <container_id or name> <new_img_name>

### **Options**
1.-a, --author  
-Sets the author of the image (e.g., your name or email).  
-docker commit -a "Author Name" <container_id> <new_image_name>
2.-m, --message
-Adds a commit message to describe what changes were made.
-docker commit -m "Commit message" <container_id> <new_image_name>
3.--pause
-Pauses the container before committing.
-By default, this is set to true.
-When the container is paused, it ensures the file system's state is consistent during the commit process.
-docker commit --pause=false <container_id> <new_image_name>

---

## **Build**
-Usage: Used to build an image from a Dockerfile.
-docker build -t my-image

---

## **ps**
-Usage: Lists the running containers.

---


## **ps -a**
-Usage: Lists all containers, including stopped ones.
-docker ps -a

---

## **stop**

-Usage: Stops a running container.
-docker stop container_id_or_name

---

##**start**
-Usage: Starts a stopped container.
-docker start container_id_or_name

---

##**rm**
-Usage: Removes a container.
-docker rm container_id_or_name

---

##**rmi**
-Usage: Removes an image.
-docker rmi image_id_or_name

---

##**inspect**
-Usage: Provides detailed information about containers, images, volumes, or networks.
-docker inspect container_id_or_name

---

##**pull**
-Usage :To download Docker images from a registry (like Docker Hub or a private registry) to local machine.
-docker pull <image_name>

---

##**push**

-Usage :To upload Docker images from local machine to a Docker registry (e.g., Docker Hub or a private registry).
-Generally use this command after we've built our own image and want to share it with others or deploy it on different machines.
-docker push <image_name>

---
