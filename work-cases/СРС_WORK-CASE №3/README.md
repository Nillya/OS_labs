# 🛠️ Практичне завдання “Work-case 3”

## 📌 Дисципліна: "Операційні системи"
## 👨‍🎓 Виконав: **Нагорний І.М.** (група РПЗ-23Б)


## 🎯 **Мета роботи**

- Ознайомитися з процесом клонування віртуальної машини та перенесення ОС у інше віртуальне середовище.
- Вивчити типи мережевих з'єднань між віртуальними машинами.
- Налаштувати мережу між основною ОС та її клоном.
- Організувати обмін файлами між основною ОС і віртуальними машинами.

---

### 🔹 **1. Клонування віртуальної машини**  
📌 В робочому середовищі віртуальної машини Virtual Box, VMWare Workstation (або інший на Ваш вибір) необхідно виконати:

1️⃣ Клонування вашої віртуальної робочої ОС (Work-case 2). Яким чином це можна зробити? Продемонструйте всі етапи:

At the first stage, you need to select the "images" section
![NOT-----](https://i.ibb.co/hFhM95PT/image.png)  

Next, you need to click on the "Clone" button
![NOT-----](https://i.ibb.co/zHGMV9gG/firefox-5q2de-P5oa-E.png)  

This screen should have a name for the clone and a path for its location
![NOT-----](https://i.ibb.co/RTpLVf7H/image.png)  

Next, you need to select the type of cloning
![NOT-----](https://i.ibb.co/Tq4xvXmw/image.png)  

And then wait for the cloning to finish
![NOT-----](https://i.ibb.co/Q38bHwGn/image.png)  

The system clone will appear in the list of available systems
![NOT-----](https://i.ibb.co/rGhpmqp4/image.png)  

2️⃣ Може виникнути необхідність перенесення (клонування) ОС у інше віртуальне середовище. Які треба виконати дії для експорту вашої віртуальної робочої ОС?

From the File menu, select "Export Configurations"
![NOT-----](https://i.ibb.co/cSCRsBzN/image.png)  

In the window that appears, select the system to export
![NOT-----](https://i.ibb.co/tpSn5ppc/image.png)  

Next, choose a location
![NOT-----](https://i.ibb.co/1GmkP0D3/image.png)  

In this menu click "done"
![NOT-----](https://i.ibb.co/gMnqQFyg/image.png)  

---

### 🔹 **2. Типи мережевих з'єднань у віртуальних машинах**  
📌 В ході роботи одна робоча віртуальна машина може взаємодіяти з іншою. Для цього необхідно між ними розгорнути мережу. Опишіть які типи організації мережевих з’єднань підтримуються в середовищі віртуальних машин, в чому особливість кожного з них:

  - Трансляція мережевих адрес (NAT):  
  NAT (Network Address Translation) network allows virtual machines to communicate with the external network, but not with each other. This is useful when you want to isolate virtual machines from each other while still providing them with internet access.
  - Мережевий міст (Bridged):
    This type of network connection allows virtual machines to communicate with the external network and other machines on the same network as the host machine. In a bridged network, the virtual machine is connected to the physical network adapter of the host machine, which allows it to use the same network as the host.
  - Віртуальний адаптер хоста (Host-only):  
    This is a private network that only allows communication between the virtual machines and the host machine. Host-only networks are useful when you want to test network configurations or services without exposing them to the outside world.
  - Внутрішня мережа (Internal Network):  
    This type of network connection only allows communication between virtual machines on the same host machine. It does not allow communication with the external network or the host machine.  
      
    Each type of network connection has its own unique features and use cases, depending on the specific needs of the virtual machine environment. Host-only networks are useful for testing and development, while bridged networks are useful for production environments where virtual machines need access to the external network. NAT networks are useful for providing internet access to virtual machines while maintaining isolation, and internal networks are useful for creating private networks between virtual machines on the same host.

---

### 🔹 **3. Налаштування мережі між віртуальними машинами**  
📌 Розгорніть мережу між вашою робочою ОС та її клоном (завдання 1):

1️⃣ **Налаштування мережевих параметрів ОС:**  
📌 Продемонструйте базові команди для налаштування мережевих параметрів ОС, поясніть, що вони виконують.
![](https://i.ibb.co/xSsWmb8P/image.png)  
![](https://i.ibb.co/n8NSx4pK/image.png)  
📌 Both vital machines have two adapters, 1 for internet access, the other for LAN communication

2️⃣ **Перевірка доступу до Інтернету:**  
📌 Обидві ОС мають мати вихід у мережу Інтернет. Відкрийте браузер та перегляньте будь-яке відео в youtube

Both machines have Internet access
![](https://i.ibb.co/7dgYhxTf/firefox-OWYGMLw70-Z.png)  

3️⃣ **Обмін повідомленнями між ОС через локальну мережу:**  
📌 Налаштуйте та продемонструйте обмін повідомленнями між двома ОС по локальній мережі. Які команди в терміналі при цьому необхідно ввести?

![NOT-----](https://i.ibb.co/mrdB4gbk/firefox-NOjg3-Ao-Dk-P.png)  

On one machine, you need to open the listening port, and on the other, connect to it.  

4️⃣ **Налаштування спільної мережевої папки:**  
📌 Налаштуйте спільну мережеву папку для обох ОС. Спробуйте скопіювати файли з цієї директорії в домашній каталог користувача (віртуальна робоча ОС) та на робочій стіл (клон віртуальної робочої ОС).

To create a shared directory, you need to create a folder, and select "local network share" in the context menu
![NOT-----](https://i.ibb.co/k6wmpGGX/image.png)  
 
On another machine, in the "other locations" section, a folder will appear with the name of the computer from which the shared folder was made
![NOT-----](https://i.ibb.co/HmSfy99/image.png)  

I moved the tree picture to a folder
![NOT-----](https://i.ibb.co/bRmD9vq9/image.png) 

And she showed up at her original location
![NOT-----](https://i.ibb.co/wNFzJxY8/g.png) 

---

### 🔹 **4. Обмін інформацією між основною ОС та віртуальними машинами**  
📌 Яким чином можна організувати обмін інформацією між вашою основною ОС (наприклад Windows) та віртуальними ОС? Скопіюйте довільний аудіо-файл з вашої основної ОС на робочий стіл віртуальної ОС та її клона. Як зробити зворотну дію, коли треба документ з робочого столу віртуальної ОС скопіювати до вашої основної робочої ОС?

To enable file sharing between the main Windows OS and the Ubuntu virtual machine using Guest Editions, you need to install Guest Additions. This can be done by opening the Devices menu in the virtual machine window and selecting Insert Guest Additions CD image. Once installed, you can use clipboard and file-sharing features. To copy a file from Windows to Ubuntu, locate the file, copy it using Ctrl+C or the right-click Copy option, switch to Ubuntu, and paste it onto the desktop using Ctrl+V or the right-click Paste option. To transfer a file from Ubuntu to Windows, find the file in Ubuntu, copy it, switch to Windows, and paste it into the desired folder using the same method.

1️⃣ **Step 1 : Go to the settings**  
![NOT-----](https://i.ibb.co/Nd4c8rFg/h.png) 
2️⃣ **Step 2: Сreate a shared folder**  
![NOT-----](https://i.ibb.co/tT2kL1Z0/j.png) 
3️⃣ **Step 3: Аdd Guest Additions**  
![NOT-----](https://i.ibb.co/CKGQFzLn/n.png) 

Unfortunately, due to an error, I cannot demonstrate the result of performing ooperations :( Next, we would have to unzip and install Guest Additions, after which a shared chars folder would appear on the main and secondary operating system to exchange files.
