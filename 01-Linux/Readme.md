## Assessment Questions and Answers

### 1. Provide steps to create a directory inside a directory where the parent directory does not exist.

 **Ans**:
```
mkdir -p /path/to/nonexistent/parent/directory
```
This above command will create all the necessary parent directories if they don't already exist.

### 2. How to install a package on a Linux server when there is no internet connection?

**Ans**:
If you have the package file (e.g., a .deb file for Debian-based systems or a .rpm file for Red Hat-based systems), you can use the following commands:

For Debian-based systems:
```
sudo dpkg -i /path/to/package.deb
sudo apt-get install -f
```

For Red Hat-based systems:
```
sudo rpm -i /path/to/package.rpm
sudo yum install -y /path/to/package.rpm
```
These commands install the required Linux package and resolve dependencies.


### 3. How to access specific folders of Server A from Server B and Server C?

**Ans**: I an not tried these situation


### 4. How to check all the running processes from a server?

**Ans**: 
To check all the running processes from a server, we can use the following command:
```
ps aux
```

**Output**:
<img width="702" alt="Screenshot 2023-11-13 at 11 41 15 PM" src="https://github.com/YashPimple/DevOps-Internship-Assesment/assets/97302447/7bd542a9-4c19-4cfc-bc89-1e84c3e26dcc">


### 5. Provide the command to delete all the files older than X days inside a specific directory.

**Ans**:
To delete files older than 7 days in a specific directory:

```bash
find /path/to/directory -type f -mtime +7 -exec rm {} \;
```
This command finds files (-type f) in the specified directory that are older than 7 days (-mtime +7) and deletes them.



### 6. Create a shell script to identify the process ID
a. script should as a user input for process ID
b. If the process exists script should print the process ID and exit 
c. If the process doesn't exist script should print the process doesn't exist and asks for another input

**Ans**:
```bash
#!/bin/bash

read -p "Enter process ID: " pid

if ps -p "$pid" > /dev/null; then
    echo "Process ID $pid exists."
else
    echo "Process ID $pid does not exist."
fi
```
