# ЛАБОРАТОРНА РОБОТА №5

## 📌 Дисципліна: "Операційні системи"

## 🏷 **Тема:**
> Знайомство з командами навігації по файловій системі та керування файлами та каталогами

## 👨‍🎓 **Виконав:**
- **Нагорний І.М. РПЗ-23Б**

---

## 🎯 **Мета роботи**
1. Отримання практичних навиків роботи з командною оболонкою Bash.
2. Знайомство з базовими командами навігації по файловій системі.
3. Знайомство з базовими командами для керування файлами та каталогами


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
|Configuration       |Конфігурація        |
|Represent           |Представляти        |
|Destination         |Місце призначення   |
|Interactive         |Інтерактивний       |
|Store               |Зберігати           |
|Data                |Інформація          |
|Directories         |Каталоги            |
|Hierarchy           |Ієрархія            |
|Filesystem          |Файлова система     |
|Multiple            |Множинний           |



### 🔹 **2. Теоретичні питання**

📌 Завдання – Дайте відповіді на наступні питання:

**1️⃣ Порівняйте файлові структури Windows-подібної та Linux-подібної системи.**

- Windows file names can contain up to 255 characters and can include spaces and special characters. In Linux, file names are case-sensitive, can contain up to 255 characters, and cannot contain spaces.

- Windows assigns a drive letter (C:, D:, etc.) to each storage device, whereas Linux treats all devices as part of the file system hierarchy.

- In Windows, file extensions are used to indicate the file type, such as .docx for a Microsoft Word document. In Linux, file extensions are optional, and file type is determined by the file's contents.

- Windows uses a hidden attribute to hide files from view, whereas Linux uses a dot (.) at the beginning of the file name to indicate that the file is hidden.

- In Windows, system files are typically located in the Windows directory, whereas in Linux, system files are located in specific directories, such as /bin or /etc.

- In Linux, each file has a set of permissions that determines who can read, write, or execute the file. Windows also has file permissions, but they are more limited and less granular than Linux permissions.

**2️⃣ Розкрийте поняття FHS. Як даний стандарт використовується в контексті файлових систем?**

- FHS stands for the Filesystem Hierarchy Standard, which is a set of guidelines that define the directory structure of Linux and other Unix-like operating systems. The FHS was created to establish a uniform file system structure across different Linux distributions and to ensure that applications and system services can find necessary files in predictable locations.

- Following the FHS guidelines ensures that applications and services can find the files and libraries they need in a consistent and predictable location. This makes it easier to manage and maintain Linux systems, and helps ensure compatibility across different Linux distributions.
  

**3️⃣ Перерахуйте основні команди для роботи з файлами та каталогами в Linux: створення, переміщення, копіювання, видалення.**

- `ls` - This command lists the files and directories in the current directory.
- `cd` - This command changes the current working directory.
- `pwd` - This command prints the current working directory.
- `mkdir` - This command creates a new directory.
- `rm` - This command removes a file or directory.

---

