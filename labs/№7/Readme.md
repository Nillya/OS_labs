# ЛАБОРАТОРНА РОБОТА №7

## 📚 Дисципліна: "Операційні системи"

## 🎯 **Тема**
> Створення скриптових сценаріїв та визначення апаратної конфігурації системи

## 👨‍🎓 **Виконав**
- **Нагорний І.М. РПЗ-23Б** 📝

---

## 🚀 **Мета роботи**
1. Отримання практичних навиків роботи з командною оболонкою Bash. 🛠️
2. Знайомство знайомство з базовими діями при роботі зі скриптовими сценаріями. 📦

## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC
- 📦 Віртуальна машина – VirtualBox (Oracle)
- 🐧 Операційна система GNU/Linux
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси з Linux

---

## 📖 **Завдання для попередньої підготовки**

### 🔹 **1. Словник базових англійських термінів**  
📌 Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань призначення команд та їх параметрів:  

| Термін англійською | Термін українською |
|:-------------------|-------------------:|
|executable          |    виконуваний файл|
|interpreter         |          перекладач|
|editor              |            редактор|
|hash                |                 хеш|
|invoke              |           викликати|
|prompt              |               запит|
|hashbang            |                  #!|
|access              |             доступу|
|directory           |             каталог|
|syntax              |           синтаксис|

---

### 🔹 **2(4). Теоретичні питання**

📌 **Завдання:** Дайте відповіді на наступні питання:

**1️⃣ Охарактеризуйте поняття скриптового сценарію у командній оболонці.**

A shell script is a set of commands that are executed sequentially while the script is running. Scripts are commonly used to automate routine tasks to reduce the effort and time spent on performing such tasks manually. Scripts can contain branches, loops, conditional expressions, and other constructs that provide script execution flexibility and functionality.

**2️⃣ Яким чином створюються та редагуються скрипти, що треба зробити щоб запустити скрипт?**

Scripts are created in a text editor such as Vim or Nano and saved with the extension ".sh" to indicate that it is a shell script. Scripts can be run using the `sh` or `bash` command, specifying the path to the script file. Before running the script, you need to make sure that it has execute rights using the `chmod` command.


**3️⃣ Які основні компоненти материнської плати ви знаєте?**

Some of the main components of a motherboard include the processor, chipset, BIOS/UEFI, RAM and expansion slots, I/O controllers (including keyboard, mouse, USB and Ethernet ports), and GPU (in the case of embedded graphic subsystems).

**4️⃣ Коротко охарактеризуйте для яких пристроїв оперують поняттями MBR та GPT?**

MBR and GPT are disk mapping table formats. MBR (Master Boot Record) is an older format that can only support up to 4 primary partitions, one of which can be an extended partition. GPT (GUID Partition Table) is a newer format that can support up to 128 partitions and has no partition size limit.
   

**5️⃣ В чому суть операції монтування, для чого вона потрібна?**
A mount operation is the process of connecting an external storage device, such as a USB flash drive or external hard drive, to the operating system's file system. The connected device becomes readable and writable by the operating system, and operations can be performed on files stored on the device. Mounting also allows you to remove an external device safely, during which the operating system closes all open files and transfers control back to the external device before shutting down.


---

## 🎬 **Хід роботи**

### 🎥 **1(2). Таблиця команд**

📌 **Завдання:** Опрацюйте всі приклади команд, що представлені у лабораторних роботах курсу NDG Linux Essentials - Lab 11: Basic Scripting та Lab 12: Understanding Computer Hardware..

