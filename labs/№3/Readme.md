# ЛАБОРАТОРНА РОБОТА №3

## 📌 Дисципліна: "Операційні системи"

## 🏷 **Тема:**
> Знайомство з базовими командами CLI-режиму в Linux.

## 👨‍🎓 **Виконав:**
- **Нагорний І.М. РПЗ-23Б**

---

## 🎯 **Мета роботи**
1. Знайомство з базовими командами CLI-режиму в Linux.
2. Знайомство з базовими текстовими командами в термінальному режимі роботи в різних ОС.


## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC.
- 📦 Віртуальна машина – VirtualBox (Oracle).
- 🐧 Операційна система GNU/Linux.
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси по Linux.

---

## 📖 Завдання для попередньої підготовки
### 🔹 **1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань призначення команд та їх параметрів:** 


| Термін англійською | Термін українською |
|:-------------------|-------------------:|
|shell               |            оболонка|
|terminal            |            термінал|
|directory           |             каталог|
|executed            |            виконано|
|variables           |              змінні|
|accept              |          погодитися|
|expand              |           розширити|
|interpreter         |       інтерпретатор|
|environment         |          середовище|
|prompt              |            підказка|


### 🔹 **2(4). Теоретичні питання**
📌 Завдання - Дайте визначення наступним поняттям:

  1️⃣ **Яку базову інформацію надає рядок запрошення prompt?**
  
    The prompt usually contains information about the user and the system
  
  2️⃣ **Для чого команді потрібні параметри та аргументи?**
  
    Argument - what the command will work with  
    Parameter - additional information about what exactly the command should do
  
  3️⃣ **Яке призначення команд ls, які параметри та аргументи вона може мати? Наведіть 3 приклади.**
  
    The `ls` command is used to display a list of files and directories in the current working directory.
  
    Here are some examples:
  
    - Display detailed information about files and directories with the `-l` option.
    - Display a list of files and directories sorted by modification date with the `-t` option.
    - Display a list of files and directories with a given extension with an argument containing that extension. For example, to display a list of files with the extension `.txt`, you need to enter the `ls *.txt`
  
  4️⃣ **Яким чином можна використати історію команд, які переваги це надає?**
    
    The command history is stored in the command buffer and can be accessed using the up arrow and down arrow keys on the keyboard.
  
    The main advantages of using command history:

    - Quick access to previously typed commands: Using command history allows you to quickly find and repeat previously typed commands without having to retype them.
    - Time Saving and Convenience: Using command history saves time and convenience by not having to repeat long or complex commands over and over again.
    - Error correction: Command history also makes it easy to find and correct errors in previous commands without retyping the entire command.
    - Improved productivity: Using command history allows you to speed up your work with the operating system and applications, reducing the time and effort required to retype commands.
  
  5️⃣ **Яке призначення команди echo?**
  
    The "echo" command is used to display text on the screen. It allows you to display text messages on the terminal screen or output them to the output data stream.
  
    In addition, the "echo" command can be used in scripts to output the values of variables, as well as to create files and write data to them.
  
  6️⃣ **Охарактеризуйте поняття змінної в оболонці Bash, які типи змінних вона підтримує?**
  
    In the Bash shell, a variable is a name used to store a value. Variables allow you to store data that can be used in programs and scripts. Variables can hold different types of data, such as strings, numbers, arrays, booleans, etc.

    In Bash, variables can be divided into three types:

    - Environment variables are variables that are stored in the system environment and are available to all processes running on the system. Environment variables can be set using the `export` command.
    - Local context variables (local variables) are variables that are available only within the current script or function in which they were defined.
    - Positional parameters are variables that contain arguments passed to an executable program or script at startup. The first nine positional parameters are labeled as $1, $2, $3, ..., $9.
  
  7️⃣  **Яке призначення команд env, export та unset?**
  
    The `env` command is used to display the current environment variables or to run a command in a modified environment. It can be used to set environment variables for a specific command without affecting the current environment.

    The `export` command is used to set environment variables in the current shell session or to mark variables for export to child processes. When a variable is marked for export using the export command, it becomes part of the environment and is passed on to any child processes.

    The `unset` command is used to remove variables and functions from the current shell session or from the environment. When a variable is unset using the unset command, it is no longer available for use in the current shell session or in any child processes.
  
  8️⃣ **Які команди для отримання довідки по командам в терміналі ви знаєте?**

    There are several ways to get help about commands in the terminal, including:

    - `man` - command to display command help in the terminal. For help, run the `man` command with the name of the command.
    - `--help` - Most commands have a `--help` option that displays a brief description of the command and a list of available options.
    - `help` - This command displays help on built-in Bash shell commands. Run `help` without parameters to get a list of built-in Bash commands, or run `help` with the name of a command to get help about a built-in command.
    - `apropos` - this command searches for commands matching the specified keyword in the help text. Run the `apropos` command with a keyword to get a list of commands associated with that keyword.
    - `whatis` - this command displays a brief description of the command. Run the `whatis` command with the command name to get a brief description.
  


 ---   
