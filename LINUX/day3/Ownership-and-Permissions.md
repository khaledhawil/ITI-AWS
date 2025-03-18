# Changing File and Folder Ownership and Permissions

## Task 1: Change Ownership

### Change Ownership of CompanyA Folder
To change ownership of the `companyA` folder to the CEO `mjackson` and group ownership to `Personnel`, use:
```bash
sudo chown -R mjackson:Personnel /home/ec2-user/companyA
```

### Change Ownership of HR Folder
To change ownership of the `HR` folder to the HR manager `ctee` and group ownership to `HR`, use:
```bash
sudo chown -R ctee:HR HR
```

### Change Ownership of Finance Folder
To change ownership of the `Finance` folder to the finance manager `mmajor` and group ownership to `Finance`, use:
```bash
sudo chown -R mmajor:Finance HR/Finance
```

### Validate Ownership Changes
To verify changes, run:
```bash
ls -laR
```

---

## Task 2: Change Permission Modes

### Create and Modify a File Using Symbolic Mode
1. Create a file named `symbolic_mode_file` using Vim:
    ```bash
    sudo vi symbolic_mode_file
    ```
2. Save and close the file (`ESC`, then `:wq` and `Enter`).
3. Grant group write permission:
    ```bash
    sudo chmod g+w symbolic_mode_file
    ```

### Create and Modify a File Using Absolute Mode
1. Create a file named `absolute_mode_file`:
    ```bash
    sudo vi absolute_mode_file
    ```
2. Save and close the file (`ESC`, then `:wq` and `Enter`).
3. Assign permission `764` (user: read/write/execute, group: read/write, others: read):
    ```bash
    sudo chmod 764 absolute_mode_file
    ```
4. Validate permissions:
    ```bash
    ls -l
    ```

---

## Task 3: Assign Permissions

### Change Ownership of Shipping Folder
To change the ownership of the `Shipping` folder to `eowusu` and group ownership to `Shipping`:
```bash
sudo chown -R eowusu:Shipping Shipping
```

### Change Ownership of Sales Folder
To change the ownership of the `Sales` folder to `nwolf` and group ownership to `Sales`:
```bash
sudo chown -R nwolf:Sales Sales
```

### Validate Changes
To verify the changes:
```bash
ls -laR Shipping
ls -laR Sales
```

