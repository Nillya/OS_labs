# ЛАБОРАТОРНА РОБОТА №2

## 📌 Дисципліна: "Операційні системи"

## 🏷 **Тема:**
> Знайомство з інтерфейсом та можливостями ОС Linux.

## 👨‍🎓 **Виконав:**
- **Нагорний І.М. РПЗ-23Б**

---

## 🎯 **Мета роботи**
1. Знайомство з інтерфейсами ОС Linux.
2. Отримання практичних навиків роботи в середовищах ОС Linux та мобільної ОС – їх графічною оболонкою, входом і виходом з системи, ознайомлення зі структурою робочого столу, вивчення основних дій та налаштувань при роботі в системі


## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC.
- 📦 Віртуальна машина – VirtualBox (Oracle).
- 🐧 Операційна система GNU/Linux.
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси по Linux.

---

## 📖 Завдання для попередньої підготовки
### 🔹 **1. Складання словника базових термінів** -

| Термін англійською   | Термін українською |
|:---------------------|-------------------:|
|Hardware              |Обладнання| 
|Implementation        |Забезпечення, впровадження| 
| Operating System     |Операційна система|
|Server Applications   |Серверні програми| 
|Central processing unit (CPU)|Центральний процессор| 
|The command line interface|Інтерфейс командного рядка| 
|Traffic               |Трафік|

### 🔹 **2(4). Теоретичні питання**
📌 Завдання - Дайте визначення наступним поняттям:

 - CLI-режим:
    - `CLI-mode`: CLI stands for "Command Line Interface," which is a type of user interface that allows users to interact with a computer system through typed text commands. CLI-mode refers to a state or mode in which a computer system is operating solely through this type of interface, with no graphical user interface (GUI) components visible. CLI-mode is often used in server administration, software development, and other technical tasks that require fine-grained control over system processes.
 - Термінал на основі графічного інтерфейсу користувача:
    - `Terminal based on the graphical user interface`: A terminal is a program that allows users to access a command-line interface on a computer system. In a graphical user interface (GUI) environment, a terminal program can be used to provide a CLI-mode experience within a window or other graphical element. This type of terminal is often referred to as a "terminal emulator," since it emulates the behavior of a traditional hardware terminal (which was a physical device used to communicate with computer systems in the early days of computing). Terminal programs may offer additional features such as tabs, color coding, and copy/paste functionality.
 - Віртуальний термінал:
    - `Virtual terminal`: A virtual terminal (VT) is a software interface that allows multiple text-mode sessions to run concurrently on a computer system. Each virtual terminal can be thought of as a separate CLI-mode environment, with its own login prompt, command history, and other features. Virtual terminals are often used in Unix-like operating systems such as Linux, where they provide a way for multiple users to access a shared system without interfering with each other's work. In a GUI environment, virtual terminals can be accessed through a terminal emulator program, as described above.

 ---   
## 🎬 **Хід роботи**
### 🎥 **1. Робота в графічному режимі в ОС сімейства Linux (робота з інтернет-джерелами):**
#### 1.1. Розгляньте структуру робочого простору користувача Ubuntu, та опишіть основні його компоненти:
     - Меню Applications: 
     - Меню System
     - Навігаційний простір Activities overview
     
     The Application menu is located in the control panel, and looks like a square with nine dots. If you open it, a menu of installed programs will be expanded. From there, you can open them and add them to the Quick Access panel.
     
     The System menu is located on the right on the top panel, and contains a basic set of functions for system management: shutdown, user lock, system sound control, settings button, power saving and network connection management options.
     
     The Activities tab is located on the top left and allows you to switch workspaces (similar to desktops in Windows)

