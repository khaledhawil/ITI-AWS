# **Lab: Managing and Monitoring an Apache Web Server on AWS EC2**

## **Task 1: Checking and Starting the httpd Service**

### **Step 1: Check the Status of the httpd Service**
The `httpd` service is the Apache HTTP server running on your instance. To check its status, run:

```sh
sudo systemctl status httpd.service
```

#### **Expected Output:**
The output should indicate that the `httpd` service is **loaded** but **inactive (dead)**.

### **Step 2: Start the httpd Service**
Since the service is inactive, start it using:

```sh
sudo systemctl start httpd.service
```

### **Step 3: Verify the Service is Running**
Check again if the service is running:

```sh
sudo systemctl status httpd.service
```

#### **Expected Output:**
- The `httpd` service should now be **active (running)**.
- This confirms that Apache is successfully started.

### **Step 4: Verify Apache Web Server is Working**
Open a web browser and enter:

```
http://<public-ip>
```

Replace `<public-ip>` with the actual public IP address of your EC2 instance.

#### **Expected Output:**
- You should see the **Apache HTTP Server Test Page**.
- This means the server is working correctly.

### **Step 5: Stop the httpd Service (Optional)**
To stop the Apache server, use:

```sh
sudo systemctl stop httpd.service
```

---

## **Task 2: Monitoring a Linux EC2 Instance**

### **Step 1: Display Running Processes**
To monitor system processes and resource usage, use:

```sh
top
```

#### **Expected Output:**
- The list of currently running processes.
- CPU and memory usage statistics.
- Press **Q** to exit `top`.

### **Step 2: Simulate High CPU Load**
Run a stress script to generate high CPU usage:

```sh
./stress.sh & top
```

### **Step 3: Check CPU Usage Again**
Run `top` again to see the CPU spike:

```sh
top
```

#### **Expected Output:**
- The CPU usage should be significantly higher.
- The stress script is consuming system resources.
- The script runs for **6 minutes** before stopping.

---

## **Task 3: Monitoring EC2 Instance with AWS CloudWatch**

### **Step 1: Open AWS CloudWatch**
1. Go to the **AWS Management Console**.
2. Search for **CloudWatch** in the search bar.
3. Click on **CloudWatch**.

### **Step 2: Open EC2 Dashboard in CloudWatch**
1. On the left pane, select **Dashboard**.
2. Click **Automatic Dashboards**.
3. Select **EC2**.

#### **Expected Output:**
- The **EC2 dashboard** will show key metrics like:
  - **CPU Utilization**
  - **Disk Read/Write Operations**
  - **Network Traffic**

### **Step 3: Monitor CPU Utilization Spike**
- You should see a **spike in CPU usage** matching when the stress script ran.
- Wait **5 minutes**, and you should see the CPU usage **drop back to normal**.

#### **Note:**
- By default, CloudWatch aggregates data every **5 minutes**.
- This can be changed to a **1-second interval** for real-time updates.

---

## **Conclusion**
- You learned how to **check, start, and stop** the Apache `httpd` service.
- You used `top` to monitor system processes and **simulate high CPU usage**.
- You monitored **EC2 instance performance using AWS CloudWatch**.
- This helps in **troubleshooting, performance analysis, and resource management** on AWS.
