# 🛠️ Практичне завдання "Work-case 4"

## 📌 Дисципліна: "Операційні системи"
## 👨‍🎓 Виконав: **Нагорний І.М.** (група РПЗ-23Б)

---

## 🎯 **Мета роботи**

- 📎 Ознайомитися з процесом клонування віртуальної машини та перенесення ОС у інше віртуальне середовище.
- 🌐 Вивчити типи мережевих з'єднань між віртуальними машинами.
- 🔧 Налаштувати мережу між основною ОС та її клоном.
- 🔄 Організувати обмін файлами між основною ОС і віртуальними машинами.

---

### 🔹 **1. Робота з менеджерами пакетів у терміналі Linux:**  
📌 В ході роботи досить часто виникає необхідність встановлювати нові програми та додатки. Для цього необхідно в терміналі вміти працювати з менеджерами пакетів:

1️⃣ Дайте розгорнуте визначення таким поняттям як «пакет» та «репозиторій».

- 📦 **Package** and 🗂 **Repository** are concepts used in the context of managing software packages on Linux systems.
- A **package** is an archive that contains all the files needed to install, configure, and run a particular program. It may contain information about dependencies on other packages, program versions, documentation, etc.
- A **repository** is a centralized storage of software packages that provides convenient access for users to packages from a network. Repositories usually contain packages for different distributions and their versions and provide mechanisms for automatically updating programs.

2️⃣ Надайте короткий огляд існуючих менеджерів пакетів у Linux. Охарактеризуйте їх основні можливості.  
 🔽 There are several package managers in Linux, including:  
  - 🟢 **APT (Advanced Package Tool)** – used in Debian and its derivatives like Ubuntu, Linux Mint, etc.
  - 🔵 **YUM (Yellowdog Updater, Modified)** – used in Red Hat-based distributions like Fedora, CentOS, RHEL.
  - 🔴 **Pacman** – used in Arch Linux.
  - 🟡 **Zypper** – used in SUSE-based distributions like openSUSE.
    
 **The main features of Linux package managers include:**  
  - ✅ Easy installation, updating and uninstallation of packages through the terminal.
  - ✅ Automatic updating of programs and their dependencies.
  - ✅ Manage dependencies between packages.
  - ✅ Ability to view information about installed packages.
  - ✅ Search and install new packages from repositories.
  - ✅ Create your own packages and distribute them through repositories.

---

### 🔹 **2. Визначення менеджера пакетів у дистрибутиві Linux та основні команди:**  
📌 Визначте, який менеджер пакетів використовує ваш дистрибутив Linux. Опишіть основні команди для роботи з ним:

💻 **Основні команди для APT в Ubuntu:**  

🔍 **Пошук пакетів:**  
```bash
sudo apt search <package_name>
```
📥 **Завантаження пакета:**  
```bash
sudo apt download <package_name>
```
📦 **Встановлення пакета:**  
```bash
sudo apt install <package_name>
```
📌 **Додавання нового репозиторію:**  
```bash
sudo add-apt-repository <repository>
sudo apt update
```
📋 **Перегляд встановлених пакетів:**  
```bash
dpkg --list
```
🗂 **Перегляд доступних пакетів:**  
```bash
sudo apt-cache pkgnames
```
🗑 **Видалення пакетів:**  
```bash
sudo apt remove <package_name>
sudo apt autoremove
```
🔄 **Оновлення пакетів та менеджера:**  
```bash
sudo apt update
sudo apt upgrade
```

---

### 🔹 **3. Встановлення програм через менеджер пакетів у терміналі**  
📌 Встановіть у терміналі через менеджер пакетів на свою систему:

🎵 **Новий відео- чи аудіоплеєр.**  
![Install Player](https://i.ibb.co/mC8W3JsZ/image.png)  
✅ It successfully installed, but I have an error on launching this program, so I don't put a screenshot of a working program there.

💻 **Середовище для мови програмування, що ви вивчаєте.**  
![Install IDE](https://i.ibb.co/j9V7v4tw/image.png)

---

### 🔹 **4. Встановлення програм через магазини додатків та менеджери пакетів у графічному середовищі**  
📌 Яким чином можна встановити нові програми через магазини додатків та менеджери пакетів у графічному середовищі? Наведіть свої приклади:

🛒 **Установка через Ubuntu Software:**  
📌 Відкриваємо **Ubuntu Software**  
![Ubuntu Software](https://i.ibb.co/pVywv8R/image.png)  

🔍 **Пошук програми**  
![Search App](https://i.ibb.co/DHp4gSKr/image.png)  

📦 **Вибір програми для встановлення**  
![Select App](https://i.ibb.co/gbDhwp31/image.png)  

🟢 **Натискаємо "Install"**  
![Install Button](https://i.ibb.co/xtc86m4k/image.png)  

💻 **Установка через термінал:**  
```bash
apt install <name>
```
![Terminal Install](https://i.ibb.co/M5DHDskg/image.png)  

🟡 **Підтверджуємо установку командою "y"**  
![Confirm Install](https://i.ibb.co/wZv70c4y/image.png)
