# 🛠️ Практичне завдання "Work-case 6"

## 📌 Дисципліна: "Операційні системи"
## 👨‍🎓 Виконав: **Нагорний І.М.** (група РПЗ-23Б)

---

## 🎯 **Мета роботи**

- Встановити декілька командних інтерпретаторів в операційній системі.
- Створити нових користувачів та розподілити їх по групам.
- Визначити командний інтерпретатор за замовчуванням для кожного користувача.
- Продемонструвати приклади роботи кожної групи користувачів у своєму командному інтерпретаторі.

---

### 🔹 **1. Встановлення командних інтерпретаторів**

📌 В робочому просторі операційної системи необхідно встановити декілька командних інтерпретаторів (окрім bash ще 2 на ваш вибір).

#### 1️⃣ Якими командами це можна зробити?

To install additional command-line interpreters in a Linux operating system (e.g., Ubuntu), we use the `apt` package manager. I have selected `zsh` and `fish` as the additional shells. The commands are as follows:

```bash
sudo apt-get update
sudo apt-get install zsh
sudo apt-get install fish
```

#### 2️⃣ Опишіть коротко можливості кожного з них.

**a) Zsh (Z Shell):**  
Zsh is an advanced shell that builds on the features of the Bourne Shell (sh).  
- Offers command autocompletion with suggestions.  
- Supports themes and plugins for interface customization.  
- Provides enhanced globbing for file operations.  
- Allows flexible configuration via files like `.zshrc`.

**b) Fish (Friendly Interactive SHell):**  
Fish is designed for ease of use and interactivity.  
- Features intuitive autocompletion and syntax highlighting.  
- Includes real-time command history search.  
- Comes with built-in themes for appearance customization.  
- Simplifies configuration without requiring complex scripts.

Both shells offer significant improvements over the default `bash` experience.

---

### 🔹 **2. Створення користувачів та розподіл по групам**

📌 Необхідно створити 10 нових користувачів у вашій системі та розподілити їх по групам: Technical support, Developers, Financiers, Founders, Guests.

#### How to do this?

First, create the groups using the `groupadd` command:

```bash
sudo groupadd techsupport
sudo groupadd developers
sudo groupadd financiers
sudo groupadd founders
sudo groupadd guests
```

Next, create the users and assign them to their respective groups:

```bash
# Technical support
sudo useradd -m -G techsupport user1
sudo useradd -m -G techsupport user2

# Developers
sudo useradd -m -G developers user3
sudo useradd -m -G developers user4
sudo useradd -m -G developers user5

# Financiers
sudo useradd -m -G financiers user6
sudo useradd -m -G financiers user7

# Founders
sudo useradd -m -G founders user8
sudo useradd -m -G founders user9

# Guests
sudo useradd -m -G guests user10
```

Set passwords for each user:

```bash
sudo passwd user1
sudo passwd user2
sudo passwd user3
sudo passwd user4
sudo passwd user5
sudo passwd user6
sudo passwd user7
sudo passwd user8
sudo passwd user9
sudo passwd user10
```

To confirm the group assignments, use:

```bash
groups user1
```

---

### 🔹 **3. Визначення командного інтерпретатора за замовчуванням**

📌 Для кожного з користувачів визначити його командний інтерпретатор:  
- Technical support – bash;  
- Developers – zsh;  
- Financiers – deny access;  
- Founders – fish;  
- Guests – deny access.

Use the `usermod` command to assign the default shells:

```bash
# Technical support - bash
sudo usermod -s /bin/bash user1
sudo usermod -s /bin/bash user2

# Developers - zsh
sudo usermod -s /bin/zsh user3
sudo usermod -s /bin/zsh user4
sudo usermod -s /bin/zsh user5

# Financiers - deny access
sudo usermod -s /usr/sbin/nologin user6
sudo usermod -s /usr/sbin/nologin user7

# Founders - fish
sudo usermod -s /bin/fish user8
sudo usermod -s /bin/fish user9

# Guests - deny access
sudo usermod -s /usr/sbin/nologin user10
```

The `/usr/sbin/nologin` shell prevents users from accessing a command-line interpreter.

---

### 🔹 **4. Демонстрація роботи кожної групи користувачів**

📌 Продемонструвати приклади роботи груп у своїх оболонках: збір відомостей про систему, базова конфігурація, системна дата, поточний каталог.

Since Financiers and Guests are denied shell access, examples are provided only for Technical support, Developers, and Founders.

#### Technical support (bash):

- Gather system information:  
```bash
uname -a
```

- Basic configuration:  
```bash
lshw
```

- System date:  
```bash
date
```

- Current directory:  
```bash
pwd
```

#### Developers (zsh):

- Gather system information:  
```zsh
uname -a
```

- Basic configuration:  
```zsh
lshw
```

- System date:  
```zsh
date
```

- Current directory:  
```zsh
pwd
```

#### Founders (fish):

- Gather system information:  
```fish
uname -a
```

- Basic configuration:  
```fish
lshw
```

- System date:  
```fish
date
```

- Current directory:  
```fish
pwd
```
