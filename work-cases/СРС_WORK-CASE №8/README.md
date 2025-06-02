# 📚 Самостійна робота студента: Work-case 8

## 📌 Дисципліна: "Операційні системи"

## 👨‍🎓 **Виконав**
- **Нагорний І.М. РПЗ-23Б** 📝

---

## 🎯 **Мета роботи**
1. Ознайомитися з можливостями виконання типових завдань у терміналі ОС Linux без графічної оболонки.
2. Вивчити та встановити програми для редагування тексту, моніторингу системи та інших адміністративних завдань у терміналі.
3. Дослідити інтерактивні "пасхалки" в терміналі для підвищення мотивації та ознайомлення з креативними можливостями Linux.

---

## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC.
- 📦 Віртуальна машина – VirtualBox (Oracle).
- 🐧 Операційна система GNU/Linux (Ubuntu).
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси з Linux.

---

## 📖 **Завдання для виконання**

### 🔹 **1. Виконання завдань у терміналі без графічної оболонки**

📌 **Завдання:** Виконати дії через термінал і пояснити, які команди/пакети використовуються.

**1.1. Перегляд файлів та папок через файловий менеджер у терміналі**  
**Tool**: `mc` (Midnight Commander)  
- **Description**: Midnight Commander is a text-based file manager that provides a two-panel interface for browsing, copying, moving, and deleting files.  
- **Installation**:  
  ```bash
  sudo apt-get update
  sudo apt-get install mc
  ``` 
- **Usage**:  
  ```bash
  mc
  ```
  ![](https://i.ibb.co/p6qy7Mkq/image.png)  
- **Functionality**: Navigate directories using arrow keys, perform file operations with function keys (e.g., F5 to copy, F8 to delete).

**1.2. Переглядати веб-сторінки через браузер, що працює у терміналі**  
**Tool**: `lynx`  
- **Description**: Lynx is a text-based web browser that renders web pages in the terminal.  
- **Installation**:  
  ```bash
  sudo apt-get install lynx
  ```
- **Usage**:  
  ```bash
  lynx https://abobasite.com
  ```
  ![](https://i.ibb.co/Lzg54N9q/image.png)  
- **Functionality**: Navigate links with arrow keys, follow links with Enter, exit with `q`.

**1.3. Перегляд електронної пошти в терміналі**  
**Tool**: `mutt`  
- **Description**: Mutt is a text-based email client that supports IMAP, POP3, and SMTP.  
- **Installation**:  
  ```bash
  sudo apt-get install mutt
  ```
- **Configuration**: Create a `.muttrc` file in the home directory:
  ```bash
  nano ~/.muttrc
  set imap_user = "your_email@abobasite.com"
  set imap_pass = "your_password"
  set folder = "imap://imap.abobasite.com/"
  set spoolfile = "+INBOX"
  ```
- **Usage**:  
  ```bash
  mutt
  ```
  ![](https://i.ibb.co/Zp370yDz/image.png) 

- **Functionality**: View, compose, and send emails using keyboard shortcuts.

**1.4. Слухати музику через термінал**  
**Tool**: `mpg123`  
- **Description**: mpg123 is a command-line audio player for MP3 files.  
- **Installation**:  
  ```bash
  sudo apt-get install mpg123
  ```
- **Usage**:  
  ```bash
  mpg123 /path/to/song.mp3
  ```
- **Functionality**: Play, pause, and stop audio files with simple commands.

**1.5. Скачувати торенти через термінал**  
**Tool**: `rtorrent`  
- **Description**: rtorrent is a text-based BitTorrent client.  
- **Installation**:  
  ```bash
  sudo apt-get install rtorrent
  ```
- **Usage**:  
  ```bash
  rtorrent
  ```
  Add a torrent file or magnet link using the interface. 

- **Functionality**: Download and manage torrents with a text-based interface.

**1.6. Планувати дії в календарі та нагадувати про них через термінал**  
**Tool**: `calcurse`  
- **Description**: Calcurse is a text-based calendar and scheduling application.  
- **Installation**:  
  ```bash
  sudo apt-get install calcurse
  ```
- **Usage**:  
  ```bash
  calcurse
  ```
- **Functionality**: Add events, set reminders, and view a calendar with a text interface.

**1.7. Переглядати зображення в терміналі**  
**Tool**: `fbi` (Framebuffer Imageviewer)  
- **Description**: fbi displays images in the terminal using the framebuffer.  
- **Installation**:  
  ```bash
  sudo apt-get install fbi
  ```
- **Usage**:  
  ```bash
  sudo fbi /path/to/image.jpg
  ```
- **Functionality**: View images directly in the terminal (requires framebuffer access).

---

### 🔹 **2. Класичні адміністративні дії**

📌 **Завдання:** Описати програми для редагування тексту та моніторингу системи, встановити по одній.

**2.1. Вводити, редагувати, видаляти текст (редактори файлів)**  
**Tool**: `nano`  
- **Description**: Nano is a user-friendly, lightweight text editor for the terminal.  
- **Installation**:  
  ```bash
  sudo apt-get install nano
  ```
- **Usage**:  
  ```bash
  nano file.txt
  ```
 ![](https://linuxhint.com/wp-content/uploads/2021/06/word-image-239.png)
- **Functionality**: Edit text with simple keyboard shortcuts (e.g., Ctrl+O to save, Ctrl+X to exit).

**2.2. Здійснювати моніторинг процесів та ресурсів системи**  
**Tool**: `htop`  
- **Description**: htop is an interactive process viewer, similar to Task Manager, with a colorful interface.  
- **Installation**:  
  ```bash
  sudo apt-get install htop
  ```
- **Usage**:  
  ```bash
  htop
  ```
  ![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/Htop_on_a_48_core_computer.png/1024px-Htop_on_a_48_core_computer.png) 
- **Functionality**: View CPU, memory, and process details; kill processes with F9.

---

### 🔹 **3. Пасхалки та інтерактиви**

📌 **Завдання:** Продемонструвати "пасхалки" та інтерактивні можливості терміналу.

**3.1. Паровий локомотив**  
**Tool**: `sl`  
- **Description**: Displays an animated steam locomotive in the terminal.  
- **Installation**:  
  ```bash
  sudo apt-get install sl
  ``` 
- **Usage**:  
  ```bash
  sl
  ``` 
  ![](https://i.ibb.co/93pcWFzC/image.png) 


---

## 🏁 **Висновки**
У ході самостійної роботи я ознайомився з можливостями виконання складних завдань у терміналі Linux без графічної оболонки, включаючи перегляд файлів, веб-сторінок, пошти, прослуховування музики, завантаження торентів, планування подій та перегляд зображень. Встановлення та використання інструментів, таких як `nano` і `htop`, поглибило мої навички адміністрування. "Пасхалки", такі як `sl`, `cowsay` і ASCII-версія "Зоряних війн", додали креативності та мотивації до роботи з терміналом.