## 🎬 **Хід роботи**
### 🎥 **1(2). Створіть таблицю для опису цих команд:**
📌 Завдання – Опрацюйте всі приклади команд, що представлені у лабораторних роботах курсу NDG Linux Essentials-Lab 7: Navigating the Filesystem та Lab 8: Managing Files and Directories. Створіть таблицю для опису цих команд:
|Назва команди|Її призначення та функціональність|
|:------------|:---------------------------------|
|`pwd  `      |Визначає місце знаходження користувача у файловій системі, показує поточну робочу директорію (print working directory)|
| `cp /etc/hosts hosts` | Make a copy of the /etc/hosts file and place it in the current directory. Then, list the contents of the current directory before and after the copy |
| `cp –v /etc/hosts hosts` | Next, you will remove the file, then copy it again, but have the system tell you what is being done. This can be achieved using the -v or --verbose option. Enter the following commands |
| `cp –p hosts /home/sysadmin` | Enter the following commands to copy from the source directory and preserve file attributes by using the -p option |
|`cd Documents` |Команда cd здійснює перехід до каталогу, який у неї вказаний як аргумент. В даному випадку це каталог Documents|
|` echo  ~ ~sysadmin ~root ~mail ~nobody `| Use the echo command below to display some other examples of using the tilde as part of the path |
| `echo *` | Use the following echo command to display all filenames in the current directory that match the glob pattern * |
| `echo D* echo P*` | The following commands will display all the files in the current directory that start with the letter D, and the letter P |
| `echo *s` | The asterisk * can be used anywhere in the string. The following command will display all the files in your current directory that end in the letter s |
| `echo ??????` | Since each question mark matches one unknown character, typing six of them will match six-character filenames. Type the following to display the filenames that are exactly six characters long |
| `echo D????????` | Using the question mark with other characters will limit the matches. Type the following to display the file names that start with the letter D and are exactly nine characters long |
| `echo ?????*s` | Wildcards or glob characters can be combined together. The following command will display file names that are at least six characters long and end in the letter s |
| `echo [D-P]\* echo [!D-P]\*` | In these next examples, a range of characters will be specified. In the first example, the first character of the file name can be any character starting at D and ending at P. In the second example, this range of characters is negated, meaning any single character will match as long as it is not between the letters D and P |
|` cd .. `| Use a relative path to change to the directory above the current directory |
| `cd ../dict `| Use a relative path to change up one level from the current directory and then down into the dict directory |
|`ls` | To list the contents of the current directory, use the ls command |
|`ls -a` | Not all files are displayed by default. There are files, called hidden files, that are not displayed by default. To display all files, including hidden files, use the -a option to the ls command |
| `ls -R` | Sometimes you want to see not only the contents of a directory, but also the contents of the subdirectories. You can use the -R option to accomplish this |
| `ls -d` | You can use file globbing (wildcards) to limit which files or directories you see. For example, the * character can match "zero or more of any characters" in a filename. Execute the following command to display only the files that begin with the letter s in the /etc directory |
| `ls -d /etc/????` | The ? character can be used to match exactly 1 character in a file name. Execute the following command to display all of the files in the /etc directory that are exactly four characters long |
| `ls –d /etc/[abcd]*` | By using square brackets [ ] you can specify a single character to match from a set of characters. Execute the following command to display all of the files in the /etc directory that begin with the letters a, b, c or d |
| `mkdir Myetc` | Naturally, the directory must be created before files can be added to it. In this example we will use the default settings for mkdir to create the “Myetc” directory. Options are available for the mkdir command to set security, permissions and other attributes of a new directory. |
| `rm -r Myetc` | To remove a directory, use the -r option to the rm command: |
|`touch premove` | Creates an empty file called premove |
| `mv premove postmove` | This command “cuts” the premove file and “pastes” it to a file called postmove |
| `rm postmove`  | Removes postmove file |
---

### 🔹 **2(3). Запустіть термінал, та в командному рядку виконайте наступні дії для ознайомлення з роботою з процесами:**

#### 💡 Робота в в терміналі
- Визначте ваш поточний робочий каталог;
- Перейдіть до кореневого каталогу та визначте Ваш поточний робочий каталог (дві команди);
- Перегляньте вміст поточного каталогу у довгому форматі (скористайтесь відповідним ключем команди ls);
- Перейдіть до каталогу /usr/share та визначте Ваш поточний робочий каталог (дві команди).