## 🎬 **Хід роботи**
### 🎥 **1. Опрацюйте всі приклади команд, що представлені у лабораторній роботі курсу NDG Linux Essentials - Lab 5: Command Line Skills та Lab 6: Getting Help. Створіть таблицю для опису цих команд:**


|Назва команди|Її призначення та функціональність|
|:------------|---------------------------------:|
|ls           |Виводить інформації про каталоги та файли. За замовчуванням без аргументів відображає інформацію для поточного каталогу|
|ls -l        |Використанні параметру -l в команді ls дозволяє відобразити інформацію про файли, розташовані в поточному робочому каталозі, у довгому форматі, який надає більш розширену додаткову інформацію|
|ls -l /tmp   |Використання аргументу /tmp в поєднанні з параметром -l в команді ls дозволяє відобразити детальну інформацію про файли в каталозі /tmp.|
|whoami       |The output of the whoami command, sysadmin, displays the user name of the current user. Although in this case your username is displayed in the prompt, this command could be used to obtain this information in a situation when the prompt did not contain this information.|
|  uname      | Execute the uname command again twice in the terminal, once with the option -n and again with the option --nodename. This will display the network node hostname, also found in the prompt. |
|pwd          | The current directory in the example above is /home/sysadmin. This is also referred to as your home directory, a special place where you have control of files and other users normally have no access. By default, this directory is named the same as your username and is located underneath the /home directory.  |
|history      | To view a limited number of commands, the history command can take a number as a parameter to display exactly that many recent entries.  |
|!9           |To execute a command again, type the exclamation point and the history list number. For example, to execute the 9th command in your history list  |
|echo Hello Student|The echo command can be used to print text and the value of a variable, and to show how the shell environment expands metacharacters (more on metacharacters later in this lab)    |
|echo $PATH   | The PATH variable is displayed by placing a $ character in front of the name of the variable.  |
|which date   | The output of the which command tells you that when you execute the date command, the system will run the command /bin/date. The which command makes use of the PATH variable to determine the location of the date command. |
| type command| The type command identifies the cd command as an internal command  |
|which ls     | External commands are binary executables stored in directories that are searched by the shell. If a user types the ls command, the shell searches through the directories that are listed in the PATH variable to try to find a file named ls that it can execute. Use the which command to display the full path to the ls command. |
|Aliases      |  Aliases can be used to map longer commands to shorter key sequences. When the shell sees an alias being executed, it substitutes the longer sequence before proceeding to interpret commands.  |
|date         | Execute commands in the bash shell by typing the command and then pressing the Enter key.  |
| man date    | To learn more about commands, access the manual page for the command with the man command.    |
|/file        |  Searches are not case sensitive and do not "wrap" around from the bottom to top, or vice versa. Start a forward search for the word "file" by typing:  |
| man -k password |   In some cases you may not remember the exact name of the command. In these cases you can use the -k option to the man command and provide a keyword argument. For example, execute the following command to display a summary of all man pages that have the keyword "password" in the description:  |
| apropos password  | Note that the apropos command is another way of viewing man page summaries with a keyword. Type the following command:  |
|man -f passwd   | There are often multiple man pages with the same name. For example, the following command shows three pages for passwd. Execute the following command to view the man pages for the word passwd:  |
| whatis passwd |  Instead of using man -f to display all man page sections for a name, you can also use the whatis command:  |
| info date   | Almost all system features (commands, system files, etc.) have man pages. Some of these features also have a more advanced feature called info pages. For example, execute the following command: |
| date --help | Another way of getting help is by using the --help option to a command. Most commands allow you to pass an argument of --help to view basic command usage:  |

