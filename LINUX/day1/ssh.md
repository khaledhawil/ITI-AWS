ssh username@server_ip
✍ Here’s the Markdown Content for ssh_guide.md:
md
￼Copy code
# 🔐 How to Connect to a Server via SSH  

SSH (Secure Shell) allows you to securely connect to a remote server. Follow these simple steps:  

## 1️⃣ Check if SSH is Installed  
To check if SSH is installed, run:  
```bash
ssh -V
```
If it's not installed, install it using:

```bash
sudo apt install openssh-client  # For Ubuntu/Debian
sudo yum install openssh-clients  # For CentOS/RHEL
sudo brew install openssh  # For macOS
```

## 2️⃣ Connect to a Remote Server
To connect, use:

```bash
ssh username@server_ip
```
Example:

```bash
ssh ec2-user@18.234.56.78
```
If it's your first time connecting, type `yes` when prompted.

## 3️⃣ Using an SSH Key (For AWS EC2)
If your server requires a private key (.pem file), use:

```bash
ssh -i path/to/your-key.pem username@server_ip
```
Example:

```bash
ssh -i path/to/my-key.pem ec2-user@18.234.56.78
```
Ensure the key has correct permissions:

```bash
chmod 400 path/to/your-key.pem
```
Note: Replace `username` with your actual username and `server_ip` with your actual server IP address.