![](https://i.ibb.co/SwYyJMH8/image.png)

- Перегляньте вміст поточного каталогу включаючи і приховані файли (hidden files)(скористайтесь відповідним ключем команди ls);

![](https://i.ibb.co/9f78H9b/image.png)

- Перейдіть до каталогу /etc;
- Перегляньте вміст даного каталогу, але щоб виводило тільки назви файлів, що починаються з літери вашого імені;
- Перегляньте вміст даного каталогу, але щоб виводило тільки файли, назви яких складаються з 6 літер;
- Перегляньте вміст даного каталогу, але щоб виводило тільки файли, назви яких закінчуються на літери ваших імен, наприклад якщо ваші імена Ivan, Anna, Maks, то вибірку робиму, щоб назви файлів закінчувались на літери [i,a,m];
- Перейдіть до домашнього каталогу поточного користувача та перегляньте його вміст у рекурсивному (зворотному до алфавітного) форматі (виконати цю дію через конвеєр команд);

![](https://i.ibb.co/Y4hM3FR1/image.png)

- В поточній директорії створити директорію з назвою вашої групи;
- Переглянути оновлений вміст домашнього каталогу поточного користувача. Скористайтесь ключем -r команди ls, яку інформацію ви отримаєте?
- Перейдіть у створену вами директорію з назвою Вашої групи та створіть у ній порожній файл lab5
- Створити в даній директорії 3 директорії з прізвищами студентів вашої команди surname1, surname2, surname3* (команда mkdir мульти аргумента, тому всі три каталоги можна створити однією командою);
- Перейдіть у перший підкаталог surname1 та створіть порожній файл з ім'ям першого студента name1;
- За допомогою команди echo "Hello, my name is Name1" > name1 внесіть у цей файл дані про студента (символ > дозволяє вивід команди echo перенаправити одразу у файл name1;
- Перегляньте вміст файлу name1 за допомогою команди cat name1 (має містити щойно введену Вами інформацію)
- Зробіть копію першого файлу name1 та перейменуйте її у файл з другим ім'ям студенту Вашої команди name2;
- Перегляньте вміст каталогу, обидва файли мають з'явитися;
- Перегляньте вміст другого файлу cat name2 (він має поки що містити повну копію вмісту файлу name1)
- Замініть зміст файлу name2, щоб він містив відповідне ім'я другого студента за допомогою команди echo"Hello, my name is Name2" > name2
- Перегляньте вміст другого файлу cat name2 (він вже має містити оновлену інформацію)
- Перемістіть файл name2 у директорію surname2;
- Зробіть копію першого файлу name1 та перейменуйте її у файл з третім ім'ям студенту Вашої команди name3;
- Перемістіть файл name3 у директорію surname3;
- Перейдіть до директорії surname3;
- Перегляньте вміст третього файлу командою cat name3 (він має містити дані про другого студента)
- Замініть зміст файлу name3, щоб він містив відповідне ім'я третього студента за допомогою команди echo "Hello, my name is Name3" > name3
- Перегляньте вміст файлу за допомогою cat name3 (він вже має містити оновлену інформацію)
- Поверніться до домашнього каталогу користувача;
- Перегляньте вміст даного каталогу, але щоб виводило тільки Ваш підкаталог з назвою групи та весь його вміст (підкаталоги surname1, surname2, surname3 та файли name1, name2, name3) до того ж файли та катлоги були відкоремлені кольорами (скористайтесь відповідним ключем -R команди ls та не забудьте використати спеціальний glob-шаблон [імя каталогу]*)

![](https://i.ibb.co/gZy0KfYY/image.png)
![](https://i.ibb.co/PzcvYPK0/image.png)

---

### 🔹 **3(5). Опишіть дії, які виконують команди для переміщення по системі каталогів:**

  - команда `cd /`

    This command changes the current working directory to the root directory of the file system. This is the top-level directory that contains all other directories and files.
  
  - команда `cd /home`

    This command changes the current working directory to the "home" directory. This is the directory where user home directories are typically located.
  
  - команда `cd ~`

    This command changes the current working directory to the current user's home directory. The tilde (~) represents the user's home directory.
  
  - команда `cd` (без аргумента)

    This command changes the current working directory to the user's home directory.
  
  - команда `cd ..`

    This command moves the current working directory up one level in the directory hierarchy.
  
  - команда `cd ../..`

    This command moves the current working directory up two levels in the directory hierarchy.
  
  - команда `cd`

    This command changes the current working directory to the user's home directory. It is equivalent to `cd ~`.
---

### ✏️ **Відповіді на контрольні питання:**

#### 1. Як можна переглянути шлях до домашньої директорії користувача за допомогою команди echo? Існує 2 способи, наведіть обидва приклади у терміналі
 ![](https://i.ibb.co/dsBddLym/image.png)
#### 2. Чи можна переглянути вміст кореневого каталогу, перебуваючи у домашньому каталозі користувача без переходу у кореневий каталог? Продемонструйте це в командному рядку.
 ![](https://i.ibb.co/9kmB8t1C/image.png)

#### 3. Яким чином в терміналі можна додати інформацію в порожній файл?

  `echo "This is some information to add to the file" > filename.txt`

#### 4. Як скопіювати та видалити існуючий каталог? Чи буде відмінність в командах, якщо каталог буде не порожній при цьому

  - `cp source_directory target_directory` to copy an empty directory
  - `cp -r source_directory target_directory` to copy a non-empty directory
  - `rmdir directory_name` to removing an empty directory
  - `rm -r directory_name` to remove a non-empty directory

#### 5. У якому з наведених нижче прикладів відбувається переміщення файлу? його перейменування? одночасно обидві дії?
  - `mv /work/tech/comp.png. /Desktop` - moving
  - `mv /work/tech/comp.png. /work/tech/my_car.png` - renaming
  - `mv /work/tech/comp.png. /Desktop/computer.png` - moving and renaming

---
   
## 🏁 **Висновки**

During the lab work, I learned the basics of working in the Bash command shell and learned how to navigate the Linux file system using the cd, pwd, ls commands. I also successfully mastered creating, copying, and moving files and directories!