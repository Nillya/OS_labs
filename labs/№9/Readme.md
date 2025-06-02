# ЛАБОРАТОРНА РОБОТА №9

## 📚 Дисципліна: "Операційні системи"

## 🎯 **Тема**
> Захист системи та користувачів у Linux. Створення користувачів та груп

## 👨‍🎓 **Виконав**
- **Нагорний І.М. РПЗ-23Б**

---

## 🚀 **Мета роботи**
1. Отримання практичних навиків роботи з командною оболонкою Bash. 🛠️  
2. Знайомство з базовими діями при створенні нових користувачів та нових груп користувачів. 📊  

## 🛠 **Material Requirements**
- 💻 IBM PC-type computer  
- 📦 Virtual machine – VirtualBox (Oracle)  
- 🐧 GNU/Linux operating system (Ubuntu)  
- 🌐 Cisco Networking Academy website (netacad.com) and its Linux online courses  

---

## 📖 **Завдання для попередньої підготовки**

### 🔹 **1. Dictionary of Basic English Terms**
After reviewing the theoretical material for the lab, I compiled a dictionary of key English terms related to command purposes and their parameters:

| **Term in English** | **Термін українською** |
|:--------------------|:-----------------------|
| requires            | вимагає                |
| allows              | дозволяє               |
| perform             | виконувати             |
| separated           | розділені              |
| primary             | первинний              |
| supplemental        | додатковий             |
| switching           | перемикання            |
| distributions       | розподіли              |
| collaborate         | співпрацювати          |
| access              | доступ                 |

---

### 🔹 **2(4). Answers to Theoretical Questions**

📌 **Завдання:** Дати відповіді на питання з підготовки до лабораторної роботи.

**4.1. Розкрийте поняття UPG, коли їх доцільно використовувати?**  
UPG (User Private Group) is a concept in Unix/Linux systems where each user is automatically assigned a unique group with the same name as the user, serving as their primary group. It simplifies file access management by allowing users to have a private group, making it easier to control permissions without complex group structures. UPGs are appropriate when you need to ensure isolated access for individual users or simplify permission settings.

**4.2. Якими командами можна створити групи користувачів? Наведіть приклади**  
User groups can be created using the `groupadd` command. Example:  
```bash
sudo groupadd developers
```
This creates a new group named "developers."

**4.3. Якими командами можна змінити налаштування груп користувачів? Наведіть приклади**  
Group settings can be modified with the `groupmod` command. Examples:  
- To rename a group:  
  ```bash
  sudo groupmod –n newname oldname
  ```
- To change the group ID (GID):  
  ```bash
  sudo groupmod –g 1001 developers
  ```

---

## 🎬 **Хід роботи**

### 🎥 **1(2). Command Table**
📌 **Завдання:** Process all command examples from NDG Linux Essentials Labs 15 ("System and User Security") and 16 ("Creating Users and Groups") and create a descriptive table.

| **Command Name**       | **Purpose and Functionality** 🎯                  |
|-------------------------|--------------------------------------------------|
| `su`                   | Switches to another user (e.g., root) and starts a new shell session. |
| `sudo`                 | Executes a single command with root privileges.   |
| `exit`                 | Logs out of the current user session (e.g., root).|
| `head /etc/passwd`     | Displays the first lines of the `/etc/passwd` file, showing user account details. |
| `getent passwd username`| Retrieves account information for a specified user.|
| `w`                    | Shows detailed info about currently logged-in users.|
| `last`                 | Displays login and reboot history from `/var/log/wtmp`. |
| `groupadd`             | Creates a new user group.                         |
| `groupmod`             | Modifies group settings (e.g., name or GID).      |
| `useradd`              | Creates a new user account.                       |
| `passwd`               | Sets or changes a user’s password.                |
| `usermod`              | Modifies user account settings (e.g., group membership). |
| `groupdel`             | Deletes a group if it’s not a primary group for any user. |
| `getent group groupname`| Retrieves information about a specified group.    |
| `userdel`              | Deletes a user account.                           |

---

### 🔹 **2(3). Practical Tasks in the Terminal**

📌 **Завдання:** Perform the following practical tasks in the terminal (screenshots would be provided if performed live).

#### **Display Information About the Current User**
- Using different methods:  
  - `id`: Shows UID, GID, and group memberships.  
  - `whoami`: Displays the current username.  
  - `grep "^$(whoami):" /etc/passwd`: Extracts the user’s line from `/etc/passwd`.

#### **Practice Commands `last`, `w`, and `who`**
- `last`: Displays login history.  
- `w`: Shows current users and their activities.  
- `who`: Lists currently logged-in users.  
**Comparison:**  
- `last` provides historical login data, missing current activity details.  
- `w` includes current user activity (e.g., processes), missing historical data.  
- `who` lists current users but lacks activity or historical details.

