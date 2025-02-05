# ЛАБОРАТОРНА РОБОТА №1

## 📌 Дисципліна: "Операційні системи"

## 🏷 **Тема:**
> Знайомство з робочим середовищем віртуальних машин та особливостями операційної системи Linux.

## 👨‍🎓 **Виконав:**
- **Нагорний І.М. РПЗ-23Б**

---

## 🎯 **Мета роботи**
1. Знайомство з гіпервізорами різного типу, віртуалізацією при роботі з операційними системами.
2. Ознайомлення з основними видами сучасних ОС та огляд їх можливостей.


## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC.
- 🖥 ОС сімейства Windows (Windows 7).
- 📦 Віртуальна машина – VirtualBox (Oracle).
- 🐧 Операційна система GNU/Linux – CentOS.
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси по Linux.

---

## 📖 Завдання для попередньої підготовки
### 🔹 **1. Складання словника базових термінів** -
📌 Завдання - Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань класифікації віртуальних середовищ

| Термін англійською   | Термін українською |
|:---------------------|-------------------:|
|hipervizor            |гіпервізор          |
|host operating system |головна ОС          |
|guest operating system|гостьова ОС         |
|shared hosting        |спільний хостинг    |
|machine simulator     |машинний емулятор   |
|binary translation    |бінарний транслятор |
|kernel                |ядро                |
|distibution           |розподілення        |
|embrace               |надбудова           |

### 🔹 **2. Теоретичні питання**
📌 Завдання - Прочитавши матеріал з коротких теоретичних відомостей дайте відповіді на наступні питання:
#### 🖥 **Гіпервізори та їх типи**

  1. Охарактеризуйте поняття «гіпервізор». Які бувають їх типи?
  A **hypervisor** is a computer program or processor hardware that provides simultaneous and parallel execution of several virtual machines, each of which runs its own operating system, on one physical computer
    
   - Offline hypervisor 
    - A standalone hypervisor is booted with a bootloader or firmware, and runs configured operating systems in separate virtual machines. 
    - Examples: VMware ESX, PR/SM. 
  - Based on the underlying OS
    - This is a component that runs in the same ring as the kernel of the underlying OS. The guest code can run directly on the physical processor, but access to the I/O devices of the computer from the guest OS is through a second component, a normal process of the main OS - the user-level monitor.
    - Examples: Windows Virtual PC, VMware Workstation, QEMU, Parallels, VirtualBox, OVirt.
    
  - Hybrid 
    - A hybrid hypervisor consists of two parts: a thin hypervisor that controls the processor and memory, and a special service OS in a lower-level ring that runs under the hypervisor. Through the service OS, guest OSes access the physical hardware.
    - Examples: Microsoft Virtual Server, Sun Logical Domains, Xen, Citrix XenServer, Microsoft Hyper-V.

    ### 🔹 **2.1. Основні компоненти та можливості гіпервізорів**
    📌 Завдання - Перерахуйте основні компоненти та можливості гіпервізорів відповідно до свого варіанту (порядковий номер по журналу), табл.1.
    
    #### Xen Hypervisor

    Xen is a powerful open-source hypervisor widely used in server and cloud environments. Its key advantages include high performance, hardware virtualization support, and strong isolation of virtual machines for enhanced security.

   #### Key Features of Xen:

- **Support for Para-Virtualization and Full Virtualization**  
  Xen allows running both fully virtualized and para-virtualized operating systems, optimizing performance based on the hardware capabilities.

- **Domain-Oriented Architecture (Dom0 and DomU)**  
  Xen uses a privileged control domain (Dom0) to manage guest virtual machines (DomU), ensuring efficient resource management and security.

- **Multi-VM Support**  
  Enables running multiple virtual machines with different operating systems simultaneously.

- **Flexible Resource Management**  
  Allows fine-tuned control over CPU, RAM, and storage allocation for each virtual machine.

- **Live Migration**  
  Supports seamless migration of virtual machines between physical servers without downtime.

Xen is widely used in cloud platforms like AWS, thanks to its scalability, stability, and security.  

 ---   
