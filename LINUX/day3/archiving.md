# Backup and Logging Tasks

## Task 1: Verify Folder Structure
1. Navigate to the working directory:
   ```bash
   pwd
   ```
   **Expected Output:** `/home/ec2-user`

2. Verify the `CompanyA` folder exists and check its structure:
   ```bash
   ls -R CompanyA
   ```

## Task 2: Create a Backup
1. Create a compressed backup of the `CompanyA` directory:
   ```bash
   tar -csvpzf backup.CompanyA.tar.gz CompanyA
   ```

2. Verify the backup file was created:
   ```bash
   ls
   ```
   **Expected Output:** `backup.CompanyA.tar.gz  CompanyA`

## Task 3: Log the Backup
1. Navigate to the `CompanyA` directory:
   ```bash
   cd /home/ec2-user/CompanyA
   ```

2. Create an empty log file:
   ```bash
   touch SharedFolders/backups.csv
   ```

3. Log the backup information:
   ```bash
   echo "$(date '+%d %b %Y, %H:%M'), backup.CompanyA.tar.gz" | sudo tee SharedFolders/backups.csv
   ```

4. Verify the log entry:
   ```bash
   cat SharedFolders/backups.csv
   ```

## Task 4: Move the Backup File
1. Ensure you are in the `CompanyA` directory:
   ```bash
   pwd
   ```
   **Expected Output:** `/home/ec2-user/CompanyA`

2. Move the backup file to the `IA` folder:
   ```bash
   mv ../backup.CompanyA.tar.gz IA/
   ```

3. Verify the backup file was moved:
   ```bash
   ls . IA
   ```
   **Expected Output:**
   ```
   Employees  Finance  HR  IA  Management  SharedFolders
   IA:
   backup.CompanyA.tar.gz
   ```