#### **Create Three New User Groups**
- Commands:  
  ```bash
  sudo groupadd super_admins
  sudo groupadd noob_users
  sudo groupadd good_students
  ```
- Check their identifiers (GIDs):  
  ```bash
  grep "super_admins" /etc/group
  grep "noob_users" /etc/group
  grep "good_students" /etc/group
  ```
  Output shows group names and GIDs (e.g., `super_admins:x:1001:`).
  ![](https://ibb.co/Z6m8kwH5)

#### **Create Three New Users**
- Commands (assuming working alone):  
  ```bash
  sudo useradd user1
  sudo passwd user1
  sudo useradd user2
  sudo passwd user2
  sudo useradd user3
  sudo passwd user3
  ```
  Each user is assigned a password immediately after creation.

#### **Add Users to Groups**
- Distribution:  
  - `super_admins`: user1, user2  
  - `noob_users`: user1, user3  
  - `good_students`: user1, user2, user3  
- Commands:  
  ```bash
  sudo usermod –aG super_admins user1
  sudo usermod –aG noob_users user1
  sudo usermod –aG super_admins user2
  sudo usermod –aG noob_users user3
  sudo usermod –aG good_students user1
  sudo usermod –aG good_students user2
  sudo usermod –aG good_students user3
  ```

#### **View Group Information**
- Commands:  
  ```bash
  grep "super_admins" /etc/group
  grep "noob_users" /etc/group
  grep "good_students" /etc/group
  ```
- Explanation: The output shows group names, GIDs, and member lists (e.g., `super_admins:x:1001:user1,user2`).

#### **Delete Users and Check Groups**
- Delete each user and verify:  
  - `sudo userdel user1` → Check with `grep` commands (user1 removed from groups).  
  - `sudo userdel user2` → Check again (user2 removed).  
  - `sudo userdel user3` → Check again (user3 removed).  

#### **View Existing Groups**
- Command:  
  ```bash
  cat /etc/group
  ```
  Displays all groups and their members (created groups remain, now empty).

#### **Delete Created Groups**
- Commands:  
  ```bash
  sudo groupdel super_admins
  sudo groupdel noob_users
  sudo groupdel good_students
  ```

#### **Verify Group Deletion**
- Command:  
  ```bash
  cat /etc/group
  ```
  The deleted groups no longer appear in the list.

---

## ✏️ **Контрольні запитання**

1. **Чому в конфігураційних файлах паролі не зберігається в явному вигляді?**  
   Passwords are stored as hashes (not plain text) for security. If someone accesses the file, they cannot directly see the passwords, reducing the risk of unauthorized access.

2. **Чому не рекомендується виконувати повсякденні операції, використовуючи обліковий запис root?**  
   The root account has unrestricted system access. Everyday use risks accidental damage (e.g., deleting critical files) or security breaches if exploited by malware.

3. **У чому відмінність механізмів отримання особливих привілеїв su і sudo?**  
   - `su`: Switches to another user (e.g., root) for the entire session, requiring the target user’s password.  
   - `sudo`: Runs a single command with elevated privileges, requiring the user’s own password and configured permissions.

4. **Чому домашній каталог користувача root не розміщено в каталозі /home?**  
   The root home directory is in `/root` (not `/home`) to ensure availability even if `/home` is unmounted and to isolate root files from regular users for security.

5. **Для чого використовується команда getent?**  
   The `getent` command retrieves entries from NSS databases (e.g., users from `/etc/passwd`, groups from `/etc/group`).

6. **Як можна змінити пароль користувача?**  
   Use:  
   ```bash
   sudo passwd username
   ```
   Prompts for a new password for the specified user.

7. **Яким чином можна видалити існуючі групи користувачів? Чи залишиться інформація про них десь у системі?**  
   Use `groupdel groupname` (e.g., `sudo groupdel super_admins`). Group info is removed from `/etc/group`, but file permissions referencing the GID may remain as numbers.

8. **Яке призначення команди chage?**  
   The `chage` command manages password aging policies (e.g., expiration dates) for users.

9. **Які параметри команди usermod ви вважаєте найбільш використовуваними?**  
   - `-aG`: Adds a user to supplementary groups.  
   - `-s`: Changes the login shell.  
   - `-d`: Updates the home directory.

---

## 🏁 **Висновки**

During this lab, I acquired practical skills in using the Bash shell on Linux. I learned to create and manage users and groups, assign users to groups, and handle passwords securely. I also explored the differences between `su` and `sudo`, the significance of root account restrictions, and commands like `getent` and `chage`. This work enhanced my understanding of Linux user and group management, critical for system administration and security.
