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


