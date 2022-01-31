# [Article Link](https://dev.to/zeeshanhshaheen/how-to-deploy-react-js-and-nodejs-app-on-a-single-digitalocean-droplet-using-nginx-1pcl)

# Commands
* sudo ufw app list
    * See which applications our firewall currently allows.
* sudo ufw allow OpenSSH
    * Allow OpenSSH application as this is required
* sudo ufw enable
    * Start the firewall
* sudo ufw status
    * See which applications are allowed inside the firewall.
* sudo apt-get install nginx
    * Install nginx
* systemctl status nginx
    * View the status of nginx
* 

# Steps
* View and allow OpenSSH inside the firewall
* Enable the firewall
* Install nginx
* Enable firewall for nginx http
* View status of raw, unconfigured nginx
* 