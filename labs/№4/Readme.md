# ЛАБОРАТОРНА РОБОТА №4

## 📌 Дисципліна: "Операційні системи"

## 🏷 **Тема:**
> Команди Linux для управління процесами

## 👨‍🎓 **Виконав:**
- **Нагорний І.М. РПЗ-23Б**

---

## 🎯 **Мета роботи**
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство з базовими командами для управління процесами.


## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC.
- 📦 Віртуальна машина – VirtualBox (Oracle).
- 🐧 Операційна система GNU/Linux.
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси по Linux.

---

## 📖 Завдання для попередньої підготовки
### 🔹 **1. Прочитайте короткі теоретичні відомості до лабораторної роботи та зробіть невеликий словник базових англійських термінів з питань призначення команд та їх параметрів:** 


|    Термін англійською    |  Термін українською   |
|:-------------------------|----------------------:|
|Monitoring                |Контроль               |
|Average                   |Середній               |
|Interactive               |Інтерактивний          |
|Refuse                    |Непридатний            |
|Interprocess communication|Міжпроцесна комунікація|
|Available                 |Доступний              |
|Running                   |Запущений              |
|Gleaning                  |Збір                   |
|Utilities                 |Утиліти                |
|Subset                    |Підмножина             |



### 🔹 **2. Теоретичні питання**

📌 Завдання – Дайте відповіді на наступні питання:

**1️⃣ Які команди для моніторингу стану процесів ви знаєте. Як переглянути їх можливі параметри?**

- `ps`  
- `top`  
- `htop`  
- `pstree`  
- `pgrep`  
- `lsof`  
- `strace`  

To view possible command options, you can use the `--help` or `-h` option.  
For example:  
`ps --help` or `top -h`

**2️⃣ Чи може команда `ps` у реальному часі відслідковувати стан процесів?**

The `ps` command shows the current state of the processes at the time it was run. If you add the `--watch` or `-w` option, then `ps` will start updating its output every few seconds.  
For example:  
`ps -efw`

**3️⃣ За якими параметрами можливе сортування процесів в команді top? Як переключатись між ними?**

- `p`  
- `M`  
- `T`  
- `N`  
- `K`

**4️⃣ Які команди для завершення роботи процесів ви знаєте?**

- `kill`  
- `pkill`  
- `killall`  
- `xkill`

---

## 🎬 **Хід роботи**
### 🎥 **1(2). Дайте відповіді на наступні питання:**

#### 📁 **Як вивести вміст директорії /proc? Де вона знаходиться та для чого призначена. Охарактеризуйте інформацію про її вміст?**  
To display the contents of the `/proc` directory, you can use the `ls` command:  
```bash
ls /proc
```  
The `/proc` directory is a virtual file system that is located in the root directory of a Linux system. It provides an interface to kernel data structures and information about running processes.

#### 👤 **Як вивести інформацію про поточні сеанси користувачів. Якою командою це можна зробити?**  
To display information about the processes running within a user session, you can use the `-u` option followed by the username of the user whose processes you want to display. For example, to display information about the processes running within the session of the currently logged-in user, you can use the following command:  
```bash
ps -u $USER
```

#### ⌨️ **Які дії можна зробити в терміналі за допомогою комбінацій Ctrl + C, Ctrl + D та Ctrl + Z?**  
- **Ctrl + C**: This combination sends the "interrupt" signal to the currently running process, which causes it to terminate.  
- **Ctrl + D**: This combination sends an "end of file" (EOF) character to the terminal, which signals the end of input. This is often used to exit from a command-line shell.  
- **Ctrl + Z**: This combination sends the "suspend" signal to the currently running process, which causes it to pause and be placed in the background.

#### ⚙️ **Чим відрізняється фоновий процес від звичайного. Де вони використовуються?**  
A **background process** is a process that is executed in the background without blocking the terminal or requiring the user to wait for it to complete. In contrast, a **regular process** is executed in the foreground and requires the user to wait for it to complete before proceeding.  

Background processes are often used for:  
- Running a backup or file transfer task in the background while continuing to work on other tasks.  
- Running a server or daemon process in the background that provides a service to other programs or users.  
- Running a command that takes a long time to complete, such as compiling a large program or compressing a large file.

#### 🛠️ **Опишіть наступні команди та поясніть що вони виконують – команда jobs, bg, fg.**  
- **`jobs`**: This command lists all jobs running in the current shell session, including both background and suspended jobs. Each job is assigned a unique job ID number, which can be used to refer to the job in other job control commands. The `jobs` command also displays the status of each job, which can be one of "running", "stopped", or "terminated".  
- **`bg`**: This command is used to move a suspended job to the background and continue running it. You can use the job ID number or the job’s process ID (PID) to specify which job to move to the background.  
- **`fg`**: This command is used to bring a job from the background to the foreground and continue running it. You can use the job ID number or the job’s PID to specify which job to bring to the foreground.