|  Назва команди  |  Її призначення та функціональність  |
|:----------------|-------------------------------------:|
|`vi`| Editor to create basic shell scripts using basic shell commands, variables and control statements. |
|`nano`| Simple text-only editor |
|`gedit`| Graphical editor |
|`lscpu`| Determine the type of CPU |
|`free`| Shows how much RAM and swap space is being used |
|`lspci`| Shows what devices are connected to the PCI bus |
|`lsusb`| Prints list the USB connected devices |
|`lsmod`| To view the currently loaded modules |
|`fdisk`| Useful for identifying and manipulating disk storage resources on a system |
| `vi myfile`                      | Opens the file `myfile` in the `vi` text editor.                                                  |
| `3G`                             | Moves the cursor to the third page of the text (press "3" and then "g").                         |
| `k`                               | Moves the cursor one line up in the `vi` editor.                                                  |
| `8l`                              | Moves the cursor 8 characters to the right (press "8" followed by "l").                           |
| `dw`                              | Deletes the current word in the `vi` editor.                                                      |
| `u`                               | Undoes the last action in the `vi` editor.                                                        |
| `2dw`                             | Deletes two words in the `vi` editor.                                                             |
| `xxxx`                            | Deletes four characters in the `vi` editor.                                                       |
| `4u`                              | Undoes the last four actions in the `vi` editor.                                                  |
| `14x`                             | Deletes fourteen characters in the `vi` editor.                                                   |
| `5X`                              | Deletes five characters to the left of the cursor in the `vi` editor.                             |
| `dd`                              | Deletes the current line in the `vi` editor.                                                      |
| `p`                               | Pastes the copied text after the cursor in the `vi` editor.                                       |
| `2u`                              | Undoes the last two actions in the `vi` editor.                                                   |
| `2dd`                             | Deletes two lines in the `vi` editor.                                                             |
| `4w`                              | Moves the cursor forward by four words in the `vi` editor.                                        |
| `D`                               | Deletes from the cursor to the end of the line in the `vi` editor.                                |
| `J`                               | Joins two lines in the `vi` editor.                                                               |
| `yw`                              | Copies one word from the cursor in the `vi` editor.                                               |
| `P`                               | Pastes the clipboard content before the cursor in the `vi` editor.                                |
| `1G`                              | Moves the cursor to the first line in the `vi` editor.                                            |
| `3J`                              | Moves the cursor down by three lines in the `vi` editor.                                          |
| `:%s/text//g`                     | Replaces all occurrences of "text" with an empty string in the current file in the `vi` editor.   |
| `ESC`                             | Exits insert mode in the `vi` editor and returns to command mode.                                 |
| `o`                               | Creates a new line and moves the cursor to it in the `vi` editor.                                 |
| `/line`                           | Searches for the word "line" in the file in the `vi` editor.                                      |
| `vi sample.sh`                    | Opens the file `sample.sh` in the `vi` editor.                                                    |
| `bash sample.sh`                  | Executes the script `sample.sh` in the Bash interpreter.                                          |
| `cat sample.sh`                   | Displays the content of the file `sample.sh` in the terminal.                                     |
| `./sample.sh`                     | Runs the script `sample.sh` from the current directory.                                           |
| `echo $PATH`                      | Displays the value of the `$PATH` environment variable, which contains executable file paths.     |
| `lscpu`                           | Displays information about the CPU in the system.                                                 |
| `head -n 20 /proc/cpuinfo`        | Displays the first 20 lines of the `/proc/cpuinfo` file, which contains CPU information.          |
| `free -m`                         | Displays memory usage (used and free) in megabytes.                                               |
| `free -g`                         | Displays memory usage (used and free) in gigabytes.                                               |
| `lspci`                           | Displays information about all PCI devices in the system.                                         |
| `lsusb`                           | Displays information about all USB devices connected to the system.                               |
| `lsmod`                           | Displays a list of loaded kernel modules in the system.                                           |
| `fdisk -l`                        | Displays information about disk partitions in the system.                                         |

---

### 🔹 **2(4). Робота в терміналі**

📌 **Завдання:** Створіть скриптові сценарії з виводом текстових повідомлень для користувача (продемонструйте скріншоти)::  


1️⃣ Сценарій привітання користувача з поточною датою та інформацією про систему  
📌 Створіть новий файл з розширенням `.sh` у будь-якій папці на вашій системі та відкрийте його в текстовому редакторі:  
![](https://i.ibb.co/5g9tYNdk/image.png)  
![](https://i.ibb.co/8DqPRjJZ/image.png)

2️⃣ Сценарій для виводу інформації про апаратну конфігурацію системи  
📌 Cценарій має виводити інформацію про апаратну конфігурацію поточної системи (використовуйте команди розглянуті в Lab 12: Understanding Computer Hardware);  
![](https://i.ibb.co/60wR7bKd/gg.png)  
![](https://i.ibb.co/PvgstvPQ/gh.png)

3️⃣ Введіть свій приклад скриптового сценарію:  
![](https://i.ibb.co/v4327zZY/image.png)


---

### ✏️ **Відповіді на контрольні питання**

#### 1️⃣ **Яким чином у скриптах можна опрацьовувати змінні та створювати розгалужені та циклічні сценарії?**
```
  variable_name=value для создания
  $name для получения значения
  ```
  
  branching:
  ```
  if [ $age -gt 18 ]
  then
    echo "You are an adult."
  else
    echo "You are a minor."
  fi
  ```
  cycle:
  ```
  for i in {1..10}
  do
    echo $i
  done

  i=1
  while [ $i -le 10 ]
  do
    echo $i
    i=$((i+1))
  done
  ```
#### 2️⃣ **В чому відмінність між командами arch та lscpu?**
The `arch` command returns the processor architecture on which the current processor is running.
  
The `lscpu` command displays detailed information about the processor, including architecture, processor model, number of cores, processor speed, and other parameters.

#### 3️⃣ **Якою командою можна отримати інформацію про стан використання RAM поточною системою?**
To get information about the state of use (RAM) in the current system in Linux, you can use the `free` command.

#### 4️⃣ **Які команди для перегляду стану підключення периферійних пристроїв можна використати в терміналі?**
  `lsusb`, `lspci`, `lsblk`, `df`, `dmesg`

#### 5️⃣ **Які можливості застунку gparted?**

  Some of the features of GParted are:
  
   - Create, delete and edit hard disk partitions.
   - Format partitions in various file system formats, such as NTFS, FAT32, ext4, and others.
   - Moving and resizing hard disk partitions.
   - Changing the section label and system number.
---

## 🏁 **Висновки**

In this lab, we learned about the existing ways to compress and archive files in Linux, and tried them out in practice.