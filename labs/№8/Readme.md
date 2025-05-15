# ЛАБОРАТОРНА РОБОТА №8

## 📚 Дисципліна: "Операційні системи"

## 🎯 **Тема**
> Збереження службових даних системи та її мережева конфігурація 🖥️

## 👨‍🎓 **Виконав**
- **Нагорний І.М. РПЗ-23Б** 📝

---

## 🚀 **Мета роботи**
1. Отримати практичні навички роботи з командною оболонкою Bash. 🛠️
2. Ознайомитися з базовими структурами для збереження системних даних: процеси, пам’ять, лог-файли та повідомлення про стан ядра. 📊
3. Вивчити стандарт Filesystem Hierarchy Standard (FHS). 📂
4. Ознайомитися з діями при налаштуванні мережі в Linux. 🌐

## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC
- 📦 Віртуальна машина – VirtualBox (Oracle)
- 🐧 Операційна система GNU/Linux (Ubuntu)
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси з Linux

---

## 📖 **Завдання для попередньої підготовки**

### 🔹 **1. Словник базових англійських термінів**
Прочитавши теоретичні відомості до лабораторної роботи, складено словник ключових термінів, пов’язаних із системними даними та мережею:

| **Термін англійською** | **Термін українською** |
|:-----------------------|:-----------------------|
| process                | процес                 |
| memory                 | пам’ять                |
| log files              | лог-файли              |
| kernel                 | ядро                   |
| network configuration  | мережева конфігурація  |
| virtual addressing     | віртуальна адресація   |
| user space             | простір користувача    |
| kernel space           | простір ядра           |
| system call            | системний виклик       |
| daemon                 | демон                  |
| router                 | маршрутизатор          |
| IP address             | IP-адреса              |
| hostname               | ім’я хоста             |
| URL                    | URL                    |
| DHCP                   | DHCP                   |
| DNS                    | DNS                    |
| Ethernet               | Ethernet               |
| TCP/IP                 | TCP/IP                 |
| packet                 | пакет                  |
| mask                   | маска                  |

---

### 🔹 **2(4). Відповіді на теоретичні питання**

📌 **Завдання:** Дати відповіді на питання з підготовки до лабораторної роботи.

**4.1. Розкрийте поняття "псевдо файлової системи", для чого воно потрібно системі?**  
A pseudo-file system (for example, `/proc`) is a virtual file system that does not store data on physical media, but provides an interface for accessing system state information such as processes, memory, or kernel configuration. The system needs it for convenient access to this data in the form of files, which allows programs and users to obtain system information without directly accessing the kernel.

**4.2. Чому користувачі не так часто звертаються на пряму до каталогу `/proc`, яким чином з нього можна отримати інформацію?**  
Users rarely access `/proc' directly, because the data there is presented in a specific format intended more for program use than for human reading. You can get information through specialized commands such as `ps`, `top`, or `free`, which interpret the contents of `/proc`. You can also view the files directly, for example, `cat /proc/meminfo' for memory information.

**4.3. Яке призначення файлів `/proc/cmdline`, `/proc/meminfo` та `/proc/modules`?**  
- `/proc/cmdline` - contains command line parameters passed to the kernel during boot (for example, root=UUID=xxx).
- `/proc/meminfo` - provides information about the use of system memory (total, free, cached memory).
- `/proc/modules` - a list of loaded kernel modules and their dependencies.

**4.4. Яке призначення команди `free`?**  
The `free` command displays information about the system memory usage: total, used, free memory, as well as buffers and cache. For example: `free -h` displays data in a human-readable format.

**4.5. Для чого потрібні лог-файли, наведіть приклади їх застосування?**  
Log files record system and program events, which helps with diagnostics, monitoring, and auditing. Examples:
- `/var/log/messages` - general system messages.
- `/var/log/secure` - events related to authorization and security.

**4.6. Яке призначення файлу `/var/log/dmesg`?**  
The file `/var/log/dmesg` stores kernel messages generated during system boot, for example, about hardware initialization. It can be viewed with the `dmesg` command to diagnose hardware problems.

**4.7. Для чого розроблено FHS?**  
The Filesystem Hierarchy Standard (FHS) defines a standard directory structure in Linux to ensure uniformity and compatibility between different distributions. For example, `/bin' for executable files, `/var' for data variables.

**4.8. Які основні команди є у Linux для перегляду та конфігурації мережі?**  
- `ifconfig` - displays and configures network interfaces.
- `ip` - a modern alternative to `ifconfig` with advanced features.
- `route` - displays and configures the routing table.
- `ping` - checks the connection to the host.
- `netstat` - shows network connections and statistics.
- `ss` - displays socket statistics.
- `dig` - performs DNS queries.
- `host` - searches for IP by hostname.
- `ssh` - provides remote access to the host.

---

## 🎬 **Хід роботи**

### 🎥 **1(2). Таблиця команд**
📌 **Завдання:** Опрацювати команди з NDG Linux Essentials Lab 13 ("Where Data is Stored") та Lab 14 ("Network Configuration") і скласти таблицю.