#### 🔍 **Якою командою можна переглянути інформацію про запущені в системи фонові процеси та задачі?**  
To view information about background processes and tasks running in the system, you can use the `ps` command with specific options that show the status of the processes:  
- **`ps aux`**: This command shows a detailed list of all processes running on the system, including those running in the background.  
- **`ps -ef`**: This command shows a list of all processes running on the system, including those running in the background, in a tree format.  
- **`ps -ejH`**: This command shows a list of all processes running on the system, including those running in the background, in a hierarchical format.

#### 🔄 **Як призупинити фоновий процес, як його потім відновити та при необхідності перезапусти?**  
To pause, resume, and restart a background process, you can use the following commands:  
- **`kill`**: This command can be used to send various signals to a process, including the "stop" signal (SIGSTOP) to pause a process and the "continue" signal (SIGCONT) to resume a paused process.  
- **`bg`**: This command is used to move a suspended or stopped job to the background and continue running it.  
- **`fg`**: This command is used to bring a job from the background to the foreground and continue running it.

---

### 🔹 **2(3). Запустіть термінал, та в командному рядку виконайте наступні дії для ознайомлення з роботою з процесами:**

#### 💡 **Запустіть команду `top`, проаналізуйте отриманий в цій команді результат та охарактеризуйте найбільш активні процеси у системі**

