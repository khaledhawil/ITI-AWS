# Task 2: Create a Folder Structure

## Steps to Create the Folder Structure

1. Navigate to the home directory:
   ```sh
   cd /home/ec2-user
   ```
2. Create the main directory:
   ```sh
   mkdir CompanyA
   ```
3. Move into the `CompanyA` directory:
   ```sh
   cd CompanyA
   ```
4. Create subdirectories:
   ```sh
   mkdir Finance HR Management
   ```
5. Verify the directories:
   ```sh
   ls
   ```

### Creating Files in Each Folder

6. Move into the `HR` folder and create files:
   ```sh
   cd HR
   touch Assessments.csv TrialPeriod.csv
   ls
   ```
7. Move to `Finance` and create files:
   ```sh
   cd ../Finance
   touch Salary.csv ProfitAndLossStatements.csv
   ls
   ```
8. Move to `CompanyA` and create `Management` files:
   ```sh
   cd ..
   touch Management/Managers.csv Management/Schedule.csv
   ls Management
   ```
9. Verify all files and folders:
   ```sh
   ls -laR
   ```

# Task 3: Delete and Reorganize Folders

## Steps to Reorganize the Folder Structure

1. Ensure you are in the `CompanyA` directory:
   ```sh
   pwd
   ```
2. Copy the `Finance` folder into `HR`:
   ```sh
   cp -r Finance HR
   ```
3. Verify the copy:
   ```sh
   ls HR/Finance
   ```
4. Remove the original `Finance` folder:
   ```sh
   rm -r Finance
   ```
5. Move `Management` into `HR`:
   ```sh
   mv Management HR
   ```
6. Verify the move:
   ```sh
   ls HR/Management
   ```
7. Navigate into `HR`:
   ```sh
   cd HR
   ```
8. Create `Employees` folder:
   ```sh
   mkdir Employees
   ```
9. Move `Assessments.csv` and `TrialPeriod.csv` into `Employees`:
   ```sh
   mv Assessments.csv TrialPeriod.csv Employees
   ```
10. Verify the move:
    ```sh
    ls Employees
    ```

