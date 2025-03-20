# Creating an Alias for Backup and Updating the PATH Variable

## Task 1: Creating an Alias for Backup

### Step 1: Understanding the Alias Concept
An alias is a shortcut for a command or series of commands in Linux. In this task, we will create an alias named `backup` to simplify the process of archiving files using the `tar` command.

### Step 2: Creating the Backup Alias
The `tar` command is used to create archive files. The flags used are:
- `-c`: Create a new archive.
- `-v`: Verbose mode (lists the files being archived).
- `-z`: Compress using gzip.
- `-f`: Specify the archive file name.

To create the alias, use the following command:
```bash
alias backup='tar -cvzf '
```

### Step 3: Using the Backup Alias
To use the alias and back up a directory, run:
```bash
backup backup_companyA.tar.gz CompanyA
```
This command will create a compressed archive `backup_companyA.tar.gz` containing all files and subdirectories from the `CompanyA` directory.

### Step 4: Verifying the Backup
List the files in the current directory to ensure the archive was created:
```bash
ls
```
Expected output:
```bash
backup_companyA.tar.gz  CompanyA
```

---

## Task 2: Updating the PATH Environment Variable

### Step 1: Navigate to the bin Directory
Change to the `bin` directory inside `CompanyA`:
```bash
cd /home/ec2-user/CompanyA/bin
```

### Step 2: Execute the `hello.sh` Script
Run the script using:
```bash
./hello.sh
```
Expected output:
```bash
hello ec2-user
```

### Step 3: Try Running the Script from the Parent Directory
Navigate back to `CompanyA`:
```bash
cd ..
```
Run the script using:
```bash
./bin/hello.sh
```
Expected output:
```bash
hello ec2-user
```

### Step 4: Attempt to Run the Script Without Specifying the Path
Run:
```bash
hello.sh
```
Expected error:
```bash
bash: hello.sh: command not found
```
This happens because the `bin` directory is not included in the system's `PATH` variable.

### Step 5: Display the Current PATH Variable
```bash
echo $PATH
```
Expected output:
```bash
/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/home/ec2-user/.local/bin:/home/ec2-user/bin
```
The `/home/ec2-user/CompanyA/bin` directory is missing.

### Step 6: Add `CompanyA/bin` to the PATH
```bash
PATH=$PATH:/home/ec2-user/CompanyA/bin
```

### Step 7: Verify the Change
Run the script again using:
```bash
hello.sh
```
Expected output:
```bash
hello ec2-user
```
Now, the script runs successfully because the system can find it in the updated `PATH` variable.

### Conclusion
- We created an alias `backup` to simplify the backup process.
- We updated the `PATH` variable to include the `bin` directory, making scripts in that directory executable from anywhere.

This improves efficiency when working with scripts and backups in Linux.