![Alt Text](https://i.ibb.co/LdvjmQP3/image.png)

The `top` command is an interactive process monitoring utility for Linux systems. Once launched, it displays a real-time list of processes that take up the most system resources (e.g., **CPU**, **RAM**, disk space, etc.). It also provides useful information about overall system health and resource usage.

The most active processes can be identified using these metrics:
- **CPU**: Shows the percentage of CPU utilization by each process.
- **MEM**: Displays the percentage of RAM used by each process.
- **RES**: Indicates the amount of RAM consumed by each process.
- **TIME+**: Shows the total time the process has been running since startup.
- **COMMAND**: The name of the process as it appears on the command line.


#### 💡 **Призупинити виконання команди `top` (треба використати комбінацію клавіш `CTRL + Z/C`)**

![Alt Text](https://i.ibb.co/JwcGWXkq/image.png)

Pressing `Ctrl + Z` suspends the `top` command, moving it to the background in a paused state.


#### 💡 **Вивести інформацію про процеси за допомогою команди `ps`**

![ps](https://i.ibb.co/SwXhtBCH/image.png)

The `ps` command is a command-line utility that displays information about active processes in the system.


#### 💡 **Наведіть 5 прикладів з використанням різних параметрів команди `ps` (наприклад, вивести тільки системні процеси, вивести процеси конкретного користувача, вивести дерево процесів тощо). Опишіть, що саме роблять обрані Вами параметри**

Here are five examples of the `ps` command with different parameters, each preceded by a description of what the parameter does:

1. **`-e`: Displays information about all processes in the system, not just those owned by the current user.**  
   ![ps -e](https://i.ibb.co/YTcPBVY4/image.png)

2. **`-u`: Shows process details including information about the users who started them.**  
   ![ps -u](https://i.ibb.co/hrQhYWM/image.png)

3. **`-ejH`: Displays a process tree, illustrating the hierarchy of parent and child processes since system startup.**  
   ![ps -ejH](https://i.ibb.co/3mCfgrRk/image.png)

4. **`-aux`: Combines `-a` (all processes) and `-u` (user info) to show detailed info about every process in the system.**  
   ![ps -aux](https://i.ibb.co/Qjtn5Fzb/image.png)

5. **`-f`: Provides full-format output, including PID, PPID, status, start time, and more.**  
   ![ps -f](https://i.ibb.co/rR216pv6/image.png)

#### 📋 **Summary Table of `ps` Parameters** (Optional)
| Parameter | Description                                    |
|-----------|------------------------------------------------|
| `-e`      | Shows all processes in the system.             |
| `-u`      | Includes user-related process details.         |
| `-ejH`    | Displays a process tree hierarchy.             |
| `-aux`    | Lists all processes with user info.            |
| `-f`      | Provides full-format process details.          |

#### 💡 **Передивіться чи є у Вас запущені фонові процеси, які саме?**

Typical background processes in Linux:
- **bash**: A command shell for running terminal commands, included in most Linux distributions.
- **systemd**: A system manager that oversees processes, services, and resources at startup.
- **init**: An older system manager for handling processes and services.
- **sshd**: A server enabling remote SSH connections for system management.
- **cron**: A scheduler that automates tasks to run at specified times or intervals.

`These processes run in the background to keep the system operational.`


#### 💡 **Відновити виконання призупиненого фонового процесу спочатку у позиції “на передньому плані” (foreground), потім ще раз його призупинити, а потім відновити його виконання у позиції “на задньому плані” (background)**

![fg](https://i.ibb.co/MxjsM4QZ/image.png)  
![bg](https://i.ibb.co/jPVHtpch/image.png)

- **`fg %n`**: Restores a stopped job with job number `n` to the foreground, allowing interaction in the terminal.
- **`bg %n`**: Resumes a stopped job with job number `n` in the background, freeing the terminal for other commands.


#### 💡 **Завершити роботу даного фонового процесу**

![stop prog](https://i.ibb.co/h1D22n11/image.png)

The process can be terminated using a command like `kill` followed by its process ID (PID).


---

### ✏️ **Відповіді на контрольні питання:**

#### 1. Яке призначення директорії /proc в системах Linux. Яку інформацію вона зберігає?  
The `/proc` directory is like a window into the soul of a Linux system. It’s a virtual filesystem that dishes out real-time info about the kernel, hardware, and running processes. Here’s what you can dig up inside it:  

- `/proc/cpuinfo`: all the juicy details about your CPU(s).  
- `/proc/meminfo`: a rundown of how your system’s memory is holding up.  
- `/proc/net`: network interfaces and stats for the curious.  
- `/proc/sys`: tweakable system settings you can mess with on the fly.  
- `/proc/PID`: a deep dive into a specific process, where PID is its unique ID.  

#### 2. Як серед будь-яких трьох процесів динамічно визначати, який з них в поточний момент часу використовує найбільший обсяг пам'яті? Який відсоток пам’яті він споживає від загального обсягу?  
Need to figure out which of three processes is hogging the most memory right now? Fire up the `top` command—it’s your go-to for live process tracking. Want to sort by memory usage? Just hit the `M` key. To narrow it down to the top three memory munchers, press `1` to show all CPUs, then `Shift + N` to cap the list at three. Bonus: it’ll show you the percentage of total memory each one’s scarfing down. Easy peasy!

#### 3. Як отримати ієрархію батьківських процесів в системах Linux? Наведіть її структуру та охарактеризуйте.  
To peek at the family tree of processes in Linux, use the `pstree` command. It lays out all running processes in a neat tree, starting with the big boss—`init` (or `systemd` on modern setups)—and branching out to its kids. Here’s a snapshot from a bash session on Ubuntu:  

```
init─┬─init───bash───pstree  
     └─{init}  
```

- `init`: the OG process (PID 1) that kicks off when your system boots.  
- `bash`: a shell spawned by `init`, running my `pstree` command.  
- `{init}`: a sneaky kernel thread, not your average process—it’s doing behind-the-scenes system magic.  

#### 4. Чим відрізняється команда top від ps?  
Here’s the showdown between `top` and `ps`:  

- `top` is your live, interactive buddy—updates in real-time and lets you poke around. `ps`? It’s a one-and-done snapshot of processes.  
- `top` spills more details, like resource usage percentages, while `ps` keeps it basic.  
- With `top`, you can kill or tweak processes on the spot—no extra commands needed.  

#### 5. Які додаткові можливості реалізує htop в порівнянні з top?  
`htop` takes `top` and cranks it up a notch. Here’s what it brings to the party:  

- **Colorful vibes**: makes it easier to spot processes and resource hogs with a splash of color.  
- **Hands-on control**: stop, restart, or resume processes right in the app.  
- **Tree view**: see how processes are related, parent-to-child style.  
- **Sort it out**: order by CPU, memory, or whatever you fancy.  
- **Mouse-friendly**: click around instead of just typing.  
- **Live updates**: keeps the process list fresh without breaking a sweat.  

#### 6. Опишіть компоненти вашої мобільної ОС для здійснення моніторингу запущених в системі процесів?  
The Samsung Galaxy S21 FE comes packed with tools to keep an eye on what’s running:  

- **Task Manager**: your hub for checking out active processes—CPU, RAM, the works. Stop or restart stuff as needed.  
- **Resource Analyzer**: gives you the big picture—memory, storage, even device temp—to spot resource guzzlers.  
- **Home Screen Widgets**: slap a widget on your screen for real-time process and resource tracking, no app-hopping required.  
- **Third-Party Apps**: grab extras from Google Play or Galaxy Store for deeper dives into process monitoring.  

#### 7. Чи підтримує Ваша мобільна ОС термінальне керування роботою процесів, опишіть як саме.  
Yeah, the Samsung Galaxy S21 FE can totally handle terminal action. It’s got a built-in command shell you can tap into with apps like **Terminal Emulator**—just type away to boss processes around. Want more power? Install **Termux**, a badass terminal emulator that brings Linux vibes to Android. Run `ps` to list processes, kill stuff, monitor resources, or even code on the go—it’s a game-changer for terminal junkies.

#### 8. Чи можливо поставити сторонні програмні засоби, що дозволяють організувати управління та моніторинг роботою процесів у Вашому мобільному телефоні. Коротко опишіть їх.  
You bet! The Samsung Galaxy S21 FE lets you load up third-party tools for next-level process control. Check these out:  

- **3C Task Manager**: a beast for tracking and managing processes, tweaking auto-starts, and checking battery stats.  
- **System Monitor**: lightweight and simple—watch CPU, RAM, and storage usage, plus set alerts.  
- **Greenify**: puts resource-hungry apps to sleep, boosting battery life and performance.  
- **Termux**: your portable Linux terminal—run commands, monitor processes, and geek out with full control.  

---
   
## 🏁 **Висновки**

Through this work, I’ve learned how to effectively monitor and manage processes in Linux using commands like `top`, `ps`, which helped me understand system performance and troubleshoot issues. I also gained skills in controlling processes stopping, resuming, or running them in the background making me more confident in handling Linux systems.
