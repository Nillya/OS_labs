# 📚 Самостійна робота студента: Work-case 7

## 📌 Дисципліна: "Операційні системи"

## 👨‍🎓 **Виконав**
- **Нагорний І.М. РПЗ-23Б**

---

## 🎯 **Мета роботи**
1. Ознайомитися з основними функціями планувальників завдань в операційних системах.
2. Вивчити принципи роботи з планувальником `Cron` в ОС Linux та його альтернативи.
3. Налаштувати виконання запланованих завдань через `Cron` та альтернативний планувальник у віртуальній машині з ОС Linux.

---

## 🛠 **Матеріальне забезпечення**
- 💻 ЕОМ типу IBM PC.
- 📦 Віртуальна машина – VirtualBox (Oracle).
- 🐧 Операційна система GNU/Linux (Ubuntu).
- 🌐 Сайт мережевої академії Cisco netacad.com та його онлайн-курси з Linux.

---

## 📖 **Завдання для виконання**

### 🔹 **1. Теоретичні питання**

📌 **Завдання:** Дати відповіді на питання щодо планування завдань.

**1.1. Охарактеризуйте основні функції які може виконувати планувальник завдань в будь-якій ОС. Порівняйте можливості планування завдань в різних ОС на прикладі Windows та Linux.**

Task schedulers in operating systems automate the execution of tasks at specified times or events. Their main functions include:
- Scheduling tasks to run at specific times or intervals (e.g., daily, weekly).
- Triggering tasks based on system events (e.g., system startup, user login).
- Managing task execution, including logging and error handling.
- Allowing prioritization of tasks and resource allocation.

**Comparison of Windows and Linux Task Schedulers:**
- **Windows Task Scheduler**:
  - **Interface**: Graphical user interface (GUI) via Task Scheduler application, with PowerShell scripting support.
  - **Triggers**: Time-based (e.g., daily at 8 AM), event-based (e.g., system boot), or user login/logout.
  - **Actions**: Run programs, send emails, display messages.
  - **Features**: Supports conditions (e.g., run only if the system is idle), task history, and security settings (e.g., run with highest privileges).
  - **Limitations**: Less flexible for scripting compared to Linux; GUI-heavy approach.
- **Linux Cron**:
  - **Interface**: Command-line based, configured via crontab files.
  - **Triggers**: Time-based (minute, hour, day, month, weekday) with fine-grained control.
  - **Actions**: Executes shell commands or scripts.
  - **Features**: Highly scriptable, supports user-specific and system-wide schedules, lightweight, and integrates with shell environments.
  - **Limitations**: No native GUI, requires manual configuration of crontab files.

Linux’s `Cron` is more lightweight and script-friendly, while Windows Task Scheduler offers a user-friendly GUI but is less flexible for advanced automation.

**1.2. Опишіть основні принципи роботи з планувальником Cron в ОС Linux. Як його налаштовувати? Чи є йому альтернативи (дайте їх характеристику).**

**Cron Principles**:
- **Cron** is a time-based job scheduler in Linux that runs tasks (jobs) at specified intervals or times.
- Jobs are defined in crontab (cron table) files, which specify the schedule and command to execute.
- Each user can have their own crontab, and there is a system-wide crontab (`/etc/crontab`).
- The cron daemon (`crond`) runs in the background, checking crontab files every minute to execute scheduled tasks.

**Configuring Cron**:
1. Edit a user’s crontab with `crontab -e`.
2. Add a line in the format: `* * * * * command` (representing minute, hour, day of month, month, day of week).
3. Save the file to activate the schedule.
4. Use `crontab -l` to list current jobs.

**Alternatives to Cron**:
- **Anacron**:
  - Designed for systems that are not always running (e.g., laptops).
  - Executes tasks at daily, weekly, or monthly intervals, catching up on missed jobs.
  - Configured via `/etc/anacrontab`.
  - Less precise than Cron for real-time scheduling but better for non-continuous systems.
- **Systemd Timers**:
  - A modern alternative integrated with the `systemd` init system.
  - Uses timer units (`.timer` files) for scheduling, offering more flexibility (e.g., event-based triggers).
  - Configured via systemd unit files in `/etc/systemd/system/`.
  - Provides detailed logging and dependency management.
- **at**:
  - Schedules one-time tasks (not recurring) with the `at` command.
  - Useful for single executions at a specific time (e.g., `at 8pm`).
  - Less feature-rich than Cron but simpler for one-off tasks.

---

### 🔹 **2. Планування завдань через Cron**

📌 **Завдання:** Налаштувати виконання обраних завдань через `Cron` у віртуальній машині з ОС Linux.

Вибрані задачі:
1. Запуск скрипту для створення текстового файлу о 8:00 щодня.
2. Очищення каталогу `/tmp` двічі на день (о 9:00 та 21:00).
3. Резервне копіювання файлу `backup.txt` у будні з 8:00 до 18:00 щогодини.
4. Архівування файлів раз на рік, раз на місяць, раз на день, щогодини, та при завантаженні системи.

#### **Налаштування Cron**