---

### 🔹 **2. Робота в терміналі**

#### 2.1. Робота зі змінними (Variables) та псевдонімами (Aliases) в терміналі

- Створіть змінні, що будуть містити Ваші імена та прізвища `$var_name1`, `$var_name2`, `$var_name3`.

```bash
var_name1="Illya Nagorny"
```

![var_name1="Illya Nagorny" PHOTO](https://i.ibb.co/xKyBm0kF/firefox-h-KDXFyd0cu.png)

- За допомогою команди `echo` виведіть імена студентів вашої команди.

```bash
echo "Team students: $var_name1"
```

![echo "Team students: $var_name1" PHOTO](https://i.ibb.co/xSnLT1Zs/firefox-YI2ym-RXFot.png)

- Створіть псевдоніми `mycal1`, `mycal2`, `mycal3` для команди `cal` для автоматичного виведення календарю вашого року народження. (Також додав дату)

```bash
alias mycal1='cal 7 2007; date -d "2007-06-07" "+%d.%m.%Y"'
```

![PHOTO](https://i.ibb.co/fG2Hnczc/image.png)

#### 2.2. Робота з функціями (Functions) в терміналі

- Створіть функцію `students_report`, що порядково буде виводити спочатку імена студентів Вашої команди, а потім роки їх народження.

```bash
students_report() { echo "Student name: $var_name1"; mycal1; }; students_report
```

![PHOTO](https://i.ibb.co/vx5MHjjs/image.png)

#### 2.3. Робота з лапками (Quoting) в терміналі

- Виведіть в командному рядку наступні речення:

  - **"We create such variables as `$var_name1`, `$var_name2`, `$var_name3`, which stored our names Name1, Name2, Name3"** (у реченні спочатку виводимо назви змінних, а потім їх вміст).

  ```bash
  echo "We create such variables as \$var_name1, which stored our names $var_name1"
  ```

  ![PHOTO](https://i.ibb.co/0Rq35Y40/image.png)

  - **"We create such Aliases as `mycal1`, `mycal2`, `mycal3`, which can show our calendars: Calendar1, Calendar2, Calendar3"** (у реченні спочатку виводимо назву команди-псевдонімів, потім вивід цих команд).

  ```bash
  echo We create such Aliases as \mycal1, which can show our calendars: ;mycal1
  ```

  ![PHOTO](https://i.ibb.co/PGTmWp2D/image.png)

#### 2.4. Робота з інструкціями керування (Control Statements) в терміналі

- Чи можна завдання 2.1 та 2.2 ходу роботи виконати через інструкції керування без написання окремої функції, як це буде виглядати?

```bash
echo $var_name1 ; mycal1
```

![PHOTO](https://i.ibb.co/ynY8JkF1/image.png)

#### 2.5. Робота з командами довідки (Man Pages) в терміналі

- На прикладі команди `uname` продемонструйте, як отримати довідку. На основі отриманої додаткової інформації наведіть 5 різних варіантів виводу результату інформації по даній команді з використанням 5 різних параметрів (Options):

```bash
uname -s # OS name
uname -n # Hostname
uname -r # Kernel version
uname -m # Processor architecture
uname -o # Operating System
```

![PHOTO](https://i.ibb.co/tpjbM2kj/image.png)

---

### ✏️ **Відповіді на контрольні питання:**

1. **Які типи команд існують в оболонці Bash?**
   - **Built-in commands:** These are commands that are built into the shell itself, such as `cd` (change directory) and `echo` (print to screen).
   - **External commands:** These are commands that are separate programs installed on the system, such as `ls` (list files) and `grep` (search for text in a file).
   - **Alias commands:** These are custom shortcuts that can be created by the user to execute a longer command with a shorter name.
   - **Function commands:** These are custom commands created by the user using shell programming constructs.

2. **Що таке змінні оточення? Які вони бувають? Як їх можна переглянути в терміналі?**
   - **Environment variables** are variables that are set in the shell's environment and are accessible to any program or command run in that environment. They are used to store information that may be needed by multiple programs or commands. Some common environment variables include `PATH` (which stores a list of directories to search for executables), `HOME` (which stores the path to the user's home directory), and `USER` (which stores the username of the current user). You can view these variables in the terminal by using the command `printenv` or by using the command `echo` with the variable name preceded by a `$` sign (e.g., `echo $PATH`).

3. **Опишіть змінну $PS1. Як в терміналі переглянути її вміст?**
   - The variable `$PS1` defines the prompt string displayed before each command in the terminal. The default value is `"\s-\v$ "`, which shows the shell's name and its version number, followed by a dollar sign. To view the contents of `$PS1`, use the command:
     ```bash
     echo $PS1
     ```

4. **Як можна змінити значення змінної $PS1? Що при цьому відбудеться в рядку запрошення в bash? Як змінити значення цієї змінної не на поточний сеанс, а за замовчуванням?**
   - To change the value of `$PS1`, assign a new value using the `export` command. For example:
     ```bash
     export PS1='\w$ '
     ```
     This will display the current working directory in the prompt. To make this change permanent, add the new value to the shell configuration file (`~/.bashrc` or `~/.bash_profile`).

5. **Для чого використовують лапки в оболонці Bash?**
   - Quotation marks are used to group words together as a single argument, especially when words contain spaces or special characters. There are two types of quotation marks:
     - **Single quotes** (`'...'`) preserve the literal value of all characters within the quotes.
     - **Double quotes** (`"..."`) allow certain characters (like variables) to be expanded. 
     - **Backslashes** (`\`) can also be used to escape special characters within quotes.

6. **Для чого використовують інструкції керування, які їх види Ви знаєте?**
   - **Control instructions** (also called control structures) are used to execute commands conditionally or repeatedly. Some common types include:
     - `if/else` statements: Execute commands based on a condition.
     - `for` loops: Execute commands for each element in a list or range.
     - `while` loops: Execute commands as long as a condition is true.
     - `case` statements: Execute commands based on a specific pattern.

7. **В чому різниця, якщо в кінці рядку запрошення bash стоїть символ `$` чи `#`?**
   - 📌 [centos@localhost Desktop]$ 
   - 📌 [root@localhost Desktoop]# 
     - The Bash prompt line ends with a `$` for a regular user and `#` for the root user. The hash symbol (`#`) indicates that the user has superuser privileges, while the dollar sign (`$`) indicates a regular user.

8. **Яке призначення команд `whereis` та `locate`? Яка між ними відмінність?**
   - The `whereis` and `locate` commands are used to find files on the system:
     - **`whereis`** searches for executable files, source files, and manual pages for a specific command or program.
     - **`locate`** searches the entire system for files and directories based on a specified pattern.
   - The difference is that `whereis` searches a limited set of directories, while `locate` searches the whole system's database. `Locate` is faster but may not always return the most up-to-date results if the system's database is out of date.

---
   
## 🏁 **Висновки**

У лабораторній роботі я розглянув основи роботи з командним рядком у Linux. Зокрема, я освоїв використання базових команд, таких як `alias`, `echo`, а також навчився працювати зі змінними, псевдонімами та функціями. Ці знання дозволяють мені ефективно виконувати різні операції в терміналі, спрощуючи роботу з файловою системою та підвищуючи мою ефективність у Linux-середовищі.

