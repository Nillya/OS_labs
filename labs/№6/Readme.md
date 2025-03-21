# ЛАБОРАТОРНА РОБОТА №6

## 📚 Дисципліна: "Операційні системи"

## 🎯 **Тема**
> Команди Linux для архівування та стиснення даних. Робота з текстом 🖥️

## 👨‍🎓 **Виконав**
- **Нагорний І.М. РПЗ-23Б** 📝

---

## 🚀 **Мета роботи**
1. Отримати практичні навички роботи з командною оболонкою Bash. 🛠️
2. Ознайомитися з базовими командами для архівування та стиснення даних. 📦
3. Вивчити основи роботи з текстом у терміналі. ✍️

## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC
- 📦 Віртуальна машина – VirtualBox (Oracle)
- 🐧 Операційна система GNU/Linux
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси з Linux

---

## 📖 **Завдання для попередньої підготовки**

### 🔹 **1. Словник базових англійських термінів**  
Прочитайте теоретичні відомості та складіть словник термінів:  

| **Термін англійською** | **Термін українською** |
|:-----------------------|:-----------------------|
| deflate                | здути                 |
| protocol               | протокол             |
| advantages             | переваги             |
| compress               | стискати             |
| directories            | папки                |
| sequential             | послідовний          |
| archiving              | архівувати           |
| formatted              | відформатований      |
| lossless               | без втрат            |
| utility                | корисність           |

---

### 🔹 **2(4). Теоретичні питання**

📌 **Завдання:** Дайте відповіді на наступні питання:

**1️⃣ Яке призначення команд `tar`, `xz`, `zip`, `bzip`, `gzip`? Зробіть короткий опис кожної команди та виділіть їх основні параметри. Яким чином їх можна встановити.**

- **tar** (Tape Archive): Archives files and directories into a single file.  
  **Main Parameters:**  
  - `-c`: create an archive  
  - `-x`: extract an archive  
  - `-f`: specify the archive file name  
  - `-v`: show the list of files being processed  
  **Installation:** Usually pre-installed, but additional features can be added via packages (e.g., `apt install tar`).

- **xz**: Compresses files using the LZMA algorithm for high compression ratios.  
  **Main Parameters:**  
  - `-c`: output the result to stdout  
  - `-d`: decompress the file  
  - `-z`: compress using a gzip-like algorithm  
  **Installation:** Install via the OS package manager (e.g., `apt install xz-utils`).

- **zip**: Archives and compresses files into the ZIP format.  
  **Main Parameters:**  
  - `-r`: recursively add files from subdirectories  
  - `-u`: update the archive with new files  
  - `-d`: delete a file from the archive  
  **Installation:** Install via the package manager (e.g., `apt install zip`).

- **bzip**: Compresses files using the Burrows-Wheeler algorithm for efficient compression.  
  **Main Parameters:**  
  - `-z`: compress the file  
  - `-d`: decompress the file  
  - `-k`: keep the original file after compression/decompression  
  **Installation:** Install via the package manager (e.g., `apt install bzip2`).

- **gzip**: Compresses files using the Lempel-Ziv algorithm (LZ77) for lossless compression.  
  **Main Parameters:**  
  - `-c`: output the result to stdout  
  - `-d`: decompress the file  
  - `-r`: operate recursively on directories  
  **Installation:** Install via the package manager (e.g., `apt install gzip`).

---

**2️⃣ Приклади архівування та стискання**

- `tar -czvf myfolder.tar.gz myfolder` 📦  
- `zip myfile.zip myfile.txt` 📂  
- `bzip2 -dk myarchive.bz2` 🗜️

---

**3️⃣ Призначення команд `cat`, `less`, `more`, `head`, `tail`**

- **cat** (Concatenate): Outputs the contents of text files to the console.  
  **Parameters:**  
  - `-n`: display line numbers  
  - `-s`: merge consecutive empty lines into one  
  - `-E`: show the end of each line with a `$`  
  **Installation:** Typically pre-installed on Linux systems.

- **less**: Allows viewing text files with navigation capabilities.  
  **Parameters:**  
  - `-N`: display line numbers  
  - `-S`: disable line wrapping  
  - `-F`: exit if the entire file fits on one screen  
  **Installation:** Install via the package manager (e.g., `apt install less`).

