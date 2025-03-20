# Linux Process Management and Cron Job Lab

## Overview
This lab consists of three main tasks:
1. Creating a log file containing a list of processes while filtering out certain entries.
2. Using the `top` command to observe system performance.
3. Creating a cron job to generate an audit file by modifying CSV file names.

---

## Task 1: Creating a List of Processes Log File

### **Step 1: Navigate to the Required Directory**
To ensure we are in the correct directory, we check the current location:
```bash
pwd
```
Expected output:
```
/home/ec2-user/companyA
```
If not in the correct directory, navigate using:
```bash
cd companyA
```

### **Step 2: Generate Process List and Filter Unwanted Entries**
We need to list all processes while excluding processes owned by `root` and those containing `[` or `]` in the COMMAND column.
```bash
sudo ps -aux | grep -v root | grep -v "\[" | grep -v "\]" | sudo tee SharedFolders/processes.csv
```
Explanation:
- `ps -aux`: Lists all running processes.
- `grep -v root`: Excludes processes owned by `root`.
- `grep -v "["` and `grep -v "]"`: Removes processes where the COMMAND contains `[` or `]`.
- `tee SharedFolders/processes.csv`: Saves the filtered output to `processes.csv`.

### **Step 3: Validate the Output**
To ensure the file is created and contains the expected output, run:
```bash
cat SharedFolders/processes.csv
```
Expected output: A list of processes without `root` or `[` and `]` in the COMMAND column.

---

## Task 2: Listing Processes Using `top`

### **Step 1: Run the `top` Command**
To view system performance and active processes, enter:
```bash
top
```
- The `top` command provides details such as:
  - Number of tasks (Running, Sleeping, Stopped, Zombie).
  - CPU usage.
  - Memory and Swap usage.

### **Step 2: Observe Running Tasks**
The second line of the `top` output shows:
```
Tasks: 93 total, 1 running, 48 sleeping, 0 stopped, 0 zombie
```
This provides insight into the system's load and active processes.

### **Step 3: Exit `top`**
To quit, press:
```bash
q
```
To check `top` version and usage information:
```bash
top -hv
```

---

## Task 3: Creating a Cron Job

### **Step 1: Open the Crontab Editor**
To create a cron job, open the crontab file:
```bash
sudo crontab -e
```

### **Step 2: Add the Cron Job Entries**
Inside the editor, press `i` to enter **insert mode** and add the following lines:
```bash
SHELL=/bin/bash
PATH=/usr/bin:/bin:/usr/local/bin
MAILTO=root
0 * * * * ls -la $(find .) | sed -e 's/..csv/#####.csv/g' > /home/ec2-user/companyA/SharedFolders/filteredAudit.csv
```
#### **Explanation:**
- `SHELL=/bin/bash`: Specifies the shell used by cron.
- `PATH=/usr/bin:/bin:/usr/local/bin`: Defines the execution path.
- `MAILTO=root`: Ensures the output of the job is sent to root.
- `0 * * * *`: Runs the job at the start of every hour.
- `ls -la $(find .) | sed -e 's/..csv/#####.csv/g' > /home/ec2-user/companyA/SharedFolders/filteredAudit.csv`:
  - Lists all files recursively.
  - Uses `sed` to replace `.csv` with `#####.csv`.
  - Saves the output to `filteredAudit.csv`.

### **Step 3: Save and Exit**
Press `ESC`, then enter:
```bash
:wq
```
This saves and exits the editor.

### **Step 4: Verify the Cron Job**
To check if the cron job was added correctly:
```bash
sudo crontab -l
```
Expected output:
```
SHELL=/bin/bash
PATH=/usr/bin:/bin:/usr/local/bin
MAILTO=root
0 * * * * ls -la $(find .) | sed -e 's/..csv/#####.csv/g' > /home/ec2-user/companyA/SharedFolders/filteredAudit.csv
```

---

## Conclusion
In this lab, we:
- Generated a log file of processes while filtering out certain entries.
- Used `top` to observe system performance.
- Created a cron job to modify CSV file names and generate an audit file.

This practice improves process monitoring, system administration, and automation skills in Linux.