#### 1.2. Запуск програм. Дослідіть можливості запуску додатків різними способами (описати спосіб і по можливості показати скріншоти):
 - Запуск програм через панель швидкого запуску
 - Запуск програм через пошук в меню
 - Запуск програм через глобальне меню
      
      The first option:  
      Click on the icon of the desired program and wait for the download 
      ![Запуск через панель швидкого запуску](https://i.ibb.co/7xdTFfpj/The-first-option.png)
      
      The second option:  
      Enter the name of the program in the search and click on the icon 
      ![Запуск через пошук в меню](https://i.ibb.co/BKsMcjTw/The-second-option.png)
      
      The third option:  
      Find the program you need in the menu and click on its icon  
      ![Запуск через глобальне меню](https://i.ibb.co/XZ1y3WqJ/The-third-option.png)

#### 1.3. Вихід з системи та завершення роботи в Linux. Як виконати в графічному інтерфейсі наступні дії (наведіть скріни):
- 🔄 **Зміна користувача на root**  
- 🔄 **Перезавантаження системи**  
- 🔄 **Вимкнення системи** 
      
     ## 👤 Changing the user to root  
In the graphical interface, you can change to the root user as follows:  

1️⃣ Log out of the current user:  
![](https://i.ibb.co/PsmYtSFz/Log-out-of-the-current-user.png)  

2️⃣ Click “Not listed?”:  
![](https://i.ibb.co/fd6yk6xy/Click-Not-listed.png)  

3️⃣ Enter the **root** username and password:
![](https://i.ibb.co/Gf7NPBxz/Enter-the-root-username-and-password.png)

---



### 🔧  Through the terminal:  
1️⃣ Open the terminal (**Ctrl + Alt + T**)  
2️⃣ Run one of the commands:  
   ```bash
   sudo -i
   ```
   or  
   ```bash
   su -
   ```
   🔹 `sudo -i` - prompts for the password of the current user.  
   🔹 `su -` - prompts for the **root** password.  

If the root user is disabled, enable it with the command:  
   ```bash
   sudo passwd root
   ```
   Enter a new password and then use `su -` to log in.

---

## 🔄 Reboot the system  
**In the GUI**, click the restart button in the system menu:  
![](https://i.ibb.co/7Nb8YZ6Q/Restart.png)  

### 🔧 Through the terminal:  
Run one of the commands:  
```bash
sudo reboot
```
або  
```bash
sudo shutdown -r now
```

---

## 📴 Shutting down the system  
**In the GUI**, click the shutdown button in the system menu:  
![](https://i.ibb.co/qM6dpcYM/Power-OFF.png)  

### 🔧 Through the terminal:  
Run one of the commands:  
```bash
sudo poweroff
```
або  
```bash
sudo shutdown -h now
```
📌 *If you are already running as root, use the commands without `sudo`.*  

---

### 🔹 **2. Робота в середовищі мобільної ОС.**

#### 2.1. Опишіть головне меню вашої мобільної ОС, який графічний інтерфейс вона використовує?

 My Samsung S21FE phone is an Android phone, so the main menu consists of several pages, each with icons for apps. You can open the main menu by pressing the Home button on the home screen or by swiping up from the bottom of the screen.
    The graphical user interface used on Samsung S21FE is called One UI. It has a light and cozy design, with large icons and easy to use gestures. In addition, One UI uses dark and night themes to protect your eyes and conserve battery power.
    On the main menu, you will find icons for accessing all installed applications, as well as important system settings such as Wi-Fi, Bluetooth, GPS, sound, screen, battery, and more. You can also add widgets and shortcuts to your favorite apps or contacts on the home screen to make using your phone even easier.

#### 2.2. Опишіть меню налаштувань компонентів мобільного телефону.

The main component settings menu on your mobile phone includes the following options:

    - Wi-Fi: Turn Wi-Fi on/off, connect to available Wi-Fi networks, manage the list of saved Wi-Fi networks, and configure Wi-Fi settings such as saving passwords, displaying network notifications, and more.

    - Bluetooth: Turn Bluetooth on/off, connect to available Bluetooth devices, manage the list of saved Bluetooth devices, and configure Bluetooth settings such as device visibility, audio profile, and more.

    - Display: Adjust the brightness and contrast of the display, set the power saving mode, and set the wireless power mode.

    - Sound and vibration: Adjust the volume, sound effects, select ringtones and notification sounds, and set the vibration.

    - Battery: Check the battery level, manage power saving settings, and select power saving modes.

    - Cloud and accounts: Configure cloud storage, backup, and restore settings.

    - Apps: Manage apps and permissions, and configure app settings.

    - Connectivity and advanced features: Configure mobile network settings, date and time, and device security features such as fingerprint and face recognition.

    - DeX mode: Configure settings for DeX mode, which allows you to connect your phone to an external monitor and use it as a computer.

    - Developer settings: Configure developer settings such as USB debugging and dummy location.


#### 2.3. Використання комбінацій клавіш для виконання спеціальних дій.

 - You can use keyboard shortcuts in TalkBack to use features such as speaking text, navigating the screen, and managing settings. Also, if you connect keyboard to phone and depending on the app, you may be able to use keyboard shortcuts to perform certain actions. For example, in Gmail, you can use the "R" key to reply to an email.

#### 2.4.  Вхід у систему та завершення роботи пристрою. Особливості налаштувань живлення батареї. 

To log in to your Android phone, you will need to enter your passcode, pattern, or use biometric authentication, such as fingerprint or facial recognition, depending on how you have set up your device's security features.

    To shut down your Android phone, you can press and hold the Power button until the "Power off" option appears on the screen. Tap the "Power off" option to turn off your device. If your device is unresponsive or frozen, you can try a forced restart by pressing and holding the Power and Volume Down buttons simultaneously for about 10 seconds until the device restarts.

    As for battery power settings, there are several features available in the Android settings that allow you to manage and optimize your device's battery usage:

    - Battery Saver: This feature reduces your device's performance and limits background app activity to conserve battery life when the battery level drops below a certain threshold.

    - Adaptive Battery: This feature uses machine learning to optimize your device's battery usage by identifying and limiting the activity of infrequently used apps.

    - Battery Usage: This option shows you which apps are using the most battery power and allows you to restrict their activity when the screen is off or in the background.

    - Battery Optimization: This option allows you to select specific apps that you want to optimize for battery usage.

    - Battery Health: This option displays your device's current battery health status and provides recommendations to prolong battery life.
    

---

### Відповіді на контрольні питання:

-  .1. Наведіть приклади серверних додатків Linux для сервера баз даних, серверів розсилки повідомлень та файлообмінників.

✏️ `Database server`:

      - MySQL/MariaDB - an open source relational database management system
      - PostgreSQL - an open source object-relational database management system
      - MongoDB is an open source document-oriented database management system
      - SQLite - an open source embedded database

✏️ `A server for sending messages`:

      - Postfix is an open source mail server that supports SMTP and IMAP/POP3
      - Sendmail - an open source mail server that supports SMTP and IMAP/POP3
      - Exim is an open source mail server that supports SMTP and IMAP/POP3
      - Mailman is an open source program for managing email distribution lists.

✏️`File sharing server`:

     - Samba is an open source file sharing server that supports SMB/CIFS protocols
     - vsftpd - an open source FTP server
     - ProFTPD - an open source FTP server
     - Pure-FTPd is an open source FTP server that supports security and user profile customization.
    
-  .2. Порівняйте оболонки Bourne, C, Bourne Again (Bash), the tcsh, Korn shell (Ksh) та zsh.
 There are several different Unix/Linux shells available, each with its own set of features and characteristics. Here is a brief comparison of some of the most popular ones:

      - `Bourne shell (sh)`: This is the original Unix shell, developed by Stephen Bourne in the 1970s. It is a simple, text-based shell that does not have many advanced features. It is often used for scripting and automation.

      - `C shell (csh)`: This shell was developed by Bill Joy in the late 1970s as an alternative to the Bourne shell. It has a C-like syntax and some additional features, such as command-line editing and history. However, it is not as widely used as some of the other shells.

      - `Bourne-Again shell (bash)`: This is the default shell on most Linux distributions. It is based on the Bourne shell but adds many advanced features, such as command-line editing, history, programmable tab completion, and shell scripting. It is highly customizable and widely used.

      - `Tcsh`: This shell is an enhanced version of the C shell, with additional features such as command-line editing, history, and job control. It is popular among users who prefer a C-like syntax and advanced features.

      - `Korn shell (ksh)`: This shell was developed by David Korn in the 1980s as an alternative to the Bourne shell. It combines the features of the Bourne shell and the C shell, and adds some advanced features such as command-line editing, history, and job control. It is highly customizable and widely used.

      - `Zsh`: This shell was developed in the 1990s as an alternative to bash. It is highly customizable and includes many advanced features such as command-line editing, history, programmable tab completion, and advanced globbing. It is popular among power users and developers.
    
-  .3. Для чого потрібен менеджер пакетів. Які менеджери пакетів ви знаєте у Linux?
  A `package manager` is a tool used to manage the installation, upgrading, and removal of software packages in a computer system. It simplifies the process of installing and managing software by automating tasks such as dependency resolution and version management.

    In Linux, there are several package managers available, including:

      - `Advanced Packaging Tool (APT)`: This is the default package manager used in Debian-based Linux distributions, such as Ubuntu and Debian. It is a command-line tool that can manage software packages from local repositories or from the internet.

      - `Yellowdog Updater Modified (YUM)`: This is the default package manager used in Red Hat-based Linux distributions, such as CentOS and Fedora. It is a command-line tool that can manage software packages from local repositories or from the internet.

      - `Pacman`: This is the package manager used in Arch Linux. It is a command-line tool that can manage software packages from local repositories or from the internet.

      - `Zypper`: This is the default package manager used in SUSE Linux. It is a command-line tool that can manage software packages from local repositories or from the internet.

      - `Portage`: This is the package manager used in Gentoo Linux. It is a command-line tool that can manage software packages from local repositories or from the internet.

      - `Snap`: This is a package manager used in Ubuntu and other Linux distributions. It is designed to work with containerized applications and can manage packages from a central store, which are installed in a sandboxed environment.

      - `Flatpak`: This is a package manager used in several Linux distributions. It is designed to work with containerized applications and can manage packages from a central store, which are installed in a sandboxed environment.
-  .4.  Які засоби безпеки використовуються в Linux?
   Linux is well-known for its security features and has been designed with security in mind from the ground up. Here are some of the key security features of Linux:

      - `User and group permissions`: Linux has a robust user and group permission system that restricts access to files and system resources. Each file and directory has a set of permissions that control who can read, write, and execute them.

      - `Firewall`: Linux has a built-in firewall called iptables, which can be used to restrict network traffic to and from the system.

      - `Security modules`: Linux has several built-in security modules, including SELinux and AppArmor, which can be used to restrict the actions of individual processes and applications.

      - `Encrypted filesystems`: Linux supports several encryption technologies, including dm-crypt, which can be used to encrypt entire filesystems, protecting data even if the system is stolen or compromised.

      - `Package management`: Linux package managers, such as APT and YUM, use digital signatures to ensure that packages are authentic and have not been tampered with.

      - `Sandboxing`: Linux supports containerization and virtualization technologies, such as Docker and KVM, which can be used to run applications and services in isolated environments.

      - `Regular updates`: Linux distributions provide regular security updates to address known vulnerabilities and protect against new threats.

      - `Auditd`: Linux includes the auditd daemon, which can be used to monitor system activity and provide an audit trail of actions taken on the system.

      - `Secure boot`: Linux supports secure boot, which ensures that the system boots only with trusted bootloaders and kernel images.
    
-  .5.  Чому використання віртуалізації зараз стало таким актуальним?
  The use of virtualization has become more relevant in recent years for several reasons:

      - `Server Consolidation`: Many organizations have hundreds or thousands of servers, each dedicated to a specific application or task. This can be expensive to maintain, and often results in underutilized resources. By using virtualization, multiple virtual machines (VMs) can be hosted on a single physical server, leading to better utilization of resources and cost savings.

      - `Agility`: Virtualization allows organizations to quickly spin up new VMs and test new applications and services without the need for additional physical hardware. This can lead to faster deployment times and improved time-to-market for new products and services.

      - `Disaster Recovery`: Virtualization makes it easier to create backups of entire VMs, including the operating system, applications, and data. In the event of a disaster or hardware failure, these backups can be quickly restored to another physical host or to the cloud.

      - `Security`: Virtualization allows organizations to create isolated environments for specific applications or services, reducing the risk of security breaches and improving overall system security.

      - `Cloud Computing`: Virtualization is a key technology behind cloud computing, which has become increasingly popular in recent years. Cloud providers use virtualization to offer scalable and flexible computing resources to their customers, which can be easily provisioned and deprovisioned as needed.
    
-  .6.  Як ви розумієте поняття контейнеризації?  
    `Containerization` is a technology that allows running isolated environments on a single physical server. Containers are lightweight and portable, allowing applications to be packaged with all their dependencies and libraries, and run consistently across different environments, such as development, testing, and production.

    Containers use operating system-level virtualization to isolate the application and its dependencies from the underlying infrastructure. This means that a container runs on the host operating system and shares the same kernel, but has its own file system, network stack, and other system resources.
    
- .7.  Які переваги/недоліки використання програмного забезпечення з відкритим кодом?
  Open source software refers to software whose source code is freely available for anyone to view, modify, and distribute. Here are some advantages and disadvantages of using open source software:
  `Advantages`:
      - `Cost`: Open source software is often free to use, distribute, and modify, which can result in significant cost savings for individuals and organizations.

      - `Flexibility`: Open source software can be modified and customized to meet specific needs, making it more flexible than proprietary software.

      - `Security`: With open source software, anyone can review the code for vulnerabilities and contribute fixes, which can result in faster identification and resolution of security issues.

      - `Reliability`: Open source software is often developed collaboratively by a community of developers and users, which can result in higher quality and more reliable software.

      - `Innovation`: Open source software allows anyone to contribute to the development and improvement of software, which can result in more rapid innovation.

    `Disadvantages`:

      - `Support`: Open source software often lacks the same level of professional support that proprietary software offers, which can make it difficult to get help when issues arise.

      - `Compatibility`: Some open source software may not be compatible with proprietary software or other systems, which can limit its usefulness in certain environments.

      - `Complexity`: Open source software can be more complex to use and configure than proprietary software, which may require more time and resources to learn and implement.

      - `Documentation`: Open source software may not have the same level of documentation and user guides that proprietary software offers, which can make it more difficult to learn and use.

      - `Fragmentation`: With so many different open source projects available, there can be fragmentation and duplication of effort, which can result in a lack of cohesion and standards across different projects.
    
- .8.  Скільки активних віртуальних консолей (терміналів) може бути у процесі роботи Linux по замовчуванню. Як їх викликати та між ними перемикатися? Наведіть приклади?
  
    By default, most Linux distributions have six active virtual consoles or terminals available for use. These virtual consoles are accessed by pressing the Ctrl+Alt+F1 through Ctrl+Alt+F6 keys on the keyboard, with each key combination corresponding to a different virtual console. To switch between virtual consoles, you simply press the key combination for the console you want to switch to. For example, pressing Ctrl+Alt+F2 will switch to the second virtual console.

    Here are some examples of how to call and switch between virtual consoles in Linux:

      - To switch to the second virtual console, press Ctrl+Alt+F2.
      - To switch back to the first virtual console, press Ctrl+Alt+F1.
      - To switch to the third virtual console, press Ctrl+Alt+F3.
      - To switch to the fourth virtual console, press Ctrl+Alt+F4.
      - To switch to the fifth virtual console, press Ctrl+Alt+F5.
      - To switch to the sixth virtual console, press Ctrl+Alt+F6.
      
    Once you switch to a virtual console, you can log in with your username and password to start using the command line interface.

    Virtual consoles are useful for troubleshooting and debugging Linux systems, as they provide a way to access the system directly and independently of the graphical user interface. They are also helpful in situations where the GUI is not available or not functioning properly.

- .9. Яка віртуальна консоль (термінал) виконує функцію графічної оболонки?
 
    The virtual console that serves as a graphical shell in Linux systems depends on the display manager that is used.

    On most Linux distributions, the default display manager is the X Display Manager (XDM), which runs on the seventh virtual console (Ctrl+Alt+F7) and launches the graphical user interface (GUI) when you log in. However, some Linux distributions, such as Ubuntu and Linux Mint, use the LightDM display manager, which also runs on the seventh virtual console.

    Other display managers, such as GDM, SDDM, and KDM, may use a different virtual console for the GUI, so it's important to consult the documentation or online resources for the specific distribution you are using to determine which virtual console is used for the graphical shell.
    
- .10. Чи можлива реєстрація в системі Linux декілька разів під одним і тим же системним ім’ям? Які переваги це може надати?
 
    In a Linux system, it is not possible to register multiple user accounts with the same system name. Each user account must have a unique name in the system.

    Having multiple user accounts with the same name could cause confusion and make it difficult to manage permissions and access control, as the system would not be able to distinguish between different users with the same name.

    However, it is possible to have multiple user accounts that share the same UID (user ID) in the system. This is called a "shared user account". With a shared user account, multiple users can log in to the system with the same account credentials, but each user will have their own unique home directory and profile settings.

    One advantage of using a shared user account is that it can simplify the management of access control and permissions, as all users with the same UID will have the same level of access to files and directories in the system. This can be useful in environments where multiple users need to access the same resources or work on the same projects. However, it is important to use caution when using shared user accounts, as it can also make it more difficult to track user activity and determine who made changes to files and directories.

---
   
## 🏁 **Висновки**

In the course of the laboratory work, we studied the basic principles of the Linux operating system and its functionality. We explored key system management methods using both the graphical user interface and the command line. Additionally, we gained practical experience in executing terminal commands, configuring the system, and managing files and processes. This knowledge will be useful for further work with Linux-based environments and system administration tasks.