- **more**: Displays text files gradually, page by page.  
  **Parameters:**  
  - `-n`: display line numbers  
  - `-d`: prompt the user before proceeding  
  - `-c`: clear the screen before displaying the next page  
  **Installation:** Install via the package manager (e.g., `apt install more`).

- **head**: Outputs the first lines of a file (default is 10 lines).  
  **Installation:** Part of `coreutils`, typically pre-installed (e.g., `apt install coreutils` if needed).

- **tail**: Outputs the last lines of a file (default is 10 lines).  
  **Installation:** Part of `coreutils`, typically pre-installed (e.g., `apt install coreutils` if needed).

**4️⃣ Принципи роботи з каналами, потоками та фільтрами**

- The shell in the Linux operating system has built-in support for handling I/O streams and using pipes to transfer data between processes. This allows you to combine different commands to get more complex data processing results.
- Channels allow the output of one command to be passed as input to another command. For example, if we want to list the files in the current directory and sort it alphabetically, we can use the channel | to pass the output of the `ls` command as input to the `sort` command
- I/O streams (stdin, stdout, stderr) are standard data streams used to interact with commands on the command line. The shell automatically binds standard input (stdin) to the keyboard, and standard output (stdout) and standard error stream (stderr) to the screen.

Канали (`|`) передають вивід однієї команди як вхід іншій. Наприклад:  
`ls | sort` – сортує список файлів.  
Потоки:  
- `stdin` (ввід): з клавіатури  
- `stdout` (вивід): на екран  
- `stderr` (помилки): на екран  

**5️⃣ Призначення команди `grep`**
The `grep` (Global Regular Expression Print) command is used to search input data using a specific string or regular expression.
**grep** : Шукає рядки за шаблоном або регулярним виразом у даних.

---

## 🎬 **Хід роботи**

### 🎥 **1(2). Таблиця команд**

📌 **Завдання:** Опишіть команди з курсів NDG Linux Essentials (Lab 9: Archiving and Compression, Lab 10: Working With Text).

| **Команда**                  | **Призначення та функціональність** 🎯 |
|------------------------------|----------------------------------------|
| `mkdir mybackups`            | Створює нову директорію `mybackups` у домашньому каталозі. 🗂️ |
| `head`                       | Виводить перші 10 рядків файлу. 📜 |
| `tail`                       | Виводить останні 10 рядків файлу. 📜 |
| `grep`                       | Шукає рядки за шаблоном або регулярним виразом. 🔍 |
| `egrep`                      | Розширена версія `grep` із підтримкою всіх регулярних виразів. 🔎 |
| `zip`                        | Архівує файли у форматі ZIP (тільки файли `.c` у прикладі). 📦 |
| `unzip`                      | Розпаковує файли з архіву ZIP. 📂 |
| `>`                          | Перенаправляє `stdout` у файл (перезапис). ➡️ |
| `>>`                         | Додає `stdout` у кінець файлу. ➕ |
| `tar -cvf mybackups/udev.tar /etc/udev` | Архівує вміст `/etc/udev` у `udev.tar`. `-c`: створити, `-v`: показати файли, `-f`: ім’я файлу. 📦 |
| `tar`                        | Архівує файли (спочатку для стрічок, тепер для файлів). 📼 |
| `gzip`                       | Стискає файли без втрат (алгоритм LZ77). 🗜️ |
| `bzip2`                      | Стискає файли без втрат (алгоритм Барроуза-Вілера). 🗜️ |
| `xz`                         | Стискає з високим ступенем (POSIX). 🗜️ |
| `unxz`                       | Розпаковує архіви, створені `xz`. 📂 |
| `find`                       | Шукає файли рекурсивно у вказаній директорії. 🔎 |
| `2>`                         | Перенаправляє `stderr` у файл. 🚨 |
| `tr`                         | Перетворює символи (наприклад, заміна). 🔄 |
| `cut`                        | Витягує стовпці або поля з тексту. ✂️ |
| `more` та `less`             | Переглядає текст по сторінках або рядках. 📖 |

---

