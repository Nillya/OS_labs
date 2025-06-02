# ЛАБОРАТОРНА РОБОТА №10

## 📚 Дисципліна: "Операційні системи"

## 🎯 **Тема**
> Зміна власників і прав доступу до файлів в Linux. Спеціальні каталоги та файли в Linux

## 👨‍🎓 **Виконав**
- **Нагорний І.М. РПЗ-23Б**

---

## 🚀 **Мета роботи**
1. Отримати практичні навички роботи з командною оболонкою Bash. 🛠️
2. Ознайомитися з базовими діями при зміні власників файлів та прав доступу до файлів. 🔐
3. Ознайомитися зі спеціальними каталогами та файлами в Linux. 📂

---

## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC.
- 📦 Віртуальна машина – VirtualBox (Oracle).
- 🐧 Операційна система GNU/Linux (Ubuntu).
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси з Linux.

---

## 📖 **Завдання для попередньої підготовки**

### 🔹 **1. Словник базових англійських термінів**
Прочитавши теоретичні відомості до лабораторної роботи, складено словник ключових термінів, пов’язаних зі зміною власників, правами доступу та спеціальними каталогами і файлами в Linux:

| **Термін англійською** | **Термін українською** |
|:-----------------------|:-----------------------|
| ownership              | власність              |
| permissions            | права доступу          |
| user owner             | власник-користувач     |
| group owner            | власник-група          |
| sticky bit             | липкий біт             |
| symbolic link          | символічне посилання   |
| hard link              | жорстке посилання      |
| directory              | каталог                |
| file                   | файл                   |
| execute                | виконання              |
| read                   | читання                |
| write                  | запис                  |

---

### 🔹 **2(4). Відповіді на теоретичні питання**

📌 **Завдання:** Дати відповіді на питання з підготовки до лабораторної роботи.

**4.1. Яке призначення команди id?**  
The `id` command displays information about the user ID (UID), group ID (GID), and group memberships of the current or specified user.

**4.2. Як переглянути які права доступу має власник файлу?**  
The owner’s permissions for a file can be viewed using the `ls -l <file_name>` command. The first three characters after the file type (e.g., `-rwxr-xr-x`) indicate the owner’s permissions: read (r), write (w), execute (x).

**4.3. Як змінити власника групи?**  
To change the group owner of a file, use the `chgrp <new_group> <file_name>` command. Alternatively, you can use `chown :<new_group> <file_name>` to change only the group.

**4.4. Як можна переглянути у терміналі який тип поточного файлу? Наведіть приклади для різних типів файлів**  
The file type can be determined using the `ls -l` command, where the first character in the output indicates the type:  
- `-` regular file: `-rw-r--r-- 1 user group 0 Oct 30 file.txt`  
- `d` directory: `drwxr-xr-x 2 user group 4096 Oct 30 dir`  
- `l` symbolic link: `lrwxrwxrwx 1 user group 7 Oct 30 link -> file.txt`  
- `b` block device: `brw-rw---- 1 root disk 8, 0 Oct 30 /dev/sda`  
- `c` character device: `crw-rw-rw- 1 root tty 5, 0 Oct 30 /dev/tty`

**4.5. Для чого використовуються дозволи Setuid та Setgid?**  
- **Setuid**: Allows an executable file to run with the permissions of its owner (e.g., root for `passwd`).  
- **Setgid**: On a file, it allows execution with the group’s permissions; on a directory, new files inherit the directory’s group.

**4.6. Для чого в системі потрібен так званий “липкий біт” (Sticky Bit)? Наведіть приклади коли цей дозвіл доцільно використовувати.**  
The sticky bit restricts file deletion in a directory to only the file’s owner, even if others have write permissions. Example: the `/tmp` directory, where users create temporary files but cannot delete others’ files.

---

## 🎬 **Хід роботи**

### 🎥 **1(2). Таблиця команд**
📌 **Завдання:** Опрацювати команди з NDG Linux Essentials Lab 17 та Lab 18 і скласти таблицю.

| **Назва команди** | **Призначення та функціональність** 🎯 |
|-------------------|----------------------------------------|
| `id`              | Відображає UID, GID та групи користувача. |
| `ls -l`           | Показує детальну інформацію про файли, включаючи права доступу. |
| `chown`           | Змінює власника файлу або каталогу. |
| `chgrp`           | Змінює групу власника файлу або каталогу. |
| `chmod`           | Змінює права доступу до файлу або каталогу. |
| `umask`           | Встановлює маску прав доступу за замовчуванням для нових файлів. |
| `ln`              | Створює жорсткі або символічні посилання. |
| `sudo`            | Виконує команду з правами суперкористувача. |
| `passwd`          | Змінює пароль (використовує setuid). |
| `wall`            | Надсилає повідомлення всім користувачам (використовує setgid). |

---

### 🔹 **2(3). Практичні завдання в терміналі**

📌 **Завдання:** Виконати дії в терміналі та надати скріншоти.

#### **Створення користувачів та груп**
- Створити трьох нових користувачів:  
  ```bash
  sudo useradd user1
  sudo useradd user2
  sudo useradd user3
  ```