## 🎬 **Хід роботи**
### 🎥 **1. Подивіться ознайомчі відео та демонстраційні матеріали з наступних напрямків:**
   1. [GNU/Linux. Базові відомості.](https://www.youtube.com/watch?v=k4AKMLS2Ac8)
   2. [Встановлення CentOS у VirtualBox.](https://www.youtube.com/watch?v=W3XTYYoHe9A)
   3. [Встановлення CentOS в текстовому режимі.](https://www.youtube.com/watch?v=gOR-1o3K18Q)
   4. [Встановлення оточення робочого столу Gnome в CentOS.](https://www.youtube.com/watch?v=gcEiIH3KF4Y)
   5. [Встановлення оточення робочого столу KDE в CentOS.](https://www.youtube.com/watch?v=_ruIWLExaOY)
   6. [The Shell (Linux)](https://drive.google.com/open?id=0B0PV0_SM0LoDSVNPWUVRdUxaN2s)
   7. [Огляд графічних оболонок Linux](https://www.youtube.com/watch?v=lEGplwLXZ78)

---

### 🔹 **2. Відповіді на питання з вiдео.**


   ### 💾 Operating System Deployment on VirtualBox and Linux Installation Guide

#### 2.1. Stages of Deploying an Operating System on VirtualBox

To install an operating system on a VirtualBox virtual machine, follow these steps:

1. **Download the OS image** (ISO file) of the desired system.
2. **Open VirtualBox** and click the "Create" button.
3. **Select "Expert Mode"** for advanced configuration.
4. **Configure OS details**:
   - Enter the OS name.
   - Select the system type and version.
   - Specify the location for storing VM files.
5. **Set up Automatic Installation** (optional user details).
6. **Allocate System Resources**:
   - Set CPU, RAM, and video memory limits.
7. **Configure Storage**:
   - Choose disk type (VDI, VHD, VMDK).
   - Define disk size and storage method (fixed or dynamic).
8. **Finalize the setup** and start the installation process.

---

#### 2.2. Are There Any Hardware Limitations for Installing 32-bit and 64-bit OS?

- A **32-bit processor** can only run **32-bit operating systems**.
- A **64-bit processor** supports both **32-bit and 64-bit OS**.
- To run a **64-bit OS in VirtualBox**, hardware virtualization (VT-x/AMD-V) must be enabled in BIOS/UEFI.
- Some older CPUs may lack hardware support for virtualization, limiting performance and compatibility.

---

#### 2.3. Main Stages of Installing Linux in Text Mode

The basic steps for installing a Linux OS in text mode include:

1. **Select installation language**.
2. **Choose keyboard layout**.
3. **Set up network configuration** (if required).
4. **Select disk partitioning method** (automatic or manual).
5. **Choose software packages** and additional components.
6. **Create user accounts** and set a root password.
7. **Start the installation process**.
8. **Finalize and reboot** into the installed system.

The exact steps may vary depending on the Linux distribution.

---
### **2.4. Installing GNOME and KDE Desktop Environments in Linux (After Text-Mode Installation)**

If Linux was installed in text mode, you can install graphical desktop environments using the following commands:

#### **Installing GNOME:**

For **Debian/Ubuntu-based distributions:**
```bash
sudo apt update
sudo apt install gnome-session gdm3
```
For **CentOS/RHEL:**
```bash
sudo yum groupinstall "GNOME Desktop" "X Window System"
```
For **Fedora:**
```bash
sudo dnf groupinstall "GNOME Desktop Environment"
```

#### **Installing KDE Plasma:**

For **Debian/Ubuntu-based distributions:**
```bash
sudo apt update
sudo apt install kde-plasma-desktop
```
For **CentOS/RHEL:**
```bash
sudo yum groupinstall "KDE Plasma Workspaces" "X Window System"
```
For **Fedora:**
```bash
sudo dnf groupinstall "KDE Plasma Desktop"
```

After installation, set the system to boot into graphical mode:
```bash
sudo systemctl set-default graphical.target
reboot
```

### **2.5. Overview of KDE and Fluxbox Desktop Environments**

#### **KDE Plasma**
- A full-featured desktop environment with a modern, customizable interface.
- Includes advanced features like widgets, a panel, and a powerful file manager (Dolphin).
- Offers a Windows-like experience, suitable for both new and experienced users.
- Commonly used in distributions such as **Kubuntu, Fedora KDE, and openSUSE**.

#### **Fluxbox**
- A lightweight window manager optimized for performance and minimal system resource usage.
- Uses a simple interface with configurable menus and keyboard shortcuts.
- Ideal for older computers and users who prefer a minimalistic environment.
- Found in distributions like **antiX, Debian minimal setups, and Puppy Linux**.

Both environments cater to different needs: **KDE Plasma** is designed for users who need a feature-rich experience, while **Fluxbox** is perfect for those who prioritize speed and efficiency.

---

   
## 🏁 **Висновки**
Xen is a versatile hypervisor suitable for virtualization in cloud and enterprise environments. It provides efficient resource management, strong security, and live migration capabilities.
Deploying OS in VirtualBox requires proper configuration, particularly when considering hardware limitations between 32-bit and 64-bit systems. Understanding Linux installation in text mode and adding graphical environments like GNOME or KDE enhances usability. KDE provides a full-featured experience, while Fluxbox is ideal for minimal resource usage.
By leveraging Xen and virtualization tools, users can optimize performance, security, and system flexibility for various applications.

---

### Відповіді на контрольні питання:

-   1. Type 1 hypervisor (Standalone hypervisor) type 2 (Based on the underlying OS) differ in that the type 1 hypervisor runs directly on the hardware and is independent of the underlying OS, while the type 2 hypervisor can run directly on the physical processor, but access to the computer's I/O devices from the guest OS is through a second component, the usual processor of the underlying OS - the user-level monitor. A type 1 hypervisor has a higher performance than a type 2 hypervisor. 

-  2. GNU General Public License (GNU General Public License or GNU General Public License) is one of the most popular free software licenses. The concept of "GNU GPL" is to provide licenses for the distribution of programs, plug-ins or class libraries for free and open source.
-  3. The essence of open-source software is that the source code is freely available for anyone to access, use, modify, and distribute, without restrictions or fees.
-  4. A distribution kit is a package that contains all the files necessary to install and run a software program on a particular operating system or platform.

-  5.  The main tasks of the system administrator (superuser) in Linux include:
installation of the OS;
managing the OS boot process;
setting the operating modes of the OS;
editing configuration files;
mounting and unmounting file systems;
adding and removing OS users;
update the software;
configuring the OS kernel;
ensuring reliable operation of the OS;
configuring a computer network.

- 6. Android is a mobile operating system based on the Linux kernel. It uses the Linux kernel as its foundation, but also includes its own unique user interface and software stack.

- 7. Embedded Linux is a version of the Linux operating system designed for use in embedded systems, such as smartphones, routers, and other small devices. Its main features include a small footprint, real-time capabilities, and support for a wide range of hardware architectures. The scope of Embedded Linux includes industrial automation, automotive systems, medical devices, and more.
 
- 8. The process of changing the Linux boot type from graphical to text or vice versa depends on the specific Linux distribution and version are using but there are general steps that work on some systems:
   - Boot your Linux system and wait for the bootloader screen to appear.
   - Select the boot option you want to modify and press the "e" key to edit it.
   - Locate the line that starts with "linux" or "linuxefi" and append the word "text" (for text mode) or "graphical" (for graphical mode) at the end of the line.
   - Press "Ctrl + x" to boot using the modified boot option.

🔥 CLI vs GUI: Key differences between CLI and GUI
  - CLI allows users to manually enter a command to perform a desired task, while in GUI, users are provided with visuals to interat with the operating system, such as buttons, icons, images, etc.
  - GUI tasks are easy to perform and good for beginners. The CLI, on the other hand, requires experience with commands and syntax.
  - GUI systems require a mouse and keyboard, while CLI just requires a keyboard to work.
  - Higher accuracy can be achieved in CLI compared to GUI.
  - GUI has the advantage of flexibility where CLI systems are inflexible.
  - GUI consumes more system space while CLI requires less system resources and space.
  - The appearance of the CLI cannot be changed. On the contrary, the appearance of the GUI is adjustable.
  - CLI is faster than GUI.

| Параметр  | CLI (Командний рядок) | GUI (Графічний інтерфейс) |
|-----------|----------------------|--------------------------|
| 📌 Зручність | Вимагає знань команд | Інтуїтивно зрозумілий |
| ⏱ Швидкість | Висока | Дещо повільніша |
| 🖱 Контроль | Повний контроль | Обмежені можливості |
| 💾 Витрати ресурсів | Мінімальні | Високі |
| 🎨 Гнучкість | Не змінюється | Можна налаштовувати |