### 🔹 **2(3). Робота в терміналі**

📌 **Завдання:** Виконайте наступні дії:  
- Створити файл `.tar` 📦  
- Створити `.tar` із кількома файлами та каталогами 🗂️  
- Переглянути вміст файлу 👀  
- Витягти вміст `.tar` 📂  
- Створити `.tar`, стиснений `bzip2` 🗜️  
- Витягти вміст `.tar` (`bzip2`) 📂  
- Створити `.tar`, стиснений `gzip` 🗜️  
- Витягти вміст `.tar` (`gzip`) 📂
![](https://i.ibb.co/p665gGzw/vmware-7im-Ly-Zfd-FA.png)

### 🔹 **3(4). Перенаправлення потоків у Bash**

| **Команда**          | **Що виконує?** 🛠️                     |
|----------------------|---------------------------------------|
| `cmd 1> file`        | Записує вивід у файл (перезапис).     |
| `cmd > file`         | Те саме, що `1> file`.                |
| `cmd 2> file`        | Записує помилки у файл (перезапис).   |
| `cmd >> file`        | Додає вивід у кінець файлу.           |
| `cmd &> file`        | Записує вивід і помилки у файл.       |
| `cmd > file 2>&1`    | Те саме, що `&> file`.                |
| `cmd >> file 2>&1`   | Додає вивід і помилки у кінець файлу. |
| `cmd 2>&1 > /dev/null` | Перенаправляє помилки на stdout, вивід у `/dev/null`. |
| `cmd 2> /dev/null`   | Відправляє помилки у `/dev/null`.     |
| `cmd1 \| cmd2`       | Передає вивід `cmd1` як вхід `cmd2`.  |
| `cmd1 2>&1 \| cmd2`  | Передає вивід і помилки `cmd1` у `cmd2`. |

### 🔹 **4(5). Аналіз прикладів перенаправлення**

| **Команда**                     | **Що виконує?** 🛠️                     | **Тип перенаправлення** 🚀 |
|--------------------------------|---------------------------------------|---------------------------|
| `echo "It is a new story." > story` | Записує рядок у файл `story`.         | `>` (перезапис)           |
| `date > date.txt`             | Записує дату у `date.txt`.            | `>` (перезапис)           |
| `cat file1 file2 file3 > bigfile` | Об’єднує файли у `bigfile`.         | `>` (перезапис)           |
| `ls -l >> directory`          | Додає вивід `ls -l` у `directory`.    | `>>` (додавання)          |
| `sort < file1_unsorted > file2_sorted` | Сортує `file1_unsorted` у `file2_sorted`. | `<` (ввід), `>` (вивід) |
| `find -name '*.txt' > file.txt 2> /dev/null` | Шукає `.txt` файли, вивід у `file.txt`, помилки у `/dev/null`. | `>` (вивід), `2>` (stderr) |
| `cat file1_unsorted \| sort > file2_sorted` | Сортує `file1_unsorted` у `file2_sorted`. | `|` (канал), `>` (вивід) |
| `cat myfile \| grep student \| wc -l` | Рахує рядки зі словом `student` у `myfile`. | `|` (канал)             |

---

### ✏️ **Відповіді на контрольні питання**

#### 1️⃣ **Порівняння стискання та архівування**
📌 **Надайте порівняльну характеристику процесам стискання та архівування.**
- **Архівування:** 📦 Archiving is the process of creating a single file that contains multiple files or directories. Archiving is typically used to store or transfer a group of files in order to preserve their structure and relationships between them.   
- **Стискання:** 🗜️ Compression is the process of reducing the size of a file or data by removing redundant information. Compression can be lossless or lossy. 

#### 2️⃣ **Інші програми для стискання та архівування в Linux**
📌 **Які програми, окрім наведених в роботі, можуть використовуватись для стискання та архівування файлів та каталогів в ОС Linux? Наведіть приклади та їх короткий опис.**
- **7zip**: is an open source program that supports many compression and archiving formats, including 7z, ZIP, TAR, and WIM. It has a high degree of compression and can work with encrypted archives. 
- **PeaZip**: is an open source program that supports many compression and archiving formats, including 7z, ZIP, TAR, GZ, and XZ. It has a graphical user interface and can be used to create archives, unpack and view their contents.  
- **rar**: is a program for compressing and archiving files that supports the RAR format. It has a high degree of compression and can work with encrypted archives.  

#### 3️⃣ **Порівняння алгоритмів стискання**
📌 **Порівняйте алгоритми стискання, що використовуються в командах (програмах), використовуваних в Linux. Які з алгоритмів можна вважати найшвидшим та найефективнішим?**

| **Алгоритм** | **Швидкість** ⚡ | **Ступінь стиснення** 📉 | **Ресурси** 💻 |
|--------------|-----------------|-------------------------|---------------|
| `gzip`       | Швидкий         | Низький                 | Низьке        |
| `bzip2`      | Помірний        | Високий                 | Високе        |
| `xz`         | Повільний       | Дуже високий            | Високе        |

#### 4️⃣ **Стискання та архівування на мобільному**
📌 **Опишіть програмні засоби для стискання та архівування, що можуть бути використані у вашому мобільному телефоні?**
On Samsung Galaxy S21 FE, you can use both built-in tools and third-party applications from the Google Play Store to compress and archive files. The built-in My Files file manager allows you to create and unpack ZIP archives, which is convenient for basic tasks, but it only supports ZIP and does not have advanced options such as encryption or selection of compression level. The popular RAR application by RARLAB provides compression to RAR and ZIP, decompression of many formats (RAR, ZIP, TAR, GZ, BZ2, X

- **My Files**: Створює/розпаковує ZIP, базові функції. 📱  
- **RAR (RARLAB)**: Підтримує RAR, ZIP, розпаковує TAR, GZ, BZ2. 🗜️  

#### 5️⃣ **Стискання та архівування у Windows**
📌 **Опишіть та порівняйте програмні засоби для стискання та (де)архівування даних у ОС сімейства Windows.**
Windows uses both built-in and third-party programs to compress and archive data. The built-in Windows compression feature through Windows Explorer allows you to create ZIP archives without additional tools, but it has limitations in terms of efficiency and functionality. WinRAR is a powerful commercial archiver that supports RAR and ZIP formats, provides a high degree of compression and encryption, but is paid. 7-Zip is a free and open-source archiver that has high compression and support for many formats, but is less intuitive. WinZip is convenient for users of cloud services, but has a lower compression rate and is paid. Compared to the others, WinRAR and 7-Zip have better compression speed and efficiency, while the built-in Windows function and WinZip are inferior in these aspects.
- **Windows Explorer**: Створює ZIP, обмежені функції.
- **WinRAR**: Підтримує RAR, ZIP, висока компресія, платний.  
- **7-Zip**: Безкоштовний, висока компресія, багато форматів.  
- **WinZip**: Зручний для хмар, платний, нижча компресія.  

#### 6️⃣ **Використання стискання та архівування**
📌 **Поясніть яким чином стиснення та архівування даних може бути використано для резервування даних. В яких ще задачах системного адміністрування воно може бути використано.**
Data compression and archiving are used for backup, where archiving collects files into one, and compression reduces their size, saving space and speeding up transmission over the network. This reduces storage costs and simplifies data recovery. They are also used for data transfer (reducing network load), disk space cleanup (archiving old files), update management, system testing and migration, and security through encryption.
- **Резервування:** Зменшує розмір даних, спрощує зберігання. 💾  
- **Інші задачі:** Передача даних, очищення диска, оновлення, тестування, безпека. 🔐  

#### 7️⃣ **Призначення `/dev/null`**  
📌 **Яке призначення директорії файлу /dev/null?**
The /dev/null file in Unix/Linux is a virtual device that rejects any data directed to it and does not store it. It is used to suppress command output, test programs without accumulating data, and clean up unnecessary logs or errors. Also, if /dev/null is read from, it returns an empty result, which is useful for programs that require an empty input. It is an important tool for optimizing and automating processes on the command line.
`/dev/null` – A virtual device that rejects data. It is used for output suppression, testing, and log cleaning.

---

## 🏁 **Висновки**

In this lab, we learned about the existing methods of file compression and archiving in Linux and tried them out in practice.