- Створити групу та додати до неї двох користувачів:  
  ```bash
  sudo groupadd mygroup
  sudo usermod -aG mygroup user1
  sudo usermod -aG mygroup user2
  ```
  ![](https://i.ibb.co/KjwSQ9dF/image.png)

#### **Робота з файлами та правами**
- Створити файл із правами власника на читання, запис і виконання:  
  ```bash
  touch myscript.sh
  echo "#!/bin/bash" > myscript.sh
  echo "echo 'Hello, World!'" >> myscript.sh
  chmod 700 myscript.sh
  ```

- Надати групі права на перегляд і виконання:  
  ```bash
  chmod 750 myscript.sh
  ```

- Заборонити доступ іншим:  
  ```bash
  chmod 750 myscript.sh  # Вже встановлено
  ```

#### **Робота з директоріями**
- Створити директорію, доступну для всіх:  
  ```bash
  mkdir shared_dir
  chmod 777 shared_dir
  ```

- Створити директорію, доступну лише власнику:  
  ```bash
  mkdir private_dir
  chmod 700 private_dir
  ```

- Створити директорію для перегляду групою без редагування:  
  ```bash
  mkdir group_dir
  chmod 750 group_dir
  ```

#### **Експеримент із правами**
- Створити файл і "обнулити" права:  
  ```bash
  touch emptyfile
  chmod 000 emptyfile
  ```

- Змінити права на `chmod 4`:  
  ```bash
  chmod 4 emptyfile
  ```
  
- Змінити права на `chmod 44`:  
  ```bash
  chmod 44 emptyfile
  ```
  
#### **Каталог із успадкуванням групи**
- Створити каталог із setgid та sticky bit:  
  ```bash
  mkdir team_dir
  chgrp mygroup team_dir
  chmod 2770 team_dir
  chmod o+t team_dir
  ```

#### **Робота з посиланнями**
- Створити файли та посилання під user1:  
  ```bash
  su user1
  touch file1
  ln file1 hardlink1
  ln -s file1 symlink1
  exit
  ```

- Переглянути файли під user2:  
  ```bash
  su user2
  ls -l /home/user1/file1
  ```

- Спробувати видалити файли під user2:  
  ```bash
  rm /home/user1/file1
  ```

---

## ✏️ **Відповіді на контрольні питання**

1. **Наведіть приклади зміни прав доступу символічним методом (Symbolic Method)?**  
   - `chmod u+x file` — adds execute permission for the owner.  
   - `chmod g-w file` — removes write permission for the group.  
   - `chmod a+r file` — adds read permission for all.

2. **Наведіть приклади зміни прав доступу числовим методом (numeric method, octal method)?**  
   - `chmod 754 file` — sets `rwxr-xr--`.  
   - `chmod 640 file` — sets `rw-r----`.  
   - `chmod 700 file` — sets `rwx------`.

3. **Яке призначення команди umask?**  
   The `umask` command sets the default permission mask for new files and directories.

4. **Порівняйте жорсткі та символічні посилання?**  
   - **Hard link**: An additional name for a file, pointing to the same inode.  
   - **Symbolic link**: A reference to a file’s path, becomes invalid if the original file is deleted.

5. **Чи можна виконати файл, для якого є права на виконання, але не встановлені права на читання (--x)? Поясніть.**  
   Yes, execute permission alone is sufficient to run a file; read permission is not required.

6. **Якщо ми змінюємо права доступу та дозволи в поточній сесії чи будуть вони збережені в наступній?**  
   Yes, permission changes are saved on the filesystem and persist across sessions.

7. **Чи є якийсь шаблон, яким система користується щодо прав та доступів при створенні нових файлів. Як можна змінити права дозволу за замовчуванням?**  
   Yes, the default permissions are set by `umask`. Change it using: `umask <value>`.

8. **Яким чином можна створити жорстке посилання? В яких ситуаціях їх доцільно використовувати?**  
   Create with `ln <file> <link>`. Useful for backups within the same filesystem.

9. **Яким чином можна створити символічне посилання? В яких ситуаціях їх доцільно використовувати?**  
   Create with `ln -s <file> <link>`. Useful for shortcuts across filesystems.

10. **Уявіть, що програмі потрібно створити одноразовий тимчасовий файл, який більше ніколи не знадобиться після закриття програми. Який правильний каталог для створення цього файлу?**  
   The `/tmp` directory is the standard location for temporary files.

11. **Є файл оригінал та для нього створено два посилання - символічне та жорстке. Що відбудеться з іншими файлами, якщо видалити:**  
    - **Original file**: The hard link remains functional; the symbolic link becomes invalid.  
    - **Symbolic link**: The original and hard link remain unaffected.  
    - **Hard link**: The file is deleted only if it’s the last link.

---

## 🏁 **Висновки**
У ході роботи я освоїв зміну власників і прав доступу до файлів у Linux, ознайомився зі спеціальними каталогами та файлами, такими як `/tmp`, і зрозумів використання `setuid`, `setgid` та `sticky bit`. Практичні навички роботи з Bash поглибили моє розуміння адміністрування ОС.