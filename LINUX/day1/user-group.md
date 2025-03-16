# Managing Users and Groups

## Task 1: Connect to an Amazon Linux EC2 Instance via SSH


## Task 2: Create Users
### User List
| First Name | Last Name | User ID | Job Role | Starting Password | Group |
|------------|-----------|---------|----------|-------------------|-------|
| Alejandro  | Rosalez   | arosalez| Sales Manager | P@ssword1234!    | Sales, Managers |
| Efua       | Owusu     | eowusu  | Shipping    | P@ssword1234!    | Shipping |
| Jane       | Doe       | jdoe    | Shipping    | P@ssword1234!    | Shipping |
| Li         | Juan      | ljuan   | HR Manager  | P@ssword1234!    | HR, Managers |
| Mary       | Major     | mmajor  | Finance Manager | P@ssword1234! | Finance, Managers |
| Mateo      | Jackson   | mjackson| CEO         | P@ssword1234!    | CEO |
| Nikki      | Wolf      | nwolf   | Sales Representative | P@ssword1234! | Sales |
| Paulo      | Santos    | psantos | Shipping    | P@ssword1234!    | Shipping |
| Sofia      | Martinez  | smartinez| HR Specialist | P@ssword1234!  | HR |
| Saanvi     | Sarkar    | ssarkar | Finance Specialist | P@ssword1234! | Finance |

# create the users 
```bash
sudo useradd arosalez 
sudo useradd eowusu
sudo useradd jdoe
sudo useradd ljuan
sudo useradd mmajor
sudo useradd mjackson
sudo useradd nwolf
sudo useradd psantos
sudo useradd smartinez
sudo useradd ssarkar
```
# set passwords for the users
```bash
sudo passwd arosalez
sudo passwd eowusu
sudo passwd jdoe
sudo passwd ljuan
sudo passwd mmajor
sudo passwd mjackson
sudo passwd nwolf
sudo passwd psantos
sudo passwd smartinez
P@ssword1234!
```
### Steps to Add Users
1. Validate current directory:
   ```sh
   pwd
   ```
2. Add a new user:
   ```sh
   sudo useradd <User ID>
   ```
3. Set a password:
   ```sh
   sudo passwd <User ID>
   ```
4. Verify users:
   ```sh
   sudo cat /etc/passwd | cut -d: -f1
   ```
### Create Groups
1. Create a new group:
   ```sh
   sudo groupadd Sales
   sudo groupadd HR
   sudo groupadd Finance
   sudo groupadd Shipping
   sudo groupadd Managers
   sudo groupadd CEO
   sudo groupadd Personnel
   ```
2. Verify groups:
   ```sh
   cat /etc/group
   ```

### Assign Users to Groups
1. Assign a user to a group:
   ```sh
   sudo usermod -a -G Sales arosalez
   sudo usermod -a -G Sales nwolf
   sudo usermod -a -G HR ljuan
   sudo usermod -a -G HR smartinez
   sudo usermod -a -G Finance mmajor
   sudo usermod -a -G Finance ssarkar
   sudo usermod -a -G Shipping eowusu
   sudo usermod -a -G Shipping jdoe
   sudo usermod -a -G Shipping psantos
   sudo usermod -a -G Managers arosalez
   sudo usermod -a -G Managers ljuan
   sudo usermod -a -G Managers mmajor
   sudo usermod -a -G CEO mjackson
   ```
2. Verify user groups:
   ```sh
   cat /etc/group
   ```
### Create Groups
1. Create a new group:
   ```sh
   sudo groupadd <Group Name>
   ```
2. Verify groups:
   ```sh
   cat /etc/group
   ```

### Assign Users to Groups
1. Assign a user to a group:
   ```sh
   sudo usermod -a -G <Group Name> <User ID>
   ```
Example Assignments:
   ```sh
   sudo usermod -a -G Sales arosalez
   sudo usermod -a -G HR ljuan
   sudo usermod -a -G Finance mmajor
   sudo usermod -a -G Shipping eowusu
   sudo usermod -a -G Managers arosalez
   sudo usermod -a -G CEO mjackson
   ```
2. Verify user groups:
   ```sh
   cat /etc/group
   ```

## Task 4: Log in Using New Users
1. Switch to a new user:
   ```sh
   su <User ID>
   ```
   Enter password: P@ssword1234!
2. Check current directory:
   ```sh
   pwd
   ```
3. Try creating a file:
   ```sh
   touch myFile.txt
   ```
   Error: "Permission denied" (user lacks write access).
4. Try using sudo:
   ```sh
   sudo touch myFile.txt
   ```
   Error: "User is not in the sudoers file."
5. Exit to the previous user:
   ```sh
   exit
   ```
6. Check sudo logs:
   ```sh
   sudo cat /var/log/secure
   ```
   Displays failed sudo attempts.