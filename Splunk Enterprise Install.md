# Setting up Splunk Enterprise

**Download Splunk Enterprise Trial**  
- Download Splunk Enterprise Trial from the Splunk website, Linux `.tgz` file, and copy the `wget` command.  
- `wget -O splunk-9.1.1-64e843ea36b1-Linux-x86_64.tgz "https://download.splunk.com/products/splunk/releases/9.1.1/linux/splunk-9.1.1-64e843ea36b1-Linux-x86_64.tgz"`

---

## Step 1: Create Linux Instance in AWS LightSail

- Create a Linux instance within AWS LightSail.
- Change the network to allow TCP connections.
- Connect via SSH.

---

## Step 2: Install Splunk

1. Once connected, use the `sudo su` command to assume root privileges.
2. Run the following commands:
   - `useradd splunk` - Creates the account for Splunk.
   - `mkdir /opt/splunk` - Creates the home directory for Splunk.
   - `cd /opt/` - Changes the directory to `/opt/` (reserved for installation of add-on application software packages).
3. Run the `wget` command:
   - `wget -O splunk-9.1.1-64e843ea36b1-Linux-x86_64.tgz "https://download.splunk.com/products/splunk/releases/9.1.1/linux/splunk-9.1.1-64e843ea36b1-Linux-x86_64.tgz"`
4. Untar the file:
   - `tar xvzf splunk-9.1.1-64e843ea36b1-Linux-x86_64.tgz -C /opt`
     - `x`: Extracts files and directories from an existing archive.
     - `v`: Displays verbose information during the archiving or extraction process.
     - `z`: Uses gzip compression when creating a tar file, resulting in a `.tar.gz` archive.
     - `f`: Specifies the filename of the archive to be created or extracted.
5. Change ownership of the Splunk directory:
   - `chown -R splunk:splunk /opt/splunk` - Changes ownership to the `splunk` user account.
6. Navigate to the Splunk binary directory:
   - `cd /opt/splunk/bin`
7. Start Splunk:
   - `sudo /opt/splunk/bin/splunk start --accept-license`
8. Set the username and password, then wait for the service to start.

---

## Step 3: Access Splunk Web Interface

- Connect to the web interface using the public IP:  
  `http://<your_public_IP>:8000`
