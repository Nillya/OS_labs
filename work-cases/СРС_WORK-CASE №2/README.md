# 🛠️ Практичне завдання “Work-case 2”

## 📌 Дисципліна: "Операційні системи"
## 👨‍🎓 Виконав: **Нагорний І.М.** (група РПЗ-23Б)

---

## 🎯 **Мета роботи**
- Створити інструкцію зі встановлення Linux-системи на гіпервізорі ІІ типу.

---

## ❗ Linux Installation Guide ❗

### 🔹 **1. Встановлення гіпервізора**

1️⃣ **Встановіть на своїй домашній робочій станції гіпервізор ІІ типу – Virtual Box, VMWare Workstation, Hyper-V (або інший на Ваш вибір**
 - Download an Ubuntu ISO
 - Download and install VirtualBox or VMware Workstation

2️⃣ **Опишіть набір базових дій в встановленому Вами гіпервізорі:**
#### 🖥️ **2.1. Створення нової віртуальної машини**
- In VirtualBox, click “Create” and select the downloaded ISO file.
- In VMware Workstation, click Create a New Virtual Machine.

#### 🛠️ **2.2. Налаштування обладнання**  

#### 🔹 **VMware Workstation:**  

🖥️ **Крок 1:** Open VMware Workstation and click **Create a New Virtual Machine**.  
![Step 1](https://i.ibb.co/DHj3Nq6z/image.png)

⚙️ **Крок 2:** Select **type of installation** (Typical or Custom)  
![Step 2](https://i.ibb.co/5WZcW33c/image.png)  

💿 **Крок 3:** Specify the path to the **ISO image** of the selected Linux system  
![Step 3](https://i.ibb.co/S4XbPn2v/vmware-Ahx1ud-A1h-R.png)

✏️  **Крок 4:** Enter the data (Username, Password)

![Step 4](https://i.ibb.co/zW5CTD4B/vmware-z-JTb5-WUG4-H.png)  

💾 **Крок 5:** Configure the **saving options** of the virtual machine  
![Step 5](https://i.ibb.co/LXKgL663/image.png)  

🔧 **Крок 6:** Complete the setup and start the virtual machine! 🚀  
![Step 6](https://i.ibb.co/LdWpDj3K/image.png)  

#### 🔹 **Virtual Box:**
![Create VirtualBox](https://i.ibb.co/n8b8XrSQ/image.png)
Enter the name and select the Ubuntu Iso we downloaded 
![VirtualBox](https://i.ibb.co/m5GrgK1D/image.png)


#### 🌐 **2.3. Налаштування мережі**
Right click on the VM and click on settings go to Hardware and go to Network Adapter
#### 🔹 **VMware Workstation:** 
![VMware](https://i.ibb.co/vvY7TmHf/image.png)
![VMware](https://i.ibb.co/WW8MGj5w/image.png)

In settings we can go to menu "network" and select "enable network adapter" 
#### 🔹 **Virtual Box:**
![VirtualBox](https://i.ibb.co/B527Yn2P/image.png)

#### 🔌 **2.4. Робота із зовнішніми носіями**
Right click on the VM and click on settings go to Hardware and go to USB Controller
#### 🔹 **VMware Workstation**
![VMware](https://i.ibb.co/vvY7TmHf/image.png)
![VMware](https://i.ibb.co/Z1xC6GMN/image.png)
#### 🔹 **Virtual Box:**
For external media, we also need to go into settings and select the usb-port that is available. 
![VirtualBox](https://i.ibb.co/60yCnKNZ/image.png)


3️⃣ **Встановіть в вашому гіпервізорі операційну систему GNU/Linux (будь-який зручний Вам дистрибутив) у базовій конфігурації з графічною оболонкою.**
Далі все буде показано на прикладі VirtualBox, тому що потрібно виконати ті ж дії

- Installed Ubuntu 20.04.1 LTS on my virtual machine. To do this, you need to go to the official ubuntu website and download the Ubuntu Desktop ISO. Then, when you create a new virtual machine, you need to choose a pre-booted Iso, and the rest of the settings are made as you wish. Next, you need to wait for the installation. Once the new OS is set up, you need to update the packages. To do this, press Ctrl+Alt+F3/F4/F5/F6/F7 to launch the virtual console and enter the commands apt-get update and apt-get upgrade
![Install](https://i.ibb.co/FqYM2Ddv/image.png)
After that, press Ctrl+Alt+F1/F2 to return to the graphical interface. Now you can use the visual terminal (in my case, before these operations, the visual terminal did not start at all)

### 4️⃣ **Створення другої віртуальної машини**  

#### 🖥️ **4.1 Встановлення GNU/Linux у мінімальній конфігурації**  
📌 Встановіть операційну систему **GNU/Linux** без графічного інтерфейсу, використовуючи лише термінальний ввод-вивід.  
✅ **This was demonstrated above.**  

#### 🎨 **4.2 Встановлення графічної оболонки GNOME**  
📌 Після встановлення мінімальної версії ОС виконайте інсталяцію **GNOME** як основного графічного середовища.  

🔹 **Процес встановлення:**  
![Step 1](https://i.ibb.co/fV0jhLZP/image.png)  
![Step 2](https://i.ibb.co/R47ZNQVW/image.png)  
![Step 3](https://i.ibb.co/rRp36FqR/image.png)  
![Step 4](https://i.ibb.co/W4PsVwDs/image.png)  

#### 🖌 **4.3 Встановлення другої графічної оболонки та порівняння з GNOME**  
📌 Встановіть **додаткову графічну оболонку** (їх можливий перелік можна знайти в лабораторній роботі №1) та порівняйте її можливості з GNOME.  

🔹 **KDE Plasma i installed:**  
![KDE Step 1](https://i.ibb.co/1GD80nPn/image.png)  
![KDE Step 2](https://i.ibb.co/nNBjtsSY/XGova-Ejh-A6.png)  
![KDE Step 3](https://i.ibb.co/XZ39CPHJ/Fn-Lc-KAb-EOO.png)  

### ⚖️ **GNOME and KDE Plasma Comparison**  
GNOME and KDE Plasma are two of the most popular graphical desktop environments on Linux. Both have their advantages and disadvantages, and neither is clearly better, as the choice depends on the user's needs and preferences.  

✅ **GNOME**  
- 🔹 Characterized by simplicity, convenience, and ergonomics, offering a clean and minimalist interface.  
- 🔹 Equipped with useful features such as a notification system, search, multi-touch gesture support, and more.  
- 🔹 Has the largest number of extensions that allow you to flexibly customize the environment to your own needs.  

✅ **KDE Plasma**  
- 🔹 Offers extensive customization options, allowing you to change the shell to your liking.  
- 🔹 Provides a large number of settings and supports multiple desktops simultaneously.  
- 🔹 Contains built-in programs such as a terminal, a text editor, and integration with a Google account.  

📌 **Conclusion:** The choice between GNOME and KDE Plasma depends on user preferences:  
- If you prefer **simplicity and ergonomics**, go with **GNOME**.  
- If you value **customization and flexibility**, **KDE Plasma** is the better choice.  

---
⚠️ [Another good installation guide (Virtual box)](https://www.educba.com/install-linux/) - If there are any questions this is a more detailed download

❗❗❗ Why are there different Ubuntu versions in the photos?

The reason is simple: in VMware Workstation, the installation was performed with a graphical environment included from the start, while in VirtualBox, the installation began without a graphical interface.