| **Назва команди** | **Призначення та функціональність** 🎯 |
|-------------------|----------------------------------------|
| `su`              | Змінює поточного користувача на root. |
| `ls /proc`        | Переглядає вміст каталогу `/proc` (потрібні права root). |
| `free`            | Відображає статистику використання пам’яті. |
| `dmesg`           | Показує повідомлення ядра з буфера. |
| `journalctl`      | Переглядає журнали на системах з systemd. |
| `ifconfig`        | Відображає та налаштовує мережеві інтерфейси. |
| `ip`              | Сучасна команда для роботи з мережею (інтерфейси, маршрути). |
| `route`           | Переглядає та налаштовує таблицю маршрутизації. |
| `ping`            | Перевіряє доступність хоста в мережі. |
| `netstat`         | Показує мережеві з’єднання, порти, статистику. |
| `ss`              | Відображає детальну статистику сокетів. |
| `dig`             | Виконує DNS-запити для пошуку IP-адрес. |
| `host`            | Перетворює імена хостів у IP-адреси. |
| `ssh`             | Забезпечує віддалене з’єднання з хостом. |

---

### 🔹 **2. Практичні завдання в терміналі**

📌 **Завдання:** Дослідити команду `cat` та інші команди, виконати практичні дії.

#### **Дослідження команди `cat`**
Команда `cat` (concatenate) використовується для:  
1. Перегляду вмісту файлів.  
2. Створення нових файлів.  
3. Перенаправлення вмісту.  
4. Об’єднання кількох файлів.  

**Приклади використання:**  
- **Створення файлу:**  
  ```bash
  cat > newfile.txt
  Привіт, світ! [Ctrl+D]
  ```
- **Перегляд вмісту:**  
  ```bash
  cat newfile.txt
  ```
- **Перенаправлення:**  
  ```bash
  cat newfile.txt > copy.txt
  ```
- **Об’єднання файлів:**  
  ```bash
  cat file1.txt file2.txt > combined.txt
  ```

**Параметри `cat`:**  
- `-n` — нумерує рядки файлу:  
  ```bash
  cat -n newfile.txt
  ```
- `-v` — відображає недруковані символи:  
  ```bash
  cat -v newfile.txt
  ```
- `-s` — видаляє повторювані порожні рядки:  
  ```bash
  cat -s newfile.txt
  ```

#### **Можливості команди `dig`**
Команда `dig` (Domain Information Groper) використовується для DNS-запитів, щоб отримати інформацію про IP-адреси чи інші записи.  
**Приклад:**  
```bash
dig test.com
```
Вивід покаже IP-адресу `test.com`, сервер DNS та час відповіді.

#### **Можливості команди `netstat`**
Команда `netstat` відображає мережеву статистику, з’єднання, порти.  
**Приклади:**  
- Перегляд активних з’єднань:  
  ```bash
  netstat -a
  ```
- Перегляд прослуховуваних портів:  
  ```bash
  netstat -l
  ```
- Статистика протоколів:  
  ```bash
  netstat -s
  ```

---

## ✏️ **Відповіді на контрольні питання**

1. **Як пов’язані між собою команди `cat` та `tac`?**  
   The `cat` displays the contents of a file from beginning to end, and the `tac` displays the contents from end to beginning. They are inverse to each other.

2. **Що робить команда `ss`?**  
   The `ss' command displays socket statistics, including active connections, listening ports, and network connection details.

3. **В чому відмінність між командами `ps --forest` та `pstree`?**  
   `ps --forest` shows the process tree in text format, and `pstree` shows it in a more structured form using graphical symbols.

4. **У яких каталогах зберігаються налаштування системи?**  
   System settings are usually stored in `/etc`.

5. **У яких каталогах можна знайти встановлені системні програми, доступні для користувача?**  
   U `/usr/bin` ta `/usr/local/bin`.

6. **У яких каталогах можна знайти встановлені системні програми і програми, призначені для виконання суперкористувачем?**  
   At `/sbin`, `/usr/sbin`.

7. **Поясніть призначення команд `ping`, `ifconfig`, `traceroute`.**  
   - `ping` - checks the connection to the host by sending packets.
   - `ifconfig` - displays and configures network interfaces.
   - `traceroute` - shows the path of packets to the host through the network.

8. **Як називаються мережеві інтерфейси в Linux?**  
   For example, `eth0` (Ethernet), `wlan0` (Wi-Fi), `lo` (local interface).

9. **Як за допомогою команди `ifconfig` вивести параметри тільки одного мережевого інтерфейсу (наприклад, `eth1`), а не всіх?**  
   ```bash
   ifconfig eth1
   ```

---

## 🏁 **Висновки**

During laboratory work #8, I gained practical skills in working with the Bash shell in Linux. I studied how the system stores service data in the `/proc` directory, got acquainted with memory management through the `free` command, studied log files (`/var/log/dmesg`, `/var/log/messages`) and their importance for diagnostics. I also mastered the basics of network configuration using the commands `ifconfig`, `ip`, `ping`, `netstat`, `ss`, `dig`, etc. Understanding the FHS standard helped me to systematize my knowledge of the directory structure in Linux. The work deepened my knowledge of operating systems and their administration.