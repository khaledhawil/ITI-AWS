# Linux File and Folder Ownership and Permissions Lab

## Task 1: Change Ownership

### Step 1: Navigate to the Correct Directory
First, ensure you are in the `/home/ec2-user/companyA` directory:
```sh
pwd
```
If you are not in the correct directory, navigate to it:
```sh
cd /home/ec2-user/companyA
```

### Step 2: Change Ownership of the `companyA` Folder
Change the ownership of the `companyA` folder to the CEO `mjackson` and the group ownership to `Personnel`:
```sh
sudo chown -R mjackson:Personnel /home/ec2-user/companyA
```
`-R` ensures that all files and subdirectories inside `companyA` are also updated.

### Step 3: Change Ownership of the `HR` Folder
Assign the `HR` folder ownership to the HR manager `ljuan` and the group to `HR`:
```sh
sudo chown -R ljuan:HR HR
```

### Step 4: Change Ownership of the `Finance` Folder
Assign ownership of `HR/Finance` to the finance manager `mmajor` and group `Finance`:
```sh
sudo chown -R mmajor:Finance HR/Finance
```

### Step 5: Verify Changes
To verify ownership changes recursively:
```sh
ls -laR
```
This lists all files and directories along with their ownership and permissions.

## Task 2: Change Permission Modes

### Step 1: Create a File Using `vim`
Create a file named `symbolic_mode_file` using `vim`:
```sh
sudo vi symbolic_mode_file
```
Press `i` to enter insert mode, then type any content. Save and exit by pressing `ESC`, then `:wq` and `Enter`.

### Step 2: Modify Permissions Using Symbolic Mode
Grant write permission to the group:
```sh
sudo chmod g+w symbolic_mode_file
```

### Step 3: Create Another File for Absolute Mode
Create a file named `absolute_mode_file`:
```sh
sudo vi absolute_mode_file
```
Save and exit the same way (`ESC`, then `:wq`).

### Step 4: Modify Permissions Using Absolute Mode
Set permissions to `764`:
```sh
sudo chmod 764 absolute_mode_file
```
- `7` (Owner: Read, Write, Execute)
- `6` (Group: Read, Write)
- `4` (Others: Read only)

### Step 5: Verify File Permissions
Check the permissions using:
```sh
ls -l
```

## Task 3: Assign Permissions to Folders

### Step 1: Change Ownership of the `Shipping` Folder
Assign ownership to the shipping manager `eowusu` and the group to `Shipping`:
```sh
sudo chown -R eowusu:Shipping Shipping
```

### Step 2: Change Ownership of the `Sales` Folder
Assign ownership to the sales manager `nwolf` and the group to `Sales`:
```sh
sudo chown -R nwolf:Sales Sales
```

### Step 3: Validate Changes
Check the changes for `Shipping`:
```sh
ls -laR Shipping
```
Check the changes for `Sales`:
```sh
ls -laR Sales
```

## Conclusion
In this lab, we successfully changed folder and file ownership, assigned correct user permissions, and verified our changes using `ls -l`. This exercise is crucial for managing user access in Linux environments.