1. **Запуск скрипту о 8:00 щодня**:
   - Створити скрипт `create_file.sh`:
     ```bash
     echo '#!/bin/bash' > create_file.sh
     echo 'echo "Task executed at $(date)" > /home/user/task_log.txt' >> create_file.sh
     chmod +x create_file.sh
     ```
     ![](https://i.ibb.co/1Y1nyZBn/image.png)

   - Додати до crontab:
     ```bash
     crontab -e
     0 8 * * * /home/user/create_file.sh
     ```
     ![](https://i.ibb.co/KcDKmXSb/image.png)

2. **Очищення /tmp двічі на день (9:00 та 21:00)**:
   - Додати до crontab:
     ```bash
     crontab -e
     0 9,21 * * * rm -rf /tmp/*
     ```
     ![](https://i.ibb.co/4R2tsG8G/vmware-yu0b-Qmdn-MQ.png)

3. **Резервне копіювання у будні щогодини (8:00–18:00)**:
   - Створити скрипт `backup.sh`:
     ```bash
     echo '#!/bin/bash' > backup.sh
     echo 'cp /home/user/backup.txt /home/user/backup_$(date +\%F_\%H\%M).txt' >> backup.sh
     chmod +x backup.sh
     ```
     ![](https://i.ibb.co/4DdF3jD/image.png)

   - Додати до crontab:
     ```bash
     crontab -e
     0 8-18 * * 1-5 /home/user/backup.sh
     ```
     ![](https://i.ibb.co/KcGbShWk/image.png)

4. **Архівування файлів (раз на рік, місяць, день, годину, при завантаженні)**:
   - Створити скрипт `archive.sh`:
     ```bash
     echo '#!/bin/bash' > archive.sh
     echo 'tar -czf /home/user/archive_$(date +\%F_\%H\%M).tar.gz /home/user/data' >> archive.sh
     chmod +x archive.sh
     ```
     ![](https://i.ibb.co/WpGps4Bw/image.png)

   - Додати до crontab:
     ```bash
     crontab -e
     0 0 1 1 * /home/user/archive.sh  # Yearly (Jan 1, 00:00)
     0 0 1 * * /home/user/archive.sh  # Monthly (1st day, 00:00)
     0 0 * * * /home/user/archive.sh  # Daily (00:00)
     0 * * * * /home/user/archive.sh  # Hourly
     @reboot /home/user/archive.sh    # On reboot
     ```
     ![](https://i.ibb.co/fYZ3xj4z/vmware-j-XZff1-Rqz-W.png)

---

### 🔹 **3. Альтернативний планувальник (Anacron)**

📌 **Завдання:** Встановити альтернативний планувальник (`Anacron`) і повторити задачі з пункту 2.

Anacron – це планувальник, який ідеально підходить для систем, що не завжди включені, і запускає задачі з періодичністю в днях, тижнях або місяцях, компенсуючи пропущені запускі. Він конфігурується через `/etc/anacrontab`.

1. **Запуск скрипту о 8:00 щодня**:
   - Додача до `/etc/anacrontab`:
     ```
     1   5   daily-create   /home/user/create_file.sh
     ```

2. **Очищення /tmp двічі на день (9:00 та 21:00)**:
   - Додача до `/etc/anacrontab`:
     ```
     1   5   clean-tmp-morning   /bin/rm -rf /tmp/*
     1   15  clean-tmp-evening  /bin/rm -rf /tmp/*
     ```

3. **Резервне копіювання у будні щогодини (8:00–18:00)**:
   - Зміна `backup.sh`:
     ```bash
     echo '#!/bin/bash' > backup.sh
     echo 'if [ "$(date +\%u)" -le 5 ] && [ "$(date +\%H)" -ge 8 ] && [ "$(date +\%H)" -le 18 ]; then cp /home/user/backup.txt /home/user/backup_$(date +\%F_\%H\%M).txt; fi' >> backup.sh
     chmod +x backup.sh
     ```
   - Додача до `/etc/anacrontab`:
     ```
     1   5   daily-backup   /home/user/backup.sh
     ```
     ![](https://i.ibb.co/cK98KKn0/image.png)
4. **Архівування файлів (раз на рік, місяць, день, годину, при завантаженні)**:
   - Зміни `archive.sh`:
     ```bash
     echo '#!/bin/bash' > archive.sh
     echo 'DAY=$(date +\%d); MONTH=$(date +\%m); YEAR=$(date +\%Y); HOUR=$(date +\%H)' >> archive.sh
     echo 'if [ "$DAY" = "01" ] && [ "$MONTH" = "01" ] && [ "$HOUR" = "00" ]; then tar -czf /home/user/archive_$YEAR-01-01.tar.gz /home/user/data; fi' >> archive.sh
     echo 'if [ "$DAY" = "01" ] && [ "$HOUR" = "00" ]; then tar -czf /home/user/archive_$(date +\%F).tar.gz /home/user/data; fi' >> archive.sh
     echo 'if [ "$HOUR" = "00" ]; then tar -czf /home/user/archive_$(date +\%F).tar.gz /home/user/data; fi' >> archive.sh
     echo 'tar -czf /home/user/archive_$(date +\%F_\%H\%M).tar.gz /home/user/data' >> archive.sh
     chmod +x archive.sh
     ```
   - Додача до `/etc/anacrontab`:
     ```
     1   5   daily-archive   /home/user/archive.sh
     @monthly  5   monthly-archive   /home/user/archive.sh
     @yearly  5   yearly-archive    /home/user/archive.sh
     ```
   - Для запуску при завантаженні `/etc/rc.local`:
     ```
     /home/user/archive.sh &
     exit 0
     ```

---

## 🏁 **Висновки**
У ході самостійної роботи я вивчив основи планування завдань в операційних системах, порівняв можливості `Cron` і Windows Task Scheduler, а також ознайомився з альтернативними планувальниками, такими як `Anacron`. Практичні завдання з налаштування `Cron` і `Anacron` дозволили мені автоматизувати задачі, такі як створення файлів, очищення каталогів, резервне копіювання та архівування, з різними розкладами. Робота з Anacron показала його переваги для систем з нерегулярним запуском, але з обмеженнями для погодинних задач, які вимагали додаткових умов у скриптах.