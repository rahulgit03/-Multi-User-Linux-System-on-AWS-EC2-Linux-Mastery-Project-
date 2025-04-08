# -Multi-User-Linux-System-on-AWS-EC2-Linux-Mastery-Project-



## 🔥 Why This Mini-Project?
Earlier, I forgot to stop my EC2 instance at night and wasted AWS resources 😅. That made me realize: **"Let’s build cool mini projects daily to become Linux masters and stay within free tier!"**

This one is 🔥 — we simulate a real Linux server with **multiple users**, **groups**, and **shared access**. This is how real servers work in companies!

---

## 🎯 Project Goal:
- Create multiple users on an EC2 Linux instance
- Create a group and add users to it
- Share a folder among the group with proper read/write permissions
- Understand `chmod`, `chown`, `usermod`, and group access in real-time

---

## 🛠️ Step-by-Step Implementation:

### ✅ Step 1: Create Users
```bash
sudo adduser rahulbro
sudo adduser devfriend
```

### ✅ Step 2: Create a Group
```bash
sudo groupadd cloudteam
```

### ✅ Step 3: Add Users to Group
```bash
sudo usermod -aG cloudteam rahulbro
sudo usermod -aG cloudteam devfriend
```

### ✅ Step 4: Create Shared Folder
```bash
sudo mkdir /opt/sharedfolder
sudo chown :cloudteam /opt/sharedfolder
sudo chmod 770 /opt/sharedfolder
```

### ✅ Step 5: Test Access
Switch to each user and check if both can create and see files inside the shared folder:
```bash
sudo su - rahulbro
cd /opt/sharedfolder
touch rahul.txt

exit

sudo su - devfriend
cd /opt/sharedfolder
ls -l
cat rahul.txt
```

🚀 SUCCESS: Both users from same group can read/write in the shared folder!

---

## 🧠 Key Linux Concepts Learned:
| Command | Meaning |
|--------|---------|
| `adduser` | Create new users |
| `groupadd` | Create user groups |
| `usermod -aG` | Add user to a group |
| `chown` | Change file/folder ownership |
| `chmod` | Change file/folder permissions |

---

## 💻 Real-World Use Case:
This is how **teams inside companies** get access to shared directories like project folders, logs, configs, etc. This project mirrors exactly how you’d do it in a real production environment!

---



