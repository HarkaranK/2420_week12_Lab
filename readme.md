# <ins>**2420 Week 12 Lab**</ins>
##<ins>**1. Table of Contents**</ins>
- [**2420 Week 12 Lab**](#2420-week-12-lab)
    - [**1. Table of Contents**](#1-table-of-contents)
    - [**2. Set B Members**](#2-set-b-members)
    - [**3. Technologies Used**](#3-technologies-used)
    - [**4. Creating The Website**](#4-creating-the-website)
    - [**5. Creating Firewall**](#5-creating-firewall)
- [**Go to top**](#go-to-top)

---

## <ins>**2. Set B Members**</ins>

Harkarn Kang - A01292258
(Kooby) Hai Run Yin - A01186094

---

## <ins>**3. Technologies Used**</ins>
- Bash
- Windows Subsystem for Linux(WSL) - Ubuntu
- Digital Ocean Droplets

---

##  <ins>**4. Creating The Website**</ins>
### <ins>**4.1. Installing Nginx**</ins>
1.Use "sudo apt update" to check for available updates
2.Use "sudo apt upgrade" to update all existing services
3.Use "sudo apt install nginx" to install nginx
4.You will be prompted to continue the installation. Type "Y" to install or "n" to cancel
5.If you are prompted to restart any service, press "tab" then "ok" to accept default services reboot
### <ins>**4.2. Creating An HTML File**</ins>
1.Create a simple HTML document to serve
2.Create a directory using "mkdir dirName"/ If it exists already you can use "cd" to enter the directory
3.Next use "touch" and "vi" to create then edit the new HTML file.
4.Once the HTML file is open you can press "i" to enter Insert Mode then write your HTML code"
5.Once the HTML file is complete press "esc" then type ":wq" to save and quit.
### <ins>**4.3. Creating Nginx Server Block**</ins>
Writing an Nginx Server to serve your HTML document
1. start editing your server block by typing "sudo vim /etc/nginx/sites-available/
2. Use the arrow keys to navigate to the default option, once over press "enter"
3. Replace the IP addresses with your own droplet's IP adresses. Keep the rest as default.
4. After saving the file(use the same method in 4.2) use "sudo nginx -t" to test syntax of file
5. After syntax is checked run "sudo ln -s /etc/nginx/sites-available/your ip address /etc/nginx/sites-enabled/" this "enables" the server block you coded.
6. Using "mv" move the files to the appropriate directories if you did not create them in the default locations.
### <ins>**4.4. Starting Server/Website**</ins>
1. use the command "sudo systemctl restart nginx" to restart the nginx server with the new serverblock file
2. use the command "sudo systemctl status nginx.service" to check status and for errors
3. If there are no errors you should be able to go to your website by typing in the IP address associated with your droplet into a browser.

---

## <ins>**5. Creating Firewall**</ins>
1. Log in to digital ocean and click the green "Create" button
2. Select Firewall from the dropdown menu
3. Name the firewall and choose the optional rules for inbound/outbound traffic. In our case we limited inbound traffic to only SSH and HTTP requests
4. Choose which droplets the firewall should be applied to, either by using tags associated with droplets or the droplet names themselves.
### <ins>**5.1. Testing Firewall**</ins>
1. We can test the firewall by editing the firewall rules.
2. Disable inbound SSH traffic
3. Attempt to connect via SSH, if your connection times out then you have successfully enabeled
4. Renable inbound ssh Traffic and save firewall.
